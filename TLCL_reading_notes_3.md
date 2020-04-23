---
title: "TLCL Ch 19 & 20 Notes"
tags: [reading notes]
sidebar: home_sidebar
permalink: TLCL_3.html
toc: false
---

# Notes on TLCL Ch 19 & 20

{% include note.html content="We are going to skip a bunch of chapters in TLCL. Chapters 9 and 10 can be helpful, we may come back to them if questions arise, and certainly look at them if you want more of an understanding of permissions and processes.

Part 2 and the first chapters of Part 3 get more into system configuration and management. Again, the content is good and could be useful for you, but we don't have the time to get into these and for the most part, on HiPerGator, you don't need to (or can't) manage these things." %}

## Regular Expressions

{% include note.html content="Feel free to read through this on your own, but we will work on this together in class." %}

Start by reading p. 251 as an introduction. But before continuing, I have some additional exercises that I hope make it easier to learn about regular expressions.

At the start of Ch 19, William Shotts says (p. 251):
> As we have seen, text data plays an important role on all Unix-like systems, such as Linux.

While this is true, text data plays an important roll everywhere! Much of our data is textual, whether it is numerical data or words, much data is textual. Even images can be processed as matrices of numeric values representing pixel intensities. Fundamentally, all computer data is stored as 1s and 0s--text! Manipulating, summarizing, searching, processing text makes up a large part of data processing.

William Shotts, goes on to say (p. 251):
>Regular expressions ... may be (arguably) the most arcane feature of them all. This is not to suggest that the time it takes to learn about them is not worth the effort. Quite the contrary. A good understanding will enable us to perform amazing feats, though their full value may not be immediately apparent.

I am not sure I can agree regular expressions are arcane, to me they are magic! If the only thing you take away from this course is how to use regular expressions (regex), and only use them with find and replace text in a text editor, you will have gotten a valuable skill from this course. I use regex all the time! People ask for seemingly complex transformations and a few minutes with regex, provides a solution.

Regex will transform your life! Or at least change how you transform data for the rest of your life...

## RegEx in your text editor

Chapter 19 of TLCL focuses on the `grep` utility, which is a great utility, but let's take a step back for a second and use your text editor. This will be easier to get started with.

Open VSCode, the MobaXterm editor, BBEdit or whatever editor you are using (make sure it has RegEx abilities!).

Make a new document and paste the following line into the new file:

`Go Gators, Come on Gators, Get up and Go!`

Open the Find dialog box and turn on regular expression searches. In VSCode, that is the "`.*`" button, in MobaXterm, there is a "Regular expressions" checkbox in the find modal.

In the Find box enter the text "`Go`" and either look through the found text (highlighted in the document) or click Find All.

Regular expressions are a symbolic notation that allow you to find and replace with superpowers! You may be familiar with the "*" wildcard used in many search function, RegEx are so much more!

Change the "`Go`" in the Find box to "`G.`" (G-period). Again, look at the results.

**What just happened?** Since you have Regular Expression search turned on, the "`.`" is being interpreted not as a period, but as a regular expression. And in the regex syntax, a "`.`" means "any character". So, "`G.`" matches "`Go`", "`Ga`", and "`Ge`" in our string. In fact it would match "`G`" followed by any character.

{% include tip.html content="VSCode, and other editors, also have a case sensitive option. I suggest leaving it on, so that searches are case sensitive unless you specifically do not want them to be. That way, the search is more similar to standard grep and you are less likely to be surprised." %}

I've put together a [Regular_Expressions_Cheat_Sheet.pdf](images/RegEx_CheetSheet.pdf), print this out and keep it handy for this section.

## Ch. 19: Regular Expressions

As useful as it is to use regular expression in your text editor, there's lots of cool things you can do with them on the command line. Chapter 19 of TLCL is a good walk through of the "`grep`" tool, so back to that...

* p. 253: **`grep bzip dirlist*.txt` output**: Note that `bzip` is found in both /bin and /usr/bin on HiPerGator, so you will get four lines that match rather then the two shown in this box. The same applies to the other similar searches.
* p. 254: **The Any Character**: Look in the man page to see what the `-h` option does for `grep`.
* p. 256: **A Crossword Puzzle Helper**: Our word dictionary (see grey box) has 479,828 words! So results are a bit different.
* p. 258-263: **POSIX Character Classes** through **POSIX Basic vs Extended Regular Expressions**: Have a look a this, but I wouldn't worry too much about the details.

### Some additional practice

Since I think RegEx are so important, here are some additional searches to try to make. In each case, the goal is to create one search string that finds the indicated text. Check your results by seeing what is found with your string and play until it gets the correct text.

Write a RegEx to find:

1. "Get" and "Gat"
1. Two letter words
1. The first "Go"
1. The last "Go"
1. Words that start with "G"
1. Words that start with a vowel
1. Words that start with an uppercase letter
1. Commas
1. "t"s at the end of words
1. "t"s not at the end of words.

## Replacing text with RegEx

Now that you've practiced finding text, you can also replace it, either with entered text, or keeping "captured" text and replacing/deleting the rest. To capture text, put parentheses around the regex that finds it.

For example, "`(Go) Gators`" will find the text "Go Gators" and put the "Go" into a variable called `$1`. In the replace string, we could keep that and write the replace to be "`$1 Seminoles`" and the result would be "Go Seminoles".

### Practice with replace using ReGex

Here is a list of names. Copy and paste into your text editor.

```bash
Fred Jones
Jane Smith
Jose Rodriguez
Tamika Reynolds
```

Write a regular expression to:

1. Find everyone's first name
1. Find everyone's last name
1. Find the first names and last names and then replace each name in the list using the format: Last, First
1. Find the first names and replace with just the first initial and a period (F. Jones, J. Smith, etc.)

Amazing stuff right??  ![Amazing gif](images/amazing.gif)

## Ch. 20: Text Processing

The next set of tools are another great resource.

Don't forget you can use the PDF to copy/paste larger chunks of data...In this case, it takes some regex playing to make it work, so I have put a copy of the distros.txt file in `/ufrc/bsc4452/share/Class_Files/TLCL_files/`.
