---
layout: post
title: Linux Command Line - Piping and Redirection
key: 20201021
tags:
  - Linux
  - Ubuntu
  - Shell
---

## Redirecting to a file

save current command output to a file instead of printed to the screen.
```bash
hadley@hadley-MacBookPro:~/Developments/parentDirectory$ ls -l > list
hadley@hadley-MacBookPro:~/Developments/parentDirectory$ cat list
total 16
-rw-rw-r-- 1 hadley hadley  230 Okt 21 22:08 data_test.txt
-rw-rw-r-- 1 hadley hadley  230 Okt 21 21:01 data.txt
-rwxrwxrwx 1 hadley hadley   92 Okt 20 21:28 file.txt
-rw-rw-r-- 1 hadley hadley    0 Okt 21 22:08 list
drwxrwxr-x 2 hadley hadley 4096 Okt 21 21:09 test1
-rw-rw-r-- 1 hadley hadley    0 Okt 20 21:42 test.cpp
-rw-rw-r-- 1 hadley hadley    0 Okt 20 21:01 ttt
-rw-rw-r-- 1 hadley hadley    0 Okt 20 21:42 x
-rw-rw-r-- 1 hadley hadley    0 Okt 20 21:43 x1
-rw-rw-r-- 1 hadley hadley    0 Okt 20 21:42 y
```






























