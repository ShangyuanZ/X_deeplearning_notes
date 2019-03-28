# 9. Class imbalance and metric learning

[TOC]

## 深度学习的训练数据问题

* 理论中：
  * 每一个样本有一个标签
  * 若干个class，每个class都有成千上万的样本
* 实际情况：
  * 样本属于多个class
  * 数据集不平衡，有噪音
  * 几百万个class，每个class只有十几个样本

## 多标签和取样策略

* 必须采用oversampling，importance weighting等策略来处理数据，进行优化过程。

  ```python
  # build your own batches and add weights
  model.train_on_batch(self, x, y, class_weight=None, sample_weight=None)
  ```

* multi-label classification

  * 对每一个class都做一个二分类

* 弱监督

  * 输出空间的维度非常大(input ：图片 ， output：对图片的语言描述)

## Metric Learing & Siamese network

* 学习一个distance function $d_\theta (x_1,x_2)​$ 来判断两个样本点之间的距离，如果小于阈值 $T​$ ，那么就认为 $x_1,x_2​$ 属于一个class

  $$d_\theta(x_1,x_2) = ||f_\theta (x_1) - f_\theta (x_2)||_2 ​$$

  * Training $f_\theta$ 被称作 representation learning

* 损失函数：两者越近函数值越小，越远函数值越大

  * 余弦距离 $cosine(f_\theta (x_1) ,f_\theta (x_2))$ 

  * Absolute difference + binary classification 

    $y = sigmoid ( \mathbf{w} \cdot |f_{\theta}(x_1) - f_{\theta}(x_2)| + b)$ 

* 训练

## Triplet Loss

* A triplet: $(x^a,x^+,x^-)​$
  * an anchor image
  * positive image (same person as anchor)
  * negative image (different person as anchor)
* minimize $||f(x^a) - f(x^{+})||_2 - ||f(x^a) - f(x^{-})||_2 + \alpha​$ 

  * $\alpha$ is **margin**, which is a small positive number $(0.2,0.5)$
  * $l(x^a, x^{+}, x^{-}) = max(||f(x^a) - f(x^{+})\|\|_2 -  \|\|f(x^a) - f(x^{-})\|\|_2 + \alpha, 0)​$
* Hard negative sampling
* Quadruplet loss
* Histogram loss
* Available open source implementations / pretrained models:
  * [Openface](https://cmusatyalab.github.io/openface/)
  * [FaceNet](https://github.com/davidsandberg/facenet)
  * DeepFace

## Take aways on classification

* For most cases, user **classifier with softmax**
* For case that have many classes, or/and strong class imbalance. Use **representation learning**
* Use **ImageNet pre-trained features** in most cases

