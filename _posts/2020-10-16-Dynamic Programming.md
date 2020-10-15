---
layout: post
title: Array
key: 20201015
tags:
  - C++
  - data structure and algorithm
  - Dynamic Programming
---

## 1.Array Definition
```c++
//Tree Declaration
struct TreeNode
{
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode():val(0),left(nullptr),right(nullptr){};
    TreeNode(int x):val(x),left(nullptr),right(nullptr){};
    TreeNode(int x, TreeNode* l,TreeNode* r):val(x),left(l),right(r){};
};
//Tree Initializaiton with default value zero
TreeNode *root = new TreeNode(0, nullptr, nullptr);
```
<!--more-->

## Array Basic Operation
### Rotate Array
* 189 Rotate Array([Q](https://leetcode.com/problems/rotate-array/):[A](https://github.com/Hadleyhzy/data_structure_and_algorithm/blob/master/array/leetcode_array/189_rotate_array.cpp))

Note that reverse function range used is [first, last), which contains all the elements between first and last, including the element pointed by first but not the element pointed by last. 
{:.info}
Complexity Linear in half the distance between first and last, swap elements.
{:.info}

## Topic
### DFS/Backtracking Intuitive approach to dynamic programming
#### 2D array
* 221 Maximal Square([Q](https://leetcode.com/problems/maximal-square/):[A]())(DFS->DP)

