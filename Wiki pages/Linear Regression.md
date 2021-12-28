---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Linear regression
## Data :
Inputs are continuous vectors of length $K$ (dimensions, features). Outputs are continuous scalars.
$$\mathcal{D} = \{ x^{(i)}, y^{(i)} \}_{i=1}^N \text{ where } x \in \mathbb{R}^K \text{ and } y \in \mathbb{R}$$

## Prediction : Outputs is a linear function of the inputs.
$$
\begin{aligned}  
\hat{y} & = h_{\theta}(x) = \theta_1 x_1 + \theta_2 x_2 + \cdots + \theta_K x_K \\

\hat{y} & = h_{\theta}(x) = \theta^T x
\end{aligned}
$$

## Learning  :
Finding the parameters $\theta$ that minimize some objective function.

$$ \theta^* = \operatorname*{argmin}_{\theta} J(\theta)$$