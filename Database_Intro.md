---
title: "Database Introduction"
tags: [sql]
sidebar: home_sidebar
permalink: Database_Introduction.html
sidebar: home_sidebar
summary: This page in an introduction to databases. The Py4E text covers databases some, but not really enough to really get you using a database. Much of this will mirror the content in the LinkedIn Learning Programming Foundations Databases course.
keywords:
---

The LinkedIn Learning [Programming Foundations: Databases](https://www.linkedin.com/learning/programming-foundations-databases-2/) course provides a good intro to databases. These notes will mirror and in some places supplement that material.

## Why use a database?

* Databases facilitate working with large amounts of data efficiently.
* Databases provide the tools to easily, reliably and efficiently add and update data in the database.
* Databases ensure that the stored data are organized, consistent, reliable and searchable.

## What you should know

* The LinkedIn Learning course is general and not focused on any particular <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.DBMS}}">DBMS</a>.
  * Many of the code examples are general <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.SQL}}">SQL</a> code. SQL, like regex, is a standard, and different databases implement the standard in slightly different ways.
  * In class, we will use `sqlite`, which has its own uniquenesses that we will cover as we get there.

## Understanding databases: Benefits of structured data

* The **structure** of tables in the database is called the <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.schema}}">schema</a>.
* Databases allow enforcement of rules for data.
* Databases can protect data from unauthorized access or changes.

## Relational databases

* Alternatives to relational databases:
  * Graph databases, which focus on relationships connecting data records, or nodes: [Neo4j](https://neo4j.com/)
  * Object databases, which provide persistent storage for your <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.OOP}}">OOP</a> objects: [Realm](https://www.mongodb.com/realm) and [Objectivity/DB](https://www.objectivity.com/products/objectivitydb/)
  * Document databases relax the structure of relational databases, storing and searching data stored as documents. These are ofte referred to a <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.NoSQL}}">NoSQL</a> databases. Examples: [CouchDB](https://docs.couchdb.org/en/stable/) and [MongoDB](https://www.mongodb.com/)

### Column Data Types

We keep running into data types this semester! So far, none of our programming languages have forced data types to be declared. We've talked about types because you can't add a string and a float. I've also mentioned that an integer can use less memory space than a string, and this is why programmers often care about data types. Databases, in general, are even more focused on types, with many more data types than we have seen so far, differentiating stings of different length, or integers of different values, for example.

This example from YouTube in 2014 is one my favorite examples of why data types matter. The developers of YouTube had opted to store the number of plays that a video had in a `int` type column--that is a 32-bit integer, which has values from -2,147,483,647 to 2,147,483,647. So, in late 2014, PSY broke YouTube when the [Gangnam Style video](https://www.youtube.com/watch?v=9bZkp7q19f0) crossed more than 2,147,483,647 views!

{% include image.html file='PSY_data_types.png' alt="Image of YouTube announcement about PSY video exceeding 2,147,483,647 view" position="center" %}

An unsigned `int` (only positive numbers) would have worked and still been (barely) sufficient for the views in 2020. Or `bigint`, which stores 64-bit integers. Again, the main thing to consider when developing a database is what is the largest value that could possibly be stored, while at the same time, considering where you can save space by using reasonable values.

{% include note.html content="The main thing to note here is that the database we will use, `sqlite`, does not use types. Of the major relational databases I am familiar with, it is the only one to be un-typed. The developers consider this a feature and the insistence on typed data in other databases a bug." %}

## Keys and unique values

* A unique values can be used as keys
* Keys can be used to refer to a specific row, or record, in a table
* <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.primary_key}}">Primary keys</a> help with accessing data.
* We often add a column with an auto-incrementing number as the value and the <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.DBMS}}">DBMS</a> automatically fills in the key value when each record is added to the table.
* In some cases, multiple columns are needed to make a unique value. This is called a composite key.
* <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.foreign_key}}">Foreign keys</a> are references in one relational database table to a primary key in another table.

## Relationships

* Three general classes of relationships
  * One-to-many
    * The most common type of relationship
    * e.g. Dishes to customer favorite dishes. Each dish can be many customers favorite dish.
    * Use a <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.foreign_key}}">foreign key</a> in the table of the many side of the relationship referencing the <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.primary_key}}">primary key</a> in the table on the one side.
  * Many-to-many
    * Uses a linking table that links the tables being associated.
    * e.g. Associate many customers with many dishes. Like for what dishes each customer has ordered.
  * One-to-one
    * Not widely used
      * I don't really like the example used of a special request table, because a customer can only have one special request.
    * Later in the videos, they mention a better example, splitting personal information like birthday and address apart from the customer name.

## ACID and transactions

* Each action in a database is refered to as a transaction.
* Transactions meet the ACID test when they are:
  * **Atomic**: A transaction should be on one piece of information.
  * **Consistent**: All transactions should leave the database in a good or consistent state.
    * Any rules setup in the database--no null values, type definitions, unique values, etc.--are enforced.
    * If the transaction fails part way through, the previous state is restored. Transactions are sometimes referred to as all or nothing--either the transaction succeeds, or it fails--no partial success.
  * **Isolated**: Only one transaction can be processed at a time.
  * **Durable**: Each transaction is written to the database, not merely changed in memory.

## Basic SQL

* SQL = Structured Query Language
* RDBMS = Relational Database Management System
* As noted, there is a standard--in this case the ANSI SQL standard, and then RDBMS-dependent modifications/implementations of that standard.
  * I will say that sqlite has more non-standard features than others, but there are other good reasons to use it.
* DML = Data Manipulation Language
  * The SQL features that allow interacting with data
* DDL = Data Definition Language
  * The SQL features that allow managing the database and tables, defining the data that will be stored.
* DCL = Data Control Language
* SQL statements are composed of clauses, which can contain expressions and predicates.
* SQL keywords are usually written in UPPER CASE for readability
* CRUD--the basics of what we do with data in a database
  * **Create**: add data
  * **Read**: read data
  * **Update**: change data
  * **Delete**: delete data

## Modeling and planning a database

* Entity Relationship Diagrams (ER Diagrams) show the tables, fields and relationships in a database

## Naming tables

* Name tables with a plural version of the data stored in the table
  * Start with a capital letter
  * No spaces or punctuation
* Field names should be singular
  * Start with a capital letter
  * No spaces or punctuation

## Columns and data types

As you go through this next set of videos, think about the importance of data types, but also remember that sqlite doesn't care about data types...

## Primary and Foreign Keys

* An ID column is often used as the primary key for a table.

## Relationship rules and referential integrity

* Databases are aware of the relationships we define and prevent users from adding or modifying data that would violate those relationships. This is referred to as <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.referential_integrity}}">referential integrity</a>.
  * Can be used in deleting records or prevent deletion.
    * e.g. Delete a customer's orders when we delete the customer
    * or prevent deletion of a dish that is someone's favorite dish.

## Normalization Rules

* First normal form (1NF)
  * Values in each cell are atomic
    * Each field has one piece of data
  * Tables have no repeating groups
  * No duplicate rows
  * Order of rows is not important to the data
* Second normal form (2NF)
  * No value in the table should depend only on part of a key that can be used to uniquely identify a row
    * e.g. since BSC4452 is always called "Computational Tools for Research in Biology" a classes table should not have both a course number and course name column--we know the name, based on the course number.
* Third normal form (3NF)
  * Values should not ve stored if they can be calculated from another non-key field.
    * e.g. We should not store birthdays and ages, or price, discount and discounted price--the discounted price can be determined from price and discount.
* Denormalization
  * The process of intentionally breaking a rule of normalization

## Creating a database

If you want to follow along with making a database in sqlite on HiPerGator, here are the commands to use. We will see right from the start that sqlite uses different commands, especially in the DDL (data definital language) portion of SQL. There are several dot commands, like `.open`, `.database`, `.help` (a *very* handy one) for many commands that other databases use SQL for.

First we need to load the module and open sqlite3:

1. `module load sqlite`
1. `sqlite3`
1. Now in sqlite3, I can create the Restaurant database:
  * Standard SQL `CREATE DATABASE Restaurant;`
  * sqlite: `.open Restaurant`
    * There isn't a `.create` command, just open it and it is created...
    * The `.databases` command shows the open database

    ```
    sqlite> .open Restaurant
    sqlite> .databases
    seq  name             file
    ---  ---------  --------------------------
    0    main       /home/magitz/Restaurant
    sqlite>
    ```

1. Now we can create the table. This is more or less standard SQL syntax, though sqlite doesn't (and suggests against using) the AUTO_INCREMENT statement and also doesn't need a NOT NULL on the PRIMARY KEY column. Here's the code:

  ```
  CREATE TABLE Customers (
  CustomerID INTEGER PRIMARY KEY ,
  FirstName TEXT NOT NULL,
  LastName TEXT NOT NULL,
  Email TEXT,
  Address TEXT, City TEXT , State TEXT,
  Phone TEXT NOT NULL,
  Birthday DATE,
  FavoriteDish REFERENCES Dishes(DishID_)
  );
  ```

1. Watch the rest of the videos, but we don't have the database to do the queries. We will have exercises similar to this, but just watch for now and take in the ideas.

## Joining tables

This section is really important for databases as it is one of the best features of databases. Don't worry about the code used, but focus on the idea of taking information from different tables and joining that into a query result.

## Modifying data

One thing that is touched on here is that there is no undo button in databases. Modifications to databases can be catastrophic when things go wrong...be careful, and for the most part, use carefully tested code to work with databases rather than typing SQL directly as the demos show.

