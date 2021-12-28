# Very Deep convolutional networks for large-scale image recognition
It is the first [[Convolutional network|CNN]] to use only small receptive fields $(3 \times 3)$ throughout the whole network. The network is also designed to be simple to create with few hyperparameters, this can be seen has reducing the risk to [[Overfitting|overfit]] on the [[TestSet| test set]] by tuning those hyperparameters.

## Justification

The network uses $(3 \times 3)$ [[ConvolutionLayer|convolution]] as it is the smallest convolution capturing a notion of direction (left/right, up/down). Futhermore, a succession of $(3 \times 3)$ [[ConvolutionLayer|convolution]] can be seen as a $(5 \times 5)$, $(7 \times 7)$  with some extra non-linearities which in theory will just add more discrimination to the decision function.
The other advantage of smaller convolution is the number of parameters : 
For a simple 7 kernel convolution from C channels to C channels we have  : $7^2C^2$
For 3 simple 3 kernel convolution from C channels to C channels we have : $3(3^2C^2)$.

VGG also uses $(1 \times 1)$ convolutions as in [[Network in Network]].