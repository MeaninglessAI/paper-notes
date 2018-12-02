## 1.DYAN: A Dynamical Atoms-Based Network For Video Prediction



### Abstract

视频预测，实时性很重要。但现在的State-of-art方法基于复杂的结构，需要学习很多的参数，训练也很困难，而且还会产生很多不准确的预测。在这篇paper中，提出了一个网络的结构——DYAN，相比现在其他的方法，他需要学习的参数很少，而且容易训练，也能够更快地做出高质量的，准确的帧预测。

之所以DYAN效果这么好，是因为他有两个关键组件，encoder 和decoder。这两个组件的设计原理来自于systems identiﬁcation theory，而且还利用了数据的动力学不变性（dynamics-based invariants of the data）。

我们在几个标准的video datasets 上进行了实验，实验表明DYAN预测效果很好，而且在不同的数据集（across domains）上泛化效果很好。

### Introduction

