---
title: "Notes on TLCL Ch 24 - 26"
tags: [linux]
sidebar: home_sidebar
permalink: TLCL_4.html
toc: true
summary: "This starts with a quick explanation of some of the issues surrounding ongoing racism in STEM and one small step that can be taken to create a more inclusive community. Then it dives into using git and GitHub--topics not covered in the TLCL textbook. And finally, uses these tools as we develop scripts to move beyond what can be done in a single command line operation."
keywords: black lives matter, blm, racism, git, github, hello_world, branch, init, commit, add, push, origin, main, master, merge, functions, pseudocode, scope, local, global, variable, stub, path, PATH
---

{% include note.html content="Again, we are going to skip some chapters. As always, there's good content in these, but not enough time to cover everything." %}

## Confronting histories of racism and oppression

<ul id="VideoTabs" class="nav nav-tabs">
    <li class="active"><a href="#Stream_1" data-toggle="tab">MS Stream (UF account needed)</a></li>
    <li><a href="#Dropbox_1" data-toggle="tab">Dropbox (No account, offers picture-in-picture, but no captions or search)</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="Stream_1">
        <iframe width="853" height="480" src="https://web.microsoftstream.com/embed/video/5efaf501-e1f5-41ed-8940-2034bf1cdb09?autoplay=false&amp;showinfo=true" allowfullscreen style="border:none;"></iframe>
    </div>
    <div role="tabpanel" class="tab-pane" id="Dropbox_1">
        <video width="800"  controls>
          <source src="https://www.dropbox.com/s/pqib0ame6ewvzwn/Git_github_and_confronting_systemic_racism_in_small_ways.mp4?dl=1" type="video/mp4" />
        </video>
    </div>
</div>

In 2020, America once again turned its focus to the long, unbroken history of systemic racism and oppression of Black, Indigenous and People of Color (BIPOC, see [www.thebipocproject.org](http://thebipocproject.org)). The facts of systemic racism have, unfortunately, changed little in centuries. The situation merely became so bad that more of the country paid attention for some time.

Science and technology fields have, in many cases, actively excluded BIPOC and women. It will remain to be seen if the conversations, commitments, and promises of action turn into true, lasting change to improve inclusion of historically marginalized groups.

{% include image.html file='black-lives-matter-5329164_640.png' alt="Black Lives Matter logo" position="right" max-width=250 %} It is my hope that all feel welcome in this class and that we build up and cherish the strengths of all, regardless of race, ethnicity, gender identity, sexuality, socioeconomic status, religion, nationality, neurodiversity, or physical disability. I stand against violence and in solidarity with the Black Lives Matter movement.

### Why is this in a coding class?

It should probably have been there from the first day of class. It is my hope that all have felt included and supported so far. We have immersed ourselves in the tools of Linux and the command line: tools that have been developed by and for a largely white, male, cisgendered community. A community that has a long history of sexist, racist actions.

Progress is slow, but I am encouraged by groups such as [Women who code](https://www.womenwhocode.com/), [BlacksInTech](https://www.blacksintechnology.net/), and [/dev/Color](https://www.devcolor.org/). We must do better.

One action, small as it is, that we *can* take is to change the terms we use when they do harm to others.

### Small changes to reduce harm

In this section, we are starting to work with `git` and [GitHub](https://github.com). The historical, and until October 1, 2020, default name for the main branch of a git <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.repository}}">repository</a> is `master`. Similarly, the terms "master" and "slave" are frequently used in computer programming and hardware for controlling and subordinate processes/devices, respectively. **This terminology is offensive and unnecessary**. Importantly, it is easy to make changes in order to create a more inclusive community, and, I believe, we must do so.

There has been much discussion on the topic in the tech community. It is clear that
> <i class="fa fa-quote-left"></i> 'master'...brings the idea of human bondage and suffering to mind for a non-trivial number of people" ([Brian Carlson](https://lore.kernel.org/git/20200505231641.GH6530@camp.crustytoothpaste.net/)).

As such, many organizations, such as the [Software Freedom Conservancy](https://sfconservancy.org/news/2020/jun/23/gitbranchname/) and [GitHub](https://github.com/github/renaming) have pledge to work to change the convention to instead use the name `main` for the main branch of a <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.repository}}">repository</a>.

**We are still in the process.** In fact, my first attempts to transition this site failed as GitHub only allowed websites to be based on the master branch. That changed on July 31, 2020 and this site was transitioned to use the main branch on August 6, 2020, when I learned of GitHub's new feature. Incidentally, the transition took about 5-minutes--it is truly a small change that I hope causes a little less harm.

### Configure the default branch name in GitHub

As of [August 26, 2020](https://github.blog/changelog/2020-08-26-set-the-default-branch-for-newly-created-repositories/), you can now [change the default name for your repositories](https://github.blog/changelog/2020-08-26-set-the-default-branch-for-newly-created-repositories/), and on October 1, 2020, that default will become `main` unless you opt out.

{% include note.html content="I recommend that you take a minute now and change the default branch name for new repositories in your account to `main`.<br>
  • <a href='https://github.com/settings/repositories'>Follow this link to change settings for your personal account.</a><br>
  • Click the 'Update default branch name now' button to update your default.
  <img src='images/git_update_default_branch_now.png'><br>
  • The new name filed will be pre-populated with the suggested `main` name and you can just click the Update button.
" %}

## Getting setup in github.com

<ul id="VideoTabs" class="nav nav-tabs">
    <li class="active"><a href="#Stream_2" data-toggle="tab">MS Stream (UF account needed)</a></li>
    <li><a href="#Dropbox_2" data-toggle="tab">Dropbox (No account, offers picture-in-picture, but no captions or search)</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="Stream_2">
        <iframe width="853" height="480" src="https://web.microsoftstream.com/embed/video/6c5b0e86-d551-408f-86fa-8c7b38b0c135?autoplay=false&amp;showinfo=true" allowfullscreen style="border:none;"></iframe>
    </div>
    <div role="tabpanel" class="tab-pane" id="Dropbox_2">
        <video width="800"  controls>
          <source src="https://www.dropbox.com/s/wuq4govg6n6bvlm/Getting_started_with_github.mp4?dl=1" type="video/mp4" />
        </video>
    </div>
</div>

One thing that TLCL doesn't include that I think is critical for good coding is the use of version control, like git. We [already created a github.com account](github_account.md) and created a <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.repository}}">repository</a> through the github classroom.

As we embark on writing shell scripts, we will continue to use git and github. To get things setup, let's create your first repository from scratch.

### Create the repository on GitHub

1. Log into your github.com account.
1. There are two ways to create a new <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.repository}}">repository</a>. Either click the +-icon on the top right and select "New repository", or click the green "New" button on the left.
  ![Screenshot of methods of creating a new repository in github.com](images/git_new_repo.png)
1. For the Repository name, enter "hello_world" (you can use whatever name, but do not use a space!). If you want, you can add a description.
  ![Screenshot of creating a new repository in github.com](images/git_hello_world_new_repo.png)
1. **Check the "Initialize this repository with a README" checkbox** and click the green "Create repository" button.
1. That will create your repository and setup a template markdown file for the README.md--every repository should have a README.md file that describes the contents of the repository.
  ![Screenshot of a newly created repository in github.com](images/git_fresh_repo_main.png)
1. If you have not set your default branch name to `main`, change the name of the main branch to `main`.

   1. Click the Branch button <i class="fa fa-code-branch"></i> that currently says master, type "main" in the box and hit Enter or click "Create branch main from master".
 ![Screenshot of creating the new main branch](images/git_new_branch.png)
   1. Now we have two branches, main and master, but master is still the default. Click on the Branches button again and click on the the "View all branches" link at the bottom of the dropdown.
   1. Click the "Change default branch" button.
 ![Screenshot of the change default branch button](images/git_change_default_branch.png)
   1. This will take you to the Branches portion of the Settings page. Click on the master and select the main branch and click Update. On the window that pops up, click that "I understand, update the default branch."
 ![Screenshot of the Default branch settings page](images/git_set_default_branch.png)
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

Now we are ready to write our scripts...so back to the text.

## Ch 24: Writing Your First Script

<ul id="VideoTabs" class="nav nav-tabs">
    <li class="active"><a href="#Stream_3" data-toggle="tab">MS Stream (UF account needed)</a></li>
    <li><a href="#Dropbox_3" data-toggle="tab">Dropbox (No account, offers picture-in-picture, but no captions or search)</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="Stream_3">
        <iframe width="853" height="480" src="https://web.microsoftstream.com/embed/video/8112db4e-216b-4c9b-ae69-15d8be189ffa?autoplay=false&amp;showinfo=true" allowfullscreen style="border:none;"></iframe>
    </div>
    <div role="tabpanel" class="tab-pane" id="Dropbox_3">
        <video width="800"  controls>
          <source src="https://www.dropbox.com/s/2dnkjtpb2o4xwmh/TLCL_Ch_24_scripts.mp4?dl=1" type="video/mp4" />
        </video>
    </div>
</div>

I had to make a quick cut in this video, here's the second part of this.

<ul id="VideoTabs" class="nav nav-tabs">
    <li class="active"><a href="#Stream_4" data-toggle="tab">MS Stream (UF account needed)</a></li>
    <li><a href="#Dropbox_4" data-toggle="tab">Dropbox (No account, offers picture-in-picture, but no captions or search)</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="Stream_4">
        <iframe width="853" height="480" src="https://web.microsoftstream.com/embed/video/71e6953c-c519-4a06-8d56-b7441d999dc7?autoplay=false&amp;showinfo=true" allowfullscreen style="border:none;"></iframe>
    </div>
    <div role="tabpanel" class="tab-pane" id="Dropbox_4">
        <video width="800"  controls>
          <source src="https://www.dropbox.com/s/01aseyyd2ciqrfj/TLCL_Ch_24_part2_scripts.mp4?dl=1" type="video/mp4" />
        </video>
    </div>
</div>

### Setup nano to show syntax highlighting

* p. 364: **How to Write a Shell Script**: point one talks about different text editors. There are many options, the easiest for now will be the `nano` text editor. Before we use that, let's turn on syntax highlighting. This makes it easier to read scripts by adding color to different kinds of things. Nano uses a file called .nanorc (a hidden file) stored in your home directory to control this. I have a template you can copy to your home directory. **Copy and paste the following command on the terminal while logged into HiPerGator:**

    ```bash
    cp /blue/bsc4452/share/Class_Files/TLCL_files/.nanorc ~/
    ```

* Before you start writing the hello_world script, change directories into your repository directory: e.g. `cd hello_world`
* p. 365: **Script File Format**: As noted, we will use the nano text editor. To create the hello_world script, type: `nano hello_world.sh`. The `.sh` ending is not needed, but, I think it helps you know that the file is a shell script and suggest using meaningful file extensions.

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

  Since `bash` is the program that is running, `hello_world.sh` doesn't need execute permissions. I frequently take this route. Seems easier to me than messing with permissions...do what works best for you...

* p. 366: **Script File Location**: This section gets into the PATH variable, which is really important to understand, and PATHs are critical and the source of *many* problems for users.

  The PATH <a href='#' data-toggle='tooltip' data-original-title='{{site.data.glossary.variable}}'>variable</a> is our first example of an <a href='#' data-toggle='tooltip' data-original-title='{{site.data.glossary.environment_variable}}'>environment_variable</a>. To see the value of the PATH variable, use the echo command:

   ```bash
   [magitz@login3 ~]$ echo $PATH
   /opt/slurm/bin:/usr/lib64/qt-3.3/bin:/usr/local/bin:/usr/bin:/usr/local/sbin:/usr/sbin:/opt/puppetlabs/bin:/bin:/opt/dell/srvadmin/bin:/home/magitz/bin
   [magitz@login3 ~]$
   ```

   Your PATH is a list of directories, strung together with `:`s where the operating system will look from programs you ask to run. It will start in the first directory in the list and work its way through to the last one. So, **order does matter**--if there are applications with the same name, the first one found will be the one run. We typically speak of <a href='#' data-toggle='tooltip' data-original-title='{{site.data.glossary.prepend}}'>prepending</a> to the PATH vs <a href='#' data-toggle='tooltip' data-original-title='{{site.data.glossary.append}}'>appending</a>.

   By convention, environment variables are written in `ALL_CAPS`.

  The text discusses a couple of options:

    1. You could move your `hello_world.sh` script to a directory in your PATH. And you will see that `/home/<gatorlink>/bin` is in your PATH by default. But, that would move it out of the git repository and all the goodness that comes with version control.
    1. You could add the current directory to your PATH, but that can lead to a very long list of PATHs and cause other issues.
    1. Personally, I generally suggest that for your own scripts, just use relative or absolute PATHs to call the script. So, either `./hello_world.sh` or `~/hello_world/hello_world.sh`.

### `add`, `commit` and `push` your changes

* Before we move on, we have a functional copy of a new script. Now is the time to tell git, we want to track the `hello_world.sh` file (`git add hello_world.sh`), commit the changes we've made (`git commit -m "First version of saying hello"`) and push them to the remote repo (`git push`).

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

  That is it for this repository.

## Ch 25: Starting a Project

{% include tip.html content="We are starting a new project, which means, we should, you guessed it, start a new git repository! Follow the steps we used above to make a new repository called `sys_info_page` and clone that onto HiPerGator." %}

<ul id="VideoTabs" class="nav nav-tabs">
    <li class="active"><a href="#Stream_5" data-toggle="tab">MS Stream (UF account needed)</a></li>
    <li><a href="#Dropbox_5" data-toggle="tab">Dropbox (No account, offers picture-in-picture, but no captions or search)</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="Stream_5">
        <iframe width="853" height="480" src="https://web.microsoftstream.com/embed/video/13bc3317-15ae-4023-826f-9891b6ff821e?autoplay=false&amp;showinfo=true" allowfullscreen style="border:none;"></iframe>
    </div>
    <div role="tabpanel" class="tab-pane" id="Dropbox_5">
        <video width="800"  controls>
          <source src="https://www.dropbox.com/s/mp39n7w8e3bl24z/TLCL_Ch_25_Projects.mp4?dl=1" type="video/mp4" />
        </video>
    </div>
</div>

* p. 371: **First Stage: Minimal Document**: To view this page in a browser, you will need to download the file and open it on your computer.

* p. 372: **First Stage: Minimal Document**: We will make the sys_info_page file in the sys_info_page git repo directory, not ~/bin. Again, I'd suggest calling the file `sys_info_page.sh`.

  Also, once you have the first version of the `sys_info_page.sh` script, `git add`, `git commit` and `git push`.

* p. 373: **Second Stage: Adding a Little Data**: Let's add a little more of the git workflow here. We'll come back to this, but let's take a look at branches in git first.

## More on git branches

Every repo has one branch, hopefully called `main`. But you can create <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.branch}}">branches</a> that essentially give you another copy to work on without messing up that main copy. When you are satisfied with the changes you have made, they can be merged back into the `main` branch. Or, if you mess things up or realize your idea was not well thought out, you can just delete it and not worry that you could have messed up your `main` branch.

Here is an image to illustrate the idea:

![Illustration of branching in git](images/branching.png)

 We currently have a functional script that we are happy with. We are about to start making some major changes. Rather than making these changes here, it is easier to make a branch of the repository. This allows us to try new things, test features, etc. without messing up the current functional version. If we don't like what we do, it is easy to trash it and be back where we are. If we do like it, we can <a href='#' data-toggle='tooltip' data-original-title='{{site.data.glossary.merge}}'>merge</a> our changes back into the main branch and have the new version become the main version.

  Let's create a branch called `variables` (we are going to learn about variables as we do this section).

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

  {% include note.html content="Notice how the initial `git push` command fails. git tells you there is a fatal error because there is not a `variables` branch on github (we just created it here). `git` is also helpful and suggests a command that you may have wanted to use instead: `git push --set-upstream origin variables` which says, create a `variables` branch at the `origin` (github.com) and push the content there." %}

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

  Now, let's go look at the repo on github. Click on the `sys_info_page.sh` file to view it in the repo.

  ![Screenshot of status in github](images/git_main_branch.png)

  The repo still looks like it did before! That is because the `main` branch is set to be default. But you can click on the "Branch: main" button and select "`variables`" to see that version.

  In fact the original file is still there in our folder too. Checkout the `main` branch and look at the file:

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

  This is part of the magic of `git`!

  {% include warning.html content="The wonders of `git` a brought to you by a special hidden folder called `.git` located in the root folder of a git repository. Do not mess with this folder! It is hidden for a reason! If you go in there and start messing with stuff, bad things will happen!" %}

  Checkout the `variables` branch again and keep working through the chapter. Remember to `git add`, `git commit`, `git push` now and then--typically when you think you have point in time you might want to return to, or have done a significant change.

### Merging git branches

At some point we decide we are ready to <a href='#' data-toggle='tooltip' data-original-title='{{site.data.glossary.merge}}'>merge</a> the branch back into the `main` branch. This updates the `main` branch with the changes you have made in the development branch.

If you are the only one working and you are only working on one thing, this may be simple. If other developers have made changes to the `main` branch, there may be conflicts that your changes create--if you both change the same lines of a file, `git` can't merge on its own and needs your help to resolve the conflicts. We will come back to this later, but since you shouldn't have any conflicts, you are set to merge...

Checkout the `main` branch and then merge:

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

Since we are done with the `variables` branch we can delete it:

  ```bash
  [magitz@login2 sys_info_page]$ git branch -d variables
  Deleted branch variables on (was 2627d71).
  ```

## Ch 26: Top-Down Design

 {% include callout.html content="This chapter is really important in starting to help you think about how to break down a task into small steps. Taking a complex task and breaking it down into pieces is a lot of what programmers do. Often the stumbling block isn't necessarily the coding, but figuring out how to break the task down into pieces to start the coding. <BR>
 <BR>
 When you are working through this process, you may get stuck. Take a break. Work on something else. Maybe make a sketch of what you want to do. Ask for help!" type="primary" %}

<ul id="VideoTabs" class="nav nav-tabs">
    <li class="active"><a href="#Stream_6" data-toggle="tab">MS Stream (UF account needed)</a></li>
    <li><a href="#Dropbox_6" data-toggle="tab">Dropbox (No account, offers picture-in-picture, but no captions or search)</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="Stream_6">
        <iframe width="853" height="480" src="https://web.microsoftstream.com/embed/video/99e89a99-4cfd-4378-ab8e-276ea8a9a785?autoplay=false&amp;showinfo=true" allowfullscreen style="border:none;"></iframe>
    </div>
    <div role="tabpanel" class="tab-pane" id="Dropbox_6">
        <video width="800"  controls>
          <source src="https://www.dropbox.com/s/o9oh76ryvv7ar00/TLCL_Ch26_Top_down_design.mp4?dl=1" type="video/mp4" />
        </video>
    </div>
</div>

 {% include note.html content="Remember to keep practicing with `git`, using branches as you implement changes, pushing to github.com, merging branches back into main when you are done with a section, etc." %}

 There is a ton of great stuff in this chapter and you can work through most of it. Sometimes we talk about writing <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.pseudocode}}">pseudocode</a>. Writing down the steps, as the text does for going to the market on p. 383 is a good way to start breaking down what you need your code to do. Lay out, what do I have, where to I need to get? Fill in the steps you would take to get there. Add more details iteratively. As you go, your notes will progressively look more and more like code. You can start translating steps into real code. Again, breaking down the task into pieces is the main challenge in writing a program. People often get scared by focussing on the goal and not being able to see how to get there, but when you break it down into pieces, each step becomes more tractable and the whole program emerges.

Some notes...

* p. 384: **Shell Functions**: <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.function}}">Functions</a> facilitate breaking down code into manageable chunks. Using the text's analogy, we can write a function to park the car. Once we have the park_car function, that part of the go to the market problem is solved. In fact, that part is solved both when we park the car at the market and when we park the car at home when we return! Write once, use many times--this greatly facilitates our coding experience. Additionally, if we realize that we forgot to, for example, add the step to set the parking break, we only need to update the code one place, rather than find everywhere we used the parking code. And lastly, if we move on to writing a program for going to the work, we can re-use the park_car function from this program in the new program!

### Passing arguments into functions

I did not realize until someone asked, that this was not covered in the text. It seems so fundamental to how functions work that it didn't even occur to me that it wouldn't be covered...Adding this information now.

We've seen how functions can be used to organize code, promote reusability, and help us think about the steps that are needed to accomplish a task. It may not be clear from the text that functions, similar to scripts and programs, can take input arguments and return information. In keeping with the driving to the market analogy, the park_car function might take a parking lot isle number as an argument and return the parking spot number so you know where your car is parked.

Here is an example of a function that takes two numbers, adds them and returns the sum, this script is also located at `/blue/bsc4452/share/Class_Files/Examples/add_two.sh`:

  ```bash
  #!/usr/bin/bash

  # This script shows how parameters can be passed into a function

  add_two () {
    # Take 2 numbers and add them, returning the sum

    num1=$1 # The first argument is $1, assign to num1 variable
    num2=$2 # The second argument is $2, assign to num2 variable

    sum=$((num1 + num2))  # Add the two numbers
    return $sum  # Return the sum
  }

  value1=5
  value2=10

  add_two $value1 $value2  # Call the add_two function with 2 arguments

  echo "$value1 plus $value2 is $?"  # Print the result
  ```

When we call the function `add_two` we can pass in our two numbers. Those are assigned to the variables $1 and $2. There is also a special variable created that lists all of the arguments passed in, its name is `$@`. **Try modifying the code of the add_two function to print the value of `$@` when it is called.**

We can use those variables in the function to do our stuff. Then we can return information from the function. The main script can use the returned value with the `$?` variable.

Note that Bash does not include the argument names in the function definition line...most languages, including Python, would have something like `add_two (arg1, arg2)` indicating that the function takes two arguments. That's just not how Bash works...

### Back to the text...

* p. 387: **Local Variables**: It is good to think about <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.local_variable}}">local</a> vs <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.gloabal_variable}}">global variables</a> and the concept of <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.scope}}">scope</a>. We will encounter this throughout the semester as local and global variables are common to most programming languages. The idea is that most variables defined within a function are local to that function, are only available within the function, and are lost when the function ends.

* p. 388-389: **Keep Scripts Running**: The idea of using <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.stub}}">stubs</a> is very useful. This is also a good method to share code development. One developer can work on implementing one function, while another developer implements a different function.

  {% include warning.html content="<strong>WARNING!!</strong><br>
When you get the p. 391, where you implement the `report_home_space()` function, Do not implement as written! The TLCL version tries to get home directory use for all users. There are several thousand users on HiPerGator! Do not try to run this! But if you do and it is taking forever, Control-C (`Ctrl-C`) will cancel the program." %}

* p. 391: Modification to **`report_home_space()`**: I suggest using the following in place of what is in TLCL (use your GatorLink, not mine...). This will check *your* home directory space usage...

  ```bash
  report_home_space(){
    cat <<- _EOF_
        <h2>Home Space Utilization</h2>
        <pre>$(du -sh /home/magitz/*)</pre>
  _EOF_
    return
  ```
