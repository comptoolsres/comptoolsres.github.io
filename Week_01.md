---
title: "Week 1: Aug. 31 - Sept. 4"
tags: [week-by-week]
sidebar: home_sidebar
permalink: Week_01.html
toc: false
week_num: 1
series: "Week-by-week series"
weight: 0.1
---

{% include custom/series_week_by_week.html %}

## Overview for Week {{page.week_num}}

* Introduction to the class
* Getting setup with [software](software.html)
* Overview of UF Research Computing and HiPerGator
* Getting started on the Linux command line

## What's due by the end of the week?

* Nothing to turn in this week.
* Quiz 1 will be available on Friday. It is due {{site.quiz_1_due}}.
  * It covers basic Linux commands like: `pwd, cd, ls, less, cp, mv, mkdir, rm, which, man, cat, sort, uniq, wc, head, tail, echo, history, grep, cut, paste, join, diff, tr, sed`

## For Monday

{% include image.html file='monday.png' alt="Calendar icon with Monday" position="right" max-width=75 %}

<ul id="MondayTabs" class="nav nav-tabs">
    <li class="active"><a href="#MonBefore" data-toggle="tab">Before Class</a></li>
    <li><a href="#MonDuring" data-toggle="tab">During Class</a></li>
</ul>
<div class="tab-content">
  <div role="tabpanel" class="tab-pane active" id="MonBefore">
    <ul>
      <li><b>Watch the intro video</b></li>
        <ul id="VideoTabs" class="nav nav-tabs">
          <li class="active"><a href="#Stream" data-toggle="tab">MS Stream (UF account needed)</a></li>
          <li><a href="#Dropbox" data-toggle="tab">Dropbox (No account, offers picture-in-picture, but no captions or search)</a></li>
        </ul>
        <div class="tab-content">
            <div role="tabpanel" class="tab-pane active" id="Stream">
                <iframe width="640" height="360" src="https://web.microsoftstream.com/embed/video/cc9f32f0-e439-4e7b-a7ae-f403d126a12d?autoplay=false&amp;showinfo=true" allowfullscreen style="border:none;"></iframe>
            </div>
            <div role="tabpanel" class="tab-pane" id="Dropbox">
                <video width="800"  controls>
                  <source src="https://www.dropbox.com/s/6mhxt13ig7sn9ih/Intro_to_class.mp4?dl=1" type="video/mp4" />
                </video>
            </div>
        </div>
        <li><b>Follow the directions on the <a href="software.html">software download page</a></b></li>
      </ul>
    </div>
    <div role="tabpanel" class="tab-pane" id="MonDuring">
        <ol>
          <li>Zoom meeting for class: {{site.class_zoom_link}}</li>
          <li>This will be one of the few classes that is mostly lecture. <a href="https://comptoolsres.github.io/slides/Lect_01_Intro.html">Here are the slides</a> for today's introduction to the class.</li>
        </ol>
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
        <ol>
          <li><a href="TLCL_1.html">Read TLCL Introduction & Ch 1-4</a></li>
          <li>Watch the <a href="https://training.it.ufl.edu/training/items/orientation-materials-for-courses-using-rc.html">Orientation Materials for Courses Using HiPerGator</a> video</li>
        </ol>
    </div>
    <div role="tabpanel" class="tab-pane" id="WedDuring">
        <ol>
          <li>Zoom meeting for class: {{site.class_zoom_link}}</li>
          <li>Getting started: <a href="https://comptoolsres.github.io/slides/Lect_02_Computers.html">Computers</a></li>
          <li>UF Research Computing Intro & getting started</li>
        </ol>
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
        <ol>
          <li><a href="TLCL_2.html">Read TLCL Ch 5-8</a></li>
        </ol>
    </div>
    <div role="tabpanel" class="tab-pane" id="FriDuring">
        <ol>
          <li>Zoom meeting for class: {{site.class_zoom_link}}</li>
          <li>Building Command Line skills</li>
          <li><a href="https://forms.gle/fZSskLMgw2exxfq47">This Google form has exercises for you to work on</a></li>
          <ul>
            <li>The files used in this exercise are on HiPerGator and the path is in the form. For those not working on HiPerGator, the files are also in the repo at: <a href="https://github.com/comptoolsres/Class_Files">https://github.com/comptoolsres/Class_Files</a></li>
          </ul>
        </ol>
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