# 10. Unspervised learning and Generative models

[TOC]

## Unsupervised learning

* Find **underlying structure** in data
  * Cluster
  * Reducing the dimensionality
  * Build a better representation (word embedding)
  * Learning likelyhood function
  * Generating new samples

* For complex data

  * **Image data** : capture low dimensional semantic representation
  * **Text data** : find fixed size, dense semantic representation of data

  `Latet space might be more efficient`

* Self-supervised learning

  * Build supervision without labels
  * Use **text structure** to create supervision
    * Word2Vec, Skip-thought vectors, language models
  * **Image** : spatial context of an object
  * **Sound,video** : exploit temporal context

  `No direct accuracy measure`

## Autoencoders

![](https://ws2.sinaimg.cn/large/006tKfTcgy1g1bnw1n9coj30tw0kkjuy.jpg)

Keeping the **latend code $z$** low-dimensional forces the network to learn a "smart" compression of the data

Encoder and decoder can have arbitrary architectures (CNNs, RNNs)



* Sparse/Denoising Autoencoder

  * Adding a sparsity constraint on activations to learn sparse features.

    $||encoder(x)||_1 \sim p, p=0.05$

* Uses and limitations

  * After **pre-training** , use the latent code **z** as input to a classifier
  * **Semi-supervised learning** 
  * Use decoder $D(x)$ as a **Generative model**
  * **Limitations**
    * Not good for complex data such as images

* Reality Check

  * **ImageNet pretraining** is still **much better** than unsupervised models

## Variational Autoencoders



## Genarative Adversarial Networks

Alternate training of a **generative network** $G$ and a **discrimininative network** D



<img src="https://ws3.sinaimg.cn/large/006tKfTcly1g1j94lukycj30jk0q6gqg.jpg" width="300">

* D tries to find out which example are generated or real
* g tries to fool D into thinking its generated examples are real



