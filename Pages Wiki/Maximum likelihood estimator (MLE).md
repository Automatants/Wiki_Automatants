---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Maximum likelihood estimator (MLE)
Suppose that we have data $\mathcal{D} = \left\{ x^{(i)} \right\}_{i=1}^N$
$$
\theta^{MLE} = \operatorname*{argmax}_{\theta} \prod_{i=1}^N p(x^{(i)}|\theta)
$$

We used this estimator in the [[Logistic regression]] classifier.

If we have prior knowledge:
Maximum a posteriori estimate (MAP)

$$
\theta^{MAP} = \operatorname*{argmax}_{\theta} \prod_{i=1}^N p(x^{(i)}|\theta)p(\theta)
$$