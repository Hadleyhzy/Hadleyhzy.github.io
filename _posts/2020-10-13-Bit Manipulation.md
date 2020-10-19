---
layout: post
title: Bit Manipulation
key: 20201013
tags:
  - C++
  - data structure and algorithm
  - Bit Manipulation
---

## Power of Two
1. Get the Rightmost 1-bit
two's complement:
`-x = ~x + 1;`

``` c++
bool isPowerOfTwo(int n){
	return (n&(-n))==n;
}
```

2. Turn off the rightmost 1-bit
``` c++
bool isPowerOfTwo(int n){
	return n&(n-1)==0;
}
```

* 231 Power of Two([Q](https://leetcode.com/problems/power-of-two/):[A]())
<!--more-->

## XOR Operator
Imagine, you have a problem to indentify an array element (or elements), which appears exactly given number of times. Probably, the key is to build first an array bitmask using XOR operator. Examples: In-Place Swap, Single Number, Single Number II.

* 136 Single Number([Q](https://leetcode.com/problems/single-number/):[A]())
* 137 Single Number II([Q](https://leetcode.com/problems/single-number-ii/):[A]())
* 260 Single Number III([Q](https://leetcode.com/problems/single-number-iii/):[A]())



## Count set bits


## Bitwise Operation
* Bitwise And of Numbers Range([Q](https://leetcode.com/problems/bitwise-and-of-numbers-range/):[A]())
1.brute force 2.bit shift operation 3.Brian Kernighan's Algorithm
{:.info}



