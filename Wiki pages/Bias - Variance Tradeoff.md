---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Bias-Variance tradeoff
$y =f(x) +\epsilon$

We train a model to approximate $f(x)$ with $\hat{f}(x)$ :
- $\hat{f}(x)$ can be any model (SWM, NN, [[Logistic regression]], etc...)
- We train the model by minimizing a [[Loss Function]] such that $y \approx \hat{f}(x)$
- $\hat{f}(x)$ will be different for different realizations of the training data

## Bias and Variance
### Bias
Difference bewteen the expected value of the estiamtor and the true value.
$$ \text{Bias}(\hat{f}(x)) = \mathbb{E} \{ \hat{f}(x) - f(x) \} $$

- A simpler model has a higher bias
- High bias can cause underfitting

### Variance
Deviation from the expected value
$$ \text{Var}(\hat{f}(x)) = \mathbb{E} \{ (\hat{f}(x) - \mathbb{E} [\hat{f}(x) ])^2 \} $$

- A more complex model has a higher variance
- High variance can cause [[Overfitting]]

## Tradeoff
![[biasorvaraince.png]]
![[trainandtestbias.png]]

If we make the model more complicated, for the same training set size, the bias decreases but the variance increases.

