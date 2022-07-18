---
title: "Week 1"
tags: [week-by-week]
sidebar: home_sidebar
permalink: Week_01.html
toc: false
week_num: 1
series: "Week-by-week series"
weight: 0.1
---

# Week 1: {{site.wk01_wed_date | date: '%b %d' }} - {{site.wk01_fri_date | date: '%b %d' }}


{% include custom/series_week_by_week.html %}

## Overview for Week {{page.week_num}}

* Introduction to the class
* Getting setup with [software](software.html)
* Overview of UF Research Computing and HiPerGator
* Getting started on the Linux command line

## What's due by the end of the week?

* Nothing to turn in this week.
* Quiz 1 will be available on Friday. It is due {{site.quiz_1_due | date: '%A, %B %d' }}.
  * It covers basic Linux commands like: `pwd, cd, ls, less, cp, mv, mkdir, rm, which, man, cat, sort, uniq, wc, head, tail, echo, history, grep, cut, paste, join, diff, tr, sed`

## For Wednesday

{% include image.html file='wednesday.png' alt="Calendar icon with Wednesday" position="right" max-width=75 %}

<ul id="WednesdayTabs" class="nav nav-tabs">
    <li class="active"><a href="#WedBefore" data-toggle="tab">Before Class</a></li>
    <li><a href="#WedDuring" data-toggle="tab">During Class</a></li>
</ul>

<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="WedBefore">
        {% include day/001_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="WedDuring">
        {% include day/001_during.html %}
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
    {% include day/002_before.html %}
  </div>
  <div role="tabpanel" class="tab-pane" id="FriDuring">
    {% include day/002_during.html %}
  </div>
</div>

## By the end of this week you should

{% include image.html file='checkmark.png' alt="Check mark icon" position="right" max-width=75 %}

1. Be confident logging into HiPerGator via ssh.
1. Understand the basics of Linux filesystems and where to store your data on HiPerGator.
1. Be able to use the following Linux commands: `pwd, cd, ls, less, cp, mv, mkdir, rm, which, man, cat, sort, uniq, wc, head, tail, echo, history`.
1. Understand command arguments to modify how commands function.
1. Be able to use redirect output to a file (`>, >>`).
1. Be able to link commands with pipes (`|`).

{% include custom/office_hours.html %}

{% include custom/series_week_by_week_next.html %}