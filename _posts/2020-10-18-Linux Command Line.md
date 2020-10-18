---
layout: post
title: Linux Command Line
key: 20201018
tags:
  - Linux
  - Ubuntu
---


## Basic Command Line

### The Shell, Bash
Sheel is a program that takes commands from the keyboard and gives them to the operating system to perform.
If you would like to know which shell you are using you may use a command called `echo` to display a system variable stating your current shell.

``` bash
hadley@hadley-MacBookPro:~$ echo $SHELL
/bin/bash
```

### pwd
``` bash
hadley@hadley-MacBookPro:~$ pwd
/home/hadley
```

### ls
To list the contents of your current working directory:  
``` bash
hadley@hadley-MacBookPro:~/Developments$ ls
data_structure_and_algorithm  Hadleyhzy.github.io
```

To list the contents of desired working directory:
```bash
hadley@hadley-MacBookPro:~/Developments$ ls /home
hadley
```
Hidden Files:
```bash
hadley@hadley-MacBookPro:~/Developments$ ls -a
.  ..  data_structure_and_algorithm  Hadleyhzy.github.io
```

Hidden Files without `.` and `..` directory in the list:
```bash
hadley@hadley-MacBookPro:~/Developments/Hadleyhzy.github.io$ ls -A
404.html          .eslintrc                  LICENSE            screenshot.png
about.md          favicon.ico                node_modules       
```

Enable and Disable colored output:
You can enable and disable the colored output of the ls command using the –color option. The –color option takes 3 values, never, always and auto.

Long listing format of ls:
``` bash
hadley@hadley-MacBookPro:~/Developments$ ls -l
total 8
drwxrwxr-x 20 hadley hadley 4096 Okt 18 12:48 data_structure_and_algorithm
drwxrwxr-x 17 hadley hadley 4096 Okt 18 11:15 Hadleyhzy.github.io
```

* First character indicates whether it is a normal file ( - ) or directory ( d ).
* Next 9 characters are permissions for the file or directory. 
* The next field is the number of blocks. 
* The next field is the owner of the file or directory.
* The next field is the group the file or directory belongs to (users in this case).
* Following this is the file size(default size should be bytes).
* Next up is the file modification time.
* Finally we have the actual name of the file or directory.

Changin file size unit in long listing format:
``` bash
hadley@hadley-MacBookPro:~/Documents/test6$ ls -l --block-size=k
total 44K
-rwxrwxr-x 1 hadley hadley 38K Okt 10 22:57 main
-rw-rw-r-- 1 hadley hadley  1K Okt 10 22:55 main.cpp
hadley@hadley-MacBookPro:~/Documents/test6$ ls -l --block-size=M
total 1M
-rwxrwxr-x 1 hadley hadley 1M Okt 10 22:57 main
-rw-rw-r-- 1 hadley hadley 1M Okt 10 22:55 main.cpp
hadley@hadley-MacBookPro:~/Documents/test6$ ls -l --block-size=G
total 1G
-rwxrwxr-x 1 hadley hadley 1G Okt 10 22:57 main
-rw-rw-r-- 1 hadley hadley 1G Okt 10 22:55 main.cpp
```
Printing human readable file size in long listing format:
``` bash
hadley@hadley-MacBookPro:~/Documents/test6$ ls -lh
total 44K
-rwxrwxr-x 1 hadley hadley 38K Okt 10 22:57 main
-rw-rw-r-- 1 hadley hadley 198 Okt 10 22:55 main.cpp
```
Getting help:
```bash
hadley@hadley-MacBookPro:~/Documents/test6$ man ls
```

### Paths
Absolute paths specify a location (file or directory) in relation to the root directory. You can identify them easily as they always begin with a forward slash ( / )

Relative paths specify a location (file or directory) in relation to where we currently are in the system. They will not begin with a slash.

#### More on path
``` bash
hadley@hadley-MacBookPro:~$ cd ~
hadley@hadley-MacBookPro:~$ pwd
/home/hadley
hadley@hadley-MacBookPro:~$ ls ./Books/
Modern+Operating+Systems+4th@www.java1234.com.pdf
hadley@hadley-MacBookPro:~$ ls ./Books/../
Books    Developments  Downloads  Pictures  snap       Videos
Desktop  Documents     Music      Public    Templates
```

#### home directory and root directory
``` bash
hadley@hadley-MacBookPro:~$ pwd
/home/hadley
hadley@hadley-MacBookPro:~$ ls ../../
bin    cdrom  home   lib64       media  proc  sbin  sys  var
boot   dev    lib    libx32      mnt    root  snap  tmp
build  etc    lib32  lost+found  opt    run   srv   usr
hadley@hadley-MacBookPro:~$ ls /
bin    cdrom  home   lib64       media  proc  sbin  sys  var
boot   dev    lib    libx32      mnt    root  snap  tmp
build  etc    lib32  lost+found  opt    run   srv   usr
```
If you run the command cd without any arguments then it will always take you back to your home directory.
``` bash
hadley@hadley-MacBookPro:~/Documents$ pwd
/home/hadley/Documents
hadley@hadley-MacBookPro:~/Documents$ cd 
hadley@hadley-MacBookPro:~$ pwd
/home/hadley
```

### Special folders
* /etc - Stores config files for the system.
* /var/log - Stores log files for various system programs. (You may not have permission to look at everything in this directory. Don't let that stop you exploring though. A few error messages never hurt anyone.)
* /bin - The location of several commonly used programs (some of which we will learn about in the rest of this tutorial.
* /usr/bin - Another location for programs on the system.


## Files
Everything is a file
A text file is a file, a directory file, your keyboard is a file, your monitor is a file. Under linux system, it igonres the extension and looks inside the file to determine what type of file it is. `file` command can be used to find certain type of file is.

``` bash
hadley@hadley-MacBookPro:~/Developments$ file Hadleyhzy.github.io/
Hadleyhzy.github.io/: directory
hadley@hadley-MacBookPro:~/Developments$ file Hadleyhzy.github.io/index.html 
Hadleyhzy.github.io/index.html: UTF-8 Unicode text
hadley@hadley-MacBookPro:~/Developments$ file data_structure_and_algorithm/array/leetcode_array/283_move_zeros.cpp 
data_structure_and_algorithm/array/leetcode_array/283_move_zeros.cpp: C++ source, UTF-8 Unicode text
```

Deal with spaces in names  
* Quotes  
* Escape Characters  
``` bash
hadley@hadley-MacBookPro:~/Developments$ cd 'holiday photos'
hadley@hadley-MacBookPro:~/Developments/holiday photos$ pwd
/home/hadley/Developments/holiday photos
hadley@hadley-MacBookPro:~/Developments/holiday photos$ cd ..
hadley@hadley-MacBookPro:~/Developments$ cd holiday\ photos
hadley@hadley-MacBookPro:~/Developments/holiday photos$ pwd
/home/hadley/Developments/holiday photos
```










