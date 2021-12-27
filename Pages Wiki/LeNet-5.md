---
author: 'Thomas LEMERCIER'
date: '2021-12-27 (last update)'
description: 'Un des premiers papiers sur les CNNs'
---

# Gradient-Based Learning Applied to Document Recognition

One of the first article that demonstrates the power of [[Convolutional network|convolutional neural network]].

It used the [[MNIST]] dataset. The architecture is straight forward, it's a succession of [[ConvolutionLayer|convolution layer]] and  [[AvgPooling|average pooling]] followed by a plain network of [[LinearLayer|linear layer]] each of this layers ([[ConvolutionLayer|convolution layer]] and [[LinearLayer|linear layer]]) are followed by an [[Sigmoid|sigmoid activation]] in the convolutional part of the network and [[Tanh|hyperbolic tangent]] in the plain network.

## Network

![[lenet5.png]]

### Network parameters



```mermaid
flowchart TD
 input([1*32*32]) --Conv--> state1([6*28*28])
 state1 --AvgPool--> state2([6*14*14])
 state2 --Conv--> state3([16*10*10])
 state3 --AvgPool--> state4([16*5*5])
 state4 --Conv equiv to Linear--> state5([120*1*1])
 state5 --Linear--> state6([84])
 state6 --Linear--> output([10])
```


https://axon.cs.byu.edu/~martinez/classes/678/Papers/Convolution_nets.pdf