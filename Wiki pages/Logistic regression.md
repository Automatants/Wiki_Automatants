---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Logistic regression
Logitics regression aims to model : $p(\text{label}|\text{data})$
By training a classifier of the form:
$$
\hat{y}(x) = \left\{
\begin{array}{ll}
1 \quad \text{ if } \theta^Tx \geq 0 \\
0 \quad \text{ otherwise}
\end{array}
\right.
$$
Intuitively, it does not make sens for $y_i$ to take values larger than 1 or smaller than 0.

To turn a real-valued $\theta^Tx$ into a probability $p_0(y|x) \ in [0,1]$ we replace the $\operatorname*{sign}$ with the *sigmoid* of *logistic* function :
$$
\begin{align}
y(x) &= \sigma (\theta^Tx)\\
\text{with } \sigma(z) &= \frac{1}{1+e^{-z}}
\end{align}
$$

## Formulation
Probabilistic interpretation : 
$$
\begin{align}
\hat{y}(x) &= p(y=1|x,\theta)\\
1-\hat{y}(x) &= p(y=0|x,\theta)\\
\text{Combined : } p(y|x,\theta) &= (\hat{y})^y(1-\hat{y})^{1-y}
\end{align}
$$

## Maximum Likelihood estimator
Assuming we have $m$ training examples generated independently, we can write the likelihood of the parameters.
$$
\begin{align}
L(\theta) = p(y|X,\theta) &= \prod_{i=1}^m p(y^i|x^i,\theta) \\
&= \prod_{i=1}^m (y(x^i))^{y^i}(1-y(x^i))^{1-y^i} 
\end{align}
$$

We can then learn the parameters of the model by maximizing the likelihood.
$$
\begin{align}
\mathcal{L}(\theta) &= \operatorname*{log}L(\theta) \\
&= \sum_{i=1}^m y^i \operatorname*{log}(y(x^i)) + (1-y^i)\operatorname*{log}(1-y(x^i))
\end{align}
$$

using $-\mathcal{L}(\theta)$ as a [[Loss Function]] we can use a [[Gradient Descent]] or [[Stochastic gradient descent]] to tune the model.