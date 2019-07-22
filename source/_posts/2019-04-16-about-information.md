---
layout: post
categories: Mind
title: 信息的隐藏、暴露和传递

---

![](https://raw.githubusercontent.com/thzt/hexo-blog/master/source/images/_posts/2019-04-16-about-information/1023733-16f88d518fb63c18.png)

<br/>

信息是一个很复杂的概念，信息论影响了很多学科，

包括电子工程，计算机科学，物理学，数学，科学哲学，经济学，等等。

<br/>

> Information theory studies the transmission, processing, extraction, and utilization of information. 

> Abstractly, information can be thought of as the resolution of uncertainty.

> —— [wikipedia: Information theory](https://en.wikipedia.org/wiki/Information_theory)

<br/>

信息可以用来消除不确定性，这个说法来源于 [Shannon](https://en.wikipedia.org/wiki/Claude_Shannon)，

1948年他发表了 [A Mathematical Theory of Communication](https://en.wikipedia.org/wiki/A_Mathematical_Theory_of_Communication)，

提出了[信息熵](https://zh.wikipedia.org/wiki/%E7%86%B5_(%E4%BF%A1%E6%81%AF%E8%AE%BA))的概念。

<br/>

信息熵是随机变量不确定度的度量，

设<span data-katex="X"></span>是一个随机变量，其字母表（即概率论中的取值空间）为<span data-katex="\mathcal{X}"></span>，

概率密度函数<span data-katex="p(x)=Pr(X=x),~x\in\mathcal{X}"></span>。

<br/>

则，离散型随机变量<span data-katex="X"></span>的**熵**<span data-katex="H(X)"></span>定义为，

<span data-katex="H(X)=-\sum_{x\in\mathcal{X}}p(x)log_2p(x)"></span>

<br/>

熵的单位用比特表示，例如抛掷均匀硬币这一事件的熵为，

<span data-katex="H(X)=-\left [ \frac{1}{2}log_2\left ( \frac{1}{2} \right ) + \frac{1}{2}log_2\left ( \frac{1}{2} \right ) \right ] = 1"></span> 比特。

### 信息隐藏

既然信息可以用来消除不确定性，那么是不是信息量越大越好呢？

其实不然，因为能够**传递信息**的[带宽](https://zh.wikipedia.org/wiki/%E5%B8%A6%E5%AE%BD)是有限的。

并且，对于接受信息的一方而言，单位时间内能够**接受**的信息量也是有限的。

<br/>

因此，在涉及信息传递的时候，

我们一方面要考虑如何提高带宽，如何提高接受方的信息处理效率，

另一方面，还要考虑如何减少**无效信息量**。

<br/>

现如今，如何处理信息，如何加速有效信息的传递，

已逐渐成为了**知识密集型**工作的新瓶颈点。

<br/>

从这个意义上来看，面向对象编程范式提倡的**封装**思想，

确实有利于工作效率的进一步提高。

<br/>

不过，封装也本不应该与任何编程范式进行强绑定，

这可能是面向对象所起到的反作用之一吧。

<br/>

封装隐藏了具体的细节，只暴露出必要的信息，

有效的降低了信息处理的负荷。

### 信息暴露

之前在知乎上看到了一个回答，[VR 电影目前最大的瓶颈是什么？](https://www.zhihu.com/question/39947219/answer/214338328)，

> 电影的本质，是有**框视觉**。「框」是导演给到观众的信息感受区。

> 框内框外都是导演出于自己的艺术创造，为观众重新打造的空间。

> 而景别，就是决定这个框里框外边界的根本。

> 真正电影创作者非常看重画外空间。

<br/>

可见电影的好坏，很大程度上取决于创作者特意给观众营造的**视听效果**。

电影如此，软件设计也是如此。

<br/>

我们应该对哪些细节进行隐藏，哪些信息进行暴露，

对于软件，尤其是框架/工具的设计而言，起着至关重要的作用。

它会极大的改变用户的使用成本和**学习曲线**。

<br/>

让别人能更好的理解，是一件很有学问的事情。

陡峭的学习曲线会使人望而却步，会浪费很多不必要的人力成本。

<br/>

人们总是很难站在缺少信息的一方考虑问题的，

这称为[知识的诅咒](https://zh.wikipedia.org/zh-hans/%E7%9F%A5%E8%AD%98%E7%9A%84%E8%A9%9B%E5%92%92)，是一种[认知偏差](https://zh.wikipedia.org/wiki/%E8%AA%8D%E7%9F%A5%E5%81%8F%E8%AA%A4)，

知识的诅咒是影响沟通的重大阻碍之一。

### 信息传递

对于软件开发而言，代码与其说是开发者对功能的具体实现，

倒不如说是他们对**领域知识**的理解和描述。

<br/>

不幸的是，由于代码只要能运行就完成了基本功能，

所以，很大一部分信息量都没有被包含在代码中。

它们存在于开发者的大脑中，存在于代码之外的地方。

<br/>

在有众多开发者的企业中，每天产出的新信息是无法估量的，

如果这些信息没有被很好的隐藏和暴露，

就会造成信息污染，严重的影响整体的开发效率。

<br/>

不仅如此，软件质量也会受到波及。

在一个不确定的系统中，发生**莫名其妙的故障**概率大大增加。

中医讲究“**不通则痛**”，是有道理的。

<br/>

因此，仅从代码的可复用角度来解决问题，是不可取的，

应该对组织的**沟通结构**和软件**系统架构**，更为关心。

<br/>

[康威](https://zh.wikipedia.org/wiki/%E9%A9%AC%E5%B0%94%E6%96%87%C2%B7%E5%BA%B7%E5%A8%81)在1967年提出，

> 设计系统的架构受制于产生这些设计的组织的沟通结构。

> —— [康威定律](https://zh.wikipedia.org/zh-hans/%E5%BA%B7%E5%A8%81%E5%AE%9A%E5%BE%8B)

<br/>

所以，沟通结构不合理的组织，所产出的软件系统，

对于解决业务问题而言是力不从心的。

<br/>

也就是组织文化决定了人们做事的方式。

团队是领导本人处事态度的缩影。

### 结语

软件开发工作中，与信息相关的内容，还远不止如此，

比如，组内成员的做事方式，是否纵容了[信息孤岛](https://wiki.mbalib.com/wiki/%E4%BF%A1%E6%81%AF%E5%AD%A4%E5%B2%9B)的形成，

又比如，管理者是否关心由于信息沟通不畅所产生的问题排查成本。

<br/>

这既是软件本身的特点问题，也是软件团队的管理方式问题，

违反软件规律的做法，就会受到惩罚。

<br/>

> 你一个人要干三天，我给你三个人，你给我干一天。

> 五个人不够，我给你加十个人、加二十个人。

- - -

### 参考

[wikipedia: Information theory](https://en.wikipedia.org/wiki/Information_theory)

[信息论基础](https://book.douban.com/subject/2305237/)

[信息熵](https://zh.wikipedia.org/wiki/%E7%86%B5_(%E4%BF%A1%E6%81%AF%E8%AE%BA))

[康威定律](https://zh.wikipedia.org/zh-hans/%E5%BA%B7%E5%A8%81%E5%AE%9A%E5%BE%8B)
