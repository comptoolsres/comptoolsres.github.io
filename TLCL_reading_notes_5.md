---
title: "Notes on TLCL Ch 27-33"
tags: [reading notes]
sidebar: home_sidebar
permalink: TLCL_5.html
toc: false
---

## Flow Control: Branching with `if`

Below is a graphical representation of the logic behind an `if` statement.

![Diagram of if and if-else statements](images/if_statements.png)

`if` statements are used throughout programming for flow control--making decisions and controlling how the program runs. If some condition is met, do one thing, otherwise (`else`) do something else. If statements are used to make choices among multiple conditions. Once one condition is met, that portion of the code is executed, so it is important to think about the order of 'else if' statements. In bash and Python, 'else if' is squished together to make the `elif` statement. `else` is always the last statement because if the program makes it through all the `if` and `elif` statements without any of them being true, `else` is used to handle any other condition--there is no test, it is automatically true.

* p. 396: **test**: It is important to note that the `[ expression ]` format has a single space on either side of the expression. See what happens if I delete the spaces on this example:

    ```bash
    [magitz@login2 magitz]$ FILE=~/.bashrc
    [magitz@login2 magitz]$ if [ -f "$FILE" ]; then echo "$FILE is a regular file."; fi
    /home/magitz/.bashrc is a regular file.
    [magitz@login2 magitz]$ if [-f "$FILE"]; then echo "$FILE is a regular file."; fi
    -bash: [-f: command not found
    [magitz@login2 magitz]$
    ```

{% include warning.html content="Pay particular attention to the warning box at the top of p. 400!!<br><br>Here is an example, first with the < properly escaped with a \, and second the error when it is not escapes and bash is looking for a file to redirect into string1. Think how much worse this could have been if I used > and there was a file called string2!
<br>
`[magitz@login2 magitz]$ string1='abc'`
<br>
`[magitz@login2 magitz]$ string2='xyz'`
<br>
`[magitz@login2 magitz]$ if [ string1 \< string2 ]; then echo 'string1 comes before string2'; fi`
<br>
`string1 comes before string2`
<br>
`[magitz@login2 magitz]$ if [ string1 < string2 ]; then echo 'string1 comes before string2'; fi`
<br>
`-bash: string2: No such file or directory`
<br>
`[magitz@login2 magitz]$`
" %}

* p. 400: **Integer expressions**: note that these really do only work with integers (whole numbers with no decimal):

    ```bash
    [magitz@login2 magitz]$ x=5.4
    [magitz@login2 magitz]$ y=6.7
    [magitz@login2 magitz]$ if [ $x -lt $y ]
    > then
    > echo "x less than y"
    > fi
    -bash: [: 5.4: integer expression expected
    ```

* p. 402: **A More Modern Version of test**: Before I read this section, I had always wondered why some people used [], others used [[]], and still others used (())! It made Googling for help a challenge because I didn't understand the different cases and syntaxes. Knowing the similarities and differences will help you as you look for help.

## Ch 28: Reading Keyboard Input

Have a look at this chapter if you want. However, in general, I think most programs should be able to run without interactive input. We want to focus on automation and allowing scripts to run with input options or configuration files, not on programs that need a user to enter information manually.

It is good to know that these are options, but not something we will spend time on.

## Ch 29: Flow Control: Looping with `while` / `until`

The next type of flow control is the `while` loop. Here is a graphical representation of a `while` loop:

![Diagram of a while loop](images/while_loop.png)

The idea here is to do something **while** some condition is true. Once that condition is false, stop looping and move on with the rest of the program.

* p. 424: **`while`**: Play with the `while [[ "$count" -le 5 ]];` script and read the information about the modification to the `read-menu` program, but I am not sure it is worth actually writing/running this script.

* p.428: **`until`**: Here is the diagram for an `until` loop:

  ![Diagram of an until loop](images/until_loop.png)

  Notice that, opposite of the `while` loop, in the `until` loop, the loop executes as long as the condition is false--or **until** it is true. Choose the loop that make most sense, or is easiest to code for the conditions you want to enforce.

* p. 428: **Reading Files with Loops**: Remember that there is a copy of the `distros.txt` file at `/ufrc/bsc4452/share/Class_Files/TLCL_files/distros.txt`.

## Ch 30: Troubleshooting

There is certainly a lot of helpful content in this chapter, but again, I don't think we have time to cover it in detail. Take a look though. One of the key points about debugging here is that the line numbers called out in the error messages, aren't always where the error is. If those lines look fine, look above for missing quotes, brackets, etc.

## Ch 31: Flow Control: Branching with `case`

`case` is another helpful flow control tool, but is not as widely used outside of bash. For this reason, again, have a look, but don't worry about the details. Keep it in mind as an option as you write your scripts, and come back to this chapter if needed.

## Ch 32: Positional Parameters

This chapter seems a bit out of place and we are going to skip to Ch 33.

## Ch 33: Flow Control: Looping with `for`

Given how much `for` loops are used, I am surprised William Shotts waits until this late to introduce them! Here is a diagram of the `for` loop:

![Diagram of a for loop](images/for_loop.png)

The idea is to pass a lits of items, or a range of numbers, into the loop and execute the commands in the loop using each item in the list (or range) as the input. Do this for every item in the list and when the program has fished, move on with the rest of the program.

* p. 466: **for: Traditional Shell Form**: Here is the example from the text, as well as the same example split across multiple lines:

    ```bash
    [magitz@login2 ~]$ for i in A B C D; do echo $i; done
    A
    B
    C
    D
    [magitz@login2 ~]$ for i in A B C D
    > do
    > echo $i
    > done
    A
    B
    C
    D
    [magitz@login2 ~]$
    ```

    The `for` loop is set up with the `for` command, "`i`" is a variable to hold each instance of the items in the list, "`in`" separates the variable and the list of items, and then the items are listed. Within the loop, everything between the "`do`" and "`done`" is executed for each item in the list.

{% include tip.html content="Take the time now to play with and understand for loops--this is easily the most common programming tool and something you will use all the time!" %}

* The list passed into the for loop can take many forms, some examples:

  * `for file in *.txt` (a list of files ending in .txt in the current directory)
  * `for i in {1..30}` (a list of numbers from 1-30)
  * ``for sample in `cat samples.txt` `` (the lines of the files samples.txt one at a time--the backtick was covered in ch 7. In this case, the list for the `for` loop is every line in the `samples.txt` file, one line at a time.)

* p. 469: **Why `i`?**: This box, should really be called "Why **not** `i`?" As the box describes, `i` is a commonly used variable, but it is a terrible variable! Especially if your next loops and have i, j, k! Use meaningful variable names! `for file in *.txt` is much easier to understand. We will look at this more in the Python section, but the developer of Python, Guido van Rossum, is often quoted as saying:

  > ...code is read much more often than it is written.

  Write your code so that others, and your future self, can read and understand it!

* p. 468: **for: C Language Form**: Have a look at this as another way to write for loops. I rarely use this form, but you may run into it. As you might suspect, C programmers are the main users of this in bash.

* p. 471: **Summing Up**: This goes back to looking at each user's home space. Again, something you probably don't want to do on the cluster, so skip this, or have a look and see that you understand what is being attempted.
