---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Loss Function
Loss function, or cost function, risk
$$ \mathcal{L} : \mathcal{Y} \times \mathcal{Y} \rightarrow \mathbb{R} $$
$$ y, f(x) \rightarrow \mathcal{L}(y,f(x)) $$

Quantifies how far the decision function is from the truth.

Example of loss functions:
- $\mathcal{Y} = [0,1], \, \mathcal{L}(y, f(x)) = 0 \text{ if } y=f(x), \, 1 \text{ otherwise}$
- $\mathcal{Y} = \mathbb{R}, \, \mathcal{L}(y, f(x)) = || y - f(x) ||^2$

