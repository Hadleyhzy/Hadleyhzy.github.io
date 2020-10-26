---
layout: post
title: Linked List
key: 20201026
tags:
  - C++
  - data structure and algorithm
  - Linked List
---

## 1.Linked List Definition
```c++
//Tree Declaration
struct Node
{
    int val;
    Node *next;
    Node():val(0),next(nullptr){};
    Node(x):val(x),next(nullptr){};
    Node(x,Node* node):val(x),next(node)(); 
};
//Tree Initializaiton with default value zero
Node *node=new Node();
```
<!--more-->
## Reorder Linked List
### inplace
* 328 Odd Even Linked List([Q](https://leetcode.com/problems/odd-even-linked-list/):[A]())(two node pointers through iteration)