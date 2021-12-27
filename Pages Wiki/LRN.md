# Local Responsce Normalization

Denoting by $a^i_{x,y}$ the activity of a neuron computed by applying kernel i at position $(x,y)$ and then applying the ReLU nonlinearity, the response-normalized activity $b^i_{x,y}$ is given by the expression :

$$b^i_{x,y} = a^i_{x,y}/\Bigg(k + \alpha \sum_{j=max(0,i−n/2)}^{min(N−1,i+n/2)}
(a^j_{x,y})^2\Bigg)^\beta$$
where the sum runs over $n$ “adjacent” kernel maps at the same spatial position, and N is the total number of kernels in the layer.

$k, n, \alpha, \beta$ are hyper-parameters whose values are determined using a [[ValidationSet|validation set]].