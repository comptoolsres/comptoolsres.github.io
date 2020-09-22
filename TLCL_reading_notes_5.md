---
title: "Notes on TLCL Ch 27-33"
tags: [linux]
sidebar: home_sidebar
permalink: TLCL_5.html
toc: true
summary: "Flow control is the last foundational tool that we need to cover. Testing for and acting on given conditions and repeating actions are fundamental to programming. These chapters introduce conditional execution with <code>if</code> statements and repetition with <code>while</code> and <code>for</code> loops."
keywords: if, is-else, elif, for, while, unitl, loop, 
---

## Flow Control: Branching with `if`

<ul id="VideoTabs" class="nav nav-tabs">
    <li class="active"><a href="#Stream_1" data-toggle="tab">MS Stream (UF account needed)</a></li>
    <li><a href="#Dropbox_1" data-toggle="tab">Dropbox (No account, offers picture-in-picture, but no captions or search)</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="Stream_1">
      <iframe width="853" height="480" src="https://web.microsoftstream.com/embed/video/16bdfb20-017a-4b24-be1f-ba5c6dc5416e?autoplay=false&amp;showinfo=true" allowfullscreen style="border:none;"></iframe>
    </div>
    <div role="tabpanel" class="tab-pane" id="Dropbox_1">
        <video width="800"  controls>
          <source src="https://www.dropbox.com/s/wkl04mgx93yq5h7/TLCL_Ch_27_conditionals_if.mp4?dl=1" type="video/mp4" />
        </video>
    </div>
</div>

Below is a graphical representation of the logic behind an `if` statement.

![Diagram of if and if-else statements](images/if_statements.png)

`if` statements are used throughout programming for flow control--making decisions and controlling how the program runs. If some condition is met, do one thing, otherwise (`else`) do something else. `if` statements are used to make choices among multiple conditions. Once one condition is met, that portion of the code is executed, so it is important to think about the order of 'else if' statements. In Bash and Python, 'else if' is squished together to make the `elif` statement. `else`, if used, is always the last statement because if the program makes it through all the `if` and `elif` statements without any of them being true, `else` is used to handle any other condition--there is no test, it is automatically true.

* p. 393: **`if`**: Type (not copy/paste) the code in the box at the bottom of 393 on the command line, hitting enter at the end of the lines:

  ```bash
  [magitz@login3 ~]$ if [ "$x" -eq 5 ]; then
  >   echo "x equals 5."
  > else
  >   echo "x does not equal 5."
  > fi
  x equals 5.
  ```
  
  Notice that after the first line, the prompt changes to a `>`. This is Bash's way of saying it is expecting more information to complete the command--you haven't given it all the information that it needs yet. In this case, we have said we want to setup a conditional execution. `if` x is equal to 5...but we haven't told Bash what to do. So Bash gives the `>` prompt to ask for more commands.

  {% include tip.html content="If you get stuck at the `>` prompt, and can't or don't want to finish the command, the **Ctrl-c** (control-c) key combination will cancel the command and get you back to the normal prompt." %}

  {% include note.html content="The `;` before the `then` is used in Bash to put multiple commands on the same line. You can string multiple commands together, separating each with a `;`. Personally, I prefer to put the `then` on the next line, in which case the semi-colon isn't needed and the `then` visually lines up with the `else` and `fi`" %}
 
  {% include important.html content="One last important point here...Bash is extremely picky about spaces. We have seen before that something as simple as adding a space in an assignment causes problems: e.g.
  <br>
  <code>
  [magitz@login3 ~]$ x = 5<br>
  -bash: x: command not found<br>
  [magitz@login3 ~]$ x=5 # This works<br>
  [magitz@login3 ~]$<br>
  </code>
  <br>
  The same is true when it comes to `if` statements. If we remove the spaces within the square brackets, we get incorrect results!
  <br>
  <code>
  [magitz@login3 ~]$ if [\"$x\" -eq 5]; then echo \"x equals 5.\"; else echo \"x does not equal 5.\"; fi<br>
  -bash: [5: command not found<br>
  x does not equal 5.<br>
  [magitz@login3 ~]$<br>
  </code>
  " %}

* p. 394: `if`: In the box on the next page, the text shows the same command typed out on one line using the `;` to separate each part of the command instead of new lines. Both work just fine. Also, rather than re-type the command, remember about the <i class="fas fa-arrow-up"></i>-arrow to bring back commands from your `history`. Also note that even though we typed the command on multiple lines, when we recall it from the `history`, it is on a single line.

* p. 394: **`if` statement syntax**: We discussed the format of documentation before, but here is another good example:

  ```bash
  if commands; then
  commands
  [elif commands; then
  commands...]
  [else
  commands]
  fi
  ```

  An `if` statement must start with `if`, followed by some commands (a conditional statement). Those commands have to be followed by either a `;` or a new line and the word `then`. That must be followed by what to do when the commands result in a true statement. Optionally (they are in square brackets, so interpreted as optional), we can add a second set of commands with the `elif`. The `elif` can be repeated ('...'). Optionally, that is followed by the `else` (without commands or `then`). The entire `if` statement must end in `fi` ("if spelled backward--we will see this is a convention Bash uses frequently).

  The concept and structure of an `if` statement is common to all programming languages that I know. The <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.syntax}}">syntax</a> changes from language to language, but the concept is the same. For example, how a language bounds the parts of a statement varies. Bash uses `if`, `then`, `fi`; other languages use parentheses, curly-braces, or square-brackets; Python uses indentation. **Regardless of syntax, the concept is the same and important to understand.**

* p. 396: **test**: As above, it is important to note that the `[ expression ]` format has a single space on either side of the expression. See what happens if I delete the spaces on this example:

    ```bash
    [magitz@login2 magitz]$ FILE=~/.bashrc
    [magitz@login2 magitz]$ if [ -f "$FILE" ]; then echo "$FILE is a regular file."; fi
    /home/magitz/.bashrc is a regular file.
    [magitz@login2 magitz]$ if [-f "$FILE"]; then echo "$FILE is a regular file."; fi
    -bash: [-f: command not found
    [magitz@login2 magitz]$
    ```

{% include warning.html content="Pay particular attention to the warning box at the top of p. 400!!<br><br>Here is an example, first with the < properly escaped with a \, and second the error when it is not escapes and Bash is looking for a file to redirect into string1. Think how much worse this could have been if I used > and there was a file called string2!
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

* p. 402: **A More Modern Version of test**: Before I read this section, I had always wondered why some people used [], others used [[]], and still others used (())! It made Googling for help a challenge because I didn't understand the different cases and syntaxes. Knowing the similarities and differences will help you as you look for help. Again, don't focus on the details--you can always look these up. Focus on the concepts.

## Ch 28: Reading Keyboard Input

<ul id="VideoTabs" class="nav nav-tabs">
    <li class="active"><a href="#Stream_2" data-toggle="tab">MS Stream (UF account needed)</a></li>
    <li><a href="#Dropbox_2" data-toggle="tab">Dropbox (No account, offers picture-in-picture, but no captions or search)</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="Stream_2">
      <iframe width="853" height="480" src="https://web.microsoftstream.com/embed/video/f9ed1108-174d-4d14-93d3-593b6985b5a3?autoplay=false&amp;showinfo=true" allowfullscreen style="border:none;"></iframe>
    </div>
    <div role="tabpanel" class="tab-pane" id="Dropbox_2">
        <video width="800"  controls>
          <source src="https://www.dropbox.com/s/dbk3spmj1aonpnr/TLCL_Ch_28_keyboard_input.mp4?dl=1" type="video/mp4" />
        </video>
    </div>
</div>

Have a look at this chapter. Taking input from the user while your code is running has many use cases. However, in general, I think most programs should be able to run without interactive input. We want to focus on automation and allowing scripts to run with command line options or configuration files, not on programs that need a user to enter information manually.

It is good to know that these are options, but not something we will spend time on. **Implementing user input will likely be an extra credit opportunity on one of the problem sets.**

## Ch 29: Flow Control: Looping with `while` / `until`

<ul id="VideoTabs" class="nav nav-tabs">
    <li class="active"><a href="#Stream_3" data-toggle="tab">MS Stream (UF account needed)</a></li>
    <li><a href="#Dropbox_3" data-toggle="tab">Dropbox (No account, offers picture-in-picture, but no captions or search)</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="Stream_3">
      <iframe width="853" height="480" src="https://web.microsoftstream.com/embed/video/d074ae71-f1ae-4575-9ca4-0e79a9a092ec?autoplay=false&amp;showinfo=true" allowfullscreen style="border:none;"></iframe>
    </div>
    <div role="tabpanel" class="tab-pane" id="Dropbox_3">
        <video width="800"  controls>
          <source src="https://www.dropbox.com/s/vqsfkscdskg4i4x/TLCL_Ch_29_while_until_loops.mp4?dl=1" type="video/mp4" />
        </video>
    </div>
</div>

The next type of flow control is the `while` loop. Here is a graphical representation of a `while` loop:

![Diagram of a while loop](images/while_loop.png)

The idea here is to do something **while** some condition is true. Once that condition is false, stop looping and move on with the rest of the program.

* p. 424: **`while`**: Play with the `while [[ "$count" -le 5 ]];` script. Read the information about the modification to the `read-menu` program, but I am not sure it is worth actually writing/running this script.

* p. 426: **Breaking Out of a Loop**: the `break` and `continue` commands are used a fair bit and have a very different effect:
  * **`break`**: *Terminates* the loop and the program continues with the next command *after* the loop.
  * **`continue`**: stops the *current iteration* of the loop and resumes the loop with the *next* iteration.
* p. 426: `while true`: This is a handy way of creating what is referred to as an <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.infinite_loop}}">infinite loop</a>. But, by using the `break` command, you can break out of the loop when some desired condition is met.

* p.428: **`until`**: Here is the diagram for an `until` loop:

  ![Diagram of an until loop](images/until_loop.png)

  Notice that, opposite of the `while` loop, in the `until` loop, the loop executes as long as the condition is false--or **until** it is true. Choose the loop that make most sense, or is easiest to code for the conditions you want to enforce.

* p. 428: **Reading Files with Loops**: Remember that there is a copy of the `distros.txt` file at `/blue/bsc4452/share/Class_Files/TLCL_files/distros.txt`. This is a great example of processing a file--both in reading a file line by line, but also in getting fields from that file. Notice how each of the three columns of the dataset are automatically assigned to the three variables--`distro`, `version`, `release`. Also note the next box on p. 429 that would allow you to <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.parse}}">parse</a> files with different field separators.

## Ch 30: Troubleshooting

There is certainly a lot of helpful content in this chapter, but again, I don't think we have time to cover it in detail. Take a look though. One of the key points about debugging here is that the line numbers called out in the error messages, aren't always where the error is. If those lines look fine, look above for missing quotes, brackets, etc.

## Ch 31: Flow Control: Branching with `case`

`case` is another helpful flow control tool, but is not as widely used outside of Bash. For this reason, again, have a look, but don't worry about the details. Keep it in mind as an option as you write your scripts, and come back to this chapter if needed.

## Ch 32: Positional Parameters

This chapter seems a bit out of place and we are going to skip to Ch 33.

## Ch 33: Flow Control: Looping with `for`

<ul id="VideoTabs" class="nav nav-tabs">
    <li class="active"><a href="#Stream_4" data-toggle="tab">MS Stream (UF account needed)</a></li>
    <li><a href="#Dropbox_4" data-toggle="tab">Dropbox (No account, offers picture-in-picture, but no captions or search)</a></li>
</ul>
<div class="tab-content">
    <div role="tabpanel" class="tab-pane active" id="Stream_4">
      <iframe width="853" height="480" src="https://web.microsoftstream.com/embed/video/52866b5e-c156-4a93-8db7-29579b868fc5?autoplay=false&amp;showinfo=true" allowfullscreen style="border:none;"></iframe>
    </div>
    <div role="tabpanel" class="tab-pane" id="Dropbox_4">
        <video width="800"  controls>
          <source src="https://www.dropbox.com/s/bfadan01c246akf/TLCL_Ch_33_for_loops.mp4?dl=1" type="video/mp4" />
        </video>
    </div>
</div>

Given how much `for` loops are used, I am surprised William Shotts waits until this late to introduce them! But here we are...Here is a diagram of the `for` loop:

![Diagram of a for loop](images/for_loop.png)

The idea is to pass a list of items, or a range of numbers, into the loop and execute the commands in the loop using each item in the list (or range) as the input. Do this for every item in the list and when the program has fished, move on with the rest of the program.

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

{% include tip.html content="Take the time now to play with and understand `for` loops--this is one of the most common programming tools and something you will use all the time!" %}

* The list passed into the for loop can take many forms, some examples:

  * `for file in *.txt` (a list of files ending in .txt in the current directory)
  * `for i in {1..30}` (a list of numbers from 1-30). This is what the text calls 'brace expansion' and can also be used for letter ranges: e.g. `{A-L}`.
  * ``for sample in `cat samples.txt` `` (the lines of the files samples.txt one at a time--the backtick was covered in ch 7. In this case, the list for the `for` loop is every line in the `samples.txt` file, one line at a time.)

* p. 468: You may have noticed back on p. 466 the `[in words]` part of the `for` loop syntax is in square brackets, meaning it is optional. This section points out that if you omit the list of items, `for` iterates over command line options that are passed in. For the example with the longest-word2.sh script (located at `/blue/bsc4452/share/Class_Files/TLCL_files/longest-word2.sh`), if you run `/blue/bsc4452/share/Class_Files/TLCL_files/longest-word2.sh file1 file2 file3`, you will get the longest word in each file.

* p. 469: **Why `i`?**: This box, should really be called "Why **not** `i`?" As the box describes, `i` is a commonly used variable, but *it is a terrible variable!* Especially if your nested loops and have `j`, and `k`! **Use meaningful variable names!** `for file in *.txt` is much easier to understand. We will look at this more in the Python section, but the developer of Python, Guido van Rossum, is often quoted as saying:

  > <i class="fa fa-quote-left"></i> ...code is read much more often than it is written.

  Write your code so that others, and your future self, can read and understand it! While variable names like `i` and `x` can be easier to type, the reader will need to pause and figure out what information is `i` or `x` holding.

* p. 468: **for: C Language Form**: Have a look at this as another way to write for loops. I rarely use this form, but you may run into it. As you might suspect, C programmers are the main users of this in Bash.

* p. 471: **Summing Up**: This goes back to looking at each user's home space. Again, something you probably don't want to do on the cluster, so skip this, or have a look and see that you understand what is being attempted.
