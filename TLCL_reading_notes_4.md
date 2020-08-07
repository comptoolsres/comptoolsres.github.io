---
title: "Notes on TLCL Ch 24 - 26"
tags: [linux]
sidebar: home_sidebar
permalink: TLCL_4.html
toc: false
---

{% include note.html content="Again, we are going to skip some chapters. As always, there's good content in these, but not enough time to cover everything." %}

## Confronting histories of racism and oppression

In 2020, America once again turned its focus to the long, unbroken history of systemic racism and oppression of Black, Indigenous and People of Color (BIPOC, see <www.thebipocproject.org>). The facts of systemic racism have, unfortunately, changed little in centuries. The situation merely became so bad that more of the country paid attention for some time.

Science and technology fields have, in many cases, actively excluded BIPOC and women. It will remain to be seen if the conversations, commitments, and promises of action turn into true, lasting change to improve inclusion of historically marginalized groups.

{% include image.html file='black-lives-matter-5329164_640.png' alt="Black Lives Matter logo" position="right" max-width=250 %} It is my hope that all feel welcome in this class and that we build up and cherish the strengths of all, regardless of race, ethnicity, gender identity, sexuality, socioeconomic status, religion, nationality, neurodiversity, or physical disability. I stand against violence and in solidarity with the Black Lives Matter movement.

### Why is this in a coding class?

It should probably have been there from the first day of class. It is my hope that all have felt included and supported so far. We have immersed ourselves in the tools of Linux and the command line: tools that have been developed by and for a largely white, male community. A community that has a long history of sexist, racist actions.

Progress is slow, but I am encouraged by groups such as [Women who code](https://www.womenwhocode.com/_), [BlacksInTech](https://www.blacksintechnology.net/), and [/dev/Color](https://www.devcolor.org/). We must do better.

One action, small as it is, that we *can* take is to change the terms we use when they do harm to others.

### Small changes to reduce harm

In this section, we are starting to work with git and [GitHub](https://github.com). The historical, and as of August 6, 2020, default name for the main branch of a git repository is `master`. Similarly, the terms "master" and "slave" are frequently used in computer programming and hardware for controlling and subordinate processes/devices, respectively. **This terminology is offensive and unnecessary**. Importantly, it is easy to make changes in order to create a more inclusive community, and, I believe, we must do so.

There has been much discussion on the topic in the tech community. It is clear that "'master'...brings the idea of human bondage and suffering to mind for a non-trivial number of people" ([Brian Carlson](https://lore.kernel.org/git/20200505231641.GH6530@camp.crustytoothpaste.net/)). As such, many organizations, such as the [Software Freedom Conservancy](https://sfconservancy.org/news/2020/jun/23/gitbranchname/) and [GitHub](https://github.com/github/renaming) have pledge to work to change the convention to instead use the name `main` for the main branch of a repository.

**We are still in the process.** In fact, my first attempts to transition this site failed as GitHub only allowed websites to be based on the master branch. That changed on July 31, 2020 and this site was transitioned to use the main branch on August 6, 2020, when I learned of GitHub's new feature. Incidentally, the transition took about 5-minutes--it is truly a small change that I hope causes a little less harm.

### Configuring the default branch name in git

When creating a repository however, GitHub and git still set the default branch to "master". The July 27, 2020 release of git 2.28 adds a configuration option to change the name of the default branch:

`git config --global init.defaultBranch main`

I suggest you run this on your computer now. Unfortunately, HiPerGator still has older versions, so we cannot change the default there.

### Configure the default branch name in GitHub

[This GitHub page](https://github.com/github/renaming) tracks their plans on renaming the default branch. As of August 6, 2020, GitHub proposes adding a configuration option to allow you to change the name of the default branch "this summer". It is not, however currently available. Will it be available by Sept 14 when you are scheduled to read this page? I don't know...Hopefully!

## Getting setup in github.com

One thing that TLCL doesn't include that I think is critical for good coding is the use of version control, like git. We [already created a github.com account](github_account.md) and created a repository through the github classroom.

As we embark on writing shell scripts, we will continue to use git and github. To get things setup, let's create your first repository from scratch.

### Create the repository on GitHub

1. Log into your github.com account.
1. There are two ways to create a new repository. Either click the +-icon on the top right and select "New repository", or click the green "New" button on the left.
  ![Screenshot of methods of creating a new repository in github.com](images/git_new_repo.png)
1. For the Repository name, enter "hello_world" (you can use whatever name, but do not use a space!). If you want, you can add a description.
  ![Screenshot of creating a new repository in github.com](images/git_hello_world_new_repo.png)
1. **Check the "Initialize this repository with a README" checkbox** and click the green "Create repository" button.
1. That will create your repository and setup a template markdown file for the README.md--every repository should have a README.md file that describes the contents of the repository.
  ![Screenshot of a newly created repository in github.com](images/git_fresh_repo_master.png)
1. Let's change the name of the main branch to `main`. Click the branch button that currently says master, type "main" in the box and hit Enter or click "Create branch main from master".
 ![Screenshot of creating the new main branch](images/git_new_branch.png)
1. Now we have two branches, main and master, but master is still the default. Click on the Branches button again and click on the the "View all branches" link at the bottom of the dropdown.
1. Click the "Change default branch" button.
 ![Screenshot of the change default branch button](images/git_change_default_branch.png)
1. This will take you to the Branches portion of the Settings page. Click on the master and select the main branch and click Update. On the window that pops up, click that "I understand, update the default branch."
1. Click either the "<>Code" tab or "hello_world" link at the top and go back to the main page of the repository.
1. You now have the `main` branch set as the default. If you want, you can click on the Branches button and View all branches again, then delete the master branch!

### Clone the repository to HiPerGator

Now we want to make a copy of the repository on HiPerGator.

1. Click the green Code download button and click the copy button next to the URL to copy it.
 ![Screenshot of copying git clone url](images/git_clone.png)
1. Log into HiPerGator and `cd` to where ever you want to put this--your home directory is fine, so you can stay there if you want.
1. Type `git clone ` (with a space at the end) and paste the copied URL. Hit enter. The command and output should look like this:
  ```bash
  [magitz@login3 ~]$ git clone https://github.com/magitz/hello_world.git
  Cloning into 'hello_world'...
  remote: Enumerating objects: 3, done.
  remote: Counting objects: 100% (3/3), done.
  remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
  Unpacking objects: 100% (3/3), done.
  [magitz@login3 ~]$
  ````

Now we are ready to write our scripts...

## Setup nano to show syntax highlighting

* p. 364: **How to Write a Shell Script**: point one talks about different text editors. There are many options, the easiest for now will be the `nano` text editor. Before we use that, let's turn on syntax highlighting. This makes it easier to read scripts by adding color to different kinds of things. Nano uses a file called .nanorc (a hidden file) stored in your home directory to control this. I have a template you can copy to your home directory:
  ```bash
  cp /blue/bsc4452/share/Class_Files/TLCL_files/.nanorc ~/
  ```

## Ch 24: Writing Your First Script

* Before you start writing the hello_world script, change directories into the repository directory.
* p. 365: **Script File Format**: As noted, we will use the nano text editor. To create the hello_world script, type: `nano hello_world.sh`. The `.sh` ending is not needed, but again, I think it helps you know that the file is a shell script.

{% include important.html content="Remember that we called the script `hello_world.sh`, so be sure to add the `.sh` when following along in TLCL." %}

* p. 366: **Executable Permissions**: Before you change the execution permissions, try running your script:
  ```bash
  [magitz@login3 hello_world]$ ./hello_world.sh
  -bash: ./hello_world.sh: Permission denied
  [magitz@login3 hello_world]$
  ```
  The `./` says to look in the current directory. As TLCL mentions in this section, we can't run the script like this because it doesn't have execute permissions set. There are actually a couple of ways around this. One way, as the text does, add execute permission, the other is to call it slightly differently:
  ```bash
  [magitz@login3 hello_world]$ bash hello_world.sh
  Hello World!
  [magitz@login3 hello_world]$
  ```
  Since `bash` is the program that is running, `hello_world.sh` doesn't need execute permissions. I frequently take this route. Seems easier to me than messing with permissions...but moving on...

* p. 366: **Script File Location**: This section gets into the PATH variable, which is really important to understand, and PATHs are critical and the source of many problems. The text discusses a couple of options:
  1. You could move your `hello_world.sh` script to a directory in your PATH. And you will see that `/home/<gatorlink>/bin` is in your PATH by default. But, that would move it out of the git repository and all the goodness that comes with version control.
  1. You could add the current directory to your PATH, but that can lead to a very long list of PATHs and cause other issues.
  1. Personally, I generally suggest that for your own scripts, just use relative or absolute PATHs to call the script. So, either `./hello_world.sh` or `~/hello_world/hello_world.sh`.

### The git workflow

* Before we move on, we have a functional copy of a new script. Now is the time to tell git, we want to track the `hello_world.sh` file, commit the changes we've made and push them to the remote repo.
  ```bash
  [magitz@login3 hello_world]$ git add hello_world.sh
  [magitz@login3 hello_world]$ git commit -m "First version of saying hello"
  [main 8c29b7f] First version of saying hello
  1 file changed, 3 insertions(+)
  create mode 100644 hello_world.sh
  [magitz@login3 hello_world]$ git push
  Counting objects: 6, done.
  Delta compression using up to 32 threads.
  Compressing objects: 100% (5/5), done.
  Writing objects: 100% (5/5), 625 bytes | 0 bytes/s, done.
  Total 5 (delta 1), reused 0 (delta 0)
  remote: Resolving deltas: 100% (1/1), done.
  To git@github.com:magitz/hello_world.git
    cf23ef4..8c29b7f  main -> main
  [magitz@login3 hello_world]$
  ```

## Ch 25: Starting a Project

{% include tip.html content="We are starting a new project, which means, we should, you guessed it, start a new git repository! Follow the steps we used above to make a new repository called `sys_info_page` and clone that onto HiPerGator." %}

* p. 371: **First Stage: Minimal Document**: To view this page in a browser, you will need to download the file and open it on your computer.

* p. 372: **First Stage: Minimal Document**: We will make the sys_info_page file in the sys_info_page git repo directory, not ~/bin. Again, I'd suggest calling the file `sys_info_page.sh`.

  Also, once you have the first version of the `sys_info_page.sh` script, `git add`, `git commit` and `git push`.

* p. 373: **Second Stage: Adding a Little Data**: Let's add a little more of the git workflow here. We'll come back to this, but let's take a look at branches in git first.

## More on git branches

Every repo has one branch, hopefully called `main`. But you can create branches that essentially give you another copy to work on without messing up that main copy. When you are satisfied with the changes you've made, they can be merged back into the main branch. Or if you mess things up or realize your idea was not well thought out, you can just delete it and not worry that you've messed up your main branch.

Here is an image to illustrate the idea:

![Illustration of branching in git](images/branching.png)

 We currently have a functional script that we are happy with. We are about to start making some major changes. Rather than making these changes here, it is easier to make a branch of the repository. This allows us to try new things, test features, etc. without messing up the current functional version. If we don't like what we do, it's easy to trash it and be back where we are. If we do like it, we can merge our changes back into the main branch and have the new version become the main version.

  Let's create a branch called `variables` (we're going to learn about variables as we do this section)

```bash
  [magitz@login3 sys_info_page]$ git branch variables
  [magitz@login3 sys_info_page]$ git checkout variables
  Switched to branch 'variables'
  [magitz@login3 sys_info_page]$
  ```

  These two commands could have also been simplified to the single `git checkout -b variables`, which creates and checks out the branch in one step.
  
* p. 373: **Second Stage: Adding a Little Data**: make these changes and then run the `git add`, `git commit`, `git push` commands.

  ```bash
  [magitz@login3 sys_info_page]$ git add sys_info_page.sh
  [magitz@login3 sys_info_page]$ git commit -m "Add a little data"
  [variables f512adf] Add a little data
  1 file changed, 2 insertions(+), 2 deletions(-)
  [magitz@login3 sys_info_page]$ git push
  fatal: The current branch variables has no upstream branch.
  To push the current branch and set the remote as upstream, use

      git push --set-upstream origin variables

  [magitz@login3 sys_info_page]$ 
  ```
  {% include note.html content="Notice how the initial `git push` command fails. git tells you there is a fatal error because there isn't a variables branch on github (we just created it here). git is also helpful and suggests a command that you may have wanted to use instead: `git push --set-upstream origin variables` which says, create a variables branch at the 'origin' (github.com) and push the content there." %}

  ```bash
  [magitz@login3 sys_info_page]$ git push --set-upstream origin variables
  Counting objects: 5, done.
  Delta compression using up to 32 threads.
  Compressing objects: 100% (3/3), done.
  Writing objects: 100% (3/3), 415 bytes | 0 bytes/s, done.
  Total 3 (delta 0), reused 0 (delta 0)
  remote:
  remote: Create a pull request for 'variables' on GitHub by visiting:
  remote:      https://github.com/magitz/sys_info_page/pull/new/variables
  remote:
  To git@github.com:magitz/sys_info_page.git
  * [new branch]      variables -> variables
  Branch variables set up to track remote branch variables from origin.
  [magitz@login3 sys_info_page]$
  ```

  Now, lets go look at the repo on github. Click on the `sys_info_page.sh` file to view it in the repo.

  ![Screenshot of status in github](images/git_main_branch.png)

  The repo still looks like it did before! That is because the main branch is set to be default. But you can click on the "Branch: main" button and select "variables" to see that version.

  In fact the original file is still there in our folder too. Checkout the main branch and look at the file:
  ```bash
  [magitz@login3 sys_info_page]$ git checkout main
  Switched to branch 'main'
  [magitz@login3 sys_info_page]$ cat sys_info_page.sh
  #!/bin/bash
  # Program to output a system information page
  echo "<html>
    <head>
        <title>Page Title</title>
    </head>
    <body>
        Page body.
    </body>
  </html>"

  [magitz@login3 sys_info_page]$
  ```
  This is part of the magic of git!

  {% include warning.html content="The wonders of git a brought to you by a special hidden folder called `.git` located in the main folder of a git repository. Do not mess with this folder! It is hidden for a reason! If you go in there and start messing with stuff, bad things will happen!" %}

  Checkout the variables branch again and keep working through the chapter. Remember to `git add`, `git commit`, `git push` now and then--typically when you think you have point in time you might want to return to, or have done a significant change.

### Merging git branches

At some point we decide we are ready to merge the branch back into the main. This updates the main branch with the changes you have made in the development branch.

If you are the only one working and you are only working on one thing, this may be simple. If other developers have made changes to the main branch, there may be conflicts that your changes create--if you both change the same file, git can't merge on its own and needs your help to resolve the conflicts. We will come back to this later, but since you shouldn't have any conflicts, you are set to merge...

Checkout the main branch and then merge:

```bash
[magitz@login2 sys_info_page]$ git checkout main
  Switched to branch 'main'
[magitz@login2 sys_info_page]$ git status
# On branch main
nothing to commit, working directory clean
[magitz@login2 sys_info_page]$ git merge variables
Updating 8ad541d..2627d71
Fast-forward
 sys_info_page.sh | 41 ++++++++++++++++++++++++++++++++---------
 1 file changed, 32 insertions(+), 9 deletions(-)
[magitz@login2 sys_info_page]$ git push
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/magitz/sys_info_page.git
   8ad541d..2627d71  main -> main
```

Since we are done with the function branch we can delete it:

```bash
[magitz@login2 sys_info_page]$ git branch -d function
Deleted branch function (was 2627d71).
```

## Ch 26: Top-Down Design

 {% include tip.html content="This chapter is really important in starting to help you think about how to break down a task into small steps. Taking a complex task and breaking it down into pieces is a lot of what programmers do. Often the stumbling block isn't necessarily the coding, but figuring out how to break the task down into pieces to start the coding. <BR>
 <BR>
 When you are working through this process, you may get stuck. Take a break. Work on something else. Maybe make a sketch of what you want to do. Ask for help!" %}

 {% include note.html content="Remember to keep practicing with git, using branches as you implement changes, pushing to github.com, merging branches back into main when you are done with a section, etc." %}

 There is a ton of great stuff in this chapter and you can work through most of it. But...

 {% include warning.html content="<strong>WARNING!!</strong><br>
When you get the p. 391, where you implement the `report_home_space()` function, Do Not implement as written! The TLCL version tries to get home directory use for all users. There are several thousand users on HiPerGator! Do not try to run this!" %}

* p. 391: Modification to **`report_home_space()`**: I suggest using the following in place of what is in TLCL. This will check *your* home directory space usage...

  ```bash
  report_home_space(){
    cat <<- _EOF_
        <h2>Home Space Utilization</h2>
        <pre>$(du -sh /home/magitz/*)</pre>
  _EOF_
    return
  ```
