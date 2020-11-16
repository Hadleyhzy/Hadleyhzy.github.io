---
layout: post
title: OOP Comparison between C++ and Python
key: 20201115
tags:
  - Python
  - C++
  - OOP
---

1. Inheritance
2. Polymorphism
3. Encapsulation
4. Abstraction

## class definition


### C++
```C++
// class
class SoftwareEngineer{
public:

private:
};
```


### Python

```python
# class
class SoftwareEngineer:
	# class attribute
	alias = 'SE'

	def __init__(self,name,age,level,salary):
		#instance attribute
		self.name = name
		self.age = age
		self.level = level
		self.salary = salary


#instance/object
student1 = SoftwareEngineer('max',20,'Junior',5000)
```