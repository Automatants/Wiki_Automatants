---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Classification as regression
Given $\mathcal{D} = \left\{ x^i, y^i \right\}_{i=1,\ldots,n}$ find $f$ such that $f(x) \approx y$

- Binary classification : $y^i \in \left\{ 0,1 \right\}$
- Multiclass classification : $y^i \in \left\{ 0, 1, \ldots, k \right\}$

## Idea
Suppose that we have a binary classification problem : $y^i \in \left\{ -1,1 \right\}$.
Assuming the standard model for [[Linear Regression]] : $y(x) = \theta^Tx$
We can obtain theta by optimizing a [[Loss Function]] like the [[Least-Squares Regression]].

## Computing a prediction
In one dimension, the classifier has the form : $y = \theta_0 + \theta^Tx$.
A reasonable decision rule is :
$$
\hat{y} = \left\{
\begin{array}{ll}
1 \quad \text{ if } \theta_0 + \theta^Tx \geq 0 \\
-1 \quad \text{ otherwise}
\end{array}
\right.
$$
Which we can write as : $\hat{y} = \operatorname*{sign}(\theta_0 + \theta^Tx)$
This specifies a classifier with a linear boundary : $\theta_0 + \theta^Tx = 0$  which separates the space into two half-spaces.

## Examples
![[1dclass.png|200]]![[2dclass.png|200]]![[3dclass.png|200]]