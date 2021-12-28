---
author: 'Thomas LEMERCIER'
date: '2021-12-29 (last update)'
description: ''
---

# Dropout: A Simple Way to Prevent Neural Networks from Overfitting

Dropout pursue goals :
1.  Reducing [[Overfitting|overfitting] ([[Regularization|regularization technique]])
2. Approximately combine exponentially many different neural network architectures efficiently

![[dropout.png]]

Dropout will drop some of our neurons by dropping their value to zero during training time. The idea behind this is that neurons should be independent from the others neurons at least as independent as possible and not co-adapt. This is the first part of dropout which prevent [[Overfitting|overfitting]]. The second can be explained with the second part (b) of the image. As you can see, the network after applying dropout is a smaller network and during training time as the dropout is random we will get thousand or even millions of those small networks which will be trained.

![[dropoutneuron.png]]

During test time we don't want to have any randomness in our network to compensate the fact that an neuron was not present with a propability $p$ during training we scale the weight with a factor $p$ such that $w' = pw$, this is equivalent to scaling down the neuron value by a factor $p$.

The paper also uses max-norm regularization which implies training the network under the condition that $||w||_2 \le c$, with c being and constant and an hyperparameter. To do so they projected the $w$ onto the surface of a ball of radius c, whenever $w$ went out of it i.e. setting $w' = c \frac{w}{||w||_2}$.

They also observe that setting large decaying learning rates and high momentum provides a significant boost over just using dropout.

## Some results

On [[MNIST]] :
![[mnistdropoutresult.png]]
![[mnistdropoutgraph.png]]
![[mnistdropoutfeatures.png]]
![[mnistdropoutneuron.png]]



## Mathematical definition

Let $L \rightarrow$ number of hidden layers in your network
$l \in \{1, ..., L-1\}$, for a hidden unit $i$

Classic propagation :
$$z^{(l+1)}_{i} = w^{(l+1)}_{i}y^{(l)} + b^{(l+1)}_{i}$$
$$y^{(l+1)}_{i} = f(z^{(l+1)}_{i}y^{(l)})$$

Dropout propagation :
$$r^{(l)}_{i} \sim Bernoulli(p)$$
$$\tilde{y}^{(l)} = r^{(l)}*y^{(l)}$$
$$z^{(l+1)}_{i} = w^{(l+1)}_{i}\tilde{y}^{(l)} + b^{(l+1)}_{i}$$
$$y^{(l+1)}_{i} = f(z^{(l+1)}_{i}y^{(l)})$$

With $*$ being the element-wise product.

## Some of the guideline for training Dropout network

### Size of the network

As we drop a part of our network using dropout if we have $n$ neurons and a probability $p$ of dropping then we will train on pn neurons and different each time.
Therefore, if an $n$-sized layer is optimal for a standard neural net on any given task, a good dropout net should have at least $n/p$ units.

### Learning rate
Dropout introduces a significant amount of noise in the gradients compared to standard stochastic gradient descent. Therefore, a lot of gradients tend to cancel each other. In order to make up for this, a dropout net should typically use 10-100 times the learning rate that was optimal for a standard neural net. Another way to reduce the effect the noise is to use a high momentum. While momentum values of 0.9 are common for standard nets, with dropout we found that values around 0.95 to 0.99 work quite a lot better. Using high learning rate and/or momentum significantly speed up learning.  


### Max-norm Regularization  
Though large momentum and learning rate speed up learning, they sometimes cause the network weights to grow very large. To prevent this, we can use max-norm regularization. This constrains the norm of the vector of incoming weights at each hidden unit to be bound by a constant c. Typical values of c range from 3 to 4.  

A more popular way to regularize the network and constraint the network weights is to use [[WeightDecay|weight decay]].

### Dropout Rate  
Dropout introduces an extra hyperparameter—the probability of retaining a unit p. This hyperparameter controls the intensity of dropout. Typical values of p for hidden units are in the range 0.5 to 0.8.


https://www.cs.toronto.edu/~hinton/absps/JMLRdropout.pdf



