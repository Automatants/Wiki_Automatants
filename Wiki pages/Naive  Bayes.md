---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Naive Bayes : General Case.
Multivariate [[Classification as regression|classification]] : $x$ is $d$-dimensional
Assumming that $x1, \ldots, x_d$ are conditionnaly independent given the class $C_K$ ($K$ different classes) :
$$
\begin{aligned}
p(C_k|x) &= \frac{p(x|C_k)p(C_k)}{\sum_{k=1}^K p(x|C_k)p(C_k)}\\
p(x1, \ldots, x_d|C_k)
&= p(x_1|C_k)p(x_2|C_k)\ldots p(x_d|C_k)
\end{aligned} 
$$
because variables are conditionally independant.

We have : 
$$
p(C_k|x) \propto p(C_k) \prod_{i=1}^d p(x_i|C_k) 
$$

## Naive Bayes Classification Model.
$$
p(C_k|x) = \frac{1}{Z} p(C_k) \prod_{i=1}^d p(x_i|C_k) 
$$
$$ Z = p(x) $$

Classification using the maximum a posteriori rule (MAP) :
$$
\hat{y} = \operatorname*{argmax}_{k} p(C_k) \prod_{i=1}^d p(x_i|C_k) 
$$

## Bernouilli Naive Bayes for spam detection
![[spam1.png]]
![[spam2.png]]
![[spam3.png]]