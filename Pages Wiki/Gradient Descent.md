---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Gradient Descent
## Algorithme de base
```python
theta = theta0

while not converged:
	theta = theta - lr*grad(theta,(J(theta))
	
return theta
```

In order to apply GD, we need to compute the gradient of the [[Loss Function]], $\nabla_{\theta} J(\theta)$.

## Convergence
There are many ways to detect convergence. For example we could check wether the L2 norm of the gradient is below some small tolerance. $$||\nabla_{\theta} J(\theta)||_2 \leq \epsilon$$ 

We could also check that the value of the objective function is not decreasing fast.
