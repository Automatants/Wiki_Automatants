---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Polynomial regression

If our linear model is not good enough it is possible to create a more complicated model using a polynomial function of order M.
$$y(x, \theta) = \theta_0 + \sum_{i=1}^M \theta_i x^i$$

We can use  [[Gradient Descent|GD]] or [[Stochastic gradient descent|SGD]] Algorithms to optimize the model.