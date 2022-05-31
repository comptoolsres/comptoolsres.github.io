---
title: "Week 9"
tags: [week-by-week]
sidebar: home_sidebar
permalink: Week_09.html
toc: false
week_num: 9
series: "Week-by-week series"
weight: 0.9
---


# Week 9: {{site.wk09_mon_date | date: '%b %d' }} - {{site.wk09_fri_date | date: '%b %d' }}{% include custom/series_week_by_week.html %}

## Overview for Week {{page.week_num}}

* Additional data visualization with Matplotlib
* Start working on Project 1

## What's due by the end of the week?

* Nothing is due this week
* Problem Set 4 due {{site.ps_4_due | date: '%A, %B %d' }}
* Project 1 will be available on Friday. It is due {{site.project_1_due | date: '%A, %B %d' }}

## For Monday

{% include image.html file='monday.png' alt="Calendar icon with Monday" position="right" max-width=75 %}

<ul id="MondayTabs" class="nav nav-tabs">
    <li class="active"><a href="#MonBefore" data-toggle="tab">Before Class</a></li>
    <li><a href="#MonDuring" data-toggle="tab">During Class</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="MonBefore">
        {% include day/022_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="MonDuring">
        {% include day/022_during.html %}
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
        {% include day/023_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="WedDuring">
        {% include day/023_during.html %}
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
        {% include day/024_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="FriDuring">
        {% include day/024_during.html %}
    </div>
</div>

## By the end of this week you should

{% include image.html file='checkmark.png' alt="Check mark icon" position="right" max-width=75 %}

1. Understand how to use Numpy arrays and access elements of arrays
1. Become familiar with Pandas
1. Know how to open csv files to create Pandas data frames
1. Know the basics of producing graphs in matplotlib
1. Be getting more comfortable with producing graphs in matplotlib

{% include custom/office_hours.html %}

{% include custom/series_week_by_week_next.html %}