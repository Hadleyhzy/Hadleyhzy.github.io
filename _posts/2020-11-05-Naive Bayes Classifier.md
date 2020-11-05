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

* <img src="https://latex.codecogs.com/svg.latex? p( \overrightarrow{x} |y)" /> is a posteriori probability of y.

Since given assumption that all features are independent, then

<img src="https://latex.codecogs.com/svg.latex? p(y| \overrightarrow{x})= \frac{p( \overrightarrow{x}|y) p(y)}{p( \overrightarrow{x} )}" title="x_{ij}" />

As the denomitor remains constant for a given input, we can obtain equations like follows:

<img src="https://latex.codecogs.com/svg.latex? p(y| \overrightarrow{x}) \propto  \prod_i^n   {p(  x_{i} |y) p(y)}" title="x_{ij}" />

To maximize the probability of event y given the probability of event x is the same as to choose/calculate `parameter` y which result maximal probability using MLE.

<img src="https://latex.codecogs.com/svg.latex? \widehat{y} =   argmax_{y=\{0,1\}}   p(y) \prod_i^n p( x_{i}|y)" title="x_{ij}" />



## Compare between MLE and MAP


## Example

|  Outlook  |  Temperature | Humidity | Windy | Play Golf |
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

Task: estimate whether or not to play golf when it's {Rainy, Hot, High, False}

Solution:

<img src="https://latex.codecogs.com/svg.latex? p(y|outlook,temperature,humidity,windy)= \frac{p(outlook,temperature,humidity,windy|y)p(y)}{p(outlook,temperature,humidity,windy}= p(outlook,temperature,humidity,windy|y)p(y)=p(outlook|y)p(temperature|y)p(humidity|y)p(windy|y)p(y)" title="x_{ij}" />

Given specific observations mentioned in the task:

<img src="https://latex.codecogs.com/svg.latex? p(y=yes|outlook,temperature,humidity,windy)=p(outlook=rainy|y=yes)p(temperature=Hot|y=yes)p(humidity=High|y=yes)p(windy=False|y=yes)p(y=yes)= \frac{2}{9} \frac{2}{9} \frac{6}{9} \frac{6}{9} \frac{9}{14}" title="x_{ij}" />

Now after normalization or logarithmic calculation, we compare both probabilities for playing gold and not playing gold, and the prediction would be the one with higher probability:

<img src="https://latex.codecogs.com/svg.latex? p(yes|today)= \frac{0.0141}{0.0141+0.0068} =0.67" title="x_{ij}" />

<img src="https://latex.codecogs.com/svg.latex? p(no|today)= \frac{0.0068}{0.0141+0.0068} =0.33" title="x_{ij}" />


## Implementation from scratch


## Implementation using pytorch
