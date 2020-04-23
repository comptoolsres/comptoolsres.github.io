---
title: "LinkedIn Learning Linux"
tags: [video notes]
sidebar: home_sidebar
permalink: LinkedInLearningLinux.html
toc: false
---

# LinkedIn Learning: Learn the Linux Command Line

From the [e-learning page](https://elearning.ufl.edu/), click the LinkedIn Learning link and login with your GatorLink.

Then either [click on this link](https://www.linkedin.com/learning/learning-linux-command-line-2/learning-linux-command-line?u=41282748), or search for the course Learn the Linux Command Line. This LinkedIn Learning tutorial will go over some basic Linux command line usage.

## Grading

This assignment will count as **quiz 1**. To get credit, paste your command line for the solution to the challenge at the end of part 4 (Challenge: Extract information from a text file) into the box in the **Canvas assignment for Quiz 1** and submit.

The log file for this is in the Exercise Files folder and is called log.tar.gz.

{% include tip.html content="There is a solution video where you can get the answer. Two things about that...

<br><br>

1. Think for a bit about how you might approach the question. Don't spend more than a few minutes on this. If you have an idea, play for a bit and see if you can string together some commands to get what you want.
<br><br>
2. The video doesn't really give you enough information to answer this challenge. My suggestion is after thinking for a couple of minutes, watch the Solution video and try to understand what the author did. Use the commands that he walks you through and get the answer he gets. Then submit the command line..." %} 

## A few notes

### Section 1: Setting up your environment

You can skip "Section 1: Setting up your environment", we working on HiPerGator. One thing that this section does cover is downloading the example files from github. We will do this on HiPerGator. Login to HiPerGator, cd to your `/ufrc/bsc4452/<gatorlink>` directory and clone the github repository:

```bash
flmnh-C02N85F3G:~ magitz$ ssh magitz@hpg.rc.ufl.edu
magitz@hpg.rc.ufl.edu password: 
                        Welcome to UF Research Computing                        
                        ________________________________                        
[...A bunch of stuff nobody reads...]

[magitz@login1 ~]$ cd /ufrc/bsc4452/magitz/
[magitz@login1 magitz]$ git clone git://github.com/scottsimpson/commandlinebasics
Cloning into 'commandlinebasics'...
remote: Counting objects: 53, done.
remote: Total 53 (delta 0), reused 0 (delta 0), pack-reused 53
Receiving objects: 100% (53/53), 109.85 KiB | 0 bytes/s, done.
Resolving deltas: 100% (9/9), done.
[magitz@login1 magitz]$
```

### Part 3: Files, Folders and Permissions

In Part 3, where the video "Files, folders, and navigation" is navigating to Documents, you will do: `cd /ufrc/bsc4452/<gatorlink>`
 
{% include tip.html content="In the same video, the presenter goes into how to use the backslash to escape the space in a folder name. While you can do this, it is rally a pain in the neck and I would **HIGHLY** recommend that you just not use spaces in your file or folder names." %}

In part 3, you can skip the "User roles and sudo" video as you won't be able to do those--you do not have permission to change to the root user.

### Part 5: A Peek at Some More Advanced Topics

You do not need to do Part 5.