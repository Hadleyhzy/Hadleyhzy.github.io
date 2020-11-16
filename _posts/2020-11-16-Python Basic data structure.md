---
layout: post
title: Python Basic Data Structure
key: 20201116
tags:
  - Python
  - data structure
---

## List Basic


```python
x = [3,1,2]
print(x, x[2])
print(x[-1])
x[2] = 'foo'
x.append('bar')
print(x)
back = x.pop()
print(back,x)
```

    [3, 1, 2] 2
    2
    [3, 1, 'foo', 'bar']
    bar [3, 1, 'foo']



```python
### Slicing
```


```python
nums = list(range(5))
print(nums)
print(nums[2:4])
num = range(5)
print(num,type(num))
print(nums[2:])
print(nums[:2])
print(nums[:])
print(nums[:-1])
nums[2:4]=[8,9]
print(nums)
```

    [0, 1, 2, 3, 4]
    [2, 3]
    range(0, 5) <class 'range'>
    [2, 3, 4]
    [0, 1]
    [0, 1, 2, 3, 4]
    [0, 1, 2, 3]
    [0, 1, 8, 9, 4]



```python
list_1 = [[1,2,3,4],[5,6,7,8],[9,10,11,12]]
print(list_1[:,1:3])
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-8-965a0a36bfb7> in <module>
          1 list_1 = [[1,2,3,4],[5,6,7,8],[9,10,11,12]]
    ----> 2 print(list_1[:,1:3])
    

    TypeError: list indices must be integers or slices, not tuple


## Loops


```python
animals = ['cat', 'dog', 'monkey']
for animal in animals:
    print(animal)
```

    cat
    dog
    monkey



```python
for idx, animal in enumerate(animals):
    print('%d:%s' % (idx,animal))
```

    0:cat
    1:dog
    2:monkey


## List comprehensions


```python
nums = [0,1,2,3,4]
squares = [ x**2 for x in nums]
print(squares)
```

    [0, 1, 4, 9, 16]



```python
nums = [[1,2,3],[4,5,6],[7,8,9]]
col_2 = [ row[2] for row in nums ]
print(col_2)
```

    [3, 6, 9]



```python
nums = [0,1,2,3,4,5,6]
squares = [ x**2 for x in nums if x%2 == 0 ]
print(squares)
```

    [0, 4, 16, 36]


## Dictionary Basic


```python
d = {'cat':'cute', 'dog':'furry', 'fish':'yummy'}
print(d['dog'])
print('cat' in d)
d['banana'] = 'yellow'
print(d)
print(d.get('monkey', 'N/A'))
print(d.get('fish', 'N/A'))
del d['fish']
print(d.get('fish', 'N/A'))
```

    furry
    True
    {'cat': 'cute', 'dog': 'furry', 'fish': 'yummy', 'banana': 'yellow'}
    N/A
    yummy
    N/A



```python
for key in d:
    print(key,d[key])
```

    cat cute
    dog furry
    banana yellow



```python
for key,val in d.items():
    print(key,val)
```

    cat cute
    dog furry
    banana yellow


## dictionary comprehensions


```python
nums = [0,1,2,3,4,5]
square = { num:num*2 for num in nums}
print(square)
```

    {0: 0, 1: 2, 2: 4, 3: 6, 4: 8, 5: 10}


## Sets Basic


```python
animals = {'cat', 'dog'}
print(animals)
print('cat' in animals)
print('fish' in animals)
animals.add('fish')
print('fish' in animals)
print(len(animals))
animals.add('cat')
print(len(animals))
animals.remove('cat')
print(len(animals))
```

    {'dog', 'cat'}
    True
    False
    True
    3
    3
    2



```python
animals = {'cat', 'dog','fish'}
for idx,animal in enumerate(animals):
    print(idx,animal)
```

    0 dog
    1 fish
    2 cat



```python
nums = [0,1,2,3,4,5]
square = { num for num in nums}
print(square)
```

    {0, 1, 2, 3, 4, 5}



```python
from math import sqrt
nums = {int(sqrt(i)) for i in range(30)}
print(nums)
```

    {0, 1, 2, 3, 4, 5}


## Tuples


```python
nums = [0,1,2,3,4,5]
d = {(x-1,x):x+1 for x in nums }
print(d)
```

    {(-1, 0): 1, (0, 1): 2, (1, 2): 3, (2, 3): 4, (3, 4): 5, (4, 5): 6}



```python
t= (4,5)
print(type(t))
print(d[t])
print(d[(1,2)])
```

    <class 'tuple'>
    6
    3



```python
t = (1,2,3,4,5)
print(t[0:3])
```

    (1, 2, 3)



```python

```
