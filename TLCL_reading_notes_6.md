---
title: "Notes on TLCL Ch 23"
tags: [reading notes]
sidebar: home_sidebar
permalink: TLCL_6.html
toc: false
---

## Ch 23: Compiling Programs

This section gets into compiling programs from source code. As the chapter mentions, this is a bit of a lost/dying art, but I think worth some time to learn about.

On HiPerGator, users can request that UFRC staff install applications for them. But not all researchers have a staff able to do that, so it is good to at least understand how to compile an application.

As the text says, compiling is the process of translating the program written in some programming language into the native language of the processor. We won't do this much in the class, because scripting languages like Bash, Python and others, are interpreted languages. Rather than compiling before running the program, interpreted languages go line by line, translating each command for the processor as the script is run.

Interpreted languages are generally slower than compiled languages, but typically that isn't an issue and they tend to be easier to for developers, thus their popularity.

For programming languages that do need to be compiled, you need to compile the code before it can be run. The code is turned into a binary application--essentially 1s and 0s, the native language of the CPU--and executed when you run the application. If you change the code, you have to recompile the binary.

The most common compiled programming languages are C and C++. One thing we will see in this section is that while you may not know how to write C code, and the details will be a bit confusing, the fundamental structure and methods of coding are quite similar. *Once you know one coding language, it is easier to learn additional languages.*

### HiPerGator and Modules
We'll talk about this in class, but it is best to load a module for compilers and most applications (even Python when we get there).

So while we can do what the text does on p. 352:
```bash
[magitz@login4 src]$ which gcc
/usr/bin/gcc
[magitz@login4 src]$ gcc --version
gcc (GCC) 4.8.5 20150623 (Red Hat 4.8.5-16)
Copyright (C) 2015 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

[magitz@login4 src]$
```

We are better off loading the gcc module. We get a newer version of gcc and it is maintained for users to compile applications.

```bash
[magitz@login2 ~]$ module load gcc
[magitz@login2 ~]$ which gcc
/apps/compilers/gcc/5.2.0/bin/gcc
[magitz@login2 ~]$ gcc --version
gcc (GCC) 5.2.0
Copyright (C) 2015 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

[magitz@login2 ~]$
```
 

* p. 352: **Obtaining the Source Code**: We can't use FTP on the cluster (too many security issues) so we'll use wget and a URL to download the source code:

    ```bash
    [magitz@login4 ~]$ wget http://ftp.gnu.org/gnu/diction/diction-1.11.tar.gz
    --2018-09-06 15:58:33--  http://ftp.gnu.org/gnu/diction/diction-1.11.tar.gz
    Resolving ftp.gnu.org (ftp.gnu.org)... 208.118.235.20, 2001:4830:134:3::b
    Connecting to ftp.gnu.org (ftp.gnu.org)|208.118.235.20|:80... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 141062 (138K) [application/x-gzip]
    Saving to: ‘diction-1.11.tar.gz’

    100%[======================================>] 141,062      832KB/s   in 0.2s   

    2018-09-06 15:58:33 (832 KB/s) - ‘diction-1.11.tar.gz’ saved [141062/141062]
    ```
 

Then you can proceed on with extracting the tar file and other steps.

* p. 356: **Examining the Source Tree**: TLCL has you use `less` to look at the `diction.c` file. Go a few pages into the file, you probably won't understand everything, but you should see some familiar things: `if`, `else`, `for`, `while`, etc. These are universal to programming languages! The exact syntax differs, but the concepts are all the same!

  Continue with `./configure` and `make`.

 

p. 360: **Installing the Program**: We can't run the `sudo make install` command since we don't have sudo access.

We have two options here.

1. Just run the program from here: `./diction -h` will show the help contents:

    ```bash
    [magitz@login4 diction-1.11]$ ./diction -h
    Usage: diction [-b] [-d] [-f file [-n|-L language]] [-q] [file ...]
        diction [--beginner] [--ignore-double-words]
                [--file file [--no-default-file|--language]] [--quiet] [file ...]
        diction --version
    <...snip...>
    ```

2. We could decide where we want to install the application ahead of time. If we read the `INSTALL` file, on line 106, it tells you that you can use the `--prefix` option to tell it where to install the application. So if I want to install in my home directory, I can do:

    ```bash
    [magitz@login4 diction-1.11]$ ./configure --prefix=/home/magitz
    checking build system type... x86_64-unknown-linux-gnu
    checking host system type... x86_64-unknown-linux-gnu
    checking for gcc... gcc
    <...snip...>

    [magitz@login4 diction-1.11]$ make
    gcc -c -I. -DSHAREDIR=\"/home/magitz/share\" -DLOCALEDIR=\"/home/magitz/share/locale\" -g -O2 -pipe -Wno-unused -Wshadow -Wbad-function-cast -Wmissing-prototypes -Wstrict-prototypes -Wcast-align -Wcast-qual -Wpointer-arith -Wcast-align -Wwrite-strings -Wmissing-declarations -Wnested-externs -Wundef -pedantic -fno-common diction.c
    <...snip...>

    [magitz@login4 diction-1.11]$ make install
    [ -d /home/magitz/bin ] || /usr/bin/install -c -m 755 -d /home/magitz/bin
    /usr/bin/install -c diction /home/magitz/bin/diction
    <...snip...>

    [magitz@login4 diction-1.11]$ diction -h
    Usage: diction [-b] [-d] [-f file [-n|-L language]] [-q] [file ...]
        diction [--beginner] [--ignore-double-words]
                [--file file [--no-default-file|--language]] [--quiet] [file ...]
        diction --version
    <...snip...>
    ```

  Notice that with the `--prefix` option, the `make install` step shows that it is copying stuff to `/home/magitz/bin` and when I type `diction -h`, the shell finds diction in my path and gets the help info.

  