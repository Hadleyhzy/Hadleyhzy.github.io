---
layout: post
title: Numpy Cheat Sheet
key: 20201105
tags:
  - Python
  - Numpy
---

# List

## List Basic Operation

* select column from 2d list
```python
y = [ x[col] for x in list ]
```
* combine multiple list

```python
y = [ [x1[col1],x2[col2],x3[col3]] for (x1,x2,x3) in zip (list1, list2, list3)]
```

* append
```python
# animals list
animals = ['cat', 'dog', 'rabbit']

# list of wild animals
wild_animals = ['tiger', 'fox']

# appending wild_animals list to the animals list
animals.append(wild_animals)

print('Updated animals list: ', animals)
Output
```
```python
Updated animals list:  ['cat', 'dog', 'rabbit', ['tiger', 'fox']]
```


## numpy.array and list conversion

```python
list1 = array1.tolist()

array2 = np.array(list1)
```

<!--more-->
# Numpy.array()

## create array

```python
>>> arr = np.array([1,2,3,4,5])
>>> arr
array([1, 2, 3, 4, 5])
>>> print(arr)
[1 2 3 4 5]
>>> print(type(arr))
<class 'numpy.ndarray'>
>>> arr = np.array((1,2,3,4,5)).    #tuple as input
>>> arr
array([1, 2, 3, 4, 5])
>>> print(arr)
[1 2 3 4 5]
>>> print(type(arr))
<class 'numpy.ndarray'>
>>> arr = np.array([[1,2,3],[4,5,6]])       #2d array
>>> print(arr)
[[1 2 3]
 [4 5 6]]
>>> arr = np.array([[[1,2,3],[4,5,6]],[[1,2,3],[4,5,6]]])  #3d array
>>> print(arr)
[[[1 2 3]
  [4 5 6]]

 [[1 2 3]
  [4 5 6]]]
>>> print(arr.ndim)     #array dimension
3
>>> arr = np.array([1, 2, 3, 4], ndmin=5)
>>> print(arr)
[[[[[1 2 3 4]]]]]
>>> print(arr.ndim)
5
>>> np.array([1,2,3],dtype=complex)     #array type provided
array([1.+0.j, 2.+0.j, 3.+0.j])
>>> np.arange(10)      #using arange()
array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
>>> np.zeros((2,3))   #using zeros()
array([[0., 0., 0.],
       [0., 0., 0.]])
>>> np.arange(2,10,dtype=float)
array([2., 3., 4., 5., 6., 7., 8., 9.])
>>> np.arange(2,3,0.3)
array([2. , 2.3, 2.6, 2.9])
>>> np.linspace(1,10,3). #with specified number of elements
array([ 1. ,  5.5, 10. ])
>>> np.linspace(1,10,5)
array([ 1.  ,  3.25,  5.5 ,  7.75, 10.  ])
```

* array indice
```python
>>> i,j=np.indices((2,3))
>>> i
array([[0, 0, 0],
       [1, 1, 1]])
>>> j
array([[0, 1, 2],
       [0, 1, 2]])
>>> M = 2*i + 3*j
>>> M
array([[0, 3, 6],
       [2, 5, 8]])

>>> np.indices((2,3))
array([[[0, 0, 0],
        [1, 1, 1]],

       [[0, 1, 2],
        [0, 1, 2]]])
```

* array zeros
```python

```

## Array basic operation

* transpose array
```python 
arr = array.T
```

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


### array Dimension

#### list dimension
```python
dim1 = len(list)
dim2 = len(list[0])
dim3 = len(list[1])
```

### count

```python
>>> array = np.array([1,1,1,2,2,3])
>>> array
array([1, 1, 1, 2, 2, 3])
>>> unique, counts = np.unique(array, return_counts=True)
>>> unique
array([1, 2, 3])
>>> counts
array([3, 2, 1])
```



## I/O


## Array Mathematics


