# 6. Deep NLP p1

[TOC]

## Word Representation and Word2Vec

From one-hot vector to word embedding

### Supervised Text Classification

Embedding + NN

* efficient on large datasets
* State-of-the-art on several classification when adding **bigrams/trigrams**
* Little gains from depth



### Transfer Learning for Text

**Unsupervised / self-supervised** learning of word representations

**Unlabelled** text data is almost infinite



### Word2Vec

Self-supervised training : words are characterised by the company that they keep



* CBoW (continuous Bag-of-Word): context $\rightarrow$ word
  * Large impact of **context size**
* Skip Gram: word $\rightarrow$ context
  * Widely used in practice
  * **Negative Sampling** is used as a cheaper alternative to full softmax

`Other popular method: GloVe`



### Take Away on embedding

* If little training data, use pre-trained self-supervised embeddings
* If large training data with labels, directly learn task-specific embedding with methods such as **fastText in supervised mode**
* Methods use Bag-of-words ignore the order in word sequence
* Depth & non-linear activations on hidden layers are not that useful for BoW text classification



## Language Modelling and Recurrent Neural Networks

### RNN

Conditional Language models: use conditional probalility (usually a sequence of probability) to build the model

![](https://ws2.sinaimg.cn/large/006tKfTcly1g1j6r6bl1ij312g0hqary.jpg)



![](https://ws1.sinaimg.cn/large/006tKfTcly1g1j6rq79hlj317e0fi0yr.jpg)



### LSTM

![](https://ws4.sinaimg.cn/large/006tKfTcly1g1j6y3ssbkj312k0r6k44.jpg)



<img src="https://ws1.sinaimg.cn/large/006tKfTcly1g1j6ycht63j30g60nsdk5.jpg" width="200">

![](https://ws2.sinaimg.cn/large/006tKfTcly1g1j6yzu1ykj31380rqqgw.jpg)



### GRU

* Similar idea as LSTM, no systematic difference
* In practice, more recent, people tend to use LSTM more



### Vanishing / Exploding Gradients

* Gradient messages close to $0$ can shrink be $0$
* gradient messages larger than $1$ can explode
* **LSTM / GRU** mitigate that in rnns



