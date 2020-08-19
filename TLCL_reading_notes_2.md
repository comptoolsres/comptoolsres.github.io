---
title: "Notes on TLCL Ch 5-8"
tags: [linux]
sidebar: home_sidebar
permalink: TLCL_2.html
summary: These chapters will further build command line skills and confidence using the shell.
keywords: which, man, help, documentation, alias, redirection, double redirect, backtick, math, head, tail, bash
---

## Ch 5: Working with Commands

<ul id="VideoTabs" class="nav nav-tabs">
    <li class="active"><a href="#Stream_1" data-toggle="tab">MS Stream (UF account needed)</a></li>
    <li><a href="#Dropbox_1" data-toggle="tab">Dropbox (No account, offers picture-in-picture, but no captions or search)</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="Stream_1">
        <iframe width="853" height="480" src="https://web.microsoftstream.com/embed/video/09d8a3fa-5225-4039-89ab-571f0d30a963?autoplay=false&amp;showinfo=true" allowfullscreen style="border:none;"></iframe>
    </div>
    <div role="tabpanel" class="tab-pane" id="Dropbox_1">
        <video width="800"  controls>
          <source src="https://www.dropbox.com/s/zhibhu5tzg130bv/TLCL_Ch_05_Commands.mp4?dl=1" type="video/mp4" />
        </video>
    </div>
</div>

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

* p. 44: **Getting a Command's Documentation**: This section presents a number of methods to get help, which in itself can be overwhelming! How I use these generally boils down to two or three methods:

  `man` command: e.g. `man ls` will usually work for system programs--programs that are part of the OS, not applications you would install. So try that first. Sometimes it's easier to read a man page online, so Google [man ls](http://man7.org/linux/man-pages/man1/ls.1.html).

  `command -h`: this frequently works, and if not may provide some hints anyway. e.g.:

  ```bash  
  $ python -h
  usage: python [option] ... [-c cmd | -m mod | file | -] [arg] ...
  Options and arguments (and corresponding environment variables):
  -b     : issue warnings about str(bytes_instance), str(bytearray_instance)
          and comparing bytes/bytearray with str. (-bb: issue errors)
  -B     : dont write .pyc files on import; also PYTHONDONTWRITEBYTECODE=x
  -c cmd : program passed in as string (terminates option list)
  -d     : debug output from parser; also PYTHONDEBUG=x
  -E     : ignore PYTHON* environment variables (such as PYTHONPATH)
  -h     : print this help message and exit (also --help)
  [...more options...]

  ```

  For for system commands, I start with `man` and then go to Google.

  For applications, I start with `-h`, if that doesn't work, I try `--help` and then I go to Google...

  {% include tip.html content="p. 46: `man ls`: man pages can often be quite long, you can page through them with the space bar, but to quit out of the view, just type `q`." %}

* p. 50: **Creating Our Own Commands with `alias`**: The vocabulary can get a little confusing here. I noted above that the symbolic and hard links created with the `ln` command are similar to aliases in MacOS. Aliases used here are very different--in Linux an alias is a way to create your own custom command, or modifications of a command.

  In reading this section, it may be hard to see where you would use aliases. The example that I like to give is that I frequently like to view my file listing with the long listing, sorted reverse-chronologically with human readable file sizes (MB, GB vs all in bytes).

  I could type `ls -lrth` every time I want to see that, but that is a lot of typing. So in my `.bashrc` file, I added the line:  

  `alias ll='ls -lrth'`  
  
  So now, if I type `ll`, bash looks at my aliases, and knows that I want it to do `ls -lrth` and gives me that output.

## Ch 6. Redirection

<ul id="VideoTabs" class="nav nav-tabs">
    <li class="active"><a href="#Stream_2" data-toggle="tab">MS Stream (UF account needed)</a></li>
    <li><a href="#Dropbox_2" data-toggle="tab">Dropbox (No account, offers picture-in-picture, but no captions or search)</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="Stream_2">
        <iframe width="853" height="480" src="https://web.microsoftstream.com/embed/video/22d17ad9-9d32-453b-b64a-10bf20cb077f?autoplay=false&amp;showinfo=true" allowfullscreen style="border:none;"></iframe>
    </div>
    <div role="tabpanel" class="tab-pane" id="Dropbox_2">
        <video width="800"  controls>
          <source src="https://www.dropbox.com/sh/u4rf89wfjh7clb3/AAA4F8i_bUvbxpU0VVTMbIWLa?dl=1" type="video/mp4" />
        </video>
    </div>
</div>

{% include tip.html content="p. 56: `>` and `>>`: I think it is worth emphasizing that the single redirect, `>`, overwrites the file you are redirecting to. If the file existed, it will be replaced with the new output. There is no recovering the previous information. So, be careful with `>`. And possibly favor the double redirect, `>>`, which appends to the existing file, placing new content at the end of the file." %}

* p. 61: **The Difference Between `>` and `|`**: Pay particular attention to this box as people are often unclear on the difference between these commands.

* p. 65: **head / tail – Print First / Last Part of Files**: `tail -f /var/log/messages`: You will not be able to run this command since you do not have permission to view the file /var/log/messages. We will see if we can find a use for the `tail -f` command, in general it is used for watching the contents of an output file while a program is running.
* p. 66: **Linux Is About Imagination**: Another great analogy! I hope this course sparks your imagination about what you can do with the giant erector set of tools you will learn about!

## A note on Chapters 7 and 8

{% include callout.html content="The next two chapters cover a fair bit. **Do not** attempt to memorize everything. There is a lot of great information here, hopefully you will remember some of it.
<br><br>
My goal in having you read these chapters is for you to get a deeper understanding of Linux and see some of the amazing tools at your disposal. I use the command line daily, and don't have most of this memorized...
<br><br>
Think of it as a tour of the toolbox: you don't need to know how to use every tool, and probably don't have a good idea what you would ever do with many of the tools, but someday down the road, you will either remember that there is a tool to do what you need, or say to yourself, the way I am doing this is a pain, let me go back to the toolbox and see if there is a better way." type="primary" %}

## Ch 7: Seeing the World as the Shell Sees It

<ul id="VideoTabs" class="nav nav-tabs">
    <li class="active"><a href="#Stream_3" data-toggle="tab">MS Stream (UF account needed)</a></li>
    <li><a href="#Dropbox_3" data-toggle="tab">Dropbox (No account, offers picture-in-picture, but no captions or search)</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="Stream_3">
        <iframe width="853" height="480" src="https://web.microsoftstream.com/embed/video/3bfaee92-a997-4357-9082-597dcd8ff9cd?autoplay=false&amp;showinfo=true" allowfullscreen style="border:none;"></iframe>
    </div>
    <div role="tabpanel" class="tab-pane" id="Dropbox_3">
        <video width="800"  controls>
          <source src="https://www.dropbox.com/s/z9dvqxkfxlerrqd/TLCL_Ch_07_shell.mp4?dl=1" type="video/mp4" />
        </video>
    </div>
</div>

* This chapter covers a lot. It is definitely worth reading and doing your best to understand, but can get a little on the overly detailed side.
* p. 71: **Arithmetic Expansion**: One thing that this section should point out to you is that, while you *can* do math with bash, it is not the easiest thing! Especially with more complex calculations, bash quickly becomes more trouble than it is worth and it is far easier to switch to Python or other language with better math functionality.
* p. 75: **Backquotes**: The text uses the term "backquote" for the '`' character (usually the key to the left of the 1 on your keyboard), this character is also referred to as the "backtick".

## Ch 8: Advanced Keyboard Tricks

<ul id="VideoTabs" class="nav nav-tabs">
    <li class="active"><a href="#Stream_4" data-toggle="tab">MS Stream (UF account needed)</a></li>
    <li><a href="#Dropbox_4" data-toggle="tab">Dropbox (No account, offers picture-in-picture, but no captions or search)</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="Stream_4">
        <iframe width="853" height="480" src="https://web.microsoftstream.com/embed/video/e57a75dd-0352-41f6-bdc7-4b81c6cedac0?autoplay=false&amp;showinfo=true" allowfullscreen style="border:none;"></iframe>
    </div>
    <div role="tabpanel" class="tab-pane" id="Dropbox_4">
        <video width="800"  controls>
          <source src="https://www.dropbox.com/s/jxakqmwo9io0prn/TLCL_Ch_08_keyboard_tricks.mp4?dl=1" type="video/mp4" />
        </video>
    </div>
</div>

* This chapter can certainly improve your skills and make it easier to do things, but I would not spend time worrying trying to memorize these. It is helpful to know that the options exist, and find and remember the ones you find helpful, but memorizing these is not the goal.
* p. 83: **Completion**: Tab completion is definitely worth learning, you will use it all the time!
* p. 85: **Using History**: While history is maintained on HiPerGator and is very useful, please be aware that because you can be logged in on multiple servers, sometimes things get lost in the history. It will generally be there and can be used, but don't rely on exclusively. Keep notes of useful commands, etc.

## Skipping a bunch of chapters

<ul id="VideoTabs" class="nav nav-tabs">
    <li class="active"><a href="#Stream_5" data-toggle="tab">MS Stream (UF account needed)</a></li>
    <li><a href="#Dropbox_5" data-toggle="tab">Dropbox (No account, offers picture-in-picture, but no captions or search)</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="Stream_5">
        <iframe width="853" height="480" src="https://web.microsoftstream.com/embed/video/1a5cacab-1e37-42f2-b79e-715634d38fc9?autoplay=false&amp;showinfo=true" allowfullscreen style="border:none;"></iframe>
    </div>
    <div role="tabpanel" class="tab-pane" id="Dropbox_5">
        <video width="800"  controls>
          <source src="https://www.dropbox.com/s/918577gdziwmkjy/TLCL_Ch_09-18_skip.mp4?dl=1" type="video/mp4" />
        </video>
    </div>
</div>

{% include callout.html content="We are going to skip a bunch of chapters in TLCL. Chapters 9 and 10 can be helpful, we may come back to them if questions arise, and certainly look at them if you want more of an understanding of permissions and processes.

Part 2 and the first chapters of Part 3 get more into system configuration and management. Again, the content is good and could be useful for you, but we don't have the time to get into these and for the most part, on HiPerGator, you don't need to (or can't) manage these things." type="primary" %}
