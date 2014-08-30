---
layout: post
title: Basic UNIX Commands
description: Some basic commands
categories: blog
---

## UNIX commands
Here are some basic commands in UNIX

#### man
Display manual page

* man -S3 printf
* man ls
* man man
* man -k compare

### Directories
Commands for directory

* pwd
* cd / or cd pathname or cd ..
* ls -l(extra info) or ls -a(all files)
* mkdir
* rmdir

### Displaying files
Display file contents

* `cat filename`: display all
* `more/less filename`: navigation
* `head/tail filename`: beginning//end of the file

### File operations
* `mv`: move
* `cp`: copy
* `rm`: delete

### Pattern expansion
Globbing-operate on the file names in the local directory

* `*~.txt`: all filename ending with ~
* `file0[123].txt`: match file01.txt, file02.txt, file03.txt
* `file0[!123].txt`: opposite as above
* `ab?d.txt`: match one character

Expansion

* `file{1,a,X}.txt`: file1.txt, filea.txt, fileX.txt
* `{a,b,c}{1,2,3}`: {a1,a2,a3,b1,b2,b3,c1,c2,c3}

### Redirection and pipes
* `./myProgram < file1.txt > output.txt`
* `>>`: redirect the output to a file but append to the original contents
* `diff x.c y.c | less`: serve as less's input; same as `diff x.c y.c > temp` and then `less temp`

### Searching
* `grep myFunction *.c`: search myFunction in all .c files
*  `grep '^.\{4\}w.\{3\}$' /usr/share/dict/words`: use regular expression to find words in the form xxxxwxxx
* `find`

### Remote
* `ssh username@servername`: login
* `scp myFile username@servername: myFolder/`: move local file to directory

## End
More will be added

[startupjing]:    http://startupjing.github.io  "startupjing"
[1]:    {{ page.url}}  ({{ page.title }})

