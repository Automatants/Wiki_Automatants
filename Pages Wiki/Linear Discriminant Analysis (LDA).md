---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Linear Discriminant Analysis
LDA seeks to reduce dimensionality while preserving as much of the class discriminatory information as possible.
Assume we have a set of D-dimensional samples $\left\{ x_1, \ldots, x_N \right\}$ :
- 2 classes
- $N_1$ of the samples belong to class $C_1$
- $N_2$ belong to $C_2$

We want to obtain $y$ by  projecting the samples $x$ into a line $y = w^Tx$
We want the line that maximizes the *separability* of the classes.
![[LDA1.png]]

In order to find a good projection vector, we need to define a *measure of separation*.
The mean vector of each class in $x$-space and $y$-space is:
$$
\begin{aligned}
\mu_i &= \frac{1}{N_i}\sum_{x \in C_i} x \quad \text{(original space)}\\
\tilde{\mu_i} &= \frac{1}{N_i}\sum_{y \in C_i} y = w^T\mu_i
\end{aligned}
$$
We  could then choose the distance between the projected means as our objective function :
$$J(w) = |\tilde{\mu_1}-\tilde{\mu_2}| = |w^T(\mu_1 - \mu_2)|$$
But this doesn't take standard deviation into account.

## Fisher's solution
Project in a new space which maximizes the between-class separability and minimizes within-class variability.
![[LDAFIsher.png]]

### Scatter matrices
Something like variance that takes class information into account. 
- Within-class scatter matrix $S_w$
$$
\begin{aligned}
S_i &= \sum_{x \in C_i} (x-\mu_i)(x-\mu_i)^T \\
S_w &= S_1+S_2
\end{aligned}
$$
Where $\mu_i$ is the mean vector of class $i$
$S_i$ is actually the covariance matrix of class $i$
- Between-class scatter matrix $S_b$
$$
S_b = \sum_{j=1}^2 n_j (\mu_j - \mu)(\mu_j - \mu)^T
$$

The total variance is the sum of the scatter matrices:
$$
\begin{aligned}
S_t &= \sum_{x \in X} (x - \mu)(x - \mu)^T \\
S_t &= S_w + S_b
\end{aligned}
$$
We can then see $S_b$ as the difference between the total variance matrix and the sum of the variance matrices of each class.

### Fisher's criterion
We want to find $w$ that minimizes within-class separability and maximizes between-class separability
$$
\begin{aligned}
J(w) &= \frac{w^T S_b w}{w^T S_w w} \\
w_{LDA} &= \operatorname*{argmax}_w J(w)
\end{aligned}
$$
### Oprimization
To find the maximum $J(w)$ we find its derivative and set it to 0.
$$

\begin{align}
\frac{d}{dw}J(w) = \frac{d}{dw} \left[ \frac{w^TS_bw}{w^TS_ww} \right] = 0 \implies \\
0 = \left( \left[ w^TS_ww \right] \frac{d[w^TS_bw]}{dw} - \left[ w^TS_bw \right] \frac{d[w^TS_ww]}{dw}  \right) / (w^TS_ww)^2 \\
0 = \left( \left[ w^TS_ww \right] 2S_bw - \left[ w^TS_bw \right] 2S_ww  \right) 
\end{align}
$$

We then have : 

$$
\left[ \frac{w^TS_ww}{w^TS_bw} \right] S_bw - \underbrace{\left[ \frac{w^TS_bw}{w^TS_bw} \right]}_{ = \lambda} S_ww = 0
$$
Which corresponds to the generalized eigenvalue problem :
$$
S_b w - \lambda S_w w
$$
Which we can translate to :
$$
S_w^{-1}S_b w - \lambda w
$$

### The Algorithm
- Input : Training data $X = \left\{ x_1, \ldots, x_N\right\}$ where $x_i = (x^i_1, \ldots, x^i_d)$ and class labels $Y$ ($K$ classes)
- Output : Projected data $X_{LDA}$, dimension  $= N \times (K-1)$
1. Compute within class scatter matrix $S_w$
2. Compute between class scatter matrix $S_b$
3. Compute matrix $W$ solving the eignevalue problem, and getting the eigen vector that correspond to the $K-1$ largest eigenvalues 
$$ S_w^{-1}S_b w_j - \lambda w_j,\quad j = 1, \ldots, K-1 $$
4. Project the data to the new space defined by $W$ and get $X_{LDA}$