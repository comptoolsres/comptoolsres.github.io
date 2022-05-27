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

* Writing shell scripts
* Using git and github.com for version control and collaboration
* Flow control: conditionals and loops

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
      {% include day/006_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="WedDuring">
      {% include day/006_before.html %}
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
      {% include day/007_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="FriDuring">
      {% include day/007_during.html %}
    </div>
</div>

## By the end of this week you should

{% include image.html file='checkmark.png' alt="Check mark icon" position="right" max-width=75 %}
1. Have a github.com account
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