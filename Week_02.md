---
title: "Week 2"
tags: [week-by-week]
sidebar: home_sidebar
permalink: Week_02.html
toc: false
week_num: 2
series: "Week-by-week series"
weight: 0.2
---

# Week 2: {{site.wk02_mon_date | date: '%b %d' }} - {{site.wk02_fri_date | date: '%b %d' }}

{% include custom/series_week_by_week.html %}

## Overview for Week {{page.week_num}}

* Regular Expressions in text editors and with `grep`
* Text manipulation

## What's due by the end of the week?

* **Quiz 1 is due {{site.quiz_1_due | date: '%A, %B %d' }}**.
* Problem Set 1 will be available on Wednesday. It is due {{site.ps_1_due | date: '%A, %B %d' }}.
  * Covers regular expressions in text editors and with `grep` as well as some of the Linux commands from week 1.

---

## For Monday

{% include image.html file='monday.png' alt="Calendar icon with Monday" position="right" max-width=75 %}

<ul id="MondayTabs" class="nav nav-tabs">
    <li class="active"><a href="#MonBefore" data-toggle="tab">Before Class</a></li>
    <li><a href="#MonDuring" data-toggle="tab">During Class</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="MonBefore">
      {% include day/003_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="MonDuring">
      {% include day/003_during.html %}
    </div>
</div>

---

## For Wednesday

{% include image.html file='wednesday.png' alt="Calendar icon with Wednesday" position="right" max-width=75 %}

<ul id="WednesdayTabs" class="nav nav-tabs">
    <li class="active"><a href="#WedBefore" data-toggle="tab">Before Class</a></li>
    <li><a href="#WedDuring" data-toggle="tab">During Class</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="WedBefore">
      {% include day/004_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="WedDuring">
      {% include day/004_during.html %}
    </div>
</div>

---

## For Friday

{% include image.html file='friday.png' alt="Calendar icon with Friday" position="right" max-width=75 %}

<ul id="FridayTabs" class="nav nav-tabs">
    <li class="active"><a href="#FriBefore" data-toggle="tab">Before Class</a></li>
    <li><a href="#FriDuring" data-toggle="tab">During Class</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="FriBefore">
      {% include day/005_before.html %}
    </div>
    <div role="tabpanel" class="tab-pane" id="FriDuring">
      {% include day/005_during.html %}
    </div>
</div>

---

## By the end of this week you should

{% include image.html file='checkmark.png' alt="Check mark icon" position="right" max-width=75 %}

1. Be able to use regular expressions for finding and replacing text in a text editor such as VSCode.
1. Be able to use the following Linux commands: `grep, cut, paste, join, diff, tr, sed`.

<hr>

{% include custom/office_hours.html %}

{% include custom/series_week_by_week_next.html %}