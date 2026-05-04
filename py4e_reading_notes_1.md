---
title: "General Python Notes and Py4E Ch 1"
tags: [python]
sidebar: home_sidebar
permalink: py4e_1.html
toc: true
summary: With this section, we transition from using Bash to learning Python. This page covers some preliminary information and getting started in Python.
keywords: python, 
---

{% include note.html content="Page numbers and headings referenced in the Python for Everybody reading notes are for the 1/1/2026 PDF version of the text. Page numbers may differ from print or other versions." %}

Chuck Severance, the author of [Python for Everybody: Exploring Data Using Python 3](https://www.py4e.com/book.php) states in his preface:
> Few of my students were planning to be professional
computer programmers. Instead, they planned to be librarians, managers, lawyers, biologists, economists, etc., who happened to want to skillfully use technology in their chosen field.

As far as I am aware, this also applies to most of my students, which is part of why I like this text.

Further, in Chapter 1, Chuck states:
>This book assumes that *everyone* needs to know how to program, and that once you know how to program you will figure out what you want to do with your newfound skills.

I'm sold! I hope you enjoy this text as much as I do!

## Some notes on Python as we get started

### Python on HiPerGator

On HiPerGator, we install and maintain several version of Python for users. There is a version that comes with the operating system, and that is what is used unless you load a module for the version you want. In general, even if you don't care too much about the version, load a python module, because these are where most user-requested Python modules are added. As an example:

```bash
[magitz@login8 ~]$ which python
/usr/bin/which: no python in (/apps/compilers/gcc/14.2.0/bin:/home/magitz/.opencode/bin:/apps/ufrc/bin:/opt/slurm/bin:/usr/local/bin:/usr/bin:/usr/local/sbin:/usr/sbin:/opt/puppetlabs/bin:/bin:/home/magitz/bin)
[magitz@login8 ~]$ module load python
[magitz@login8 ~]$ which python
/apps/python/3.10/bin/python
[magitz@login8 ~]$
```

### The Shebang line (#!) in scripts

Remember the shebang line for bash scripts?

```bash
#!/usr/bin/bash
```

We need the same thing for Python scripts. Many sources on the internet will tell you to do:

```python
#!/usr/bin/python
```

But that means the script will always be run with `/usr/bin/python` even if that isn't the Python you want or Python isn't installed there.

Instead, use:
```python
#!/usr/bin/env python
```

`/usr/bin/env` is a program that looks in the environment path and runs the first command it finds, `python` in this case.  This is more portable and allows Python to be installed wherever in the user's path.

### Ways to use Python

Maybe even more so than Bash, there are a number of ways to use Python. With Bash, we started by running commands on the command line on HiPerGator and progressed to writing scripts. In addition to an interactive Python prompt and scripts, Python adds Jupyter notebooks and some really nice features in VSCode and other development environments. Which of these you choose to use is largely up to you, your preferences, and the task at hand.

#### Interactive Python Prompt

Python has an interactive command prompt, similar to the Bash command prompt:

```bash
[magitz@login8 ~]$ module load python
[magitz@login8 ~]$ python
Python 3.10.8 | packaged by conda-forge | (main, Nov 22 2022, 08:23:14) [GCC 10.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

And you can start working in Python there. The Py4E text does a lot at the command prompt. Personally, I don't find that terribly useful. Using the Python prompt is quite limiting and generally more frustrating than anything else. I rarely use the Python prompt myself.

#### Python Scripts

As with Bash we can put Python commands in a text file and execute the script:

```bash
[magitz@login8 Examples]$ pwd
/blue/bsc4452/share/Class_Files/Examples
[magitz@login8 Examples]$ cat HelloWorld.py 
#!/usr/bin/env python3

# This is a simple script to print some text

print ("Hello World!!")

[magitz@login8 Examples]$ module load python
[magitz@login8 Examples]$ python HelloWorld.py 
Hello World!!
[magitz@login8 Examples]$ 
```

This is what I do most of the time but requires going back and forth between editing a file and running that file. It does have the advantages of being fairly easy to run on the cluster and requiring little setup.

#### Editing scripts in VSCode

Similar to Bash scripts, Python scripts are plain text files. Any text editor can be used to write Python scripts. But VSCode (and others) have a number of added benefits that are worth checking out. We've already looked at contextual coloring, which VSCode does for many languages, including Bash and Python. This is clearly easier to read and catch errors than plain text.

Good text editors also have code suggestions now mostly powered by LLMs that can even write the code for you!) and function information popups that help you write your code. They have linters to check your syntax and flag errors. And they are configurable for how you want to code.

VSCode can also run your code and help you debug by showing you the values of variables as your code executes step by step. You can see the output in the console.

It does take some extra steps (installing the Remote Tunnels extension from Microsoft and connecting to HiPerGator), but you can even edit and run code on HiPerGator from your local computer!

This is my main tool for development. Whether I develop locally on my own computer or remotely on HiPerGator, for larger projects, I use scripts and notebooks in VSCode.

#### Jupyter Notebooks

{% include tip.html content="For the rest of the semester, I'd generally recommend Jupyter notebooks for most things. This is the easiest way to test things and work on smaller projects." %}

[Jupyter](https://jupyter.org/) is an application that creates documents that have live code, visualizations and descriptive text formatted with markdown (used in most of these pages).

Jupyter can be run on HiPerGator by going to [https://ondemand.rc.ufl.edu/](https://ondemand.rc.ufl.edu/) or [jhub.rc.ufl.edu](https://jhub.rc.ufl.edu/).

{% include note.html content="After this page, most of my Python notes will be in Jupyter notebooks, not Markdown pages as we have seen so far. I will run those notebooks in JupyterHub on the cluster. You can do the same (make a clone of the [repository](https://github.com/comptoolsres/Jupyter_content))." %}

## Ch 1: Why should you learn to write programs?

* p. 3: **1.2 Computer hardware architecture**: This is a nice review things we covered in the [Computers lecture](https://docs.google.com/presentation/d/1lwaPgzs71TuDtuz084PWYocnETpXfMhhJLL-r5UuhSs/edit?usp=sharing).

* p. 4: **Understanding programming**: Like in the Bash section where we talked about [top-down design](TLCL_5.html) and thinking out describing the steps to going to the grocery store, here the author makes the analogy to telling a story.

  Similarly, where the author talks about needing to learn the vocabulary and grammar of a language, we will find that you already know some of the grammar from Bash. Programming languages use similar grammar and vocabulary.

* p. 6: **1.5 Conversing with Python**: We will be using Python on HiPerGator. To get to the Python command prompt, login, load the python module and type python:

    ```bash
    [magitz@login8 ~]$ module load python
    [magitz@login8 ~]$ python
    Python 3.10.8 | packaged by conda-forge | (main, Nov 22 2022, 08:23:14) [GCC 10.4.0] on linux
    Type "help", "copyright", "credits" or "license" for more information.
    >>>
    ```

* p. 8: **1.6 Terminology: Interpreter and compiler**: We briefly talked about [compiling applications in the Linux section](TLCL_7.html). This section goes more into <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.interpreted_language}}">interpreted</a> vs <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.compiled_language}}">compiled</a> programming languages.

* p. 10: **1.7 What is a program**: Similar to the Bash scripts we wrote, Python can be written as a script.

{% include note.html content="p. 11: <b>1.8 What is a program?</b><br><br>There is a copy of all the example code used in the Py4E text located at <code>/blue/bsc4452/share/Class_Files/Py4E_files/code3/</code>." %}

* p. 12: **1.10 What could possibly go wrong?** A lot! As I've said many times, expect errors, expect things to not work. Learning to read and understand Python error messages is a skill! Note that of the three types of errors, Python will only tell you about the Syntax errors. Logic and Semantic errors are harder to find and result in your code not doing what you wanted it to do.

* p. 14: **1.11 Debugging**: In addition to the methods here, we will look in class at using the VSCode debugger as one way to debug code as well as writing test cases to see that you get the expected answer.

* p. 16: **1.14 Exercises**: I usually do not assign the exercises but do encourage you to think about and try some of them. They are a good way to test yourself and build more fluency with the content of the chapters.
