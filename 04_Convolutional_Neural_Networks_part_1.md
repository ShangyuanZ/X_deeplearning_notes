## 4. Convolutional Neural Networks part 1

[TOC]

![](https://ws1.sinaimg.cn/large/006tKfTcly1g1iypwca87j31j40pyk4v.jpg)



## Convolutions

### Motivations

![](https://ws1.sinaimg.cn/large/006tKfTcly1g1iyrfjgzzj310s0kkadi.jpg)

Spatial organization is destroyed by `Flatten`

We never use Dense layers directly on large images

![](https://ws4.sinaimg.cn/large/006tKfTcly1g1iytg3u8cj31c00ogte0.jpg)

### Convolution in a neural network

![](https://ws3.sinaimg.cn/large/006tKfTcly1g1iyuq1ftlj318d0u0486.jpg)

Local connectivity:

* A neuron depengs only on a few local input neurons
* Translaiton invariance
* Strong prior for vision



![](https://ws1.sinaimg.cn/large/006tKfTcly1g1iyxm1fuvj30wz0u0te4.jpg)

Some notion:

* Strides: increment step size for the convolution operator
* Padding: artificially fill borders of image



### Dealing with shapes

![](https://ws4.sinaimg.cn/large/006tKfTcly1g1iz1u2aa9j31100u0td5.jpg)

### Pooling

* Spatial dimension reduction
* Local invariance
* No parameters: max or average

![](https://ws3.sinaimg.cn/large/006tKfTcly1g1iz4bs8h0j318a0kqdrn.jpg)



## Archeitecture

### Classic ConvNet Architecture

* Input
* Conv blocks
  * Convolution + activation (relu)
  * Convolution + activation (relu)
  * ..
  * Maxpooling $2\times2$
* Output
  * Fully connected layers
  * Softmax



### AlexNet

![](https://ws3.sinaimg.cn/large/006tKfTcly1g1izceftjaj317t0u0k1y.jpg)

`Convolutional layer can extract features from low level to high level`



### VGG-16

![](https://ws1.sinaimg.cn/large/006tKfTcly1g1izejm8efj31aw0sk7gj.jpg)

![](https://ws1.sinaimg.cn/large/006tKfTcly1g1izezg3dbj312i0u0wsd.jpg)



### ResNet

Even deeper layer

Compare to VGG:

* Less parameters
* Less computational complexity
* Superior accuracy

`Deeper is better`



### State of the art

Some model comparison in `Esteban Real, et al. Regularized Evolution for Image Classifier Architecture Search (Feb 2018)`



* Modular building blocks engineering
* Finding right architectures



Automated architecture search:

* Reinforcement learning
* Evolutionary algorithms



## Pre-trained models

Training a model on ImageNet from scratch thaks days or weeks.

Many models trained on ImageNet and their weights are publicly available.

Transfer learning:

* Use pre-trained weights, remove last layers to compute representations of images
* Train a classification model from these features on a new classification task
* The network is used as generic feature extractor
* Better than handcraft feature extraction on natural images

Fine-tuning:

* Truncate the last layers(s) of the pre-trained netwok
* Freeze the remaining layers weights
* Add a (linear) classifier on top and train it for a few epochs
* Use a smaller learning rate when fine tuning



Data Augmentation