---
layout: post
title: Matplotlib Cheat Sheet
key: 20201124
tags:
  - Python
  - Matplotlib
---

## Scatter

### draw scatter points

```python
plt.scatter(X_1[:,0],X_1[:,1],marker='o',color='red') #axes1,axes2,marker,color
plt.scatter(X_2[:,0],X_2[:,1],marker='s',color='blue')
plt.show()
```

## Line

### Draw a line through two points

```python
plt.xlim(-5,11),plt.ylim(-5,11) #set range of line
plt.axline((x1,y1),(x2,y2))
plt.show()
```



    





