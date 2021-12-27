# ReLU activation

The standard way to model a neuron’s output f as a function of its input x is with $f(x) = tanh(x)$ or $f(x) = (1 + e^{−x})^{−1}$. In terms of training time with gradient descent, these [[SaturatingNonLinearity|saturating nonlinearities]] are much slower than the non-saturating nonlinearity $f(x) = max(0,x)$.

![[Pastedimage20211208162027.png]]

ReLU activation is inspirated from the paper : [Rectified Linear Units Improve Restricted Boltzmann Machines](https://www.cs.toronto.edu/~hinton/absps/reluICML.pdf) but became more used after the [[AlexNet]] paper.