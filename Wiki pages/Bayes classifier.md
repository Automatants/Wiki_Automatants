---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Bayes classifier

For clasification purposes we can compute a class probability using Bayes Rule.
$$p(c|x) = \frac{p(x|c)p(c)}{p(x)}$$

Where $p(c|x)$ is the posterior, $p(c)$ is the prior, $p(x|c)$ is the likelihood and $p(x)$ is the evidence.

## Bayes' decion rule
$$
C =
\left\{
\begin{array}{lc}
1 &\text{ if } p(C=1|x) > p(C=0|x) \\
0 &\text{otherwise}
\end{array}
\right.
$$