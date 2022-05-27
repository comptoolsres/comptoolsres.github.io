---
title: "LinkedIn Learning: Learn the Linux Command Line"
tags: [assignments, linux, resources]
sidebar: home_sidebar
permalink: LinkedInLearningLinux.html
toc: false
---

{% include note.html content="LinkedIn Learning has many great tutorials on a variety of subjects, especially tech related. The *Learn the Linux Command Line* course is a good intro. It covers much of the same content that TLCL text does. But it also provides some different tools, different views and more practice. That said, there is not a grade associated with this assignment." %}

## Accessing LinkedIn Learning

From the [e-learning page](https://elearning.ufl.edu/), click the LinkedIn Learning link and login with your GatorLink.

Then either [click on this link](https://www.linkedin.com/learning-login/share?account=41282748&forceAccount=false&redirect=https%3A%2F%2Fwww.linkedin.com%2Flearning%2Flearning-linux-command-line-14447912%3Ftrk%3Dshare_ent_url%26shareId%3DglRlwJrdRL%252BVQRcR0Zi%252BRA%253D%253D), or search for the course Learning the Linux Command Line. This LinkedIn Learning tutorial will go over some basic Linux command line usage.

## A few notes

### Section 1: Setting up your environment

You can skip "Section 1: Setting up your environment", we are working on HiPerGator. One thing that this section does cover is downloading the example files from GitHub. You should do this on HiPerGator. Login to HiPerGator, `cd` to your `/blue/bsc4452/<gatorlink>` directory and clone the github repository:

```bash
flmnh-C02N85F3G:~ magitz$ ssh magitz@hpg.rc.ufl.edu
magitz@hpg.rc.ufl.edu password: 
                        Welcome to UF Research Computing                        
                        ________________________________                        
[...A bunch of stuff nobody reads...]

[magitz@login1 ~]$ cd /blue/bsc4452/magitz/
[magitz@login1 magitz]$  git clone https://github.com/LinkedInLearning/learning-linux-command-line-3005201
Cloning into 'learning-linux-command-line-3005201'...
remote: Enumerating objects: 42, done.
remote: Counting objects: 100% (42/42), done.
remote: Compressing objects: 100% (36/36), done.
remote: Total 42 (delta 8), reused 31 (delta 2), pack-reused 0
Unpacking objects: 100% (42/42), done.
[magitz@login1 magitz]$
```

### Part 3: Files, Folders and Permissions

In Part 3, where the video "Files, folders, and navigation" is navigating to Documents, you will do: `cd /blue/bsc4452/<gatorlink>`

{% include tip.html content="In the same video, the presenter goes into how to use the backslash to escape the space in a folder name. While you *can* do this, it is rally a pain in the neck and I would **HIGHLY** recommend that you just not use spaces in your file or folder names." %}

In part 3, you can skip the "User roles and sudo" video as you won't be able to do those--you do not have permission to change to the root user.

### Part 5: A Peek at Some More Advanced Topics

You do not need to do Part 5.

## Grading

There is nothing to turn in for this. I suggest it as another overview of the tools available.
