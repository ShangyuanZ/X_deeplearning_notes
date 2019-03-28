# 7. Deep NLP p2

[TOC]

## Encoder-Decoder for machine tranlation

Encoder-Decoder

![](https://ws4.sinaimg.cn/large/006tKfTcly1g1j84ibyj9j319l0u0jw8.jpg)



## Attention Mechanism

Main problem with Encoder-Decoder:

* A sentence may have different parts with different concepts
* The **whole sentence** is represented as **single vector**

Solution :

* Use all outputs of the encoder $h_i$ to compute the outputs
* build an **Attention Mechanism** to determine which output to attend to

![](https://ws1.sinaimg.cn/large/006tKfTcly1g1j8d9skjsj31800u0ahk.jpg)



![](https://ws2.sinaimg.cn/large/006tKfTcly1g1j8e8qq2oj318f0u010q.jpg)



![](https://ws2.sinaimg.cn/large/006tKfTcly1g1j8g86rk4j31820u0guc.jpg)



## Reasonning, Attention and Memory

Question answering tasks

Memory Networks

Key-Value Networks

