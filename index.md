---
title: "Computational Tools for Research in Biology"
keywords: syllabus
tags: 
sidebar: home_sidebar
permalink: index.html
summary: An introduction to computational tools for research-- Linux command line, HPC, Bash scripting, Python, SQL, and Artificial Intelligence
toc: false
---

## BSC4452 and BSC6451 Registration information for Fall 2024

* **BSC 4452**: Class 19032 {% include image.html file='comptools.png' alt="Image of servers and tool icons" position="right" %}
* **BSC 6451**: Class 22340

## Course Description

The early 2000’s were characterized as the era of *Big Data*, with researchers across disciplines finding that large volumes of diverse data transformed research. In the past decade, this has again been transformed by the re-emergence of artificial intelligence and machine learning systems aiding in the interpretation of Big Data. As data types and volumes continue to grow, knowledge of scripting, database management, and advanced computing, including AI fundamentals, is critical for researchers across disciplines.

This course introduces students to the tools needed to be proficient, computationally enabled researchers, providing a foundation in Linux and Bash scripting for data management, Python programming, basic SQL database fundamentals, and an introduction to artificial intelligence methods.

The course assumes no prior coding or command-line skills and covers concepts that enable students to apply new technologies to a wide array of research questions. A foundation in data management and analysis concepts opens doors for well-trained researchers and allows them to work in multidisciplinary fields.

**The course assumes no prior coding or command line skills**, and covers concepts that will provide the ability for students to apply new technologies to a wide array of research questions. A foundation in data management and analysis concepts opens doors for well-trained researchers and allows them to work in multidisciplinary fields.

{% include note.html content="While the title of the course includes '*in Biology*' there is little that is actually focussed on biology. This course strives to be broadly applicable to many areas of research. Bureaucracies being what they are, the title is what it is..." %}

## Course Organization

The course is divided into four main sections:

* **Section 1**: Linux command line and Bash scripting; version control using Git and GitHub; using high-performance computing resources
* **Section 2**: Python scripting
* **Section 3**: SQL database introduction and integration with Python
* **Section 4**: A brief introduction to Artificial Intelligence

## Course Objectives

* Demonstrate how technology infrastructure can improve research and open new avenues of investigation.
* Competently navigate the Unix/Linux command line interface.
* Effectively and efficiently manipulate text files, performing complex regular expression replacements, reformatting and merging files in various ways.
* Raise and address current issues through class participation and discussion.
* Use AI-assisted tools to generate and debug code.
* Use High Performance Computing resources such as the UFIT Research Computing for cluster-based analyses. Including batch scripting and running multi-processor applications (threaded and MPI).
* Explain the basic anatomy of computer scripts/programs, with particular focus on Python scripting.
* Construct analytical pipelines to accomplish complex tasks.
* Describe basic database design, creation and manipulation. Perform scripted database operations for information discovery, data exploration and research data curation.
* Have a basic understanding of research graphics formats, preparation and manipulation
* Have a basic understanding of artificial intelligence and gain hands-on experience with computer vision.

## Course Textbooks

{% include image.html file='textbook.png' alt="textbook icon" position="right" max-width=75 %}
The main texts for the course are:

* The Linux Command Line: [http://linuxcommand.org](http://linuxcommand.org/tlcl.php) (my notes and referenced page numbers will be based on the 25.12 version of the PDF, Seventh Internet Edition, from Jan. 5, 2026.)
* Python For Everyone: [https://www.py4e.com/book.php](https://www.py4e.com/book.php)

{% include image.html file='UfAffordableBadge_2022Fall.png' alt='Affordable UF badge' position='right' max-width=100 %} Each of these is available as a free PDF download or for purchase in print. Because there are no textbook costs for this course, it has been recognized by Affordable UF as an affordable course.

{% include tip.html content="Also check out the [additional resources page](resources.md)." %}

## Course Syllabus

The full course syllabus is available on the UF SimpleSyllabus site.


## Course Calendar



{% include important.html content="This is subject to change, please check back frequently." %}

For readings, there may be links to pages with my notes and additional explanations on the content from the texts. The texts are abbreviated as TLCL = [The Linux Command Line](http://linuxcommand.org); Py4E = [Python for Everyone](https://www.py4e.com/book.php).

Week | Date | Reading/Assignment |Topic |
-----|------|--------------------|------|
[1](Week_01.html) | {{ site.wk01_fri_date | date: '%a, %b %d' }} | [Download Software](software.md)|[Introduction and course objectives](https://docs.google.com/presentation/d/1yed5Jdg_uE96qZzpAwp0agv3js3kxH8rWJxXsDgSpbA/edit?usp=sharing)
|||
[2](Week_02.html) | {{ site.wk02_mon_date | date: '%a, %b %d' }} |  [Take UFRC New User Training](https://help.rc.ufl.edu/doc/New_user_training)<br>**[GitHub Account assignment due tomorrow](github_account.md)**<br>Quiz 1 available, due {{site.quiz_1_due | date: '%A, %B %d' }}|Getting started: [Computers](https://docs.google.com/presentation/d/1lwaPgzs71TuDtuz084PWYocnETpXfMhhJLL-r5UuhSs/edit?usp=sharing)<br> Getting a [GitHub.com](https://github.com) account
[2](Week_02.html) | {{ site.wk02_wed_date | date: '%a, %b %d' }} | [Read TLCL Introduction & Ch 1-4](TLCL_reading_notes_1.md) | Building shell skills
[2](Week_02.html) | {{ site.wk02_fri_date | date: '%a, %b %d' }} | <br> [Read TLCL Ch 5-8](TLCL_reading_notes_2.md)<br>Problem Set 1 available, due {{ site.ps_1_due | date: '%A, %B %d' }}| <br>[Here are some exercises to work on](https://forms.gle/fZSskLMgw2exxfq47) 
|||
[3](Week_03.html) | {{ site.wk03_mon_date | date: '%a, %b %d' }} | | Labor Day, no class
[3](Week_03.html) | {{ site.wk03_wed_date | date: '%a, %b %d' }} | | [Continue working on the exercises](https://forms.gle/fZSskLMgw2exxfq47) 
[3](Week_03.html) | {{ site.wk03_fri_date | date: '%a, %b %d' }} |[Read Notes on Regular Expressions and TLCL Ch 19](TLCL_reading_notes_3.md)<br> Quiz 2 available, due {{site.quiz_2_due | date: '%A, %B %d'}} | Text manipulation <br> [<i class="fa fa-file"></i> Regular Expressions Handout](pdf/Regular_Expressions_Cheat_Sheet.pdf)
|||
[4](Week_04.html) | {{ site.wk04_mon_date | date: '%a, %b %d' }} | [Read TLCL Ch 20](TLCL_reading_notes_3.5.md)<br>Optional: [Watch Learn the Linux Command Line](LinkedInLearningLinux.md) | Shell Scripts and version control with git and GitHub and git/github, [Github Branching exercise](github_branches.md)
[4](Week_04.html) | {{ site.wk04_wed_date | date: '%a, %b %d' }} |<br>[Read TLCL Ch 24-26](TLCL_reading_notes_4.md)<br>**Quiz 1 due**<br> Problem Set 2 available, due {{site.ps_2_due | date: '%A, %B %d'}} | Git and GitHub.com
[4](Week_04.html) | {{ site.wk04_fri_date | date: '%a, %b %d' }} | Watch the [HiPerGator: SLURM Submission Scripts](https://help.rc.ufl.edu/doc/Prerecorded_Training#HiPerGator:_SLURM_Submission_Scripts) training| [Slides on git and GitHub.com](https://docs.google.com/presentation/d/19Rq6hg8eHcVb1VXFNlZEY_ykNc2kchGzvVMw9tvv2yE/edit?usp=sharing) and Shell Scripts and version control with git and GitHub and git/github, [Github Branching exercise](github_branches.md)
|||
[5](Week_05.html) | {{ site.wk05_mon_date | date: '%a, %b %d' }} |**Quiz 2 due** <br>  **Problem Set 1 due** <br> [Read TLCL Ch 23](TLCL_reading_notes_6.md) | Compiling source code<br>Google and Documentation <br> Using UFIT Research Computing resources<br>Running batch jobs
[5](Week_05.html)  | {{ site.wk05_wed_date | date: '%a, %b %d' }} |[Read Py4E Ch 1](py4e_reading_notes_1.md) |Introduction to Python
[5](Week_05.html)  | {{ site.wk05_fri_date | date: '%a, %b %d' }} |Problem Set 2 available, due {{site.ps_2_due | date: '%A, %B %d' }} <br> Quiz 3 available, due {{site.quiz_3_due | date: '%A, %B %d' }}<br>[Read Py4E Ch 2](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch2_varaibles_and_types.ipynb)| Python data types
|||
6 | Skipping week 6 😰 |
|||
7| {{ site.wk07_mon_date | date: '%a, %b %d' }} | [Finish up Py4E Ch 2](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch2_varaibles_and_types.ipynb) <br> [Read Py4E Ch 3](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch3_flow_control.ipynb)|Python: Flow Control
7 | {{ site.wk07_wed_date | date: '%a, %b %d' }}| [Read Py4E Ch 4](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch4_functions.ipynb)| Python: Functions 
7 | {{ site.wk07_fri_date | date: '%a, %b %d' }} | Problem Set 3 available, due {{site.ps_3_due | date: '%A, %B %d' }}<BR>[Read Py4E Ch 5](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch5_iteration.ipynb)  |Python: Iteration
|||
8 | {{ site.wk08_mon_date | date: '%a, %b %d' }}| Python data types[Read Py4E Ch 6](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch6_strings.ipynb) & [Ch 7](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch7_file_io.ipynb) | Python: try/except, Strings, File I/O
8 | {{ site.wk08_wed_date | date: '%a, %b %d' }} | [Read Ch 11](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch11_regex.ipynb) | RegEx in Python
8 | {{ site.wk08_fri_date | date: '%a, %b %d' }} | **Problem Set 3 due**<br>[[Read Py4E Ch 12](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch12_networked.ipynb) & [Ch 13](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch13_web_services.ipynb) | Scripting data acquisition
|||
9 | {{ site.wk09_mon_date | date: '%a, %b %d' }} | Problem Set 4 available, due {{site.ps_4_due | date: '%A, %B %d' }}<br>[SciPy, NumPy, Pandas](https://github.com/comptoolsres/Jupyter_content/blob/main/NumPy_SciPy_Pandas.ipynb)| SciPy, NumPy, Pandas
9 |{{ site.wk09_wed_date | date: '%a, %b %d' }} | Project 1 available, due {{site.project_1_due | date: '%A, %B %d' }} |  **Matt at Conference, no class**: Work on Problem set 4
9 | {{ site.wk09_fri_date | date: '%a, %b %d' }}| | **Homecoming, no class** 
|||
10  | {{ site.wk10_mon_date | date: '%a, %b %d' }} | Quiz 4 available, due {{site.quiz_4_due | date: '%A, %B %d' }}<br>Scan Py4E Ch 16 <BR> Py4E Ch 14: Object oriented Programming| [Py4E Ch 14: Object oriented programming](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch14_ObjectOrientedProgramming.ipynb)
10  | {{ site.wk10_wed_date | date: '%a, %b %d' }} |  | [Matplotlib and data visualization](https://github.com/comptoolsres/Jupyter_content/blob/main/Data_visualization.ipynb)<br>[Pandas with Messy Data](https://github.com/comptoolsres/Jupyter_content/blob/main/Pandas_messy_data.ipynb)<br>[Data visualization with Pandas](https://github.com/comptoolsres/Jupyter_content/blob/main/Pandas_data_vis.ipynb)
10 | {{ site.wk10_fri_date | date: '%a, %b %d' }} |**Problem Set 4 due**<br>[Programming Foundations Databases](LinkedInLearningDatabases.md)|  Work on Project 1
|||
[11](Week_11.html) | {{ site.wk11_mon_date | date: '%a, %b %d' }}| **Quiz 4 due** |[Database intro](Database_Intro.md)<br>[Flight DB Example](Databases_flights_DB_example.md)
[11](Week_11.html) | {{ site.wk11_wed_date | date: '%a, %b %d' }} | **Project 1 Due**<br> |Overview of databases<br>Database design
[11](Week_11.html) | {{ site.wk11_fri_date | date: '%a, %b %d' }} | [Read Py4E Ch. 15, through 15.5 and my notes](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch15_databases.ipynb) <br>Problem set 5 available, due {{site.ps_5_due | date: '%A, %B %d' }}| [Py4E Ch. 15, through 15.5 and my notes](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch15_databases.ipynb)<br>[Databases, SQL and sqlite](SQL_Introduction.md)
|||
[12](Week_12.html) | {{ site.wk12_mon_date | date: '%a, %b %d' }} | |  [Py4E Ch. 15, through 15.5 and my notes](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch15_databases.ipynb)<br>[Databases, SQL and sqlite](SQL_Introduction.md)
[12](Week_12.html) | {{ site.wk12_wed_date | date: '%a, %b %d' }} | Quiz 5 available, due {{site.quiz_5_due | date: '%A, %B %d' }} | More on databases and [Joins](https://github.com/comptoolsres/Jupyter_content/blob/main/JOINs.ipynb)
[12](Week_12.html) | {{ site.wk12_fri_date | date: '%a, %b %d' }} | Project 2 available, due {{ site.project_2_due | date: '%A, %B %d' }}| [SQLAlchemy](https://github.com/comptoolsres/Jupyter_content/blob/main/SQLAlchemy.ipynb)|
|||
[13](Week_13.html) | {{ site.wk13_mon_date | date: '%a, %b %d' }} | | **Veteran's Day, no class** 
[13](Week_13.html) | {{ site.wk13_wed_date | date: '%a, %b %d' }}| | [SQLAlchemy and Pandas](https://github.com/comptoolsres/Jupyter_content/blob/main/SQLAlchemy_and_Pandas.ipynb)
[13](Week_13.html) | {{ site.wk13_fri_date | date: '%a, %b %d' }}|  **Problem Set 5 due** | [Argparse](Argparse.md)
|||
[14](Week_14.html) | {{ site.wk14_mon_date | date: '%a, %b %d' }} |  | [Graphics](Graphics.html)
[14](Week_14.html) | {{ site.wk14_wed_date | date: '%a, %b %d' }} | | Work on Project 2
[14](Week_14.html) | {{ site.wk14_fri_date | date: '%a, %b %d' }} | **Quiz 5 due** <br> Quiz 6 available, due {{site.quiz_6_due}}| [Intro to AI](https://github.com/comptoolsres/brief_AI_intro)
|||
[15](Week_15.html) | {{ site.wk15_mon_date | date: '%a, %b %d' }} |  | Thanksgiving, no class
[15](Week_15.html) | {{ site.wk15_wed_date | date: '%a, %b %d' }} |  | Thanksgiving, no class
[15](Week_15.html) | {{ site.wk15_fri_date | date: '%a, %b %d' }} |  | Thanksgiving, no class
|||
[16](Week_16.html) | {{ site.wk16_mon_date | date: '%a, %b %d' }} |  | Into to AI
[16](Week_16.html) | {{ site.wk16_wed_date | date: '%a, %b %d' }} |**Project 2 due** <BR> **Quiz 6 due** | Intro to AI

