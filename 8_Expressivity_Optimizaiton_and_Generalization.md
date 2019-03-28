# 8. Expressivity, Optimizaiton and Generalization

[TOC]

## Decomposition of the Error

$\mathcal{F}$ : hypothesis calss, and $f_{\mathcal{F}} ^{\star} \in \mathcal{F}$ is the best hypothesis

* Approximation error
  * decreases when $\mathcal{F}$ increases
  * but typically bounded by computational constraints
* Estimation error
  * decreases when $n$ increases
  * Can increase when $\mathcal{F}$ increase (accoring to VC theory)
* Optimization error
  * can increase when tolerance $\rho$ increases
  * can increase when $\mathcal{F}$ gets more complex (non-convex obj)



## Expressivity and Universal Function Approximation



## Optimization for Deep Networks



## Generalization

Overfitting 



Adding hidden units:

* does not lead to more overfitting
* make optimization easier (less steps)
* make computation slower

Adding layers:

* does not cause much more overfitting either
* can cause optimization issues (underfitting)





## Conclusions

* DL optimization is non-convex but bad local minima and saddle structures are rarely a problem
* A stronger optimizer is not necessarily a stronger learner
* Neural Networks are over-parameterized but can still generalize
* We need more theoty to guide the design of architecture and optimizers that make learning faster with fewer labels






