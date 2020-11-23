---
layout: post
title: Principal Component Analysis
key: 20201123
tags:
  - Python
  - machine learning
  - PCA
---

## Principal Component Analysis

```python
import numpy as np
```

1.calculate mean values of each feature/column
2.subtracting the mean column value for each column
3.calculate covariance matrix of the centered matrix C
4.calculate list of engenvalues and eigenvectors
5.select k eigenvectors/principal components


```python
A = np.array([[1,2],[3,4],[5,6]])
print(A)
M = np.mean(A.T, axis=1)
print(M)
C=A-M
print(C)
V=np.cov(C.T)
print(V)
# eigendecomposition of covariance matrix
values, vectors = np.linalg.eig(V)
print(vectors)
print(values)
# project data
P = vectors.T.dot(C.T)
print(P.T)
print(P.T.shape)
```

    [[1 2]
     [3 4]
     [5 6]]
    [3. 4.]
    [[-2. -2.]
     [ 0.  0.]
     [ 2.  2.]]
    [[4. 4.]
     [4. 4.]]
    [[ 0.70710678 -0.70710678]
     [ 0.70710678  0.70710678]]
    [8. 0.]
    [[-2.82842712  0.        ]
     [ 0.          0.        ]
     [ 2.82842712  0.        ]]
    (3, 2)



```python
np.var([-2,-2])
C.T
```




    array([[-2.,  0.,  2.],
           [-2.,  0.,  2.]])




```python
from sklearn.decomposition import PCA
A=np.array([[1,2],[3,4],[5,6]])
print(A)
pca = PCA(2) #chosen number of dimensions
pca.fit(A)
print(pca.components_)
print(pca.explained_variance_)
B = pca.transform(A)
print(B)                   
```

    [[1 2]
     [3 4]
     [5 6]]
    [[ 0.70710678  0.70710678]
     [-0.70710678  0.70710678]]
    [8. 0.]
    [[-2.82842712e+00 -2.22044605e-16]
     [ 0.00000000e+00  0.00000000e+00]
     [ 2.82842712e+00  2.22044605e-16]]


Reference:
1. How to calculate covariance matrix?
https://www.youtube.com/watch?v=G16c2ZODcg8

2. Why covariance matrix calculation divided by n-1, not n?
https://blog.csdn.net/cherrylvlei/article/details/81430447 
https://hg526kk.blog.csdn.net/article/details/77859173?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromBaidu-1.control&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromBaidu-1.control


3.How to calculate eigen value and eigen vector?
https://jingyan.baidu.com/article/27fa7326afb4c146f8271ff3.html


4.Why eigenvectors with highest eigenvalues maximize the variance in PCA?
https://www.cnblogs.com/jerrylead/archive/2011/04/18/2020209.html  






