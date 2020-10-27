---
layout: post
title: Threas&Concurrency
key: 20201027
tags:
  - OS
  - Linux
  - Ubuntu
  - Threas
  - Concurrency
---

## Definition

* Instance of a program
An instance of a program is a copy of an executable version of the program that has been written to the computer's memory. 

* Process
When we run a program, those instructions are copied into memory and space is allocated for variables and other stuff required to manage its execution. This running instance of a program is called a process and it's processes which we manage.

### Top

<!--more-->

## What do we need to support threads?

thread data structure

mechanisms to create and manage threads

mechanisms to fasely coordinate among threads


concurrent inconsistency issue->synchronization mechanisms

mutual exclusion
exclusive access to only one thread at a time

mutex

waiting on other threads
-specific condition before proceeding
-condition variable

waking up other threads from wait state


## creation

thread type:
thread ID, pc, sp, registers, stack, attributes

thread creation:
fork(proc,args)
not unix fork which is to create a new process


