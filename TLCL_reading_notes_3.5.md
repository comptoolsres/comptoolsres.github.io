---
title: "Notes on TLCL Ch 20"
tags: [linux]
sidebar: home_sidebar
permalink: TLCL_3.5.html
summary: Text processing is one of the most frequent tasks on the command line. The tools introduced in this chapter are great tools and spending some time on these will help you in the long run.
keywords: cat, sort, uniq, cut, paste, join, diff, tr, sed
---

## Ch. 20: Text Processing

The next set of tools are another great resource.

Don't forget you can use the PDF to copy/paste larger chunks of data...In this case, it takes some regex playing to make it work, so I have put a copy of the distros.txt file in `/ufrc/bsc4452/share/Class_Files/TLCL_files/`.

* p. 273: **Applications of Text**: Mostly this is pointing out the diversity of text data that we may encounter. Again, text processing is pervasive and important to so much of what we do, so these tools are important!
* p. 274: **`cat`**: The `cat` program is maybe the most used program on the command line...it displays the contents of a text file on the screen. In the [RegEx chapter](TLCL_reading_notes_3.md) we mentioned that there is a character at the end of each line. `cat` can show you this, as well as tab characters, with the `cat -A` option.  
* p. 276: **MS-DOS Text vs. Unix Text**: Especially for Windows users this is an important box to read. DOS (the underlying OS of Windows) and Linux do not use the same characters to signify the end of a line. Many text editors on Windows default to DOS line breaks. If you then transfer a file with DOS line breaks to Linux, the file is often interpreted as one long line and this usually breaks things! VSCode, always uses Linux line breaks. But the `cat -A` command featured here is handy.

{% include callout.html content="To convert a file with DOS line breaks to Linux, you can use the `dos2unix`: e.g. `dos2unix file.txt`. There is a file in the Class_Files folder with DOS line breaks:
<br><br>
    [magitz@login3 ~]$ cat -A /blue/bsc4452/share/Class_Files/data/DOS_formatted_file.txt<br>
    This is an example DOS text file.^M$<br>
    ^M$<br>
    Notice the extra new line characters when viewed with cat -A.^M$<br>
    ^M$<br>
    Creating a file on Windows using DOS line breaks and uploading the file to^M$<br>
    Linux is a constant source of pain. When you look at the file, everything^M$<br>
    seems normal. But Linux commands will often read the file as one long line.^M$<br>
    This breaks many things and causes trouble...^M$<br>
    ^M$<br>
    To convert a DOS file to Linux, use the dos2unix command:^M$<br>
    dos2unix file.text^M$<br>

" type="warning"%}

* p. 277: **`sort`**: We have seen the `sort` command before. This section points out some of the many options that `sort` has.
* p. 280: **`sort`**: This section on sort introduces the idea of thinking of a data table as consisting of rows of *records* and columns of *fields*. 
* p. 280: **`sort`**: The `distros.txt` file can be found at `/blue/bsc4452/share/Class_Files/TLCL_files/distros.txt`. Lots of great examples of playing with data in this section!

{% include tip.html content="You may notice that the text starts with a basic command like `cut -f 4 distros.txt` and then adds another transformation, or changes an option to get a slightly different output. This iterative process, starting simple and refining to achieve a desired result is an excellent strategy when approaching a problem. A command line like the one on 290--`sort -k 3.7nbr -k 3.1nbr -k 3.4nbr distros.txt > distros-by-date.txt`--is not written fully formed, fully functional from the start; it is the product of testing, modifying, refining. Do not expect to write such commands from scratch, do not believe that the author did either!" %}

* p. 290 & 291: **`paste`** and **`join`**: `paste` can be useful, but keep in mind that the order of records in the files must be the same! `join` however can be used to combine files that have a shared column of data. We will look at joins more when we get to databases. Have a look at this section, but don't worry too much about the details.

* p. 293 - 298: **Comparing Text**: You can skip the rest of the chapter. The `diff` command can be useful, but there's too much to learn here...

* p. 298: **Editing on the Fly**: `tr` can be useful, so have a quick look at this section. `sed` is super powerful, this is a quick introduction. `sed` allows you to do regular expression find and replace like operations from the command line. I would suggest looking at this section, but focus on the substitution options: e.g. `s/first/second/g`. The text has a ton of great examples, and maybe one of them speaks to you, but I think it may be overwhelming!

* p. 309: **`aspell`**: skip this section.