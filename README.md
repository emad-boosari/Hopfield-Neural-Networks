# Hopfield Neural Networks
A Hopfield neural network (or *Ising model* of a neural network) is a form of artificial *recurrent neural networks* (__RNN__) and a type of **spin glass** system popularised by **John Hopfield** in 1982. Hopfield networks serve as `content-addressable ("associative") memory` systems with binary threshold nodes, or with continuous variables.

![image](https://user-images.githubusercontent.com/58440271/210186665-f1b38c39-d142-4964-9788-5bb375abf561.png)


Here I am going to focus on the discrete Hopfield Neural Networks (HNNs) because of some future quantum computation showcases.
***
> ## Discrete Hopfield Neural Network
The HNN can be summerized using the following simple four-steps algorithm.

1. Memorizing Process
Let me consider patterns $\vec{\xi}^1$, $\vec{\xi^2}$, $\ldots$, $\vec{\xi^M}$, are $N$-dimensional prototype patterns. Then we can easily memorize them inside the synaptic weights ${w_{ij}}$ by using **Hebb's learning rule**
$$w_{ij} = \frac{1}{N} \sum_{\mu=1}^M \xi_{i}^{\mu}\xi_{j}^{\mu} - \frac{M}{N}\delta_{ij}$$

or in the matrix form

$$
\begin{equation}
\mathbf{W} = \frac{1}{N} \sum_{\mu=1}^M \vec{\xi}^{\mu}(\vec{\xi}^{\mu})^T - \frac{M}{N} \mathbf{I}_N 
\end{equation}
$$

where $\textbf{I}_n$ is the $N\times N$ identity matrix. Once computed, the synaptic weights remain fixed.
3. Initializing



5. Iteration
The elements are updated asynchronously (i.e., one at a time in a random order) according to the rule

![image](https://user-images.githubusercontent.com/58440271/210186636-d2c99574-09ec-4a41-a1f2-8420ee5b00de.png)


![image](https://user-images.githubusercontent.com/58440271/210186627-d16ce316-a309-450c-b96b-ac230b400268.png)


7. Result
