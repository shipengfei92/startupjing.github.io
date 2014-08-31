---
layout: post
title: Unix+Vim+GDB
description: Some basic commands for Unix, Vim and GDB
categories: blog
---

**This post may be long. You can use navigation bar on the right to find what you need.**

## Basic Unix

#### man
Display manual page

* `man -S3 printf`
* `man ls`
* `man man`
* `man -k compare`

### Directories
Commands for directory

* `pwd`
* `cd /` or `cd pathname` or `cd ..`
* `ls -l(extra info)` or `ls -a`(all files)
* `mkdir`
* `rmdir`

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


## Basic Vim

Here are some basic commands for Vim
`vim filename` to open file

### Navigation

* `h,j,k,l` left,down,up,right
* `use arrow keys`
* `$` move to the end of current line
* `^` move to the front of current line

### Exit

* `:q!` exit without saving
* `:wq` save and exit
* `:w [filename]` save with filename
* `:[line1],[line2] w [filename]` save contents between line1 and line2

### Delete

* `x` delete character at current cursor
* `d [number] [object]` or `[number] d [object]` operate deletion by [number] times 
* `dd` delete current line
* `dw` delete word and space
* `de` delete word but not space
* `d$` delete all contents after cursor on the current line

### Insert

* `i` go into insert mode and edit; then `ESC` to quit mode
* `:r [filename]` append file contents at cursor
* `o` open a new line and go into insert mode
* `yy` yank current line; `2yy` yank two lines; `yw` yank a word
* `p` paste after cursor and `P` paste before cursor

### Cancel commands

* `u` cancel previous command
* `U` cancel previous command at current line
* `C+r` cancel `u` and `U`

### Replace

* `p` paste buffer content to location
* `r [character]` replace current character with input
* `c [number] [object]` or `[number] c [object]` delete and then go into insert mode; options are `cw`, `c$` and `ce`
* `:s/[word1]/[word2]/g` replace all word1 with word2 on current line
* `:%s/[word1]/[word2]/g` replace all word1 with word2 for all lines
* `:[line1],[line2]s/[word1]/[word2]/g` replace all word1 with word2 between line1 and line2

### Locate

* `C+g` show current line number and total line number
* `SHIFT+g` go to last line
* `SHIFT+g` `[line number]` `SHIFT+g` go to line number

### Search

* `/ [keyword]` search keyword; press `n` to find next
* `? [keyword]` search keyword backwards; press `SHIFT+n` to find next
* `:set ic` set to ignore case
* `%` move cursor at "(, [, or {" and use `%` to find corresponding pairs

### Execute command from outside

* `:! [command]` such as `:! ls` and `:! pwd`

## Basic GDB

### Running program
* `gdb [hello.c]` start GDB
* `run` run program
* `c` or `c [count]` continue program
* `kill` or `Control+c` kill running program

### Breakpoints
* `break [function name]` breakpoint at a function
* `break [filename]: [line]` breakpoint in file at certain line
* `info break` information about breakpoints
* `delete [breakpoint num]` delete certain breakpoint
* `enable [break num]` or `disable [break num]` enable and disable breakpoint
* `clear` clear all breakpoints
* `cond [breakpoint num] [condition]` break at this point if condition statisfied

### Trace
* `step` and `stepi` next instruction, go into function
* `next` and `nexti` next instruction, don't go into function

### Track variables
* `print [var]` print variable info
* `print &[var]` print address of variable
* `display [var]` print variable after each stepping
* `delete display [var num]` delete variable display
* `x/[number of bytes] [start addr]` print memory
* `info registers` display registers

### Program control
* `set var [var]=[val]` set variable value

### View code
* `list` or `list [function]` list nearby code
* `disassemble [label/function]` view assembly code

### Cheat sheet
See more on Marc Haisenko's GDB [cheat sheet][2]

## Ending
More in the future


[startupjing]: http://startupjing.github.io  "startupjing"
[1]: {{ page.url}}  ({{ page.title }})
[2]: /files/post/gdbsheet.pdf



