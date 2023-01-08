# Hopfield Neural Networks
A Hopfield neural network (or *Ising model* of a neural network) is a form of artificial *recurrent neural networks* (__RNN__) and a type of **spin glass** system popularised by **John Hopfield** in 1982. Hopfield networks serve as `content-addressable ("associative") memory` systems with binary threshold nodes, or with continuous variables.

Here I am going to focus on the discrete Hopfield Neural Networks (HNNs) because of some future quantum computation showcases.
***
> ## Discrete Hopfield Neural Network
The HNN can be summerized using the following simple four-steps algorithm.

1. Memorizing Process

Let me consider patterns $\vec{\xi}^1$, $\vec{\xi^2}$, $\ldots$, $\vec{\xi^M}$, are $N$-dimensional prototype patterns (vectors/states). Then we can easily memorize them inside the synaptic weights ${w_{ij}}$ by using **Hebb's learning rule**
$$w_{ij} = \frac{1}{N} \sum_{\mu=1}^M \xi_{i}^{\mu}\xi_{j}^{\mu} - \frac{M}{N}\delta_{ij}$$

or in the matrix form

$$
\begin{equation}
\mathbf{W} = \frac{1}{N} \sum_{\mu=1}^M \vec{\xi}^{\mu}(\vec{\xi}^{\mu})^T - \frac{M}{N} \mathbf{I}_N 
\end{equation}
$$

where $\textbf{I}_n$ is the $N\times N$ identity matrix. Once computed, the synaptic weights remain fixed.

2. Initialization

Let $x_p$ denote the unknown __probe vector__ (input vector/test vector) to be tested. The algorithm is initialized by setting

$$ x_i(0) = x_{ip} \qquad\qquad i= 0,1,\ldots N$$

where $x_i(0)$ is the state of neuron $i$ at time $n = 0$, $x_{ip}$ is the $i$th element of vector $x_p$, and $N$ is the number of neurons.


3. Iteration
The elements are updated asynchronously (i.e., one at a time in a random order) according to the rule
$$x_i(t+1) = hsgn\Bigg(\sum_{j=1}^N w_{ij}x_j(t) \Bigg) \qquad\qquad i= 0,1,\ldots N$$

where

$$
\begin{figure}
![image](https://user-images.githubusercontent.com/58440271/211214849-69a53a94-3fee-46f9-9eca-acf46d279c32.png) 
\end{figure}
$$



and $v_i(t+1) = \sum w_{ij} x_j(t)$. The iterations are repeated until the vector converges to a stable value. Note that at least $N$ iterations are
carried out to guarantee convergence. 

4. Result

The stable vector, say, $x_{fixed}$, is the result.

The algorithm above uses _asynchronous updating_ of synaptic weights. _Synchronous updating_ is the procedure by which weights are updated __simultaneously__. The fundamental memories should first be presented to the Hopfield
network. This tests the network’s ability to recover the stored vectors using
the computed synaptic weight matrix. The desired patterns should be recovered after one iteration; if not, then an error has been made. Distorted patterns
or patterns missing information can then be tested using the above algorithm. There are two possible outcomes.
1. The network converges to one of the fundamental memories.
2. The network converges to a spurious steady state. Spurious steady states include the following:
   * (a) __Reversed fundamental memories__— e.g., if $x_f$ is a fundamental memory, then so is $−xf$.
   * (b) __Mixed fundamental memories__— a linear combination of fundamental memories.
   * (c) __Spin-glass states__—local minima not correlated with any fundamental memories.
Before looking at an application of a Hopfield network as a content-addressable memory, a simple example is shown below to illustrate the algorithm.
