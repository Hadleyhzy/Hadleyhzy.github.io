---
layout: post
title: Backtracking
key: 20201019
tags:
  - C++
  - data structure and algorithm
  - Backtracking
---

## String Definition

### Standard Backtracking
* 294 Flip Game II([Q](https://leetcode.com/problems/flip-game-ii/):[A]())

## Permutations
### Permutations for dictinct data variables
```c++
void permutation(vector<int> &num, int l, vector<vector<int> > &res) {
    if (l == num.size()-1) {
        res.push_back(num);
        return;
    }
        
    for (int i = l; i < num.size(); i++) {
        swap(num[i], num[l]);
        permutation(num, l+1, res);
        swap(num[i], num[l]);
    }
}
```

### Permutations for duplicated data variables
```c++
void permu(vector<int> nums, int l, vector<vector<int>>&res){
    if(l==nums.size()-1){
        res.push_back(nums);
    }
    for(int i=l;i<nums.size();i++){
        if(i==l||nums[i]!=nums[l]){
            swap(nums[l],nums[i]);
            permu(nums, l+1, res);
        }
    }
}
```

* 276 Palindrome Permutation II([Q](https://leetcode.com/problems/palindrome-permutation-ii/):[A]())

## Combinations


