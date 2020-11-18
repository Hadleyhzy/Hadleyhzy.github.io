---
layout: post
title: OOP Comparison between C++ and Python
key: 20201115
tags:
  - Python
  - C++
  - OOP
---

process oriented processing
oop
范形编程
template<typename T, typname U>
	add add3(T a, U b)-.decltype(a+b){
	return a+b;
}
函数式编程

1. Inheritance
2. Polymorphism
3. Encapsulation
4. Abstraction

## class definition


### C++
```C++
//class
class Points
{
public:
	//constructor
	Points(int x, int y){
		this->_x = x;
		this->_y = y;
	}

	//print function
	void print() const{
		std::cout<<this->_x<<" "<<this->_y<<std::endl;
	}
	//public data members
	string alias = "position of point";
private:
	//private data members
	int _x;
	int _y;
};
```

* create instances:
```c++
//instance initialization implicitly
Points point1 = Points(1,1);

//instance initialization explicitly
Points point2(2,2);

//print function
point1.print();

//accessing public data member
std::cout<<point1.alias<<std::endl;
```

```
1 1
position of point
```

1. `;` after class `{}`
2. `this` is pointer, not reference, accessing current object data member needs to use this form: `this->data_member`
3. declare an instance must predeclare it's class type, for instance, `SoftwareEngineer student1 = SoftwareEngineer()` is correct, while `student1 = SoftwareEngineer()` can only be used in Python.
4. private class members are accessible by the member functions of this class only while public members are accessible everywhere.


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
```

```python
#create instance
student1 = SoftwareEngineer('Max',20,'Junior',5000)
#access instance attribute
print(student1.name,student1.alias,student1.salary)
#access class attribute
print(SoftwareEngineer.alias)
```

```
Max SE 5000
SE
```

1. create class
2. class attribute
3. instance attribute
4. create instance
5. instance vs class

## method and functions

### Python

#### instance method with input argument and return type

```python
class SoftwareEngineer:
	...
	# instance method
    def code(self):
        print(f"{self.name} is writing code...")
    
    def code_in_language(self,language):
        print(f"{self.name} is writing code in {language}...")
    
    def information(self):
        information = f"name = {self.name}, age = {self.age}, level = {self.level}"
        return information
    ...
```

```python
student1.code()
student1.code_in_language('pyhton')
print(student1.information())
```
```
Max is writing code...
Max is writing code in pyhton...
name = Max, age = 20, level = Junior
```

#### python special method

* `__eq__`

Comparison two instances without defining `__eq__` would result in false since two instances memory locations are not the same:

```python
student2 = SoftwareEngineer('Max',20,'Junior',5000)
print(student1 == student2) #comparing memory
```
```
False
```

* `__str__`

this method is called whenever object is converted to string

for instance:

```python
print(student2)
<__main__.SoftwareEngineer object at 0x106996070>
```
now adding `__str__` method to `SoftwareEngineer` class:

```python
...
def __str__(self):
        information = f"name = {self.name}, age = {self.age}, level = {self.level}"
        return information
...
```

```python
print(student2)
name = Max, age = 20, level = Junior
```

```python
class SoftwareEngineer:
	    # python default method
    def __str__(self):
        information = f"name = {self.name}, age = {self.age}, level = {self.level}"
        return information
    
    #python equal method
    def __eq__(self,other):
        return self.name == other.name and self.age == other.age
```

#### class method

```python
class SoftwareEngineer:
	...
    #class method
    def entry_salary2(age):
        if age < 10:
            return "without object <10"
        else:
            return "without object >=10"

	    #instance method
    def entry_salary1(self,age):
        if age < 25:
            return 5000
        elif age <30:
            return 7000
        return 9000
    
    #cannot access self attribute, decorator
    @staticmethod
    def entry_salary(age):
        if age < 25:
            return 5000
        elif age < 30:
            return 7000
        return 9000
    ...
```   

``` python
print(student2.entry_salary(30))
print(SoftwareEngineer.entry_salary(27))
print(SoftwareEngineer.entry_salary2(11))
```

```
9000
7000
without object >=10
```

Note that using both decorator and class method, accessing self attribute is not allowed since it is not tied to specific instance.
{:.warning}


How ever calling `entry_salary2` from instance is not allowed since it didn't pass object as input:

```python
print(student2.entry_salary2(11))
```

```
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-79-76716bf772b6> in <module>
----> 1 print(student2.entry_salary2(11))

TypeError: entry_salary2() takes 1 positional argument but 2 were given
```

### C++  

#### Default constructor

```c++
class Points{
public:
	Points(int x=0, int y=0){
		this->x=x;
		this->y=y;
	}
	...
private:
	int x;
	int y;
}
```

```c++
//defaut constructor
Points point3 = Points();
point3.print();
```

```
0 0
```

#### constructor initializer list

```c++
class Points{
public:
	Points(int x=0, int y=0):x(x),y(y){}
	...
private:
	int x;
	int y;
}
```

* When do we use initializer list

1. for initialization of non-static const data members

```c++
class Points{
public:
	Points(int x,y):x(x),y(y){};
private:
	const int x;
	const int y;
}
```



2. for initialization of reference members
3. for initialization of member objects which do not have default constructor
4. for initialization of base class members
5. when constructor's parameter name is same as data member
6. for performance

Reference: https://www.geeksforgeeks.org/when-do-we-use-initializer-list-in-c/



#### get and set

#### object pointer and dynamic allocation

### Inheritance

### Polymorphism

