---
author: 'Thomas LEMERCIER'
date: '2021-12-29 (last update)'
description: ''
---

# Average Pooling 

Average Pooling is a pooling operation that calculates the average value for patches of a feature map, and uses it to create a downsampled (pooled) feature map. It is usually used after a [[ConvolutionLayer|convolutional layer]]. It adds a small amount of translation invariance - meaning translating the image by a small amount does not significantly affect the values of most pooled outputs. It extracts features more smoothly than [[MaxPooling|Max Pooling]], whereas max pooling extracts more pronounced features like edges.

![[avgpooling.png|200]]


Another usage of average pooling is [[Network in Network#^10cee9|global average pooling]] which has been introduces in the [[Network in Network|network in network paper]].