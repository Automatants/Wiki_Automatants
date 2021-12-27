---
author: 'Thomas LEMERCIER'
date: '2021-12-27 (last update)'
description: ''
---


# ImageNet Classification with Deep Convolutional Neural Networks

Thanks to increased [[GPU]] capacity and efficiency, they are now powerful  
enough to facilitate the training of interestingly-large [[Convolutional network|CNNs]], and recent datasets such as [[ImageNet]] contain enough labeled examples to train such models without severe [[Overfitting|overfitting]].

## Innovation

### New activation

The AlexNet network introduces a new non-linearity function : the [[ReLU]].

### Training on multiple GPUs

At this time the GPU even if the GPUs had an increased in capacity and performance the GPU still had less memory than now. For instance the GPUs used for the training of AlexNet "GTX 580" had only 3GB of memory. To address this issue, the authors of the papers spreaded the network across two GPUs by putting halfs of the neurons on each GPU. Futhermore, the GPUs only communicated at specific layer of the network.

### Local Response Normalization

Thanks to the [[ReLU|ReLU activaion]] the network does not require normalization to prevent them from saturating. However, the author still find that a local normalization scheme aids generalization. This normalization is called [[LRN|Local Responce Normalization]].

### Overlapping Pooling

Traditionally, the neighborhoods summarized by adjacent pooling units do not overlap. To be more precise, a pooling layer can be thought of as consisting of a grid of pooling units spaced $s$ pixels apart, each summarizing a neighborhood of size $z\times z$ centered at the location of the pooling unit. If we set $s = z$, we obtain traditional local pooling as commonly employed in CNNs. If we set $s < z$, we obtain overlapping pooling. This is what we use throughout our network, with $s = 2$ and $z=3$.

## Training
For training, the optimizer used was a [[StochasticGradientDescent|stochastic gradient descent]] with a batch size of $128$, momentum of $0.9$ and a [[WeightDecay|weight decay]] of $0.0005$.

## Architecture

The architecture contains eight learned layers five [[ConvolutionLayer|convolutional layer]] and three [[LinearLayer|fully-connected layer]]. The main differences with the previous [[LeNet-5]] network are :
- the use of [[MaxPooling|max-pooling layer]] instead of [[AvgPooling|avg-pooling layer]]
- the activation only follows the [[ConvolutionLayer|convolutional layer]]
- uses of [[LRN|Local Responce Normalization]] after some activation layer
- to reduce [[Overfitting|overfitting]] the authors of the paper use [[Dropout|dropout]] in the first two [[LinearLayer|fully-connected layer]]

![[TL5kcp.jpg]]