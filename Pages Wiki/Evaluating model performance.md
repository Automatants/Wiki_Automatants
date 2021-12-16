---
author: 'Louis De Oliveira'
date: '2021-12-16 (last update)'
description: ''
---
# Evaluating model performance

## Confusion Matrix
![[Pasted image 20211130112039.png]]

## Evaluation Measures
- Sensitivity = Recall = True Positive Rate (TPR) 
	$$ TPR = \frac{TP}{TP+FN} $$
	
- Specificity = True Negative Rate (TNR)
	$$ TNR = \frac{TN}{FP+TN} $$

- Precision = Positive Predictive Value (PPV)
	$$ PPV = \frac{TP}{TP+FP} $$
	
- False Discovery Rate (FDR)
	$$ FDR = \frac{FP}{FP+TP} $$

- Accuracy
	$$ Acc = \frac{TP+TN}{TP+FN+FP+TN}$$
	
- F1-Score : harmonic mean of precision and recall
	$$ F1 = \frac{2TP}{2TP+FP+FN}$$