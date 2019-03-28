

# 2. Neural networks and backpropagation

[TOC]

## Structure of neuron network

![](https://ws1.sinaimg.cn/large/006tKfTcly1g1iuiodnc6j30yf0u0438.jpg)



![](https://ws3.sinaimg.cn/large/006tKfTcly1g1iuoumtr1j311s0u078z.jpg)




![](https://ws1.sinaimg.cn/large/006tKfTcly1g1iv8dpx5rj311r0u0gtb.jpg)


## Element-wise activation funciton

* $sigmoid(x)=\frac{1}{1 + e^{-x}}$

* $tanh(x) = \frac{e^{2x}-1}{e^{2x} + 1}$

* $relu(x) = max(0,x)$

  ![](https://ws4.sinaimg.cn/large/006tKfTcly1g1ivez41zgj31jm0sygsc.jpg)

* softmax

  ![](https://ws4.sinaimg.cn/large/006tKfTcly1g1ivh8wnq6j315t0u0jww.jpg)

  

## Training the network

Searching parameters $\theta$ to minimize the **negative log likelihood** (or **cross entropy**)

![](https://ws3.sinaimg.cn/large/006tKfTcly1g1ivmqmxxzj31740u0q7w.jpg)



![](https://ws4.sinaimg.cn/large/006tKfTcly1g1ivnmh4cpj31i20jen0d.jpg)

### stochastic gradient descent



![](https://ws1.sinaimg.cn/large/006tKfTcly1g1ivrb92joj31640u043b.jpg)



`We can apply the "chian rule" to calculate gradients`

![](https://ws2.sinaimg.cn/large/006tKfTcly1g1ivtnc8tbj31bs0mg770.jpg)



`By using chain rule, we can calculate backpropagation gradients`

* Compute activation gradients
* Compute layer parameters gradients
* Compute prev layer activation gradients



## Loss, initialization and learning tricks

###For loss

* Discrete output (classification)

  output function : softmax (logistic if dim=2)

  loss funciton : cross-entropy

* Continuous output (regression)

  output function : identity

  loss function : square loss



###For initializaiton and normalizaiton

* Input data should be normalized to have approx. same range:
  * Standardization or quantile normalization
* initializaing $W$
  * Zero is a saddle point: no gradient, no learning
  * Constant init: hidden units collapse by symmetry
  * Solution : random init, ex Gaussien distribution
  * Better inits: Xavier Glorot and Kaming He & orthoganal
* Biases can (should) ba initalized to zero



###For SGD learning rate

* Very sentive
* Set large value first than divide by 1

Momentum
Nesterov accelarated gradient

###Alternative optimizers

* SGD

  * simple to implement
  * sensitive to inital value of learning rate
  * need learning rate scheduling

* Adam : adaptive learning rate scale for each param

  * global $\eta$ set to $3e-4$ often works well enough
  * good defualt choise

* Well-turned SGD with LR scheduling can generalize better than Adam

* Active area of research : K-FAC stochastic second-order method

  




