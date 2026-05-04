---
title: "Notes on TLCL Ch 23"
tags: [linux]
sidebar: home_sidebar
permalink: TLCL_7.html
toc: true
summary: "Compiling programs is the process of taking the source code and turning it into machine code to be run. Bash and Python are called <i>interpreted</i> languages because compilation occurs while the program runs, line by line, by the interpreter. C and C++ are common compiled languages, and their code must be compiled before it can be run. While compiling applications can be difficult, in most cases, it is as simple as downloading the code and running <code>./configure; make; make install</code>."
keywords: compile, gcc, binary, configure, make, install
---

## Ch 23: Compiling Programs

This section gets into compiling programs from source code. As the chapter mentions, this is a bit of a lost/dying art, but I think it is worth some time to learn about.

On HiPerGator, users can request that UFIT-RC staff install applications for them. But not all researchers have a staff able to do that, so it is good to at least understand how to compile an application.

As the text says, compiling is the process of translating a program written in a programming language into the processor's native language. We won't do this much in the class, because scripting languages like Bash, Python and others are interpreted languages. Rather than compiling before running the program, interpreted languages execute each line as the script runs, translating each command for the processor.

Interpreted languages are generally slower than compiled languages, but that typically isn't an issue, and they tend to be easier for developers, which is why they're popular.

For programming languages that require compilation, you need to compile the code before it can be run. The code is compiled into a binary application — essentially 1s and 0s, the native language of the CPU — and executed when you run it. If you change the code, you must recompile the binary.

The most common compiled programming languages are C and C++. One thing we will see in this section is that, while you may not know how to write C code, the fundamental structure and coding methods are quite similar. *Once you know one coding language, it is easier to learn additional languages.*

### HiPerGator and Modules

We'll talk about this in class, but it is best to load a module for compilers and most applications (even Python when we get there).

So, while we can do what the text does on p. 370:

``` bash
[magitz@login8 ~]$ which gcc
/usr/bin/gcc
[magitz@login8 ~]$ gcc --version
gcc (GCC) 11.5.0 20240719 (Red Hat 11.5.0-5)
Copyright (C) 2021 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
[magitz@login8 ~]$ 
```

We are better off loading the gcc module. We get a newer version of gcc and it is maintained for users to compile applications.

```bash
[magitz@login8 ~]$ module load gcc
[magitz@login8 ~]$ which gcc
/apps/compilers/gcc/14.2.0/bin/gcc
[magitz@login8 ~]$ gcc --version
gcc (GCC) 14.2.0
Copyright (C) 2024 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

[magitz@login8 ~]$
```

* p. 370: **Obtaining the Source Code**: We can't use FTP on the cluster (too many security issues) so we'll use `curl`, as outlined on p. 371: and a URL to download the source code:

    ```bash
    [magitz@login8 ~]$ mkdir src
    [magitz@login8 ~]$ cd src
    [magitz@login8 src]$ curl -O https://ftp.gnu.org/gnu/diction/diction-1.11.tar.gz
    % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                    Dload  Upload   Total   Spent    Left  Speed
    100  137k  100  137k    0     0   427k      0 --:--:-- --:--:-- --:--:--  427k
    [magitz@login8 src]$
    ```

Then you can proceed with extracting the tar file and other steps.

* p. 373: **Examining the Source Tree**: TLCL has you use `less` to look at the `diction.c` file. Go a few pages into the file, you probably won't understand everything, but you should see some familiar things: `if`, `else`, `for`, `while`, etc. These are universal to programming languages! The exact syntax differs, but the concepts are all the same!

  Continue with `./configure` and `make`.

p. 378: **Installing the Program**: We can't run the `sudo make install` command since we don't have <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.sudo}}">sudo</a> access.

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
