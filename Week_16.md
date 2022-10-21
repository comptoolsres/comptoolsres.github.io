---
title: "Week 16"
tags: [week-by-week]
sidebar: home_sidebar
permalink: Week_16.html
toc: false
week_num: 16
series: "Week-by-week series"
weight: 1.6
---

# Week 16: {{site.wk16_mon_date | date: '%b %d' }} - {{site.wk16_fri_date | date: '%b %d' }}

{% include custom/series_week_by_week.html %}

## Overview for Week {{page.week_num}}

* Graphics

## What's due by the end of the week?

* **Project 2 due {{site.project_2_due  | date: '%A, %B %d'  }}**

## For Monday

{% include image.html file='monday.png' alt="Calendar icon with Monday" position="right" max-width=75 %}

<ul id="MondayTabs" class="nav nav-tabs">
    <li class="active"><a href="#MonBefore" data-toggle="tab">Before Class</a></li>
    <li><a href="#MonDuring" data-toggle="tab">During Class</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="MonBefore">
        {% include day/039_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="MonDuring">
        {% include day/039_during.html %}
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
        {% include day/040_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="WedDuring">
        {% include day/040_during.html %}
    </div>
</div>

## By the end of this week you should

{% include image.html file='checkmark.png' alt="Check mark icon" position="right" max-width=75 %}

1. Complete the course evaluation!

{% include custom/office_hours.html %}

{% include custom/series_week_by_week_next.html %}