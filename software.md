---
title: "Computer and Software Setup"
keywords: setup
tags: [resources, assignments, linux]
sidebar: home_sidebar
permalink: software.html
summary: Computer and software needed for the course.
toc: false
---

<ul id="VideoTabs" class="nav nav-tabs">
    <li class="active"><a href="#Stream" data-toggle="tab">MS Stream (UF account needed)</a></li>
    <li><a href="#Dropbox" data-toggle="tab">Dropbox (No account, offers picture-in-picture, but no captions or search)</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="Stream">
        <iframe width="853" height="480" src="https://web.microsoftstream.com/embed/video/62e0ddf6-6c46-46db-a480-1183d5d35e81?autoplay=false&amp;showinfo=true" allowfullscreen style="border:none;"></iframe>
    </div>
    <div role="tabpanel" class="tab-pane" id="Dropbox">
        <video width="800"  controls>
          <source src="https://www.dropbox.com/s/zb8h5tu67way9fa/Software_Setup.mp4?dl=1" type="video/mp4" />
        </video> 
    </div>
</div>

## Computer requirements

To complete this course, you will need a computer. It does not have to be anything fancy or have any particular operating system.

For students enrolled in the course at UF, you will do most of your work on the universities computer cluster, HiPerGator. An account will be created for you and we will walk through everything in class, so don't worry. There are still some applications that will make it easier to work as noted below.

### For people not enrolled in the course

If you are working through this course outside of a formal class, the content is freely available on this site and the main thing you need is a Linux environment and Python. Both of these are already present on a Mac and you are set. For Windows users, I recommend installing the Ubuntu Windows Subsystem for Linux (free from the Microsoft App Store) and Anaconda for Python 3.7 or later (free from [https://www.anaconda.com/](https://www.anaconda.com/)). The main thing not available through the website are quizzes.

## Software

Everything we do in class, *could* be done with UF Research Computing's Open on Demand environment, which is accessible from your web browser at: [https://ood.rc.ufl.edu/](https://ood.rc.ufl.edu/)

{% include note.html content="Open on Demand is only accessible while on the UF network. Please see this page for details and additional Open on Demand help: [https://help.rc.ufl.edu/doc/Open_OnDemand](https://help.rc.ufl.edu/doc/Open_OnDemand)" %}

That said, I personally find some of the software noted below more reliable and feature rich.

### <i class="fa fa-windows fa-3x"></i> If you have a Windows Computer

1. An ssh client to connect to remote servers, like HiPerGator
   1. As part of the course, you will learn to use `git`. While you do not need to install `git` on your computer, it may be helpful. If you do install `git`, there is a program called `Git Bash` that can serve as your ssh client. **You can download and install `git` from here: [https://git-scm.com/ <i class="fa fa-git-square fa-2x"></i>](https://git-scm.com/)**
   1. [BitVise](https://www.bitvise.com/) is another ssh client that works well. It also has an SFTP client and one nice feature is that once you authenticate, you can login multiple times without having to re-authenticate.
1. A text editor:
   1. **Microsoft [VS Code](https://code.visualstudio.com/)**: This is what I use. It has many extensions that are quite helpful. It is also free.

### <i class="fa fa-apple fa-3x"></i> If you have an Apple Computer

1. You already have the ssh client: Terminal is installed at `/Applications/Utilities/Terminal` (The Applications folder, then Utilities, and the application called Terminal).
1. A text editor:
   1. Microsoft [VS Code](https://code.visualstudio.com/): Is what I use. It has many extensions that are quite helpful. It is also free.
   1. BBEdit is a longtime favorite. It is available in the Apple App Store or [here](http://www.barebones.com/products/bbedit/). The free version is fine for what we will do in class, you do not need to purchase the paid version.
1. You may also want to install `git` on your computer, but it is not required. If you want to install it, download from here: [https://git-scm.com/ <i class="fa fa-git-square fa-2x"></i>](https://git-scm.com/) . On a Mac, I suggest using the **Binary Installer** as the easiest method to get started.
