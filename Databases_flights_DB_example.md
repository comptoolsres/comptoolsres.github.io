---
title: "Flights data to database"
tags: [sql]
sidebar: home_sidebar
permalink: Convert_Flights_to_DB.html
sidebar: home_sidebar
summary: An example of normalizing a table and creating a database and then some example queries. This example uses the flights table we've seen before.
keywords: sql, first normal form, normalization, csv, table, select, join
---

Let's work through normalizing and converting our flights data to a database. [Here's the metadata for the file](https://github.com/comptoolsres/Class_Files/blob/main/data/flights_metadata.md).

For first normal form (1NF), we want to ensure that:

* Only one value in a cell--I think we are good here
* No repeating groups--If we look at the information for the departure and arrival airports, we see that we have 3 columns of data for each:
    Column header | Description
    --------------|------------
    ORIGIN | Origin Airport
    ORIGIN_CITY_NAME | Origin Airport, City Name **Note that this column has a comma in it**
    ORIGIN_STATE_ABR | Origin Airport, State Code

  This is repeating because, for example, every time GNV is the airport code, the city name is Gainesville, FL and the state is FL. That is a lot of repeated information!

  * To solve this, we can make a new table that has the columns above. It is somewhat up to us if we want to leave the state abbreviation in the city name field. For simplicity, we'll leave it as it is.

### Prepare input files to convert the flights data to a database

Here are the bash commands I used to prepare two input tables to make out database.

```bash
# Get the header row for the main flights file 
#  (skip city name and state columns--4,5, 7,8)
cat /blue/bsc4452/share/Class_Files/data/flights.May2018-April2020.csv | cut -d, -f1,2,3,6,9-25 | head -n1 > flights.csv

# Get the rest of the rows--cols 4 & 7 have comas in them.
#  (skip "city name, state" and state columns--
#   4,5,6, 8,9,10)
cat /blue/bsc4452/share/Class_Files/data/flights.May2018-April2020.csv | cut -d, -f1,2,3,7,11-25 |tail -n+2 >> flights.csv

# Get the header row for the airports file
# I will assume that the origin column has all
# possible airports.
cat /blue/bsc4452/share/Class_Files/data/flights.May2018-April2020.csv | cut -d, -f3,4,5| head -n1 > airports.csv

# Get the rest of the rows
# Because of the sort, this does take a while to run
cat /blue/bsc4452/share/Class_Files/data/flights.May2018-April2020.csv | cut -d, -f3,4,5,6 | tail -n +2 | sort -k1 -t 2 | uniq >> airports.csv
```

### Setup sqlite to import the csv files

SQLite has different modes, one of which is a csv mode that will read a csv file into a database table. This takes a couple of minutes with the flights file.

``` bash
# Load the module for sqlite and create
#  a new database while opening sqlite3
[magitz@login3 magitz]$ ml sqlite
[magitz@login3 magitz]$ sqlite3 flights.sqlite
SQLite version 3.8.8.2 2015-01-30 14:30:45
Enter ".help" for usage hints.
# Set .mode to csv to import the flights.csv file
sqlite> .mode csv
sqlite> .import flights.csv flights
#---> LOTS of output like the line below. Takes ~10 minutes <---
flights.csv:14814674: expected 20 columns but found 19 - filling the rest with NULL
# See that the flights table has been created
sqlite> .tables
flights
# Check the schema of the flights table
sqlite> .schema flights
CREATE TABLE Flights(
  "FL_DATE" TEXT,
  "OP_UNIQUE_CARRIER" TEXT,
  "ORIGIN" TEXT,
  "DEST" TEXT,
  "DEP_TIME" TEXT,
  "DEP_DELAY_NEW" TEXT,
  "DEP_DEL15" TEXT,
  "ARR_TIME" TEXT,
  "ARR_DELAY_NEW" TEXT,
  "ARR_DEL15" TEXT,
  "CANCELLED" TEXT,
  "CANCELLATION_CODE" TEXT,
  "DIVERTED" TEXT,
  "AIR_TIME" TEXT,
  "FLIGHTS" TEXT,
  "DISTANCE" TEXT,
  "CARRIER_DELAY" TEXT,
  "WEATHER_DELAY" TEXT,
  "NAS_DELAY" TEXT,
  "SECURITY_DELAY" TEXT,
  "LATE_AIRCRAFT_DELAY" TEXT
);
sqlite>
```

Now we can do the same for the airports table:

```bash
sqlite> .import airports.csv airports
sqlite> .tables
airports  flights
sqlite> .schema airports
CREATE TABLE airports(
  "ORIGIN" TEXT,
  "ORIGIN_CITY_NAME" TEXT,
  "ORIGIN_STATE_ABR" TEXT
);
sqlite>
```

The first thing to see is that by removing the repeating data and normalizing our table, the file size has gone down.

```bash
[magitz@login3 magitz]$ ls -lh flights.sqlite
-rw-r--r-- 1 magitz bsc4452 1.5G Nov  2 13:49 flights.sqlite
[magitz@login3 magitz]$ ls -lh /blue/bsc4452/share/Class_Files/data/flights.May2018-April2020.csv
-rw-r--r-- 1 magitz bsc4452 2.1G Aug  3 11:13 /blue/bsc4452/share/Class_Files/data/flights.May2018-April2020.csv
[magitz@login3 magitz]$
```

The original file is 2.1GB, while the database is 1.5GB...About a 29% file size reduction--not trivial.

## Running some queries on the database

We will look more at SQL in another lesson, but since these data are already familiar, let's work with the flights database for a bit.

Here's our old friend, how many flights into or out of Gainesville arrived late by 15 minutes or more.
```sql
SELECT count(FL_DATE) FROM flights WHERE (ORIGIN='GNV' or DEST='GNV') and ARR_DEL15='1.00';
3446
sqlite>

```

As I mentioned SQLite doesn't care about types, but, like Python, it really does...So using `ARR_DEL15=1;` above would give us 0 results. SQLite is interpreting this as a string column. We can force it to convert it to a number with the `CAST` function:

```sql
sqlite> SELECT count(FL_DATE) FROM flights WHERE (ORIGIN='GNV' or DEST='GNV') and CAST(ARR_DEL15 as FLOAT)=1;
3446
sqlite>
```

### Speeding things up a bit

SQLite is, as the name implies, best for light weight, small databases. Our flights database is pushing its limits and some of these queries take some time to run. This is partially because the SQLite reads the file from storage each time--it is not being saved in RAM.

There is a bit of a hack to make SQLite save the database in RAM if all you want to do is query the data (not change--update or delete).

We can startup SQLite telling it to use a memory database and then "restore" our database into that RAM database. **But remember that this is now a new database and any changes are lost when you exit SQLite!**

```bash
# First we exit sqlite
sqlite> .exit

#Then open sqlite with the :memory" option,
#  telling sqlite to keep the database in RAM
[magitz@login3 magitz]$ sqlite3 :memory:
SQLite version 3.8.8.2 2015-01-30 14:30:45
Enter ".help" for usage hints.

# Use the .restore option to load the file into
#  the main database (default name of RAM DB)
sqlite> .restore main flights.sqlite
```

This too make take some time, but at least future searches will be much faster!

### More queries

```sql
# Flights leaving GNV that were diverted
SELECT FL_DATE, ORIGIN, DEST FROM flights WHERE ORIGIN='GNV' and CAST(DIVERTED as FLOAT)==1;

# Count flights leaving Florida
SELECT count(flights.ORIGIN) FROM flights JOIN airports ON flights.ORIGIN=airports.ORIGIN WHERE airports.ORIGIN_STATE_ABR="FL" ;

# This one is...complicated and maybe I made it harder
# by normalizing the data...
# I want the flights from GNV to Texas.
SELECT flights.FL_DATE, flights.ORIGIN, airports.ORIGIN_CITY_NAME, flights.DEST, d.ORIGIN_CITY_NAME FROM flights JOIN airports on flights.ORIGIN=airports.ORIGIN JOIN airports as d on flights.DEST=d.ORIGIN WHERE flights.ORIGIN='GNV' AND d.ORIGIN_STATE_ABR='TX';
```

Breaking down that last one...Because I want the city name of both the origin and destination airports, I need to do one join to match the origin airport code with its city name and another join to match the destination airport code with its city name. To do two joins, I need to use an alias for one of them. Similar to the Python's `import pandas as pd`, SQL aliases make it convenient to rename tables for shorter commands (and get us our second join in this case). I chose `d` in this case for destination, I could have use `dest` or anything else. It is common to use single letters as we are trying to make the command shorter. The `as` is also optional, but helps with clarity.

So, I am asking to print the date, origin airport code, origin city, destination airport code, destination city. The first join is flights on airports, setting `flights.ORIGIN=airports.ORIGIN` (these are the two columns with airport codes). The second join is also flights on airports, but this time aliasing airports to `d` and setting `flights.DEST=d.ORIGIN` (the column names in the airports table are all ORIGIN--we could fix this, but for now, we just need to remember that these names are just airport codes, cities and states and have no origin/destination meaning).

In the `WHERE` clause, I use the `flights.ORIGIN='GNV'` and `d.ORIGIN_STATE_ARB='TX'` to set the conditions I was after.
