---
title: "Notes on Regular Expressions & TLCL Ch 19 & 20"
tags: [linux]
sidebar: home_sidebar
permalink: TLCL_3.html
---

## Regular Expressions

Start by reading p. 251 as an introduction. But before continuing, I have some additional exercises that I hope make it easier to learn about regular expressions.

At the start of Ch 19, William Shotts says (p. 251):
> <i class="fa fa-quote-left"></i> As we have seen, text data plays an important role on all Unix-like systems, such as Linux.

While this is true, text data plays an important roll everywhere! Much of our data is textual, whether it is numerical data or words, much data is textual. Even images can be processed as matrices of numeric values representing pixel intensities. Fundamentally, all computer data is stored as 1s and 0s--text! Manipulating, summarizing, searching, processing text makes up a large part of data processing.

William Shotts, goes on to say (p. 251):
> <i class="fa fa-quote-left"></i> Regular expressions ... may be (arguably) the most arcane feature of them all. This is not to suggest that the time it takes to learn about them is not worth the effort. Quite the contrary. A good understanding will enable us to perform amazing feats, though their full value may not be immediately apparent.

I am not sure I can agree regular expressions are arcane, to me they are magic! If the only thing you take away from this course is how to use regular expressions (RegEx or regex), and only use them with find and replace text in a text editor, you will have gotten a valuable skill from this course. I use regex all the time! People ask for seemingly complex transformations and a few minutes with regex, provides a solution.

Regex will transform your life! Or at least change how you transform data for the rest of your life...

The last important quote from TLCL touches on an unfortunate truth (p. 251):
> <i class="fa fa-quote-left"></i> However, to further confuse things, not all regular expressions are the same; they vary slightly from tool to tool and from programming language to language.

We will quickly find "non-standard" implementations in VSCode, MobaXterm, the [RegExONE](https://regexone.com/) and [RegExr](https://regexr.com/) sites recommended on the [resources page](resources.md), and elsewhere. While most implement basic features in similar manners, for various reasons, many regular expressions work *slightly* differently from tool to tool. While this can be frustrating, with an understanding of the fundamentals, you can work around these differences and, in some cases, exploit them to your favor.

## RegEx in your text editor

Chapter 19 of TLCL focuses on the `grep` utility, which is a great utility, but let's take a step back for a second and use your text editor. This will be easier to get started with.

{% include warning.html content="As noted, different tools implement regular expressions slightly differently. For these notes, I will use VSCode. I will point out some non-standard implementations within VSCode. If you use a different text editor, there may be some differences." %}

Using VSCode, make a new document and paste the following line into the new file:

`Go Gators, Come on Gators, Get up and Go!`

{% include tip.html content="Add a few blank lines at the top of the file then paste this text--the VSCode find dialog box tends to cover the first few lines of text in the window" %}

Open the Find dialog box and turn on regular expression searches. In VSCode, that is the "`.*`" button, in MobaXterm, there is a "Regular expressions" checkbox in the 'Find...' modal.

In the Find box enter the text "`Go`" and either look through the found text (highlighted in the document) or click Find All.

Regular expressions are a symbolic notation that allow you to find and replace with superpowers!

{% include tip.html content="VSCode, and other editors, also have a case sensitive option. I suggest leaving it on, so that searches are case sensitive unless you specifically do not want them to be. That way, the search is more similar to standard regex and you are less likely to be surprised." %}

{% include tip.html content="I highly encourage you to play with these regular expressions either in VSCode or one of the online resources. It would probably be best to paste in or make up some other text to experiment with." %}

 **I have put together a [<i class="fa fa-file fa-2x"></i> Regular_Expressions_Cheat_Sheet.pdf](images/Regular_Expressions_Cheat_Sheet.pdf.pdf), print this out and keep it handy for this section.**

### <i class="fa fa-search"></i> Wildcard patterns

{% include note.html content="We used the '\*' wildcard on the command line for things like listing all files that end in '.txt.' (e.g.: <code>ls *.txt</code>). Regular Expressions take wildcards to a new level. It is, however, important to note that the '\*' has a very different meaning in regular expressions than it does on the command line. In regular expressions, the '\*' is used to qualify repetitions--see the Repetitions section below for more." %}

#### <i class="fa fa-search-plus"></i> The `.` wildcard--Any character

Change the "`Go`" in the Find box to "`G.`" (G-period). Again, look at the results.

**What just happened?** Since you have Regular Expression search turned on, the "`.`" is being interpreted not as a period, but as a regular expression, or **regex**. And in the regex syntax, a "`.`" means "any character". So, "`G.`" matches "`Go`", "`Ga`", and "`Ge`" in our string. In fact it would match "`G`" followed by any character.

#### <i class="fa fa-search-plus"></i> The `\w` wildcard--Any word character (Letters, numbers, and the underscore "_")

Change the "`G.`" to "`G\w`". Does that change anything? Why/why not?

<div class="panel-group" id="accordion">
    <div class="panel panel-default">
        <div class="panel-heading">
            <a class="noCrossRef accordion-toggle" data-toggle="collapse" data-parent="#accordion" href="#collapseA"> <i class="fa fa-check-circle fa-2x"></i> Click for solution</a>
        </div>
        <!-- /.panel-heading--> 
        <div id="collapseA" class="panel-collapse collapse noCrossRef">
            <div class="panel-body">
                It should not change anything, since, in our example text, all Gs are followed by a word character. If we had some text, like "This is a G.", the two regex's would give different results.
            </div>
            <!-- /.panel-body -->
        </div>
        <!-- /.panel-collapse -->
    </div>
    <!-- /.panel-default -->
</div>
<!-- /.panel-group -->

Add another "`\w`", making the search pattern "`G\w\w`". What does that change? Why?
<div class="panel-group" id="accordion">
    <div class="panel panel-default">
        <div class="panel-heading">
            <a class="noCrossRef accordion-toggle" data-toggle="collapse" data-parent="#accordion" href="#collapseB"> <i class="fa fa-check-circle fa-2x"></i> Click for solution</a>
        </div>
        <!-- /.panel-heading--> 
        <div id="collapseB" class="panel-collapse collapse noCrossRef">
            <div class="panel-body">
                Adding a second "`\w'" should now select two word characters after the G. Since "Go" does not have two letters after the G, the "Go"s are no longer matched.
            </div>
            <!-- /.panel-body -->
        </div>
        <!-- /.panel-collapse -->
    </div>
    <!-- /.panel-default -->
</div>
<!-- /.panel-group -->

#### <i class="fa fa-search-plus"></i> The `\W` wildcard--Any non-word character

Change the search pattern to be just "`\W`" (capital-W). You should now be finding all non-word characters--spaces, punctuation, etc.

#### <i class="fa fa-search-plus"></i> The `\s` wildcard--White space (spaces, tabs, end of line)

Now, let's change the search patterns to "`\s`". This is similar to the "`\W`", but does not include punctuation--only spaces. Using these minor differences allows you to carefully craft regular expressions to match what you are looking for.

{% include warning.html content="Here is our first example of the non-standard implementation of regular expressions in VSCode. The *standard* implementation of '`\s`' includes the new line character. For various reasons, VSCode does not include the new line character in the set of matches to the '`\s`'. If you want to match a new line in VSCode, use the '`\n`' wildcard covered below." %}

#### <i class="fa fa-search-plus"></i> The `\S` wildcard--Non-White space

As with the "`\W`", the "`\S`" is the *inverse* of the lowercase version and "`\S`" matches non-white space characters. Again, slightly different than "`\w`".

#### <i class="fa fa-search-plus"></i> The `\d` wildcard-- Digit character

There are not any digits (numbers) in the text that we are playing with. Either add some or trust me that "`\d`" will find digits. As noted in the handout, the "`\d`" does not match the decimal in numbers.

#### <i class="fa fa-search-plus"></i> The `\D` wildcard-- Non-digit character

As you may have guessed by now, the "`\D`" matches non-digits.

#### <i class="fa fa-search-plus"></i> The `\t` wildcard-- Tab character

Again, we do not have any tabs in this string, but if we did "`\t" would match them. There is a difference between tab and space and this can be used to find tabs, but not spaces.

#### <i class="fa fa-search-plus"></i> The `\n` wildcard-- Newline character

One thing that we may not realize is that at the end of a line of text, there is usually a newline character that is invisible. This invisible character (actually character**s** on Windows--more on that later) can be matched with the "`\n`" wildcard. Try it on your text. You may need to add a new line at the end of your text if it is the last line in the file.

#### <i class="fa fa-search-plus"></i> Escaping characters with the `\`

The last character is not really a wildcard, but is used to escape certain characters in order to match those characters. For example if you wanted to find all of the periods in a document, you couldn't just use "`.`" because that would be interpreted at the "any character" wildcard. To get around this, you escape the period, by adding a backslash in front of it to find a literal period: "`\.`" matches periods (or decimals).

### <i class="fa fa-search"></i> Repetition patterns

Above, we looked at many of the wildcard patterns. Each of these will match a single instance of the pattern. Often we want to find multiple characters. This is where these repetition patterns come in handy.

#### <i class="fa fa-search-plus"></i> `*` -- Match 0 or more times

You can find multiple occurrences of a pattern with the "`*`". **NOTE: As noted above, this is very different than the wildcard as used on the command line** For example in our string, "`Ga*`" would match a G followed by zero or more a's--so "G", "Ga", "Ga", "G" and "G". The "`*`" can be used to match things that may or may not be present.

#### <i class="fa fa-search-plus"></i> `+` -- Match 1 or more times

If we want to ensure that the pattern is found at least once, we can use the "`+`" pattern. Again, the slight difference between "`*`" and "`+`" can be very useful in crafting regular expressions.

#### <i class="fa fa-search-plus"></i> `{n}`, `{n,}` and `{n,m}`

The patterns can be used to match:
* `{n}` exactly *n* times
* `{n,}` at least *n* times
* `{n,m}` at least *n* times, but not more than *m* times

#### <i class="fa fa-search-plus"></i> `?` -- non-greedy operator

The last repetition regular expression is the "`?`" which controls what is referred to as greediness. By default regular expressions are greedy--they will match the longest possible match defined by your expression. For example:

"`G\w*\S`" matches a "G", followed by zero or more word characters, followed by a non-white space character; or "Go", "Gators,", "Gators,", "Get", "Go!". Why does "Go" match?

If we change this by adding the non-greedy operator to the "`\w*`"-- "`G\w*?\S`"--we get: "Go", "Ga", "Ga", "Ge", "Go"--all cases where we match zero characters with the "`\w*`".

### <i class="fa fa-search"></i> Character classes with `[]`

We can create our own custom wildcards by creating character classes with the square brackets. For example, we can match capital vowels with the expression "`[AEIOU]`". Note that order does not matter in this, and that each letter is independent.

Ranges of letters and numbers can be defined with "`[A-Z]`" or "`[1-5]`". 

#### <i class="fa fa-search-plus"></i> Negative character classes with `[^]`

Kind of like the `\W`, `\S` and `\D`, we can create negative classes by putting a "`^`" inside the square brackets. For example, "`[^AEIOUaeiou]`" would find anything that is not a vowel (capital or lower case).

{% include note.html content="The caret ('`^`') has two very different meanings in regular expressions. Within square brackets, it negates the set of characters, creating the negative character class. Outside of square brackets it is a boundary qualifier covered in the next section." %}

### <i class="fa fa-search"></i> Boundary qualifiers

It is often useful to anchor matches to one end of the string (or line of text) or the other. The boundary qualifiers can be used to do this. 

#### <i class="fa fa-search-plus"></i> `^` Anchor the match to the *start* of a string (or line)

If we search for "`^Go.`", we will only find the starting "Go " not the ending "Go!".

#### <i class="fa fa-search-plus"></i> `$` Anchor the match to the *end* of a string (or line)

Similarly, if we change the search to "`Go.$`", we will match the "Go!" at the end of the line.

These can also be combined, to require that the regular expression match the entire line--from start to end.

### <i class="fa fa-search"></i> Capturing and replacing

Now is where regular expressions get even more powerful! Let's imagine we decide that the chant would be better written as "Come on Gators, Go Gators, Get up and Go!". There are many ways to make this change, and for this example others may be easier, but with lines and lines of text and more complex patterns, something like this could be easier:

Find: `(Go Gators), (Come on Gators)`
Replace: `$2, $1`

The text matched with the first set of parentheses if put into a variable called `$1` and the text matched in the second set is put into a variable called `$2`. We can then use these variables in the replace to reverse their order.

## Ch. 19: Regular Expressions

As useful as it is to use regular expression in your text editor, there are lots of cool things you can do with them on the command line. Chapter 19 of TLCL is a good walk through of the "`grep`" tool, so back to that...

* p. 253: **`grep bzip dirlist*.txt` output**: Note that `bzip` is found in both /bin and /usr/bin on HiPerGator, so you will get four lines that match rather then the two shown in this box. The same applies to the other similar searches.
* p. 254: **The Any Character**: Look in the man page to see what the `-h` option does for `grep`.
* p. 256: **A Crossword Puzzle Helper**: Our word dictionary (see grey box) has 479,828 words! So results are a bit different.
* p. 258-263: **POSIX Character Classes** through **POSIX Basic vs Extended Regular Expressions**: Have a look a this, but I wouldn't worry too much about the details.

### Some additional practice

Since I think RegEx are so important, here are some additional searches to try to make. In each case, the goal is to create one search string that finds the indicated text. Check your results by seeing what is found with your string and play until it gets the correct text.

Using the "Go Gators, Come on Gators, Get up and Go!" string, write a RegEx to find:

1. "Get" and "Gat"
1. Two letter words
1. The first "Go"
1. The last "Go"
1. Words that start with "G"
1. Words that start with a vowel
1. Words that start with an uppercase letter
1. Commas
1. Words that end in "t"
1. Words with "t"s, but not ending in "t"

<div class="panel-group" id="accordion">
    <div class="panel panel-default">
        <div class="panel-heading">
            <a class="noCrossRef accordion-toggle" data-toggle="collapse" data-parent="#accordion" href="#collapseOne"> <i class="fa fa-check-circle fa-2x"></i> Click for solutions</a>
        </div>
        <!-- /.panel-heading--> 
        <div id="collapseOne" class="panel-collapse collapse noCrossRef">
            <div class="panel-body">
                Note that, as with most things in this class, there are <i>many</i> possible answers. These are possible solutions. If you have another answer that works, it is no less correct than these!
                <ol>
                    <li> "Get" and "Gat" : <code>G[ae]t</code>, or <code>G.t</code></li>
                    <li> Two letter words : <code>\W\w\w\W</code>, or <code>\W\w{2}\W</code> </li>
                    <li> The first "Go" : <code>^Go</code></li>
                    <li> The last "Go" : <code>Go!</code>, or <code>Go.$</code></li>
                    <li> Words that start with "G" : <code>^[Gg]\w*</code></li>
                    <li> Words that start with a vowel : <code>^[AEIOUaeiou]\w*</code></li>
                    <li> Words that start with an uppercase letter : <code>^[A-Z]\w*</code></li>
                    <li> Commas : <code>,</code> Note in some cases, you can/should escape the comma--<code>\,</code></li>
                    <li> Words that end in "t" : <code>w\+t\W</code></li>
                    <li> Words with "t"s, but not ending in "t" : <code>\w+t\w+</code></li>
                </ol>
            </div>
            <!-- /.panel-body -->
        </div>
        <!-- /.panel-collapse -->
    </div>
    <!-- /.panel-default -->
</div>
<!-- /.panel-group -->

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

1. Create a new list with just everyone's first name
1. Create a new list with just everyone's last name
1. Find the first names and last names and then replace each name in the list using the format: Last, First
1. Find the first names and replace with just the first initial and a period (F. Jones, J. Smith, etc.)

<div class="panel-group" id="accordion">
    <div class="panel panel-default">
        <div class="panel-heading">
            <a class="noCrossRef accordion-toggle" data-toggle="collapse" data-parent="#accordion" href="#collapseTwo"> <i class="fa fa-check-circle fa-2x"></i> Click for solutions</a>
        </div>
        <!-- /.panel-heading--> 
        <div id="collapseTwo" class="panel-collapse collapse noCrossRef">
            <div class="panel-body">
                Note that, as with most things in this class, there are <i>many</i> possible answers. These are possible solutions. If you have another answer that works, it is no less correct than these!
                <ol>
                    <li>Create a new list with just everyone's first name : <i>Find:</i><code>^(\w*)\W\w*$</code>; <i>Replace:</i> <code>$1</code></li>
                    <li> Create a new list with just everyone's last name : <i>Find:</i> <code>\w*\s+(\w*)\n</code>; <i>Replace:</i><code>$1\n</code></li>
                    <li> Find the first names and last names and then replace each name in the list using the format: Last, First : <i>Find:</i><code>(\w*)\s(\w*)\n</code>; <i>Replace:</i> <code>$2, $1\n</code></li>
                    <li> Find the first names and replace with just the first initial and a period (F. Jones, J. Smith, etc.) :  <i>Find:</i> <code>(\w)\w*\s(\w*)\n</code>; <i>Replace:</i><code>$1. $2\n</code></li>
                </ol>
            </div>
            <!-- /.panel-body -->
        </div>
        <!-- /.panel-collapse -->
    </div>
    <!-- /.panel-defualt -->
</div>
<!-- /.panel-group -->

Amazing stuff right??  ![Amazing gif](images/amazing.gif)

## Ch. 20: Text Processing

The next set of tools are another great resource.

Don't forget you can use the PDF to copy/paste larger chunks of data...In this case, it takes some regex playing to make it work, so I have put a copy of the distros.txt file in `/ufrc/bsc4452/share/Class_Files/TLCL_files/`.
