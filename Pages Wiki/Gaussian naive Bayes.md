---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Gaussian naive Bayes
This [[Classification as regression|classifier]] assumes that $p(x|c)$ is distributed according to a multivariate Gaussian distribution. General case discussed in [[Naive  Bayes]]
-> *Gaussian Discriminant Analysis*

## 1D case
$$
p(x|c) = \frac{1}{\sqrt{2\pi\sigma_C^2}}\exp \left( - \frac{(x-\mu_C)^2}{2\sigma_C^2} \right)
$$

Parameters are different for each class.

## dD case
$$
\left\{
\begin{array}{ll}
p(x|C=0) \sim \mathcal{N}(\mu_0, \Sigma) \\
p(x|C=1) \sim \mathcal{N}(\mu_1, \Sigma)
\end{array}
\right.
$$
With
$$
\left\{
\begin{array}{ll}
\mu_0 = \frac{\sum \mathcal{1}(C^{(n)}=0) x^{(n)}}{\sum \mathcal{1}(C^{(n)}=0)},\quad \mu_1 = \frac{\sum \mathcal{1}(C^{(n)}=1) x^{(n)}}{\sum \mathcal{1}(C^{(n)}=1)},\\
\Sigma = \frac{1}{N} \sum (x^{(n)} - \mu_{c^{(n)}})(x^{(n)} - \mu_{c^{(n)}})^T
\end{array}
\right.
$$