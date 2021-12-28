---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Stochastic Gradient Descent

Variant of the [[Gradient Descent]] where we only compute the gradient along some dimensions instead of all the dimensions.

## Algorithm
$$
\begin{aligned}  

& \theta \leftarrow \theta^0 \\
& \text{while not converged} \\
& \quad \text{for } i \in \text{shuffle}(\{1,2,...,N\}) \\
& \quad \quad \theta \leftarrow \theta - \lambda \nabla_{\theta} J^{(i)}(\theta) \\
& \text{return} \quad \theta
\end{aligned}
$$
