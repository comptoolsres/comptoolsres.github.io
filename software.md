---
title: "Computer and Software Setup"
keywords: setup
tags: [resources, assignments, linux]
sidebar: home_sidebar
permalink: software.html
summary: Computer and software needed for the course.
toc: false
---

## Computer requirements

To complete this course, you will need a computer. It does not have to be anything fancy or have any particular operating system.

For students enrolled in the course at UF, you will do most of your work on the universities computer cluster, HiPerGator. An account will be created for you and we will walk through everything in class, so don't worry. There are still some applications that will make it easier to work as noted below.

You will need a reliable internet connection for the course. During Summer 2020, all course meetings will be on Zoom, so you should have a webcam and microphone. Your internet service should support video conferencing.

### For people not enrolled in the course

If you are working through this course outside of a formal class, most of the content is freely available on this site and the main thing you need is a Linux environment and Python. Both of these are already present on a Mac and you are set. For Windows users, I recommend installing the Ubuntu Windows Subsystem for Linux (free from the Microsoft App Store) and Anaconda for Python 3.7 or later (free from [https://www.anaconda.com/](https://www.anaconda.com/)).

## Software

Everything we do in class, *could* be done with UF Research Computing's Open on Demand environment, which is accessible from your web browser at: [https://ood.rc.ufl.edu/](https://ood.rc.ufl.edu/)

{% include note.html content="Open on Demand is only accessible while on the UF network. Please see this page for details and additional Open on Demand help: [https://help.rc.ufl.edu/doc/Open_OnDemand](https://help.rc.ufl.edu/doc/Open_OnDemand)" %}

That said, I personally find some of the software noted below more reliable and feature rich.


### ![Windows logo](images/widows.icon_75.png) If you have a Windows Computer

1. An ssh client to connect to remote servers, like HiPerGator
   1. As part of the course, you will learn to use `git`. While you do not need to install `git` on your computer, it may be helpful. If you do install `git`, there is a program called `Git Bash` that can serve as your ssh client. You can download and install `git` from here: [https://git-scm.com/](https://git-scm.com/)
   1. I recommend MobaXterm: Use the free [Home Edition Installer](https://mobaxterm.mobatek.net/download-home-edition.html)
   ![Screenshot of MobaXterm download page indicating preference for Installer edition over Portable edition](images/mobaxterm.png)
1. A text editor:
   1. MobaXterm has a text editor built in, which is fine.
   1. Microsoft [VS Code](https://code.visualstudio.com/): This is what I use. It has many extensions that are quite helpful. It is also free.

### ![Apple logo](images/apple_logo_75.jpg) If you have an Apple Computer

1. You already have the ssh client: Terminal is installed at /Applications/Utilities/Terminal (The Applications folder, then Utilities, and the applciation called Terminal).
1. A text editor:
   1. Microsoft [VS Code](https://code.visualstudio.com/): Is what I use. It has many extensions that are quite helpful. It is also free.
   1. BBEdit is a longtime favorite. It is available in the Apple App Store or [here](http://www.barebones.com/products/bbedit/). The free version is fine for what we will do in class, you do not need to purchase the paid version.
1. You may also want to install `git` on your computer, but it is not required. If you want to install it, download from here:  [https://git-scm.com/](https://git-scm.com/).
