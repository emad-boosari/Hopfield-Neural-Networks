# Hopfield Neural Networks
A Hopfield neural network (or *Ising model* of a neural network) is a form of artificial *recurrent neural networks* (__RNN__) and a type of **spin glass** system popularised by **John Hopfield** in 1982. Hopfield networks serve as `content-addressable ("associative") memory` systems with binary threshold nodes, or with continuous variables.



Here I am going to focus on the discrete Hopfield Neural Networks (HNNs) because of some future quantum computation showcases.
***
## Discrete Hopfield Neural Network
The HNN can be summerized using the following simple four-steps algorithm.

1. Memorizing Process
Let me consider patterns $\bf{\xi}^1$, $\xi^2, \ldots, \xi^M$, are $N$-dimensional prototype patterns. Then we can easily memorize them inside the synaptic weights ${w_{ij}}$ by using **Hebb's learning rule**
$$w_{ij} = \frac{1}{N} \sum_{i=1}^M \xi_{i}^{\mu}\xi_{j}^{\mu} - \frac{M}{N}\delta_{ij}$$

or in the matrix form

$$<W> = \frac{1}{N} \sum_{i=1}^M \bf{\xi}\bf{\xi}^T - \frac{M}{N}I_N$$

3. Initializing Process
4. Iteration
5. Result
