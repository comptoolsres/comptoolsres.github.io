---
title: "Week 7"
tags: [week-by-week]
sidebar: home_sidebar
permalink: Week_07.html
toc: false
week_num: 7
series: "Week-by-week series"
weight: 0.7
---
# Week 7: {{site.wk07_mon_date | date: '%b %d' }} - {{site.wk07_fri_date | date: '%b %d' }}

{% include custom/series_week_by_week.html %}

## Overview for Week {{page.week_num}}

* Lists, Dictionaries and Tuples
* Regular Expressions in Python
* Scripting data acquisition from websites and APIs

## What's due by the end of the week?

* Problem Set 3 is due {{site.ps_3_due | date: '%A, %B %d' }}
* Quiz 3 is due {{site.quiz_3_due | date: '%A, %B %d' }}

## For Monday

{% include image.html file='monday.png' alt="Calendar icon with Monday" position="right" max-width=75 %}

<ul id="MondayTabs" class="nav nav-tabs">
    <li class="active"><a href="#MonBefore" data-toggle="tab">Before Class</a></li>
    <li><a href="#MonDuring" data-toggle="tab">During Class</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="MonBefore">
        {% include day/016_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="MonDuring">
        {% include day/016_during.html %}
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
        {% include day/017_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="WedDuring">
        {% include day/017_during.html %}
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
      Homecoming, No class
    </div>
    <div role="tabpanel" class="tab-pane" id="FriDuring">
      Homecoming, No class
    </div>
</div>

## By the end of this week you should

{% include image.html file='checkmark.png' alt="Check mark icon" position="right" max-width=75 %}

1. Understand the importance of handling errors and how to use the `try/except` functions
1. Understand the Python data types list, dictionary and tuple

{% include custom/office_hours.html %}

{% include custom/series_week_by_week_next.html %}