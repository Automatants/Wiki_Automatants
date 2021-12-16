---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# MLE for Gaussian Distribution

We want to compute the [[Maximum likelihood estimator (MLE)|MLE]] for a Gaussian distribution.

- We assume that the $N$ data points that we have are independent and identically distributed.
$$
p(x^{(1)},\ldots,x^{(N)}|C)=\prod_{i=1}^N p(x^{(n)}|C) = \prod_{i=1}^N \frac{1}{\sqrt{2\pi\sigma^2}}\exp \left( - \frac{(x^{(n)}-\mu)^2}{2\sigma^2} \right)
$$

- Now we want to maximize the log-likelihood, or minimize its negative (we can think in terms of a [[Loss Function]].
$$
\begin{align}
l_{\text{log-loss}} &= - \ln p(x^{(1)},\ldots,x^{(N)}|C) \\
&= - \ln \left( \prod_{i=1}^N \frac{1}{\sqrt{2\pi\sigma^2}}\exp \left( - \frac{(x^{(n)}-\mu)^2}{2\sigma^2} \right) \right)\\
&= \sum_{i=1}^N \ln(\sqrt{2\pi}\sigma) + \sum_{i=1}^N \frac{(x^{(n)}-\mu)^2}{2\sigma^2} \\
&= \frac{N}{2} \ln(2\pi\sigma^2) + \sum_{i=1}^N \frac{(x^{(n)}-\mu)^2}{2\sigma^2}
\end{align}
$$
To minimize this function : 
- Take the derivative and set equal to 0 to find the MLE for the parameters.

Doing this we find:
$$
\left\{
\begin{array}{ll}
\mu^{MLE} = \frac{1}{N} \sum_{n=1}^N x^{(n)} \\
\sigma^{2^{MLE}} = \frac{1}{N} \sum_{n=1}^N (x^{(n)} - \mu)^2
\end{array}
\right.
$$