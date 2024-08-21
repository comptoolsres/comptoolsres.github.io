---
title: "Week 3"
tags: [week-by-week]
sidebar: home_sidebar
permalink: Week_03.html
toc: false
week_num: 3
series: "Week-by-week series"
weight: 0.3
---

# Week 3: {{site.wk03_mon_date | date: '%b %d' }} - {{site.wk03_fri_date | date: '%b %d' }}

{% include custom/series_week_by_week.html %}

## Overview for Week {{page.week_num}}

* Regular Expressions in text editors and with `grep`
* Text manipulation
* Writing shell scripts
* Using git and github.com for version control and collaboration


## Information on ssh keys in GitHib.com

This is the github page with the information used in the video: [https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/connecting-to-github-with-ssh](Connecting to GitHub with SSH)

<ul id="VideoTabs" class="nav nav-tabs">
    <li class="active"><a href="#Stream_1" data-toggle="tab">MS Stream (UF account needed)</a></li>
    <li><a href="#Dropbox_1" data-toggle="tab">Dropbox (No account, offers picture-in-picture, but no captions or search)</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="Stream_1">
        <iframe width="640" height="360" src="https://web.microsoftstream.com/embed/video/b0e02a2d-f108-44ff-aea2-276d98a8b524?autoplay=false&amp;showinfo=true" allowfullscreen style="border:none;"></iframe></iframe>
    </div>
    <div role="tabpanel" class="tab-pane" id="Dropbox_1">
        <video width="800"  controls>
          <source src="https://www.dropbox.com/s/dst0ai6pj255bq9/Using_ssh_keys_with_github.com.mp4?dl=1" type="video/mp4" />
        </video>
    </div>
</div>


## What's due by the end of the week?

* **Quiz 2 is due {{site.quiz_2_due | date: '%A, %B %d'}}**
  * Quiz 2 covers using: `cat`, `cut`, `sort`, `uniq`, and `paste`; as well as recognizing the meaning of the commands `if`, `for`, `while`, `break`, `continue`, `else`, `git add`, `git commit`, `git pull`.
* **[Register for github.com account](github_account.md)**

## For Monday

{% include image.html file='monday.png' alt="Calendar icon with Monday" position="right" max-width=75 %}

<ul id="MondayTabs" class="nav nav-tabs">
    <li class="active"><a href="#MonBefore" data-toggle="tab">Before Class</a></li>
    <li><a href="#MonDuring" data-toggle="tab">During Class</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="MonBefore">
      Labor Day, no class
    </div>
    <div role="tabpanel" class="tab-pane" id="MonDuring">
      Labor Day, no class
    </div>
</div>

## For Wednesday

{% include image.html file='wednesday.png' alt="Calendar icon with Wednesday" position="right" max-width=75 %}

<ul id="WednesdayTabs" class="nav nav-tabs">
    <li class="active"><a href="#WedBefore" data-toggle="tab">Before Class</a></li>
    <li><a href="#WedDuring" data-toggle="tab">During Class</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="WedBefore">
      {% include day/005_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="WedDuring">
      {% include day/005_during.html %}
    </div>
</div>

## For Friday

{% include image.html file='friday.png' alt="Calendar icon with Friday" position="right" max-width=75 %}

<ul id="FridayTabs" class="nav nav-tabs">
    <li class="active"><a href="#FriBefore" data-toggle="tab">Before Class</a></li>
    <li><a href="#FriDuring" data-toggle="tab">During Class</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="FriBefore">
      {% include day/006_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="FriDuring">
      {% include day/006_during.html %}
    </div>
</div>

## By the end of this week you should

{% include image.html file='checkmark.png' alt="Check mark icon" position="right" max-width=75 %}

1. Be confident logging into HiPerGator via ssh.
1. Be able to use regular expressions for finding and replacing text in a text editor such as VSCode.
1. Be able to use the following Linux commands: `grep, cut, paste, join, diff, tr, sed`.
1. Have watched the LinkedIn Learning Linux Command Line class
1. Be comfortable writing bash scripts to accomplish more complex tasks
1. Understand how to use git and github to:
   * Create a branch
   * Modify code
   * Add modified code to stage the changes
   * Commit the modified code
   * Push the modified code to github remote repository
   * Merge the branch into the main branch
1. Be comfortable with loops and conditionals.

{% include custom/office_hours.html %}

{% include custom/series_week_by_week_next.html %}