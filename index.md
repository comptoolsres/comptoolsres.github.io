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

The early 2000's where characterized as the era of *Big Data*, with researchers across disciplines finding research transformed by large volumes of diverse data. In the past decade, this has been again transformed by the re-emergence of artificial intelligence and machine learning systems aiding in interpretation of Big Data. As data types and volumes continue to grow, knowledge of scripting, database management, and advanced computing skills, including AI fundamentals, are critical for researchers regardless of discipline.

This course introduces students to the tools needed to be proficient, computationally-enabled researchers, providing a foundation in Linux and Bash scripting for data management, Python coding, basic SQL database fundamentals, and an introduction to artificial intelligence methods.

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

## Meeting Times

### Synchronous Meetings
{% include image.html file='lecture.png' alt="lecture icon" position="right" max-width=75 %}

* Mon, Wed, Fri, 9:35 AM - 10:25 AM (Period 3)
* Bartram Hall, room 211 and on Zoom

{% include important.html content="You should make every effort to attend these sessions synchronously. While I will post most lectures ahead of time and will record these session, **this is the best opportunity to ask questions and get help from me and others in the class.**" %}

* I understand that some students will need to miss classes sometimes. That is fine and I will do my best to help you catch up, but regular attendance is the best way to learn.

### Asynchronous Work

* Students will work on projects either independently or in small, groups.
* This work can be more flexible in timing and will give you and your classmates times to get more hands-on experience and challenge yourselves to learn on your own.

### Student Help Time

{% include image.html file='office_hours.png' alt="Office Hours icon" position="right" max-width=75 %}

* Mondays from 11:00 am to noon, Physics (NPB 2334) or on Zoom
* Thursdays from 3:00 pm to 4:00 pm, Physics (NPB 2334) or on Zoom
* Fridays from 10:30 am to 11:30 am, UFII/UFBI Conference Room (ECE Building)
* By Appointment--please <a href="mailto:magitz@ufl.edu?subject=Comp%20Tools%20Res%20office%20hours%20request">Email me</a> to setup a different time if needed.

 {% include tip.html content="Coding is not always easy. Simple solutions are not always obvious. There will be some frustration. **I expect that you will need help. You should expect that you will need help.** I want to help you! I cannot always help if you do not ask for the help you need. Please ask for help." %}

## Course Textbooks

{% include image.html file='textbook.png' alt="textbook icon" position="right" max-width=75 %}
The main texts for the course are:

* The Linux Command Line: [http://linuxcommand.org](http://linuxcommand.org/tlcl.php) (my notes and referenced page numbers will be based on the 19.01A PDF, Fifth internet edition from Jan 28, 2019)
* Python For Everyone: [https://www.py4e.com/book.php](https://www.py4e.com/book.php)

{% include image.html file='UfAffordableBadge_2022Fall.png' alt='Affordable UF badge' position='right' max-width=100 %} Each of these is available as a free PDF download or for purchase in print. Because there are no textbook costs for this course, it has been recognized by Affordable UF as an affordable course. 

{% include tip.html content="Also check out the [additional resources page](resources.md)." %}

## Course videos

{% include note.html content="Most of the video content for this course was made in the Summer and Fall of 2020. The course was fully remote during the pandemic and these were mostly recorded in my living room. The quality is decent, but they are older and definately home made...That said, I think they may be useful to some, so I have opted to keep them as part of this site. Students should not feel that they need to watch all the videos, but may want to check them out for sections they miss or find more challenging." %}

## Course Calendar

{% include image.html file='calendar.png' alt="calendar icon" position="right" max-width=75 %}

{% include warning.html content="**I am still working on updating things for Fall 2024**. While the infromation below is a good guide, many pages are still being worked on." %}


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
[3](Week_03.html) | {{ site.wk03_wed_date | date: '%a, %b %d' }} | [Read Notes on Regular Expressions and TLCL Ch 19](TLCL_reading_notes_3.md)<br> Quiz 2 available, due {{site.quiz_2_due | date: '%A, %B %d'}}| Text manipulation <br> [<i class="fa fa-file"></i> Regular Expressions Handout](pdf/Regular_Expressions_Cheat_Sheet.pdf)
[3](Week_03.html) | {{ site.wk03_fri_date | date: '%a, %b %d' }} |**Quiz 1 due**<br>[Read TLCL Ch 20](TLCL_reading_notes_3.5.md)<br>Optional: [Watch Learn the Linux Command Line](LinkedInLearningLinux.md)<br>[Read TLCL Ch 24-26](TLCL_reading_notes_4.md)| Shell Scripts and version control with git and GitHub
|||
[4](Week_04.html) | {{ site.wk04_mon_date | date: '%a, %b %d' }} |  | Continue working on shell scripts and git/github, [Github Branching exercise](github_branches.md)
[4](Week_04.html) | {{ site.wk04_wed_date | date: '%a, %b %d' }} | Problem Set 2 available, due {{site.ps_2_due | date: '%A, %B %d'}} | Git and GitHub.com
[4](Week_04.html) | {{ site.wk04_fri_date | date: '%a, %b %d' }} | **Quiz 2 due** <br> **Problem Set 1 due** <br>Watch the [HiPerGator: SLURM Submission Scripts](https://help.rc.ufl.edu/doc/Prerecorded_Training#HiPerGator:_SLURM_Submission_Scripts) training| 
|||
[5](Week_05.html) | {{ site.wk05_mon_date | date: '%a, %b %d' }} | [Read TLCL Ch 23](TLCL_reading_notes_6.md) | Compiling source code<br>Google and Documentation <br> Using UFIT Research Computing resources<br>Running batch jobs
[5](Week_05.html)  | {{ site.wk05_wed_date | date: '%a, %b %d' }} |[Read Py4E Ch 1](py4e_reading_notes_1.md) |Introduction to Python
[5](Week_05.html)  | {{ site.wk05_fri_date | date: '%a, %b %d' }} | **Problem Set 2 due** <br>Quiz 3 available, due {{site.quiz_3_due | date: '%A, %B %d' }}<br>[Read Py4E Ch 2](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch2_varaibles_and_types.ipynb)| Python data types
|||
[6](Week_06.html) | {{ site.wk06_mon_date | date: '%a, %b %d' }} |Problem Set 3 available, due {{site.ps_3_due | date: '%A, %B %d' }} <br> [Read Py4E Ch 3](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch3_flow_control.ipynb)|Python: Flow Control
[6](Week_06.html) | {{ site.wk06_wed_date | date: '%a, %b %d' }}| [Read Py4E Ch 4](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch4_functions.ipynb)| Python: Functions 
[6](Week_06.html) | {{ site.wk06_fri_date | date: '%a, %b %d' }} |**Quiz 3 due**<br> [Read Py4E Ch 5](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch5_iteration.ipynb)  |Python: Iteration
|||
[7](Week_07.html) | {{ site.wk07_mon_date | date: '%a, %b %d' }}|[Read Py4E Ch 6](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch6_strings.ipynb) & [Ch 7](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch7_file_io.ipynb) | Python: try/except, Strings, File I/O
[7](Week_07.html) | {{ site.wk07_wed_date | date: '%a, %b %d' }} | [Read Ch 11](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch11_regex.ipynb) | RegEx in Python
[7](Week_07.html) | {{ site.wk07_fri_date | date: '%a, %b %d' }} | **Problem Set 3 due**<br>[[Read Py4E Ch 12](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch12_networked.ipynb) & [Ch 13](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch13_web_services.ipynb) | Scripting data acquisition
|||
[8](Week_08.html) | {{ site.wk08_mon_date | date: '%a, %b %d' }} | <br>[SciPy, NumPy, Pandas](https://github.com/comptoolsres/Jupyter_content/blob/main/NumPy_SciPy_Pandas.ipynb)| SciPy, NumPy, Pandas
[8](Week_08.html) |{{ site.wk08_wed_date | date: '%a, %b %d' }} | | [Pandas with Messy Data](https://github.com/comptoolsres/Jupyter_content/blob/main/Pandas_messy_data.ipynb)<br>[Data visualization with Pandas](https://github.com/comptoolsres/Jupyter_content/blob/main/Pandas_data_vis.ipynb)
[8](Week_08.html) | {{ site.wk08_fri_date | date: '%a, %b %d' }}| Matplotlib and data visualization](https://github.com/comptoolsres/Jupyter_content/blob/main/Data_visualization.ipynb) | Visualization|||
|||
[9](Week_09.html) |{{ site.wk09_mon_date | date: '%a, %b %d' }} | Problem Set 4 available, due {{site.ps_4_due | date: '%A, %B %d' }}<br>Project 1, due {{site.project_1_due | date: '%A, %B %d' }}| More data visualization
[9](Week_09.html) |{{ site.wk09_wed_date | date: '%a, %b %d' }} | | Matt at Conference, no class work on: TBD
[9](Week_09.html) |{{ site.wk09_fri_date | date: '%a, %b %d' }} | | **Homecoming, no class**
|||
[10](Week_10.html)  | {{ site.wk10_mon_date | date: '%a, %b %d' }} | Quiz 4 available, due {{site.quiz_4_due | date: '%A, %B %d' }}<br>Scan Py4E Ch 16 <BR> Py4E Ch 14: Object oriented Programming| [Py4E Ch 14: Object oriented programming](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch14_ObjectOrientedProgramming.ipynb)
[10](Week_10.html)  | {{ site.wk10_wed_date | date: '%a, %b %d' }} |  | Work on Project 1
[10](Week_10.html) | {{ site.wk10_fri_date | date: '%a, %b %d' }} |[Programming Foundations Databases](LinkedInLearningDatabases.md)|  Work on Project 1
|||
[11](Week_11.html) | {{ site.wk11_mon_date | date: '%a, %b %d' }}| **Quiz 4 due** |[Database intro](Database_Intro.md)<br>[Flight DB Example](Databases_flights_DB_example.md)
[11](Week_11.html) | {{ site.wk11_wed_date | date: '%a, %b %d' }} | **Project 1 Due**<br> |Overview of databases<br>Database design
[11](Week_11.html) | {{ site.wk11_fri_date | date: '%a, %b %d' }} | [Read Py4E Ch. 15, through 15.5 and my notes](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch15_databases.ipynb)<br> **Problem Set 4 Due** <br>Problem set 5 available, due {{site.ps_5_due | date: '%A, %B %d' }}| [Py4E Ch. 15, through 15.5 and my notes](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch15_databases.ipynb)<br>[Databases, SQL and sqlite](SQL_Introduction.md)
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
[14](Week_14.html) | {{ site.wk14_fri_date | date: '%a, %b %d' }} | **Quiz 5 due** <br> Quiz 6 available, due {{site.quiz_6_due}}| Intro to AI
|||
[15](Week_15.html) | {{ site.wk15_mon_date | date: '%a, %b %d' }} |  | Thanksgiving, no class
[15](Week_15.html) | {{ site.wk15_wed_date | date: '%a, %b %d' }} |  | Thanksgiving, no class
[15](Week_15.html) | {{ site.wk15_fri_date | date: '%a, %b %d' }} |  | Thanksgiving, no class
|||
[16](Week_16.html) | {{ site.wk16_mon_date | date: '%a, %b %d' }} |  | Into to AI
[16](Week_16.html) | {{ site.wk16_wed_date | date: '%a, %b %d' }} |**Project 2 due** <BR> **Quiz 6 due** | Intro to AI

## Software and Hardware

Participants will need a computer with internet connection for all classes.

Several free/open source software packages will be used throughout the course, and students will be required to install some of these.

A (free) Research Computing account will be cxreated for students to access HiPerGator for coursework.

Students will be required to apply for a (free) Github.com account for coursework.

If you have technical difficulties with Canvas, please contact the UF Helpdesk at:

*	http://helpdesk.ufl.edu
*	(352) 392-HELP (4357)
*	Walk-in: HUB 132

Any requests for make-ups due to technical issues should be accompanied by the ticket number received from the Help Desk when the problem was reported to them. The ticket number will document the time and date of the problem. Please e-mail the instructor within 24 hours of the technical difficulty if you wish to request a make-up.

All faculty, staff and student of the University are required and expected to obey the laws and legal agreements governing software use. Failure to do so can lead to monetary damages and/or criminal penalties for the individual violator. Because such violations are also against University policies and rules, disciplinary action will be taken as appropriate.

## Grading

See also the [List of Graded Work page](Grading.html).

### Assignment Values

* **Quizzes**: 6 @ 20 points each: 120 points (37%)
* **Problem Sets**: 5 @ 20 points each: 100 points (30%)
* **Class Projects**: 2 @ 40 points each: 80 points (24%)
* **Class Participation** 30 points: 30 points (9%)
  * 5 points for GitHub account assignment
  * 10 points for github commits
  * 15 points for code peer review

Grading in this class is consistent with UF policies available at: [https://catalog.ufl.edu/UGRD/academic-regulations/grades-grading-policies/]( https://catalog.ufl.edu/UGRD/academic-regulations/grades-grading-policies/)

<div class="panel-group" id="accordion">
    <div class="panel panel-default">
        <div class="panel-heading">
            <a class="noCrossRef accordion-toggle" data-toggle="collapse" data-parent="#accordion" href="#collapseA"> <H3>Grade Disputes</H3></a>
        </div>
        <!-- /.panel-heading--> 
        <div id="collapseA" class="panel-collapse collapse noCrossRef">
            <div class="panel-body">
                Should a student wish to dispute any grade received in this class (other than simple addition errors), the dispute must be in writing (via email) and be submitted to the instructor within a week of receiving the grade.
                <BR><BR>
                The dispute should clearly set out the grade that the student believes the assignment should have received as well as why they believe that they should have received such a grade.
            </div>
            <!-- /.panel-body -->
        </div>
        <!-- /.panel-collapse -->
    </div>
    <!-- /.panel-default -->
</div>
<!-- /.panel-group -->

<div class="panel-group" id="accordion">
    <div class="panel panel-default">
        <div class="panel-heading">
            <a class="noCrossRef accordion-toggle" data-toggle="collapse" data-parent="#accordion" href="#collapseB"> <H3>Grading Scale and GPA Equivalent</H3></a>
        </div>
        <!-- /.panel-heading--> 
        <div id="collapseB" class="panel-collapse collapse noCrossRef">
            <div class="panel-body">
                <table>
                  <thead>
                    <tr>
                      <th>A</th>
                      <th>A-</th>
                      <th>B+</th>
                      <th>B</th>
                      <th>B-</th>
                      <th>C+</th>
                      <th>C</th>
                      <th>C-</th>
                      <th>D+</th>
                      <th>D</th>
                      <th>D-</th>
                      <th>F</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr>
                      <td>100-93<br />(4.0)</td>
                      <td>&lt;93-90<br />(3.67)</td>
                      <td>&lt;90-87<br />(3.33)</td>
                      <td>&lt;87-83<br />(3.0)</td>
                      <td>&lt;83-80<br />(2.67)</td>
                      <td>&lt;80-77<br />(2.33)</td>
                      <td>&lt;77-73<br />(2.0)</td>
                      <td>&lt;73-70<br />(1.67)</td>
                      <td>&lt;70-67<br />(1.33)</td>
                      <td>&lt;67-63<br />(1.0)</td>
                      <td>&lt;63-60<br />(0.67)</td>
                      <td>&lt;60<br />(0)</td>
                    </tr>
                  </tbody>
                </table>
                <B>Note:</B> A grade of C- is not a qualifying grade for major, minor, Gen Ed, or College Basic distribution credit. For further information on UF's Grading Policy, see:
                <a href="https://catalog.ufl.edu/UGRD/academic-regulations/grades-grading-policies/">https://catalog.ufl.edu/UGRD/academic-regulations/grades-grading-policies/</a>
            </div>
            <!-- /.panel-body -->
        </div>
        <!-- /.panel-collapse -->
    </div>
    <!-- /.panel-default -->
</div>
<!-- /.panel-group -->

## Course Policies

### Class Attendance and Makeup Policy

Requirements for class attendance and makeup assignments, and other work in this course are consistent with university policies that can be found in the online catalog at: [https://catalog.ufl.edu/UGRD/academic-regulations/attendance-policies/](https://catalog.ufl.edu/UGRD/academic-regulations/attendance-policies/)

In general, I do not take attendance. You are all adults and I assume you are taking the class the learn. The best way to learn is to regularly attend class. I am sure students will miss class for various reasons. I am happy to help you catch up. If you regularly miss class and fall behind, I may ask that you hold questions on content you have missed until after class, or ask that you coordinate a time to go over the content. I will make every effort to record and post all classes to help those that miss classes.

### Quiz and Assignment Policy

Quiz and assignment dates will be announced at least one week in advance and students will have at least three days to complete the quiz or assignment. Each quiz or assignment will clearly state if it is an individual or group assignment.  Individual assignments must be the student’s own work, completed without the assistance of others.

All quizzes and assignments are "open book, open internet", you may use whatever resources you desire to complete the quiz/assignment. Though only assignments specifically noted as group assignments should be worked on with other people.

### Makeup and Late policy

Please notify the instructor of circumstances that lead to late work or missed classes. I will generally work with you and accept late work. **Without prior notification, late work will be penalized one point per day after the due date.**

## Students Requiring Accommodations

Students with disabilities requesting accommodations should first register with the Disability Resource Center (352-392-8565, [https://disability.ufl.edu/students/get-started/](https://disability.ufl.edu/students/get-started/)) by providing appropriate documentation. Once registered, students will receive an accommodation letter which must be presented to the instructor when requesting accommodation. Students with disabilities should follow this procedure as early as possible in the semester.

## Course Evaluation

Students are expected to provide professional and respectful feedback on the quality of instruction in this course by completing course evaluations online via GatorEvals. Guidance on how to give feedback in a professional and respectful manner is available at [gatorevals.aa.ufl.edu/students/](https://gatorevals.aa.ufl.edu/students/). Students will be notified when the evaluation period opens, and can complete evaluations through the email they receive from GatorEvals, in their Canvas course menu under GatorEvals, or via [ufl.bluera.com/ufl/](https://ufl.bluera.com/ufl/). Summaries of course evaluation results are available to students at [gatorevals.aa.ufl.edu/public-results/](https://gatorevals.aa.ufl.edu/public-results/).

## Class Demeanor and Netiquette

Students are expected behave in a manner that is respectful to the instructor and to fellow students. Opinions held by other students should be respected in discussion, and conversations that do not contribute to the discussion should be held at minimum, if at all.

Students should be working on course content during class.

### GitHub Discussion Board

Canvas can be a challenge when working with code. As such we will use the [GitHub discussion board](https://github.com/comptoolsres/comptoolsres.github.io/discussions) to ask for and provide help by all. Students should be supportive and considerate of others at all times. Rude or inappropriate comments will be removed and the poster will be warned.

## University Honesty Policy

UF students are bound by The Honor Pledge which states:
> We, the members of the University of Florida community, pledge to hold ourselves and our peers to the highest standards of honor and integrity by abiding by the Honor Code. On all work submitted for credit by students at the University of Florida, the following pledge is either required or implied: “On my honor, I have neither given nor received unauthorized aid in doing this assignment.”

[The Honor Code](https://sccr.dso.ufl.edu/policies/student-honor-code-student-conduct-code/) specifies a number of behaviors that are in violation of this code and the possible sanctions. Furthermore, you are obligated to report any condition that facilitates academic misconduct to appropriate personnel. If you have any questions or concerns, please consult with the instructor or TAs in this class

<div class="panel-group" id="accordion">
    <div class="panel panel-default">
        <div class="panel-heading">
            <a class="noCrossRef accordion-toggle" data-toggle="collapse" data-parent="#accordion" href="#collapseC"> <H2> Health and Wellness</H2></a>
        </div>
        <!-- /.panel-heading--> 
        <div id="collapseC" class="panel-collapse collapse noCrossRef">
            <div class="panel-body">
              Resources are available on-campus for students having personal problems or lacking clear career and academic goals. The resources include:
              <ul>
                <li><b>UF Counseling & Wellness Center</b>, 3190 Radio Rd, 392-1575, psychological and psychiatric services.</li>
                <ul>
                  <li>Provides counseling and support as well as crisis and wellness services including a variety of workshops throughout the semester (e.g., Yappy Hour, Relaxation and Resilience).</li>
                  <li>Many students experience test anxiety and other stress related problems. “A Self Help Guide for Students” is available through the Counseling Center (301 Peabody Hall, 392-1575) and at their web site: <a href="https://counseling.ufl.edu/">https://counseling.ufl.edu/</a>.</li>
                  <li>U Matter, We Care: If you or a friend is in distress, please contact umatter@ufl.edu or 352 392-1575 so that a team member can reach out to the student.</li>
                </ul>
                <li><b>Career Connections Center</b>, Reitz Union, 392-1601, CareerCenterMarketing@ufsa.ufl.edu, connects job seekers with employers and offers guidance to enrich your collegiate experience and prepare you for life after graduation.</li>
                <li><b>University Police Department</b>: 392-1111 or 9-1-1 for emergencies. <a href="http://www.police.ufl.edu/">https://www.police.ufl.edu/</a></li>
                <li><b>Sexual Assault Recovery Services (SARS)</b>: Student Health Care Center, 392-1161.</li>
                <li><b>Student Health Care Center</b>: Call 352-392-1161 for 24/7 information to help you find the care you need, or visit <a href="https://shcc.ufl.edu">https://shcc.ufl.edu/</a></li>
                <li><b>Food insecurity</b>: The Pantry is a resource on the University of Florida campus committed to supporting students, staff, and faculty who are experiencing food insecurity. These individuals do not have reliable access to nutritious foods for themselves and their families. If you, or anyone you know, is experiencing food insecurity, the Pantry is a resource to visit. We offer non-perishable food, toiletries and fresh produce grown at the Field and Fork Gardens during certain times of the year. There is no proof of need required in order to shop at the Pantry; you must only bring in your valid UFID card. At the Pantry, we know that a good meal makes for a good student, and we work to support all Gators who are experiencing food insecurity. <a href="https://pantry.fieldandfork.ufl.edu/">Field & Fork Food Pantry</a>.</li>
              </ul>
            </div>
            <!-- /.panel-body -->
        </div>
        <!-- /.panel-collapse -->
    </div>
    <!-- /.panel-default -->
</div>
<!-- /.panel-group -->

## Inclusive Learning Environment

This course embraces the University of Florida’s Non-Discrimination Policy, which reads:
> The University shall actively promote equal opportunity policies and practices conforming to laws against discrimination. The University is committed to nondiscrimination with respect to race, creed, color, religion, age, disability, sex, sexual orientation, gender identity and expression, marital status, national origin, political opinions or affiliations, genetic information and veteran status as protected under the Vietnam Era Veterans’ Readjustment Assistance Act.

If you have questions or concerns about your rights and responsibilities for inclusive learning environment, please see the instructor or refer to the Office of Multicultural & Diversity Affairs website: [http://multicultural.ufl.edu](http://multicultural.ufl.edu).

## Privacy

There are federal laws protecting your privacy with regards to grades earned in courses and on individual assignments. For more information, please see: [https://registrar.ufl.edu/ferpa.html](https://registrar.ufl.edu/ferpa.html)

## Statement Regarding Course Recording

Our class sessions may be audio visually recorded for students in the class to refer back to and for use of enrolled students who are unable to attend live. Students who participate with their camera engaged or utilize a profile image are agreeing to have their video or image recorded. If you are unwilling to consent to have your profile or video image recorded, keep your camera off and do not use a profile image. Likewise, students who un-mute during class and participate verbally are agreeing to have their voices recorded.  If you are unwilling to consent to have your voice recorded during class, you will need to keep your mute button activated and communicate exclusively using the "chat" feature, which allows students to type questions and comments live. The chat will not be recorded or shared. As in all courses, unauthorized recording and unauthorized sharing of recorded materials is prohibited.

## Disclaimer on Free and Open Discussion

Students are encouraged to employ critical thinking and to rely on data and verifiable sources to interrogate all assigned readings and subject matter in this course as a way of determining whether they agree with their classmates and/or their instructor. No lesson is intended to espouse, promote, advance, inculcate, or compel a particular feeling, perception, viewpoint or belief.

<div class="panel-group" id="accordion">
    <div class="panel panel-default">
        <div class="panel-heading">
            <a class="noCrossRef accordion-toggle" data-toggle="collapse" data-parent="#accordion" href="#collapseD"> <H2> Additional UF Policies and Resources</H2></a>
        </div>
        <!-- /.panel-heading--> 
        <div id="collapseD" class="panel-collapse collapse noCrossRef">
            <div class="panel-body">
                <h3>Dean of Students Office</h3>
                <a href="https://dso.ufl.edu/">Dean of Students Office</a> (352-392-1261) provides a variety of services to students and families, including <a href="https://dso.ufl.edu/areas_services/hitchcock-field-fork-pantry/">Field and Fork</a> (UF&rsquo;s food pantry) and <a href="https://dso.ufl.edu/areas_services/new-student-family-programs/">New Student and Family programs</a></p>
                <h3>Disability Resource Center</h3>
                <ul>
                  <li><a href="https://disability.ufl.edu/students/get-started/">Disability Resource Center</a> (<a href="mailto:DRCaccessUF@ufsa.ufl.edu">DRCaccessUF@ufsa.ufl.edu</a> | 352-392-8565) helps to provide an accessible learning environment for all by providing support services and facilitating accommodations, which may vary from course to course. Once registered with DRC, students will receive an accommodation letter that must be presented to the instructor when requesting accommodations. Students should follow this procedure as early as possible in the semester.</li>
                </ul>
                <h3>Multicultural and Diversity Affairs</h3>
                <p><a href="https://multicultural.ufl.edu/">Multicultural and Diversity Affairs</a> (352-294-7850) celebrates and empowers diverse communities and advocates for an inclusive campus.</p>
                <h3>Office of Student Veteran Services</h3>
                <p><a href="http://veterans.ufl.edu/">Office of Student Veteran Services</a> (352-294-2948 | <a href="mailto:vacounselor@ufl.edu">vacounselor@ufl.edu</a>) assists student military veterans with access to benefits.</p>
                <h3>ONE.UF</h3>
                <p><a href="https://one.uf.edu/">ONE.UF</a> is the home of all the student self-service applications, including access to:</p>
                <ul>
                  <li><a href="http://www.ufadvising.ufl.edu/">Advising</a></li>
                  <li><a href="http://www.fa.ufl.edu/bursar/">Bursar</a> (352-392-0181)</li>
                  <li><a href="https://www.sfa.ufl.edu/">Financial Aid</a> (352-392-1275)</li>
                  <li><a href="https://registrar.ufl.edu/">Registrar</a> (352-392-1374)</li>
                </ul>
                <h3>Official Sources of Rules and Regulations</h3>
                <p>The official source of rules and regulations for UF students is the <a href="https://catalog.ufl.edu/UGRD/">Undergraduate Catalog</a> and <a href="http://gradcatalog.ufl.edu/">Graduate Catalog</a>. Quick links to other information have also been provided below.</p>
                <ul>
                  <li><a href="https://dso.ufl.edu/resources/student-handbook/">Student Handbook</a></li>
                  <li><a href="https://catalog.ufl.edu/UGRD/student-responsibilities/">Student Responsibilities</a>, including academic honesty and student conduct code</li>
                  <li><a href="https://elearning.ufl.edu/supported-services/">e-Learning Supported Services Policies</a> includes links to relevant policies including Acceptable Use, Privacy, and many more</li>
                  <li><a href="https://accessibility.ufl.edu/">Accessibility</a>, including the Electronic Information Technology Accessibility Policy and ADA Compliance</li>
                  <li><a href="https://it.ufl.edu/policies/student-computing-requirements/">Student Computing Requirements</a>, including minimum and recommended technology requirements and competencies</li>
                </ul>
            </div>
            <!-- /.panel-body -->
        </div>
        <!-- /.panel-collapse -->
    </div>
    <!-- /.panel-default -->
</div>
<!-- /.panel-group -->