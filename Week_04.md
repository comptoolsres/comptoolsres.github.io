---
title: "Week 4"
tags: [week-by-week]
sidebar: home_sidebar
permalink: Week_04.html
toc: false
week_num: 4
series: "Week-by-week series"
weight: 0.4
---

# Week 4: {{site.wk04_mon_date | date: '%b %d' }} - {{site.wk04_fri_date | date: '%b %d' }}

{% include custom/series_week_by_week.html %}

## Overview for Week {{page.week_num}}

* Learning to use Google for coding help
* Learning to read code and application documentation
* Using UF Research Computing resources
* Writing job scripts to run batch jobs via SLURM scheduler
* Build confidence on the command line and bash scripting.

## What's due by the end of the week?

* **Problem Set 1 due {{site.ps_1_due | date: '%A, %B %d' }}.**
* Problem Set 2 will be available on Wednesday. It is due {{site.ps_2_due | date: '%A, %B %d' }}.

## For Monday

{% include image.html file='monday.png' alt="Calendar icon with Monday" position="right" max-width=75 %}

<ul id="MondayTabs" class="nav nav-tabs">
    <li class="active"><a href="#MonBefore" data-toggle="tab">Before Class</a></li>
    <li><a href="#MonDuring" data-toggle="tab">During Class</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="MonBefore">
      {% include day/008_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="MonDuring">
      {% include day/008_during.html %}
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
     {% include day/009_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="WedDuring">
     {% include day/009_during.html %}
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
      {% include day/010_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="FriDuring">
      {% include day/010_during.html %}
    </div>
</div>

## By the end of this week you should

{% include image.html file='checkmark.png' alt="Check mark icon" position="right" max-width=75 %}

1. Have a better understanding of searching for coding help on Google.
1. Have a better understanding of reading code and application documentation.
1. Be comfortable submitting jobs to the SLURM scheduler on HiPerGator
1. Understand resource requests for jobs: CPUs, RAM and time.
1. Be more familiar with the process of writing a batch script to run an application on HiPerGator.

{% include custom/office_hours.html %}

{% include custom/series_week_by_week_next.html %}