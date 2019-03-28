# 3. Recommender systems & embeddings

[TOC]

## Embeddings

Symbolic variable: Symbol $s$ in vocabulary $V$

* One -hot representation
  * Sparse, discrete, large dimension
  * Equidistant
* Embedding: $embedding('salad')=[3.23, 23.4,… 7.11] \in \mathbb{R}^d$
  * Continuous and dense
  * Embedding metric can capture semantic distance



Implementation with Keras

![](https://ws3.sinaimg.cn/large/006tKfTcly1g1ixue1no5j31fc0rw79b.jpg)



Distance:

* Euclidean distance
  * simple with good properties
  * dependent on norm
* Cosine similarity
  * regardless of norm
  * Expected cosine similarity of random paris of vectors is $0$



Visualizing Embeddings

* PCA: linear projection
* t-SNE (t-Distributed Stochastic Neighbor Embedding): not a deterministic model



## Dropout regularization

### Regularization

* Size of the embeddings
* Depth of the network
* $L_2$ penalty on embeddings
* Dropout:
  * Randomly set activations to $0$ with probability $p$
  * Bernoulli mask sampled for a forward pass / backward pass pair
  * Typically only enabled at training time



## Recommender Systems

### Content-based vs Collaborative Filtering(CF)

**Content-based** : user metadata(gender, age) and item metadata(genre, year)

**Collaborative Filtering** : passed user/item interactions : stars, likes, clicks..

**Hybrid systems** : CF + medatada to mitigate the cold-start problem



`Matrix Factorization for CF`

### Explicit vs Implicit Feedback

**Explicit**: positive and negative feedback

* Example : review star and votes
* Regression metrics: Root Mean Squared Error, Mean Absolute Error..

**Implicit**: positibe feedback only

* Examples: page views, plays, comments...
* Ranking metrics: ROC AUC, precisoin at rank, NDCG



Implicit feedback much more abundant than explicit feedback

Explicit feedback does not always reflect actual user bahaviors

Implicit feedback can be negative

Feedback distribution impacted by UI/UX changes



##  Architechture and Regularization

![](https://ws3.sinaimg.cn/large/006tKfTcly1g1iykhi9b9j314q0u0n2j.jpg)



![](https://ws2.sinaimg.cn/large/006tKfTcly1g1iyksnzkmj310o0u00yb.jpg)

![](https://ws2.sinaimg.cn/large/006tKfTcly1g1iyll8w1zj30yp0u0wn5.jpg)





## Ethical consideration

Gender bias, filter bubble...