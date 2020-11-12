---
layout: post
title: Numpy Cheat Sheet
key: 20201105
tags:
  - Python
  - Numpy
---

## Creating Arrays

list = []
array = np.array(list)

## Array Index

### Single Index
```python
>>> import numpy as np
>>> x = np.arange(10)
>>> x[2]
2
>>> x[0]
0
>>> x[10]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: index 10 is out of bounds for axis 0 with size 10
>>> x[9]
9
>>> x[-2]
8
```

## array Dimension

### list dimension
```python
dim1 = len(list)
dim2 = len(list[0])
dim3 = len(list[1])
```

## I/O


## Array Mathematics


