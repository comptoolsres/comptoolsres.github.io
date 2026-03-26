---
title: "Notes on TLCL Introduction and Ch 1-4"
tags: [linux]
sidebar: home_sidebar
permalink: TLCL_1.html
summary: The Linux command line is our gateway to immense computational power. These chapters introduce the shell, navigate the filesystem and manage files.
keywords: shell, ssh, emulator, cd, wildcard, ls, ln, bash
---

{% include note.html content="Page numbers and headings referenced in the *The Linux Command Line* reading notes are based on the 25.12 PDF, Seventh Internet Edition from Jan 5, 2026. This is the latest edition available at the time the course was taught in Fall 2026. Page numbers may differ from print or other versions." %}

{% include tip.html content=" **Reading vs. Doing**  
When you read for this class, **don't just read!** **Do the commands discussed.** Play with them, break them, try different options, explore, etc. Reading about using the command line or programming without practicing it will not teach you much!" %}

## Introduction

* p. xvii: This is one of my favorite quotes:

  > <i class="fa fa-quote-left"></i> It's been said that “graphical user interfaces make easy tasks easy, while command line interfaces make difficult tasks possible” and this is still very true today.

  * I hope you will feel the same way by the end of this course!
* p. xix: **Prerequisites** Don't worry about this section; we will be using Codespaces and HiPerGator in this course. You do not need to install Linux on your own computer.

## Ch. 1: What is the Shell?

Most of the textbook is written assuming you are running Linux on your computer. While that is certainly possible, for the most part, we will connect to a Linux server rather than run directly on your own computer. I do this for a number of reasons:

* Using GitHub Codespaces and HiPerGator makes it so that everyone's environment is the same. I don't have to troubleshoot why something isn't working on your computer.
* You don't need to install much on your computer. Sometimes, getting software setup is the hardest part of an introductory course and presents such a high barrier to entry that people give up before they start.
* I find that new users are often afraid that they will type something wrong and break their computer. While there are some things covered in the text that you cannot do on the cluster, you also can't really break the cluster.

{% include note.html content="Since it takes a bit of time for accounts to be created on HiPerGator, we will start the course using GitHub Codespaces, which provides an online environment where you can work through the exercises. " %}

### GitHub Classroom

As you did with the [GitHub Account exercise](github_account.md), we will use GitHub Classroom for this "assignment. There won't be anything to turn in for this, but the GitHub Classroom assignments make it easy to get everyone a copy of the same repository where they can do their work.

#### Log into GitHub and Accept the Assignment

* Make sure you are logged into your GitHub account.
* [Click this link to accept the GitHub Codespaces assignment](https://classroom.github.com/a/ZSc9WD01) (Fall 2026 link).

#### Open a Codespace within your repository

* Click the green **"<> Code"** button, select the **"Codespaces" tab**, then click the **"Create codespace on main" button.**

   {% include image.html file='github_create_codespace.png' alt="Screenshot of creating a Codespace" position="center" max-width=300 %}

### The Shell and Terminal Emulators

As the TLCL text notes, the shell is the program that takes commands we type on the command line and passes them to the operating system to run. A terminal emulator is a program the provides the screen to type in. We will use several emulators in class, Codespaces and VSCode have one, the SSH client we use to connect to HiPerGator has one, Open on Demand has one, Jupyter Lab has yet another one. The good thing is that these all work about 99% the same. There are some differences that can be annoying...or that make you favor one over the other.

**We will look at Ch 1 in class, and I will demonstrate launching a Codespace and using the terminal within that.**

We will start using GitHub Codespaces and later transition to using HiPerGator. Once we do that, the terminal emulators that we will use depend on the operating system of your computer. On MacOS, you will likely use the Terminal application. On Windows, you can use the Terminal, Bitvise, Git Bash or similar applications. Or, with any OS, you can use [Open on Demand](https://ood.rc.ufl.edu/) in your web browser.  

### Making Your First Keystrokes

The Codespaces shell looks very similar to the one shown on p. 2 of TLCL, but with some differences outlined below.

{% include image.html file='codespaces_command_prompt.png' alt="Labeled screenshot of codespaces command prompt" position="center" %} 

#### Connecting to HiPerGator

{% include note.html content="We won't need this section now, but I'm providing the information for later reference." %}

These videos  demonstrate the process of using different emulators to connect to HiPerGator: 

* [MacOS with the Terminal](https://mediasite.video.ufl.edu/Mediasite/Play/89b780ef71094f568a6c091953445ff31d)
* [Windows with Terminus](https://mediasite.video.ufl.edu/Mediasite/Play/227c2cae1147422c91afff28435a51ac1d)
* [Using Open On Demand](https://mediasite.video.ufl.edu/Mediasite/Play/4654bfa838624de894085bf54678848f1d)

When using an SSH client, like the Terminal or Bitvise, the hostname is `hpg.rc.ufl.edu`. Your username is your GatorLink and the password is your GatorLink password.

{% include note.html content="When you type your password, it will seem like the computer is not taking it. Nothing shows up, no *'s, no •'s, nothing...This is a security feature common in Linux, and you should just keep typing carefully and hit <kbd>Enter</kbd>" %}

### Making Your first Keystrokes

Our shell prompt looks very similar to the one shown here on p. 2:

```bash
@mgitz ➜ /workspaces/codespaces-assignment-mgitz (main) $
```

#### A note on the shell prompt on HiPerGator

When we get to HiPerGator, your shell prompt will look like:

```bash
[magitz@login7 ~]$
```

In this case, the shell prompt has my GatorLink username, `magitz`, the @ symbol followed by the hostname, `login7`, and the current working directory, `~`.

* Why `login7`? When you connect to `hpg.rc.ufl.edu`, we run what is called a <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.load_balancer}}">load balancer</a> that places users on one of several login nodes to balance the load of all the users--one server would not be enough for all of our users. It doesn't matter which you get put on, they are all the same.
* What is the current working directory? When you first log in, you are put in your home directory. Kind of like your Home on MacOS or Windows. On most Linux systems, including HiPerGator, this directory has the path of `/home/<gatorlink>`. Because you frequently want to reference your home directory, there is a shorthand way of doing that with the tilde character: `~`. So, `~` is Linux shorthand for your home directory.

### Mice and Focus

* Again, this box is mostly for people running Linux on their computer. Though the <kbd>Ctrl</kbd>-<kbd>C</kbd>. <kbd>Ctrl</kbd>-<kbd>V</kbd> caution does apply for Windows users. On MacOS, <kbd>Command</kbd>-<kbd>C</kbd>, <kbd>COmmmad</kbd>-<kbd>V</kbd> typically still work.
* <kbd>Ctrl</kbd>-<kbd>C</kbd> is the Linux key command to cancel execution of an application. This will be a handy command to know, but doesn't copy text as you may be used to.
* In general, I suggest avoiding using the mouse in the shell.

### The Console Behind the Curtain

* This is specific to those running Linux on their computer and can be ignored.

## Ch 2. Navigation

* p. 8: **Listing the contents of a Directory**:

    * On Codespaces, when you first launch, you should seem something like this:
        ```bash
        @test ➜ /workspaces/codespaces-access-test (main) $ ls
        LICENSE  README.md  data
        @gest ➜ /workspaces/codespaces-access-test (main) $
        ```

    * On HiPerGator, your account starts with no files or directories. When you type the `ls` command at the bottom of p. 8, it will not show any files:

        ```bash
        [magitz@login2 ~]$ ls
        [magitz@login2 ~]$ 
        ```

        This is expected.

* p. 11-12: **Important Facts About Filenames**
  * point 3 is worth emphasizing: File extensions generally do not matter in Linux. You don't need to end a file with .txt, .jpg, .pdf, etc. But, these endings can be helpful for *you*. Using extensions consistently can make it easier to remember the contents of a file--is this file an image or text?
  * point 4 is also critical: Do not use spaces in naming files or folders on Linux. In fact, it is a good habit to avoid using spaces on your Windows or MacOS computer if you think the files will end up transferred to Linux or analyzed with a command line tool on your computer.
    * Common conventions are to use underscores (`this_is_a_text_file.txt`) or camel case (`ThisIsATextFile.txt`). It doesn't really matter which you chose, though does help to be consistent.

## Ch. 3: Exploring the System

* p. 20: **Table 3-4**: Certainly feel free to explore, but you don't need to worry about all of the directories in this table. Most will be there, but can generally be ignored for what we will be doing.

* p. 23: **Symbolic Links**: Take a look here, we may use some symbolic links, but don't worry too much about the details. Also, a symbolic link is essentially the same as an Alias in MacOS or Shortcut in Windows. It's a small file that points to the real file.

  * I think this is the first time "foo" comes up..."foo" and "bar" are programmers' favorite names to use as examples. They are commonly used as file names, variable names, program names, etc. where the author just needs a name. See [Wikipedia for more on Metasyntactic variables](https://en.wikipedia.org/wiki/Metasyntactic_variable).

## Ch 4: Manipulating Files and Directories

* p. 29: **Wildcards Work in the GUI Too**: You can ignore this box.

{% include warning.html content="p. 34: **Be Careful with the `rm` command!** As noted, there is no undelete command, trash can, or recycle bin on Linux. So be careful!  
<br>
Also, nothing is backed up on HiPerGator.
<br><br>
In your home directory (`/home/<gatorlink>`) we do have one week of snapshots. We may cover this, but here is more information on [snapshots on HiPerGator](https://docs.rc.ufl.edu/data_transfer/snapshots/)." %}

* p. 34-35: **ln – Create Links**: Don't worry too much about the symbolic and hard link section. We won't be using them a lot.
* p. 38-40: **Creating Hard Links**: Again, you can skip the sections on hard and symbolic links.
* p. 41: **Removing Files and Directories**: Do try removing some of your playground files and directories, but again, don't worry about the link stuff.
