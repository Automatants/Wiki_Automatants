---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Training via optimization

^c047cf

Find that f among the [[Hypothesis class]] $\mathcal{F}$ that minimizes the total loss.

The goal is to find a predictor $f$ with small loss on unseen data :
$$\sum_{(x,y) \text{ is an unseen example}} \mathcal{L}(y, f(x))$$

- The loss converges to the expected loss : 
$$\sum_{(x,y) \text{ is an unseen example}}\mathcal{L}(y, f(x)) \rightarrow \mathbb{E}_{x,y} \{ \mathcal{L}(y, f(x)) \} $$

- The empirical risk also converges to the expected loss (Using a good choice of hyperparameters) : 
$$\text{Empirical Risk : } \frac{1}{n} \sum_{i=1}^n \mathcal{L}(y^i, f(x^i))$$

- We then want to solve : 
$$ \operatorname*{argmin}_{f \in \mathcal{F}} \mathbb{E} \{ \mathcal{L}(y, f(x)) \}$$

- We instead solve using the Empirical Risk :
$$ \operatorname*{argmin}_{f \in \mathcal{F}} \frac{1}{n} \sum_{i=1}^n \mathcal{L}(y^i, f(x^i))$$

Solution can be approximated by [[Gradient Descent|GD]] or [[Stochastic gradient descent|SGD]] Algorithms