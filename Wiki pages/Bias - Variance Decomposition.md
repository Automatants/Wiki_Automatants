---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Bias - Variance Decomposition

$$ \text{Bias}(\hat{f}(x)) = \mathbb{E} \{ \hat{f}(x) - f(x) \} $$
$$ \text{Var}(\hat{f}(x)) = \mathbb{E} \{ (\hat{f}(x) - \mathbb{E} [\hat{f}(x) ])^2 \} $$

We want to find a function that approximates $f$ as well as possible.

Using the Mean Squared Error (MSE):
$$
\text{MSE}(\hat{f}(x)) = \mathbb{E} \{ (y - \hat{f}(x))^2 \}
$$
$$ 
= \mathbb{E}[y^2] + \mathbb{E}[\hat{f}^2] - \mathbb{E}[2y\hat{f}]
$$ 
$$
= \text{Var}[y] + \mathbb{E}[y]^2 + \text{Var}[\hat{f}] + \mathbb{E}[\hat{f}]^2 - 2f\mathbb{E}[\hat{f}]
$$
$$
= \text{Var}[y] + \text{Var}[\hat{f}] + \mathbb{E}[f - \hat{f}]^2
$$
$$
= \sigma^2 + \text{Var}[\hat{f}] + \text{Bias}[\hat{f}]^2
$$