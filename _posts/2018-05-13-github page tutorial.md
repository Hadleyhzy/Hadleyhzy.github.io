---
layout: post
title: GitHub Pages Tutorial
key: 20180513
tags:
  - front end
---

## Create a repository

Head over to [GitHub](https://github.com/) and [create a new repository](https://github.com/new) named username.github.io, where username is your username(or organization name) on GitHub.

![Northeastern](/../Pic/N_copy.png "Northeastern"){:width="128px" :height="128px"}

If the first part of the repository doesn't exactly match your username, it won't work, so make sure to get it right.
{:.warning}

Here is a literal `` ` `` backtick. And here is `some` text.

**markdown:**
```
Here is a literal `` ` `` backtick. And here is `some` text.
```
<!--more-->

### Standard Code Blocks

Here comes some code.
This text belongs to the same code block.
^
This one is seperate.

**markdown:**
```
Here comes some code.
This text belongs to the same code block.
^
This one is seperate.
```

### javascript highlight

```javascript
(() => console.log('hello, world!'))();
```

**markdown:**

```
```javascript
(() => console.log('hello, world!'))();
```

### Language of Code Blocks

~~~
for(int i=0;i<max;i++){
	i++;
}
~~~
{:.language-c++}

**markdown:**
```
~~~
for(int i=0;i<max;i++){
	i++;
}
~~~
{:.language-c++}
```

~~~ c++
for(int i=0;i<max;i++){
	i++;
}
~~~

**markdown:**
```
~~~ c++
for(int i=0;i<max;i++){
	i++;
}
~~~
```

## Lists

### Unordered list
* Asia
* Europe
	* Austria
	* France
	* Italy
* North America

**markdown:**
```
* Asia
* Europe
	* Austria
	* France
	* Italy
* North America
```

### Ordered list
1. Asia
2. Europe
	1. Austria
	2. France
	3. Italy
3. North America

**markdown:**
```
1. Asia
2. Europe
	1. Austria
	2. France
	3. Italy
3. North America
```

## Blockquotes

> "There is nothing either good or bad, but thinking makes it so."
>
> —Hamlet in *Hamlet*

**markdown:**
```
> "There is nothing either good or bad, but thinking makes it so."
>
> —Hamlet in *Hamlet*
```

## Definition
kramdown
: A Markdown-superset converter

Maruku
: Another Markdown-superset converter

**markdown:**
```
kramdown
: A Markdown-superset converter

Maruku
: Another Markdown-superset converter
```
## Tables

|-----------------+------------+-----------------+----------------|
| Default aligned |Left aligned| Center aligned  | Right aligned  |
|-----------------|:-----------|:---------------:|---------------:|
| First body part |Second cell | Third cell      | fourth cell    |
| Second line     |foo         | **strong**      | baz            |
| Third line      |quux        | baz             | bar            |
|-----------------+------------+-----------------+----------------|
| Second body     |            |                 |                |
| 2 line          |            |                 |                |
|=================+============+=================+================|
| Footer row      |            |                 |                |
|-----------------+------------+-----------------+----------------|

**markdown:**
```
|-----------------+------------+-----------------+----------------|
| Default aligned |Left aligned| Center aligned  | Right aligned  |
|-----------------|:-----------|:---------------:|---------------:|
| First body part |Second cell | Third cell      | fourth cell    |
| Second line     |foo         | **strong**      | baz            |
| Third line      |quux        | baz             | bar            |
|-----------------+------------+-----------------+----------------|
| Second body     |            |                 |                |
| 2 line          |            |                 |                |
|=================+============+=================+================|
| Footer row      |            |                 |                |
|-----------------+------------+-----------------+----------------|
```

|---
| Default aligned | Left aligned | Center aligned | Right aligned
|-|:-|:-:|-:
| First body part | Second cell | Third cell | fourth cell
| Second line |foo | **strong** | baz
| Third line |quux | baz | bar
|---
| Second body |x|m
| 2 line |x|n
|===
| Footer row

**markdown:**
```
|---
| Default aligned | Left aligned | Center aligned | Right aligned
|-|:-|:-:|-:
| First body part | Second cell | Third cell | fourth cell
| Second line |foo | **strong** | baz
| Third line |quux | baz | bar
|---
| Second body |x|m
| 2 line |x|n
|===
| Footer row
```


