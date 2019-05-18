+++
date = "2018-02-07T13:55:04+08:00"
description = "深度学习框架Caffe"
title = "Caffe使用说明和在mac上安装Caffe"

+++

**介绍：**

[Caffe](http://caffe.berkeleyvision.org/tutorial/)是一个深度学习框架。

**说明：**

英文文档去官网上看，这儿我把说明书首页的概念提炼出来，首先对caffe有一个认识，同时回顾深度学习的概念，然后说明书的Tour部分详解了caffe的各种结构，我也会对每一层都整体介绍一下。以下是根据官方说明书的顺序和内容作的介绍和讲解。

<u>指导：</u>总而言之，caffe是一个深度学习框架，接下来的文章介绍的是它的理念（哲学），结构和用处，使用这个框架之前，最好有机器学习和神经网络的储备知识，但是这儿也会稍微介绍。

<u>哲学：</u>caffe的五个特色：压缩，高速，模块化，开放性，社区化

<u>浏览：</u>目录如下

- [Nets, Layers, and Blobs 网络，层，团](http://caffe.berkeleyvision.org/tutorial/net_layer_blob.html): 剖析caffe的模型结构
- [Forward / Backward 前进／后退](http://caffe.berkeleyvision.org/tutorial/forward_backward.html): 复合模型中必需的计算
- [Loss 损失](http://caffe.berkeleyvision.org/tutorial/loss.html): 训练计划是用loss定义的
- [Solver 解算机](http://caffe.berkeleyvision.org/tutorial/solver.html): 实现最优化
- [Layer Catalogue 层目录](http://caffe.berkeleyvision.org/tutorial/layers.html): 层结构是模型的基本单元
- [Interfaces 界面](http://caffe.berkeleyvision.org/tutorial/interfaces.html): 命令行, Python, MATLAB Caffe.
- [Data 数据](http://caffe.berkeleyvision.org/tutorial/data.html): 如何调整数据
- [Caffeinated Convolution caffe卷积](http://caffe.berkeleyvision.org/tutorial/convolution.html): 如何计算卷积

<u>深度学习：</u>

这里主要介绍了网上一些可以直接获取的深度学习的资料，特别是和视觉相关的，英文内容，直接阅读。

- [Tutorial on Deep Learning for Vision](https://sites.google.com/site/deeplearningcvpr2014/) from CVPR ‘14
- [Neural Networks and Deep Learning](http://neuralnetworksanddeeplearning.com/index.html) by Michael Nielsen
- [Deep Learning Tutorial](http://www.cs.nyu.edu/~yann/talks/lecun-ranzato-icml2013.pdf) by Yann LeCun (NYU, Facebook) and Marc’Aurelio Ranzato (Facebook). ICML 2013 tutorial.
- [LISA Deep Learning Tutorial](http://deeplearning.net/tutorial/deeplearning.pdf) by the LISA Lab directed by Yoshua Bengio (U. Montréal).

---

然后跟随目录，开始看一下caffe的结构，首先：

<u>Nets, Layers, and Blobs 网络，层，团：</u>