---
layout: post
title: Naive Bayes Classifer
key: 20201105
tags:
  - Python
  - Pytorch
  - Naive Bayes
  - machine learning
---

## Definition

Naive Bayes classifiers are based on naive bayes classifier algorithms. Let's say we have m input values <img src="https://latex.codecogs.com/svg.latex?  \overrightarrow{x} =< x_{1},x_{2},x_{3},...,x_{m} >" title="x_{ij}" />

1. Assume all these input variables/features are conditionally independent given Y and equally contributed to the outcome.  
In reality it is not quite `possible` that all features are conditionally independent
{:.info}

2. Simply chose the class label that is the most likely given the data, predict Y using <img src="https://latex.codecogs.com/svg.latex?   \widehat{Y} =   argmax_{y=\{0,1\}}   P( \overrightarrow{x},Y)" title="x_{ij}" />


## Bayes' Theorem 
Bayes' Theorem gives the probability of an event occurring given the probability of another event that has already occurred.

<img src="https://latex.codecogs.com/svg.latex? p(y| \overrightarrow{x})= \frac{p( \overrightarrow{x}|y) p(y)}{p( \overrightarrow{x} )}" title="x_{ij}" />

where y is class variable and <img src="https://latex.codecogs.com/svg.latex?  \overrightarrow{x} " title="x_{ij}" /> is a feature vector where <img src="https://latex.codecogs.com/svg.latex?  \overrightarrow{x} =< x_{1},x_{2},x_{3},...,x_{n} >" title="x_{ij}" />

* basically, we are trying to find probability of event y, given event x, event x is also termed as evidence.

* p(x) is prior probability of x and p(y) is prior probability of y.

* P(x|y) is a posteriori probability of y.

Since given assumption that all features are independent, then

<img src="https://latex.codecogs.com/svg.latex? p(y| \overrightarrow{x})= \frac{p( \overrightarrow{x}|y) p(y)}{p( \overrightarrow{x} )}" title="x_{ij}" />

As the denomitor remains constant for a given input, we can obtain equations like follows:

<img src="https://latex.codecogs.com/svg.latex? p(y| \overrightarrow{x}) \propto  \prod_i^n   {p(  x_{i} |y) p(y)}" title="x_{ij}" />

To maximize the probability of event y given the probability of event x is the same as to choose/calculate `parameter` y which result maximal probability using MLE.

<img src="https://latex.codecogs.com/svg.latex? \widehat{y} =   argmax_{y=\{0,1\}}   p(y) \prod_i^n p( x_{i}|y)" title="x_{ij}" />



## Compare between MLE and MAP


## Example

|  OUTLOOK  |  Temperature | Humidity | Windy | Play Golf |
| ----------|:------------:| --------:|------:|----------:|
| Rainy     |      Hot     |   High   | False |    No     |
| Rainy     |      Hot     |   High   | True  |    No     |
| Overcast  |      Hot     |   High   | False |    Yes    |
| Sunny     |      Mild    |   High   | False |    Yes    |
| Sunny     |      Cool    |   Normal | False |    Yes    |
| Sunny     |      Cool    |   Normal | True  |    No     |
| Overcast  |      Cool    |   Normal | True  |    Yes    |
| Rainy     |      Mild    |   High   | False |    No     |
| Rainy     |      Cool    |   Normal | False |    Yes    |
| Sunny     |      Mild    |   Normal | False |    Yes    |
| Rainy     |      Mild    |   Normal | True  |    Yes    |
| Overcast  |      Mild    |   High   | True  |    Yes    |
| Overcast  |      Hot     |   Normal | False |    Yes    |
| Sunny     |      Mild    |   High   | True  |    No     |







## Implementation from scratch


## Implementation using pytorch
