---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Regularization
Process of penalizing [[Model Complexity]]during training. A regularization term is added to the [[Loss Function]] to control complexity.

Two main approaches :
-	Ridge Regression : Adds L2 Regularization : $J_R(\theta) = J(\theta) + \lambda ||\theta||_2^2$
	-	Multicolinearity
	-	Biased but smaller variance
	- Shrinks coeffs but not parcimonious

-	LASSO Regression : Adds L1 Regularization: $J_{L}(\theta) = J(\theta) + \lambda ||\theta||_1$
	-	Enforces sparsity
	-	If predictors are correlated LASSO will pick only one

It is possible to combine the two :
Elastic Net Regression : $$J_{EN}(\theta) = J(\theta) + \lambda_1 ||\theta||_1 + \lambda_2 ||\theta||_2^2$$
- Enforce sparsity
- No limitation on the number of selected variables / encouraging grouping
- Can suffer from double shrinkage