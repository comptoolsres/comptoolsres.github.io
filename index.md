---
title: "Computational Tools for Research in Biology"
keywords: sample homepage
tags: [getting_started]
sidebar: ctr_sidebar
permalink: index.html
summary: An introduction to computational tools for research, including the Linux command line, Python scripting, and databases.
This course prepares students to conduct large-scale data analysis on high-performance computing resources.
---

{% include note.html content="This page is under construction." %}

## About this site

This site is the being developed as the main repository for Matt Gitzendanner's Computational Tools for Research in Biology. This course is typically offered every-other-year at the [University of Florida](https://ufl.edu). My hope is that this site can serve both as the primary resource when teaching the course, and as a resource for others teaching similar courses or learning on their own.

The course was designed to be a one semester, in-person, 3-credit course for upper-level undergraduate and starting graduate students. During Summer 2020, I am offering it as an online course with some modifications.

Please use the feedback button to send feedback.

## Course Description

{% include image.html file='comptools.png' alt="Image of servers and tool icons" position="right" %}

Information technology has dramatically transformed how research across many disciplines is conducted. This is particularly true in the biological sciences where researchers frequently find themselves faced with massive amounts of diverse data to analyze. As data types and volumes continue to grow, knowledge of scripting, database management, and advanced computing skills are critical for researchers.

Topics covered in the course will address a gap in how research has advanced—*and become increasingly computational*— while student training in the use of computational tools has lagged. The course assumes no prior coding or command line skills, and covers concepts that will provide the ability for students to apply new technologies to a wide array of research questions. A foundation in data management and analysis concepts opens doors for well-trained scientists and allows them to work in multidisciplinary research.

This course will survey areas where high performance computing, large-scale data access and integration, informatics tools and software, and multi-disciplinary collaboration have had high impact on research as a foundation for computationally-enabled research.

{% include note.html content="While the title of the course includes 'in Biology' there is little that is actually focussed on biology. This course strives to be broadly applicable to many areas of research. Bureaucracies being what they are, the title is what it is..." %}

## Course organization

The course is divided into three main sections:

### Section 1

* Linux command line
* Bash scripting
* Version control
* Using high-performance computing resources

### Section 2

* Python scripting

### Section 3

* SQL database introduction and integration with Python

## Course Objectives

* Demonstrate how technology infrastructure can improve research and open new avenues of investigation.
* Competently navigate the Unix/Linux command line interface.
* Effectively and efficiently manipulate text files, performing complex regular expression replacements, reformatting and merging files in various ways.
* Raise and address current issues through class participation and discussion.
* Use High Performance Computing resources such as the UF Research Computing for cluster-based analyses. Including batch scripting and running multi-processor applications (threaded and MPI).
* Explain the basic anatomy of computer scripts/programs, with particular focus on Python scripting.
* Construct analytical pipelines to accomplish complex tasks.
* Describe basic database design, creation and manipulation. Perform scripted database operations for information discovery, data exploration and research data curation.
* Have a basic understanding of research graphics formats, preparation and manipulation

## Meeting Times

Summer A runs May 11, 2020 through June 19, 2020. May 25th is Memorial Day holiday.

### Synchronous meetings: Mon, Wed, Fri

* I will be online and presenting material and/or helping students: **Mon, Wed, Fri during 3rd period (11:00am - 12:15pm)**
{% include important.html content="You should make every effort to attend these sessions. While there will be note pages and hopefully a video recording of these sessions, **this is the best opportunity to ask questions and get help from me and others in the class.**" %}
  * I understand that with all that is going on, some students will need to miss classes sometimes. That is fine and I will do my best to help you catch up, but regular attendance is the best way to learn.

### Asynchronous meetings: Tue, Thurs

* On Tuesday and Thursday, students will work on projects either independently or in small, virtual groups.
* These sessions can be more flexible in timing and will give you and your classmates times to get more hands-on experience and challenge yourselves to learn on your own.
* There will still be content that needs to be covered, and students should plan on working on Tuesday and Thursday, but can generally do the work whenever is convenient for them.

### Office hours: Thursday and by appointment

* I have scheduled office hours for **Thursday between 11:00am and 2:00pm**. I am also available at other times by appointment.
{% include tip.html content="Coding is not always easy. Simple solutions are not always obvious. There will be some frustration. I expect that you will need help. You should expect that you will need help. I want to help you! I cannot always help if you don't ask. Please ask for help." %}

## Course textbooks

The main texts for the course are:

* The Linux Command Line: [http://linuxcommand.org](http://linuxcommand.org) (my notes and referenced page numbers will be based on the 19.01A PDF, Fifth internet edition from Jan 28, 2019)
* Python For Everyone: [https://www.py4e.com](https://www.py4e.com)

Each of these is available as a free PDF download or for purchase in print.

## Course Calendar

This is subject to change, please check back frequently. 

For readings, there may be links to pages with my notes and additional explanations on the content from the texts. The texts are abbreviated as TLCL = [The Linux Command Line](http://linuxcommand.org); Py4E = [Python for Everyone](https://www.py4e.com).

Week | Date | Reading/Assignment |Topic
-----|------|--------------------|-----
1 | Mon, May 11 | [Read TLCL Introduction & Ch 1-6](TLCL_reading_notes_1.md) <br> [Download Software](software.md)|Introduction and course objectives.<br>Linux Basics: Command line
1 | Tues, May 12 | [Watch UFRC TrainingVideo](https://training.it.ufl.edu/training/items/orientation-materials-for-courses-using-rc.html) <br> [Read TLCL Ch 7 & 8](TLCL_reading_notes_2.md) | UF Research Computing Intro & getting started
1 | Wed, May 13 |Read TLCL Ch 19 & 20 through Slicing and Dicing| Linux Basics: Pipes and Redirects
1 | Thurs, May 14 | Watch Learn the Linux Command Line: The Basics| Regular Expression video and exercises
1 | Fri, May 15 | Register for github.com account <br> Problem Set 1<br> Reach TLCL Ch 24-26 <br> Quiz 1| Shell Scripts
|||
2 | Mon, May 18 | Read TLCL Ch 27, 29 & 33 |Version Control: git and GitHub
2 | Tues, May 19 |Read TLCL Ch 23 | TBD
2 | Wed, May 20 |Work on PS2| Using UF Research Computing resources<br>Running batch jobs, Compiling source code
2 | Thurs, May 21 |PS 2 Due | Catching up
2 | Fri, May 22 | Reach Py4E Ch 1 & 2|Introduction to Python <br>Python data types
|||
3 | Mon, May 25 || *Memorial Day Holiday, No Class*
3 | Tues, May 26 |Read Py4E Ch 3 & 5|
3 | Wed, May 27 | |Working in Python, Flow Control
3 | Thurs, May 28 |Read Py4E Ch 6 & 7| Working in Python: try/except, Strings, File I/O
3 | Fri, May 29 | Read Py4E Ch 4| Working in Python, Functions
|||
4 | Mon, June 1 | Read Py4E Ch 8-10 | Lists, Dictionaries, Tuples
4 | Tues, June 2 | Reach Py4E Ch 12 & 13 | SciPy, NumPy, Pandas
4 | Wed, June 3 || Scripting data acquisition
4 | Thurs, June 4 || Class project
4 | Fri, June 5 | P3 Due, Quiz 2 | Matplotlib and data visualization
|||
5 | Mon, June 8 | Read Py4E Ch 16 | Writing Functions
5 | Tues, June 9 || Class project, continue
5 | Wed, June 10 || Finishing up
5 | Thurs, June 11 | | Class project, continue
5 | Fri, June 12 | Programming Foundations Databases |Overview of databases<br>Database design
|||
6 | Mon, June 15 ||Setting up a database <br>SQLAlchemy Introduction
6 | Tues, June 16| |SQLAlchemy continued
6 | Wed, June 17 | |Graphics
6 | Thurs, Jun 18 ||Class project, complete
6 | Friday, June 19 || Last day of class




{% include links.html %}