---
layout: post
title: Numpy Cheat Sheet
key: 20201105
tags:
  - Python
  - Numpy
  - data structure
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



## Array


```python
import numpy as np
v = np.array([9,10])
w = np.array([11,12])

print(v.dot(w))
```

    219



```python
a = np.array([1,2,3])
print(type(a))
print(a.shape)
a[0] = 5
print(a)

b = np.array([[1,2,3],[4,5,6]])
print(b.shape)
print(b[0,0],b[1,2])
```

    <class 'numpy.ndarray'>
    (3,)
    [5 2 3]
    (2, 3)
    1 6



```python
a = np.zeros((2,2))
print(a)

b = np.ones((1,2))
print(b)

c = np.full((2,2),7)
print(c)

d = np.eye(2)
print(d)

e = np.random.random((5,5))
print(e)
```

    [[0. 0.]
     [0. 0.]]
    [[1. 1.]]
    [[7 7]
     [7 7]]
    [[1. 0.]
     [0. 1.]]
    [[0.1288066  0.18430645 0.01481196 0.71482745 0.91589332]
     [0.81400802 0.00570742 0.89510717 0.91255094 0.8900138 ]
     [0.8986712  0.64270948 0.14000318 0.95191005 0.05470329]
     [0.50180441 0.59401076 0.80959712 0.09922184 0.83538349]
     [0.28235452 0.06324428 0.30294262 0.48719999 0.41890105]]


## Array Indexing


```python
a = np.array([[1,2,3,4],[5,6,7,8],[9,10,11,12]])
b = a[:2,1:3]


#a slice of an array is a view into the same data, so modifying it will modify the original array
print(a[0,1])
b[0,0] = 77
print(a[0,1])
```

    2
    77



```python
row_r1 = a[1,:]
row_r2 = a[1:2,:]
print(row_r1, row_r1.shape)
print(row_r2, row_r2.shape)

col_r1 = a[:,1]
col_r2 = a[:,1:2]
print(col_r1,col_r1.shape)
print(col_r2,col_r2.shape)
```

    [5 6 7 8] (4,)
    [[5 6 7 8]] (1, 4)
    [77  6 10] (3,)
    [[77]
     [ 6]
     [10]] (3, 1)



```python
a = np.array([[1,2],[3,4],[5,6]])
print(a[[0,1,2],[0,1,0]])

print(np.array([a[0,0],a[1,1],a[2,0]]))
```

    [1 4 5]
    [1 4 5]


### selecting or mutating


```python
a = np.array([[1,2,3],[4,5,6],[7,8,9],[10,11,12]])
print(a)
b= np.array([0,1,2,0])
#select
print(a[range(4),b])
#mutate
a[range(4),b]+=10
print(a)
a[np.arange(4),b]+=10
print(a)
```

    [[ 1  2  3]
     [ 4  5  6]
     [ 7  8  9]
     [10 11 12]]
    [ 1  5  9 10]
    [[11  2  3]
     [ 4 15  6]
     [ 7  8 19]
     [20 11 12]]
    [[21  2  3]
     [ 4 25  6]
     [ 7  8 29]
     [30 11 12]]


### Boolean array indexing


```python
a = np.array([[1,2,1],[1,3,4],[5,6,1]])
bool_idx = (a > 2)
print(bool_idx)
print(a[bool_idx])
print(a>2)
print(a[a>2])
```

    [[False False False]
     [False  True  True]
     [ True  True False]]
    [3 4 5 6]
    [[False False False]
     [False  True  True]
     [ True  True False]]
    [3 4 5 6]


### Data Types


```python
x = np.array([1,2])
print(x.dtype)
x = np.array([1.0,2.0])
print(x.dtype)
x = np.array([1,2],dtype=np.float64)
print(x)
```

    int64
    float64
    [1. 2.]


### Array math


```python
x = np.array([[1,2],[3,4]],dtype=np.float64)
y = np.array([[5,6],[7,8]],dtype=np.float64)

print(x+y)
print(np.add(x,y))

print(x-y)
print(np.subtract(x,y))

print(x*y)
print(np.multiply(x,y))

print(x/y)
print(np.divide(x,y))

print(np.sqrt(x))
```

    [[ 6.  8.]
     [10. 12.]]
    [[ 6.  8.]
     [10. 12.]]
    [[-4. -4.]
     [-4. -4.]]
    [[-4. -4.]
     [-4. -4.]]
    [[ 5. 12.]
     [21. 32.]]
    [[ 5. 12.]
     [21. 32.]]
    [[0.2        0.33333333]
     [0.42857143 0.5       ]]
    [[0.2        0.33333333]
     [0.42857143 0.5       ]]
    [[1.         1.41421356]
     [1.73205081 2.        ]]


#### dot operation


```python
x = np.array([[1,2],[3,4]])
y = np.array([[5,6],[7,8]])

v = np.array([9,10])
w = np.array([11,12])

print(v.shape)

print(v.dot(w))
print(np.dot(v,w))

print(x.dot(v))
print(np.dot(x,v))

print(x.dot(y))
print(np.dot(x,y))
```

    (2,)
    219
    219
    [29 67]
    [29 67]
    [[19 22]
     [43 50]]
    [[19 22]
     [43 50]]


### sum


```python
x = np.array([[1,2],[3,4]])
print(np.sum(x))
print(np.sum(x,axis=0))
print(np.sum(x,axis=1))
```

    10
    [4 6]
    [3 7]


### transpose


```python
x = np.array([[1,2],[3,4]])
print(x)

print(x.T)

v = np.array([1,2,3])
print(v,v.shape)
print(v.T,v.T.shape)
```

    [[1 2]
     [3 4]]
    [[1 3]
     [2 4]]
    [1 2 3] (3,)
    [1 2 3] (3,)


### Broadcasting


```python
x = np.array([[1,2,3],[4,5,6],[7,8,9],[10,11,12]])
v = np.array([1,0,1])
y = np.empty_like(x)

for i in range(4):
    y[i,:] = x[i,:] + v

print(y)
```

    [[ 2  2  4]
     [ 5  5  7]
     [ 8  8 10]
     [11 11 13]]



```python
vv = np.tile(v, (4,1))
print(vv)
y = x + vv
print(y)
```

    [[1 0 1]
     [1 0 1]
     [1 0 1]
     [1 0 1]]
    [[ 2  2  4]
     [ 5  5  7]
     [ 8  8 10]
     [11 11 13]]


Below: The line y = x + v works even though x has shape (4, 3) and v has shape (3,) due to broadcasting; this line works as if v actually had shape (4, 3), where each row was a copy of v, and the sum was performed elementwise.


```python
y = x + v
print(y)
```

    [[ 2  2  4]
     [ 5  5  7]
     [ 8  8 10]
     [11 11 13]]


#### reference
https://docs.scipy.org/doc/numpy-1.13.0/user/basics.broadcasting.html

When operating on two arrays, NumPy compares their shapes element-wise. It starts with the trailing dimensions, and works its way forward. Two dimensions are compatible when

* they are equal, or
* one of them is 1

When either of the dimensions compared is one, the other is used. In other words, dimensions with size 1 are stretched or “copied” to match the other.

temp * w => dimension(3,1) * dimension(2) => dimension(3,2) * dimension(2)
=> np.array([[1,1],[2,2],[3,3]]) * np.array([4,5])

v * w_reshape => dimension(3) * dimension(2,1) => dimension(3) * dimension(2,3) => np.array([1,2,3]) * np.array([[4,4,4],[5,5,5]])



```python
v = np.array([1,2,3])
w = np.array([4,5])

temp = np.reshape(v,(3,1))
w_reshape = np.reshape(w,(2,1))

print(np.reshape(v,(3,1)) * w)
print(v * np.reshape(w,(2,1)))
```

    [[ 4  5]
     [ 8 10]
     [12 15]]
    [[ 4  8 12]
     [ 5 10 15]]



```python
x = np.array([[1,2,3],[4,5,6]])
print(x + v)
```

    [[2 4 6]
     [5 7 9]]



```python
print(x + np.reshape(w,(2,1)))
```

    [[ 5  6  7]
     [ 9 10 11]]



```python
print(x*2)
print(x**2)
```

    [[ 2  4  6]
     [ 8 10 12]]
    [[ 1  4  9]
     [16 25 36]]




