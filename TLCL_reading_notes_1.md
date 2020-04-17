---
title: "TLC Introduction and Ch 1-6 Notes"
tags: [reading notes]
sidebar: ctr_sidebar
permalink: TLC_1.html
toc: false
---

# Notes on TLCL Introduction and Ch 1-6

{% include tip.html content=" **Reading vs. Doing**  
When you do the reading for this class, **don't just read!** **Do the commands discussed.** Play with them, break them, try different options, explore, etc. Reading about using the command line or programming without practicing it will not teach you much!" %}

## Introduction

* p. xvii: This is one of my favorite quotes:
  > It's been said that “graphical user interfaces make easy tasks easy, while command line interfaces make difficult tasks possible” and this is still very true today.

  * I hope you will feel the same by the end of this course!
* p. xix: **Prerequisites** Don't worry about this section, we will be using HiPerGator in this course. You do not need to install Linux on your own computer.

## Ch. 1: What is the Shell?

Most of this text is written assuming you are running Linux on your computer. While that is certainly possible, for the most part, we will be connecting to a Linux server rather than using your own computer. I do this for a number of reasons:

* Using HiPerGator makes it so that everyone's environment is the same. I don't have to troubleshoot why something isn't working on your computer.
* You don't need to install much on your computer. Sometimes, getting software setup is the hardest part of an introductory course and presents such a high barrier to entry that people give up before they start.
* I find that new users are often afraid that they will type something wrong and break their computer. While there are some things covered in the text that you cannot do on the cluster, you also can't really break the cluster.

### Terminal Emulators

We will look at Ch 1 in class and I will demonstrate getting logged into the cluster. In our case, the terminal emulators that we will use depend on the operating system of your computer. On MacOS, you will use Terminal. On Windows, you will use MobaXterm. Or, with any OS, you can use Open on Demand in your web browser.  
These videos also demonstrate the process on:
* [MacOS with the Terminal](https://mediasite.video.ufl.edu/Mediasite/Play/0b238bfffb684fd6b7306129af63a6711d)
* [Windows with MobaXterm](https://mediasite.video.ufl.edu/Mediasite/Play/2bf4c860f19b48a593fb581018b813a11d)
* [Using Open On Demand](https://mediasite.video.ufl.edu/Mediasite/Play/8efcf534ef3c408e9238d8deeeda083a1d)

When using an ssh client, like the Terminal or MobaXterm, the hostname is `hpg.rc.ufl.edu`. Your username is your GatorLink and the password is your GatorLink password.

{% include note.html content="When you type your password, it will seem like the computer is not taking it. Nothing shows up, no *, nothing...This is a security feature common in Linux, and you should just keep typing carefully and hit Enter" %}

### Making Your first Keystrokes

Our shell prompt looks very similar to the one shown here on p. 2: 
```bash
[magitz@login3 ~]$
```
In this case, the shell prompt has my GatorLink username, `magitz`, the @ symbol followed by the hostname, `login3`, and the current working directory, `~`.

* Why `login3`? When you connect to `hpg.rc.ufl.edu`, we run what is called a load balancer that places users on one of several login nodes to balance the load of all the users--one server would not be enough for all of our users. It doesn't matter which you get put on, they are all the same.
* What is the current working directory? When you first log in, you are put in your home directory. Kind of like your Home on MacOS or Windows. On most Linux systems, including HiPerGator, this directory has the path of `/home/<gatorlink>`. Because you frequently want to reference your home directory, there is a shorthand way of doing that with the tilde character: `~`. So, `~` is Linux shorthand for your home directory.

### Mice and Focus

* Again, this box is mostly for people running Linux on their computer. Though the Ctrl-c. Ctrl-v caution does apply for Windows users. On MacOS, Command-c, Command-v typically still work.
* Ctrl-c is the Linux key command to cancel execution of an application. This will be a handy command to know, but doesn't copy text as you may be used to.
* In general, I suggest avoiding using the mouse in the shell.

### The Console Behind the Curtain

* This is specific to those running Linux on their computer and can be ignored.

## Ch 2. Navigation

* p. 8: **Listing the contents of a Directory**: On HiPerGator, your account starts with no files or directories. When you type the `ls` command at the bottom of p. 8, it will not show any files:

   ```bash
   [magitz@login2 ~]$ ls
   [magitz@login2 ~]$ 
   ```

   This is expected.

* p. 12: **Important Facts About Filenames**: 
  * point 3 is worth emphasizing: File extensions generally do not matter in Linux. You don't need to end a file with .txt, .jpg, .pdf, etc. But, these endings can be helpful for *you*. Using extensions consistently can make it easier to remember the contents of a file--is this file an image or text?
  * point 4 is also critical. Do not use spaces in naming files or folders on Linux. In fact, it is a good habit to avoid using spaces on your Windows or MacOS computer if you think the files will end up transferred to Linux or analyzed with a command line tool on your computer.
    * Common conventions are to use underscores (`this_is_a_text_file.txt`) or camel case (`ThisIsATextFile.txt`). It doesn't really matter which you chose, though does help to be consistent.

## Ch. 3: Exploring the System

{% include tip.html content="Since we still don't have any data in our home directory, this section may be easier to follow along with if you change directories to the class share folder. Type the command below:

```bash
[magitz@login2 ~]$ cd /ufrc/bot4452/share
```
" %}

* p. 20: **Table 3-4**: Certainly feel free to explore, but you don't need to worry about all of the directories in this table. Most will be there, but can generally be ignored for what we will be doing.

* p. 23: **Symbolic Links**: Take a look here, we may use some symbolic links, but don't worry too much about the details. Also, a symbolic link is essentially the same as an Alias in MacOS or Shortcut in Windows. It's a small file that points to the real file.

  * I think this is the first time "foo" comes up..."foo" and "bar" are programmers' favorite names to use as examples. They are commonly used as file names, variable names, program names, etc. where the author just needs a name. See [Wikipedia for more on Metasyntactic variables](https://en.wikipedia.org/wiki/Metasyntactic_variable).


## Ch 4: Manipulating Files and Directories

* p. 27: **Wildcards Work in the GUI Too**: You can ignore this box.

{% include warning.html content="p. 33: Be Careful with rm!: As noted, there is no undelete command, trash can or recycle bin on Linux. So be careful!  
Also, nothing is backed up on HiPerGator. We will cover this in class, but keep that in mind.  
In your home directory (`/home/<gatorlink>`) we do have one week of snapshots. We may cover this, but here is more information on [snapshots on HiPerGator](https://help.rc.ufl.edu/doc/Snapshots)." %}

* p. 33-34: **ln – Create Links**: Don't worry too much about the symbolic nad hard link section. We won't be using them a lot.
* p. 37-39: **Creating Hard Links**: Again, you can skip the sections on hard and symbolic links.
* p. 39: **Removing Files and Directories**: Do try removing some of your playground files and directories, but again, don't worry about the link stuff.

## Ch 5: Working with Commands

* p. 44: **which – Display an Executable's Location**: `which cd`: On Red Hat Linux, the distribution of Linux that HiPerGator uses, `which cd` does return the path:  
  ```bash
  [magitz@login2 ~]$ which cd
  /usr/bin/cd
  [magitz@login2 ~]$
  ```
  To see an error similar to the one displayed here, try `which` with some random text:
  ```bash
  [magitz@login2 ~]$ which foo
  /usr/bin/which: no foo in (/opt/slurm/bin:/usr/lib64/qt-3.3/bin:/usr/local/bin:/usr/bin:/usr/local/sbin:/usr/sbin:/bin:/opt/dell/srvadmin/bin:/home/magitz/bin)
  [magitz@login2 ~]$
  ```

{% include tip.html content="p. 46: `man ls`: man pages can often be quite long, you can page through them with the space bar, but to quit out of the view, just type `q`." %}

## Ch 6. Redirection

{% include tip.html content="p. 56: `>` and `>>`: I think it is worth emphasizing that the single redirect, `>`, overwrites the file you are redirecting to. If the file existed, it will be replaced with the new output. There is no recovering the previous information. So, be careful with `>`. And possibly favor the double redirect, `>>`, which appends to the existing file, placing new content at the end of the file." %}

* p. 65: **head / tail – Print First / Last Part of Files**: `tail -f /var/log/messages`: You will not be able to run this command since you do not have permission to view the file /var/log/messages. We will see if we can find a use for the `tail -f` command, in general it is used for watching the contents of an output file while a program is running.
* p. 66: **Linux Is About Imagination**: Another great analogy! I hope this course sparks your imagination about what you can do with the giant erector set of tools you will learn about!
