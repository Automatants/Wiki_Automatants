---
author: 'Thomas LEMERCIER'
date: '2021-12-29 (last update)'
description: ''
---

# Network In Network


## $1 \times 1$ Convolution

The goal of this paper was to have a network inside a [[Convolutional network|convolutional network]]. Their first idea was to introduce a MLP in between convolution which will process in input the vector of values of a pixel accros all the features map. 

![[MLPconv1x1.png]]

Let $l$ a layer of the network, $i, j$ the indices of a particular pixel, $k$ the number of feature maps at this layer, $c$ the number of wanted feature maps at the output of the layer. We denote $x_{i, j}  = [y^{(l)}_{i, j, 1}, ..., y^{(l)}_{i, j, k}]$.

Then we have :

$$y^{(l+1)}_{i, j, 1} = f(w^{(l)}_{1}x_{i, j})$$
$$.$$$$.$$$$.$$
$$y^{(l+1)}_{i, j, c} = f(w^{(l)}_{c}x_{i, j})$$

As you may have already notice this definition is equivalent to a $1 \times 1$ convolution and this $1 \times 1$ [[ConvolutionLayer|convolution]] will be used a lot in future architecture of [[Convolutional network|convolutional neural network]].

## Global Average pooling
^10cee9

Conventional convolutional neural networks perform convolution in the lower layers of the network. For classification, the feature maps of the last convolutional layer are vectorized and fed into fully connected layers followed by a softmax logistic regression layer. 
The idea is to generate one feature map for each corresponding category of the classification task. Instead of adding fully connected layers on top of the feature maps, we take the average of each feature map, and the resulting vector is fed directly into the softmax layer. 

https://arxiv.org/pdf/1312.4400.pdf