---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Partial Derivative for Least-Squares

Finding the gradient for the [[Least-Squares Regression]] using [[Gradient Descent]] or [[Stochastic gradient descent]]

Let $J(\theta) = \sum_{i=1}^N J^{(i)}(\theta)$, where $J^{(i)}(\theta) = \frac{1}{2}(\theta^T x^{(i)} - y^{(i)})^2$

$$
\begin{aligned}

\frac{d}{d\theta_k} J^{(i)}(\theta) & = \frac{d}{d\theta_k} \frac{1}{2}(\theta^T x^{(i)} - y^{(i)})^2 \\
& = \frac{1}{2} \frac{d}{d\theta_k} (\theta^T x^{(i)} - y^{(i)})^2 \\

& = (\theta^T x^{(i)} - y^{(i)})\frac{d}{d\theta_k} (\theta^T x^{(i)} - y^{(i)}) \\

& = (\theta^T x^{(i)} - y^{(i)})x_k^{(i)}

\end{aligned}
$$

