---
title: "Computational Tools for Research in Biology"
keywords: syllabus
tags: 
sidebar: home_sidebar
permalink: index.html
summary: An introduction to computational tools for research-- Linux command line, HPC, Bash scripting, Python and SQL
toc: false
---

## Course Description

{% include image.html file='comptools.png' alt="Image of servers and tool icons" position="right" %}

Information technology has dramatically transformed how research across many disciplines is conducted. This is particularly true in the biological sciences where researchers frequently find themselves faced with massive amounts of diverse data to analyze. As data types and volumes continue to grow, knowledge of scripting, database management, and advanced computing skills are critical for researchers.

Topics covered in the course will address a gap in how research has advanced—*and become increasingly computational*— while student training in the use of computational tools has lagged.

**The course assumes no prior coding or command line skills**, and covers concepts that will provide the ability for students to apply new technologies to a wide array of research questions. A foundation in data management and analysis concepts opens doors for well-trained scientists and allows them to work in multidisciplinary research.

This course will survey areas where high performance computing, large-scale data access and integration, informatics tools and software, and multi-disciplinary collaboration have had high impact on research as a foundation for computationally-enabled research.

{% include note.html content="While the title of the course includes 'in Biology' there is little that is actually focussed on biology. This course strives to be broadly applicable to many areas of research. Bureaucracies being what they are, the title is what it is..." %}

## Course Organization

The course is divided into three main sections:

* Section 1
  * Linux command line
  * Bash scripting
  * Version control
  * Using high-performance computing resources

* Section 2
  * Python scripting

* Section 3
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

### Synchronous Meetings: Mon, Wed, Fri 8:30am - 9:20am

{% include image.html file='lecture.png' alt="lecture icon" position="right" max-width=75 %}

* I will be online and presenting material and/or helping students: **Mon, Wed, Fri 8:30am - 9:20am)**
  {% include important.html content="You should make every effort to attend these sessions. While I will post most lectures ahead of time and will record these session, **this is the best opportunity to ask questions and get help from me and others in the class.**" %}
* I understand that with all that is going on, some students will need to miss classes sometimes. That is fine and I will do my best to help you catch up, but regular attendance is the best way to learn.

### Asynchronous Work

* Students will work on projects either independently or in small, virtual groups.
* This work can be more flexible in timing and will give you and your classmates times to get more hands-on experience and challenge yourselves to learn on your own.

### Office Hours

{% include image.html file='office_hours.png' alt="Office Hours icon" position="right" max-width=75 %}

* Tuesdays from 11:00am to noon
* Thursdays from 2:00pm to 3:00pm
* By Appointment--please <a href="mailto:magitz@ufl.edu?subject=Comp%20Tools%20Res%20office%20hours%20request">Email me</a> to setup a different time if needed.

 {% include tip.html content="Coding is not always easy. Simple solutions are not always obvious. There will be some frustration. **I expect that you will need help. You should expect that you will need help.** I want to help you! I cannot always help if you do not ask for the help you need. Please ask for help." %}

## Course Textbooks

{% include image.html file='textbook.png' alt="textbook icon" position="right" max-width=75 %}
The main texts for the course are:

* The Linux Command Line: [http://linuxcommand.org](http://linuxcommand.org) (my notes and referenced page numbers will be based on the 19.01A PDF, Fifth internet edition from Jan 28, 2019)
* Python For Everyone: [https://www.py4e.com/book.php](https://www.py4e.com/book.php)

Each of these is available as a free PDF download or for purchase in print.

{% include tip.html content="Also check out the [additional resources page](resources.md)." %}

## Course Calendar

{% include image.html file='calendar.png' alt="calendar icon" position="right" max-width=75 %}

{% include important.html content="This is subject to change, please check back frequently." %}

For readings, there may be links to pages with my notes and additional explanations on the content from the texts. The texts are abbreviated as TLCL = [The Linux Command Line](http://linuxcommand.org); Py4E = [Python for Everyone](https://www.py4e.com/book.php).

Week | Date | Reading/Assignment |Topic |
-----|------|--------------------|------|
[1](Week_01.html) | Mon, Aug 31 | [Download Software](software.md)|[Introduction and course objectives](https://comptoolsres.github.io/slides/Lect_01_Intro.html)
[1](Week_01.html) | Wed, Sept 2| [Read TLCL Introduction & Ch 1-4](TLCL_reading_notes_1.md) <br> [Watch UFRC Training Video](https://training.it.ufl.edu/training/items/orientation-materials-for-courses-using-rc.html) |Getting started: [Computers](https://comptoolsres.github.io/slides/Lect_02_Computers.html)<br> UF Research Computing Intro & getting started
[1](Week_01.html) | Fri, Sept 4 | [Read TLCL Ch 5-8](TLCL_reading_notes_2.md)<br>Quiz 1, due {{site.quiz_1_due}}| Continue building shell skills<br>[Here are some exercises to work on](https://forms.gle/fZSskLMgw2exxfq47)
|||
[2](Week_02.html) | Mon, Sept 7 | Labor Day, no class |
[2](Week_02.html) | Wed, Sept 9 | [Read Notes on Regular Expressions and TLCL Ch 19](TLCL_reading_notes_3.md)<br>Problem Set 1, due {{site.ps_1_due}}| [<i class="fa fa-file"></i> Regular Expressions Handout](pdf/Regular_Expressions_Cheat_Sheet.pdf)
[2](Week_02.html) | Fri, Sept 11 |**Quiz 1 due**<br>**[GitHub Account assignment due](github_account.md)**<br>[Read TLCL Ch 20](TLCL_reading_notes_3.5.md)| Text manipulation
|||
[3](Week_03.html) | Mon, Sept 14 | Quiz 2, due {{site.quiz_2_due}}<br>[Watch Learn the Linux Command Line](LinkedInLearningLinux.md)<br> [Register for github.com account](github_account.md) <br>[Read TLCL Ch 24-26](TLCL_reading_notes_4.md)| Shell Scripts and version control with git and GitHub
[3](Week_03.html) | Wed, Sept 16 || Continue working on shell scripts and git/github
[3](Week_03.html) | Fri, Sept 18 |**Problem Set 1 due** <br> [Read TLCL Ch 27, 29 & 33](TLCL_reading_notes_5.md) |Flow control: `if`, `while`, `until`, `for` etc. 
|||
[4](Week_04.html) | Mon, Sept 21 | Problem Set 2, due {{site.ps_2_due}} |Google and Documentation 
[4](Week_04.html) | Wed, Sept 23 | | Using UF Research Computing resources<br>Running batch jobs
[4](Week_04.html) | Fri, Sept 25 | **Quiz 2 due** <br> [Read TLCL Ch 23](TLCL_reading_notes_6.md) | Compiling source code<br>More bash scripting
|||
[5](Week_05.html) | Mon, Sept 28 | Quiz 3, due {{site.quiz_3_due}}<br>[Read Py4E Ch 1](py4e_reading_notes_1.md) |Introduction to Python
[5](Week_05.html)  | Wed, Sept 30 | [Read Py4E Ch 2](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch2_varaibles_and_types.ipynb)| Python data types
[5](Week_05.html)  | Fri, Oct 2 | **Problem Set 2 due** <BR>[Read Py4E Ch 3](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch3_flow_control.ipynb) | Python: Flow Control
|||
[6](Week_06.html) | Mon, Oct 5 | Problem Set 3, due {{site.ps_3_due}}<br>[Read Py4E Ch 4](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch4_functions.ipynb)| Python: Functions
[6](Week_06.html) | Wed, Oct 7 | [Read Py4E Ch 5](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch5_iteration.ipynb) | Python: Iteration
[6](Week_06.html) | Fri, Oct 9 | **Quiz 3 due** <br> [Read Py4E Ch 6](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch6_strings.ipynb) & [Ch 7](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch7_file_io.ipynb) | Python: try/except, Strings, File I/O
|||
[7](Week_07.html) | Mon, Oct 12 | Quiz 4, due {{site.quiz_4_due}}<br>[Read Py4E Ch 8](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch8_lists.ipynb), and [Chs 9-10](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch9-10_dictionaries_tuples.ipynb) | Lists, Dictionaries, Tuples
[7](Week_07.html) | Wed, Oct 14 | [Read Ch 11](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch11_regex.ipynb) | RegEx in Python
[7](Week_07.html) | Fri, Oct 16 | **Problem Set 3 due**<br> [Read Py4E Ch 12](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch12_networked.ipynb) & [Ch 13](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch13_web_services.ipynb) | Scripting data acquisition
|||
[8](Week_08.html) | Mon, Oct 19 |Problem Set 4, due {{site.ps_4_due}}<br>[SciPy, NumPy, Pandas](https://github.com/comptoolsres/Jupyter_content/blob/main/NumPy_SciPy_Pandas.ipynb)| SciPy, NumPy, Pandas
[8](Week_08.html) | Wed, Oct 21 | | Using modules
[8](Week_08.html) | Fri, Oct 23 | **Quiz 4 due**<br>[Matplotlib and data visualization](https://github.com/comptoolsres/Jupyter_content/blob/main/Data_visualization.ipynb) | Visualization|||
|||
[9](Week_09.html) | Mon, Oct 26 |Quiz 5, due {{site.quiz_5_due}}| More data visualization
[9](Week_09.html)  | Wed, Oct 28 | Scan Py4E Ch 16 <BR> Py4E Ch 14: Object oriented Programming <br> Project 1, Due {{site.project_1_due}}| Work on Project 1
[9](Week_09.html)  | Fri, Oct 30 | **Problem Set 4 Due** | Work on Project 1
|||
[10](Week_10.html) | Mon, Nov 2 | Problem set 5, due {{site.ps_5_due}}<br>[Programming Foundations Databases](LinkedInLearningDatabases.md)| Database intro
[10](Week_10.html) | Wed, Nov 4 | |Database intro
[10](Week_10.html) | Fri, Nov 6 | **Project 1 Due**<br>[Read Py4E Ch. 15, through 15.5 and my notes](https://github.com/comptoolsres/Jupyter_content/blob/main/py4e_ch15_databases.ipynb) |Overview of databases<br>Database design
|||
[11](Week_11.html) | Mon, Nov 9 | | [Databases, SQL and sqlite](SQL_Introduction.md)
[11](Week_11.html) | Wed, Nov 11 | Veteran's Day, no class |
[11](Week_11.html) | Fri, Nov 13 | **Quiz 5 due**| [SQLAlchemy](https://github.com/comptoolsres/Jupyter_content/blob/main/SQLAlchemy.ipynb)|
|||
[12](Week_12.html) | Mon, Nov 16 | Quiz 6, due {{site.quiz_6_due}} | More SQLAlchemy
[12](Week_12.html) | Wed, Nov 18 | Project 2, Due Wed, Dec 9| SQLAlchemy and Pandas
[12](Week_12.html) | Fri, Nov 20 | **Problem Set 5 due** | Argparse
|||
[13](Week_13.html) | Mon, Nov 23 | | Work on project 2
[13](Week_13.html) | Wed, Nov 25 | Thanksgiving, no class |
[13](Week_13.html) | Fri, Nov 27 | Thanksgiving, no class |
|||
[14](Week_14.html) | Mon, Nov 30 | | More on functions
[14](Week_14.html) | Wed, Dec 2 | | TBD
[14](Week_14.html) | Fri, Dec 4 | **Quiz 6 due** | Project 2
|||
[15](Week_15.html) | Mon, Dec 7 | | Graphics-[Download PDF of slides](pdf/Graphics_lect.pdf)
[15](Week_15.html) | Wed, Dec 9 | **Project 2 due** <BR> Last day of class | Finish Project 2

## Software and Hardware

Participants will need a computer with internet connection, webcam and microphone for all classes.

Several free/open source software packages will be used throughout the course, and students will be required to install some of these.
Students will be required to apply for a (free) Research Computing account to access HiPerGator for coursework.
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

In general, I do not take attendance. You are all adults and I assume you are taking the class the learn. The best way to learn is to regularly attend class. I am sure students will miss class for various reasons. I am happy to help you catch up. If you regularly miss class and fall behind, I may ask that you hold questions on content you have missed until after class, ask that you coordinate a time to go over the content. I will make every effort to record and post all classes to help those that miss classes.

### Quiz and Assignment Policy

Quiz and assignment dates will be announced at least one week in advance and students will have at least three days to complete the quiz or assignment. Each quiz or assignment will clearly state if it is an individual or group assignment.  Individual assignments must be the student’s own work, completed without the assistance of others.

All quizzes and assignments are "open book, open internet", you may use whatever resources you desire to complete the quiz/assignment. Though only assignments specifically noted as group assignments should be worked on with other people.

### Makeup and Late policy

Please notify the instructor of circumstances that lead to late work or missed classes. I will generally work with you and accept late work. Without prior notification, late work will be penalized one point per day after the due date.

## Students Requiring Accommodations

Students with disabilities requesting accommodations should first register with the Disability Resource Center (352-392-8565, [https://disability.ufl.edu/students/get-started/](https://disability.ufl.edu/students/get-started/)) by providing appropriate documentation. Once registered, students will receive an accommodation letter which must be presented to the instructor when requesting accommodation. Students with disabilities should follow this procedure as early as possible in the semester.

## Course Evaluation

Students are expected to provide professional and respectful feedback on the quality of instruction in this course by completing course evaluations online via GatorEvals. Guidance on how to give feedback in a professional and respectful manner is available at [gatorevals.aa.ufl.edu/students/](https://gatorevals.aa.ufl.edu/students/). Students will be notified when the evaluation period opens, and can complete evaluations through the email they receive from GatorEvals, in their Canvas course menu under GatorEvals, or via [ufl.bluera.com/ufl/](https://ufl.bluera.com/ufl/). Summaries of course evaluation results are available to students at [gatorevals.aa.ufl.edu/public-results/](https://gatorevals.aa.ufl.edu/public-results/).

## Class Demeanor and Netiquette

Students are expected to join class Zoom meeting on time and behave in a manner that is respectful to the instructor and to fellow students. If at all possible, please have your video on during class--it is easier for me to teach and for discussion if we can see you! Please do be aware of your surroundings and ensure that content visible on your video, or shared via screen sharing, is appropriate for class.

Opinions held by other students should be respected in discussion, and conversations that do not contribute to the discussion should be held at minimum, if at all.

Please use the "Raise Hand" feature of Zoom to ask a question.

Students should be working on course content during class.

### Discussion Boards and Slack Channel

The Canvas discussion boards and Slack can be used to ask for and provide help by all. Students should be supportive and considerate of others at all times. Rude or inappropriate comments will be removed and the poster will be warned.

## University Honesty Policy

UF students are bound by The Honor Pledge which states:
>We, the members of the University of Florida community, pledge to hold ourselves and our peers to the highest standards of honor and integrity by abiding by the Honor Code. On all work submitted for credit by students at the University of Florida, the following pledge is either required or implied: “On my honor, I have neither given nor received unauthorized aid in doing this assignment.”

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