---
layout: post
title: String
key: 20201015
tags:
  - C++
  - data structure and algorithm
  - Hash Table
---

## String Definition

## Map
### Map Definition

```c++
//using stringstream class

//using std::stoi()
string str="45";
int num = std::stoi(str);

//int to string


```
<!--more-->

### Map Basic Operation
```c++
std::map<char,int>mymap;
//find
mymap['b']=20;
//an iterator to the element, if an element with specified key is found or map::end otherwise.
std::map<char,int>::iterator it = mymap.find('b');

//erase
mymap['c']=30;
mymap.erase('c');//erasing by key
it=mymap.find('e');
mymap.erase(it,mymap.end());//erasing by range

```

### std::map::lower_bound/std::map::upper_bound

```c++
std::map<char,int> mymap;
mymap['a']=10;
mymap['b']=20;
mymap['c']=30;
mymap['d']=40;
mymap['e']=50;

auto il=mymap.lower_bound('b');  //il points to b
auto iu=mymap.upper_bound('d');  //iu points to e(not d!)
```