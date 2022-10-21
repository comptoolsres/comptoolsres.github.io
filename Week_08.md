---
title: "Week 8"
tags: [week-by-week]
sidebar: home_sidebar
permalink: Week_08.html
toc: false
week_num: 8
series: "Week-by-week series"
weight: 0.8
---
# Week 8: {{site.wk08_mon_date | date: '%b %d' }} - {{site.wk08_fri_date | date: '%b %d' }}

{% include custom/series_week_by_week.html %}

## Overview for Week {{page.week_num}}

* SciPy, NumPy and Pandas introduction
* Using Python modules
* Data visualization with Matplotlib

## What's due by the end of the week?

* **Quiz 3 due {{site.quiz_3_due | date: '%A, %B %d' }}**
* **Problem Set 3 due {{site.ps_3_due | date: '%A, %B %d' }}**
* Problem Set 4 will be available on Friday. It is due {{site.ps_4_due | date: '%A, %B %d' }}

## For Monday

{% include image.html file='monday.png' alt="Calendar icon with Monday" position="right" max-width=75 %}

<ul id="MondayTabs" class="nav nav-tabs">
    <li class="active"><a href="#MonBefore" data-toggle="tab">Before Class</a></li>
    <li><a href="#MonDuring" data-toggle="tab">During Class</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="MonBefore">
        {% include day/018_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="MonDuring">
        {% include day/018_during.html %}
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
        {% include day/019_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="WedDuring">
        {% include day/019_during.html %}
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
        {% include day/020_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="FriDuring">
        {% include day/020_during.html %}
    </div>
</div>

## By the end of this week you should

{% include image.html file='checkmark.png' alt="Check mark icon" position="right" max-width=75 %}

1. Know how to use regular expressions in python
1. Be able to scrape data from websites with BeautifulSoup
1. Be able to get data from web services using their APIs
1. Be generally aware of SciPy and Numpy


{% include custom/office_hours.html %}

{% include custom/series_week_by_week_next.html %}