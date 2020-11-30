---
title: "Passing Command Line Arguments in Python with Argparse"
tags: [python]
sidebar: home_sidebar
permalink: Argparse.html
summary: For most of the Python section, we have used Jupyter notebooks. This page covers how to pass command line arguments into Python scripts from the Bash command line. While notebooks are great for learning, testing and development, Python scripts are usually best for production analyses.
keywords: shell, argparse, command line, python, arguments
---

## Python scripts vs notebooks

For most of this class, we have used Jupyter notebooks for the Python section. Notebooks are great for learning Python, testing new things and even code development. While there are ways to automate running of Jupyter notebooks (see the [Execute API](https://nbconvert.readthedocs.io/en/latest/execute_api.html)), and you can convert notebooks to Python scripts (File menu <i class="fas fa-arrow-right"></i> Export Notebook As... <i class="fas fa-arrow-right"></i> Export Notebook to Executable Script), for the most part, the best method of automating Python scripts is to have the script saved as a text file (usually ending in `.py` by convention) and having the ability to take command line arguments.

As we saw in the Bash section, by passing command line arguments, we can change how a program works. We can adjust settings, set input and output file names, etc. It would be a pain to have to manually update a script all time to make these changes.

## Command line arguments with `sys.argv`

The Python `sys` module does have built in command line parsing, though functionality is limited.

Here is an example script that uses the `sys.argv` command line arguments:

```python
#!/usr/bin/env python

# args.py: Demo of the sys.argv command line parsing

import sys

# Print number of arguments passed in
print (f'Number of arguments: {len(sys.argv)}')

# Loop through the arguments and print them
for arg in range(len(sys.argv)):
  print(f' Argument {arg} is: {sys.argv[arg]}')
```

And here's how it is run and the output:

```bash
[magitz@login2 Examples]$ python args.py test 1 file
Number of arguments: 4
 Argument 0 is: args.py
 Argument 1 is: test
 Argument 2 is: 1
 Argument 3 is: file
```

With `sys.argv`, the arguments need to be passed in a specific order, and these are placed into a list variable. The 0th element of the list is the name of the script, and the subsequent elements are the values passes.

This can work for one or two arguments, but becomes challenging as the number of arguments grows as it becomes harder for users to get things in the correct order and there is no flexibility as far as optional arguments, etc.

## The `argparse` module

While there are a couple of argument parser modules for Python (see [`getopt`](https://docs.python.org/3.9/library/getopt.html) as another option), `argeparse` is the most robust and best supported.

Here are the [`argparse` documentation page](https://docs.python.org/3.9/library/argparse.html#module-argparse) and a nice [`argparse` tutorial](https://docs.python.org/3.9/howto/argparse.html). From the documentation:

 > The `argparse` module makes it easy to write user-friendly command-line interfaces. The program defines what arguments it requires, and `argparse` will figure out how to parse those out of `sys.argv`. The `argparse` module also automatically generates help and usage messages and issues errors when users give the program invalid arguments.

### Positional arguments

 `argparse` supports both <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.positional_arguments}}">positional arguments</a> and optional/keyword arguments.

 Using a slight modification of the example from the [tutorial](https://docs.python.org/3.9/howto/argparse.html), here's a good example of passing in a floating point value:

```python
#!/usr/bin/env python

# square.py: Demo of argparse

import argparse
parser = argparse.ArgumentParser()
parser.add_argument("square", help="display a square of a given number",
                    type=float)

# Parse the command line arguments
args = parser.parse_args()
print(f"The square of {args.square} is {args.square**2}")
```

And here is the Bash output of running this with no arguments, adding the `-h` (I could have also used `--help`) to get the automatically generated help information, and finally running with a value passed in.

```bash
[magitz@login2 Examples]$ python square.py
usage: square.py [-h] square
square.py: error: the following arguments are required: square
[magitz@login2 Examples]$ python square.py -h
usage: square.py [-h] square

positional arguments:
  square      display a square of a given number

optional arguments:
  -h, --help  show this help message and exit
[magitz@login2 Examples]$ python square.py 4.6
The square of 4.6 is 21.159999999999997
[magitz@login2 Examples]$
```

### Optional/keyword arguments

As with `sys.argv`, we could keep adding more and more positional arguments, but again, as the list of arguments grows, things can get complex. At least our code now gives users some help as to what the correct order should be. But, it is usually best to use flags for the arguments.

It is usually easier for users (and yourself) to use command line flags, to specify arguments. Has a robust set of options for setting these up for different conditions. I've highlighted some of these in the `argparse_demo.py` script, but see the [`add_argument()` documentation](https://docs.python.org/3/library/argparse.html#argparse.ArgumentParser.add_argument) for more options. New options are also added periodically, so check back for updates.

This script is not the most useful script, other than showing some examples of argparse options. It is located at `blue/bsc4452/share/Class_Files/Examples/argparse_demo.py` or in the [Class_Files repo here](https://github.com/comptoolsres/Class_Files/blob/main/Examples/argparse_demo.py).

```python
#!/usr/bin/env python

# argparse_demo.py: Demo of argparse
import sys
import argparse
import math

# Define a __version__ variable used below.
__version__ = '1.0'

parser = argparse.ArgumentParser(prog="Program to demonstrate different argparse features")

# Positional argument; no flag, will be last, after optional arguments.
# This example also adds checking the type of an argument.
parser.add_argument('square', help='Display a square of a given number',
                    type=float)

# Optional argument types

# Long, double-dash flag and short single-dash equivalent
parser.add_argument('--input', '-i', help="Name of input file, lines in file will be printed.")

# Actions
# By defualt, the action is to store the value passed with the argument
# e.g. -i file.txt stores 'file.txt' as the value for --input.

# Some other actions (See docs for more options):
parser.add_argument('--pi', action='store_const',
                    help="Use constant value of 3.1415 for pi",
                    const=3.1415)

parser.add_argument('--print', action='store_true',
                    help="Also print blank lines to screen?")

parser.add_argument('--verbose', '-v', action='count', default=0,
                    help='Verbosity level: pass multiple times to increase output level 0-2)')

parser.add_argument('--version', action='version',
                    help='Print version number',
                    version='%(prog)s. Version: ' + __version__)

# Setting default values that can be changed if passed

parser.add_argument('--times', '-t',
                    help='Number of times to print each line, default=1',
                    default=1)
# Parse the command line arguments
args = parser.parse_args()

if args.verbose > 0:
  print(f"Opening file {args.input}.")

# Open the file
try:
  file_handle=open(args.input, 'r')
except Exception as exception:
  print(f"Couldn't open {args.input}, {exception}. \nExiting")
  sys.exit()

if args.verbose > 1:
  print(f"I made it this far, so {args.input} has been opened.")

for line in file_handle:
  line=line.strip()
  #ignore blank lines initially
  if not (len(line) == 0):
    print(line)
  # if --print was passed, print the blank lines
  elif args.print:
    print(line)

if args.verbose > 1 :
  print(f"Finished reading {args.input}.")

print(f"The square of {args.square} is {args.square**2}")

if args.pi:
  print(f"Pi is: {args.pi}")
else:
  print(f"Pi is: {math.pi}")

if args.verbose > 0:
  print("Done")
```

The basic `argparse` methodology is to create a `ArgumentParser` object, often called `parser` for convenience. Then use one or more `add_argument` lines to add each of the arguments you want for your program. Finally, run the `parse_args` method and save the arguments in an object that contains the variables that have been parsed.

Look over the different options and see how they are used. Think about how you could incorporate command line options in programs that you write.
