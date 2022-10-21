---
title: "Week 11"
tags: [week-by-week]
sidebar: home_sidebar
permalink: Week_11.html
toc: false
week_num: 11
series: "Week-by-week series"
weight: 1.1
---

# Week 11: {{site.wk11_mon_date | date: '%b %d' }} - {{site.wk11_fri_date | date: '%b %d' }}

{% include custom/series_week_by_week.html %}

## Overview for Week {{page.week_num}}

* Problem Set 5 will be available on Monday. It is due {{site.ps_5_due | date: '%A, %B %d' }}
* More on databases
* More on SQL
* Start learning SQLAlchemy to use Python to interact with databases

## What's due by the end of the week?

* **Quiz 4 due {{site.quiz_4_due}}**
* **Project 1 due {{site.project_1_due | date: '%A, %B %d' }}**
* Problem Set 5 available Friday, due {{site.ps_5_due | date: '%A, %B %d' }}

## For Monday

{% include image.html file='monday.png' alt="Calendar icon with Monday" position="right" max-width=75 %}

<ul id="MondayTabs" class="nav nav-tabs">
    <li class="active"><a href="#MonBefore" data-toggle="tab">Before Class</a></li>
    <li><a href="#MonDuring" data-toggle="tab">During Class</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="MonBefore">
        {% include day/027_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="MonDuring">
        {% include day/027_during.html %}
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
        {% include day/028_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="WedDuring">
        {% include day/028_during.html %}
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
        {% include day/029_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="FriDuring">
        {% include day/029_during.html %}
    </div>
</div>

## By the end of this week you should

{% include image.html file='checkmark.png' alt="Check mark icon" position="right" max-width=75 %}

1. Understand how to open a database in sqlite
1. Have a general understanding of SQL commands to query databases
1. Have mostly completed the <a href="LinkedInLearningDatabases.md">LinkedIn Learning Programming Foundations Databases course.</a>
1. Begin to understand how to interact with a database from Python
1. Be comfortable with basic SQL commands in sqlite
1. Be starting to understand the main methods of interacting with databases using Python.

{% include custom/office_hours.html %}

{% include custom/series_week_by_week_next.html %}