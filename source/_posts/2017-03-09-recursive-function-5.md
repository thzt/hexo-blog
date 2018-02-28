---
layout: post
categories: Math
title: 递归函数（五）：递归集与递归可枚举集
---

### 回顾

上文中我们讨论了全函数和部分函数，以及计算的可终止性。

本文我们从数论函数开始，给原始递归函数集增加一种新的运算，得到了一个更大的集合。

然后根据递归函数，我们可以定义递归集和递归可枚举集，

为以后讨论可计算性与可判定性打好基础。

<br/>

### 数论函数

<br/>

![](http://upload-images.jianshu.io/upload_images/1023733-567ebbb9d0fa7c88.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

自然数集一般记为<span data-katex="N=\lbrace 0,1,2,\cdots \rbrace "></span>，那么<span data-katex="n"></span>个自然数集的笛卡尔积记为<span data-katex="N^n"></span>，

于是，我们称集合<span data-katex="N^n"></span>到<span data-katex="N"></span>的部分函数为<span data-katex="n"></span>元部分数论函数。

作为数论函数，<span data-katex="2x"></span>是一个全函数，而<span data-katex="x/2"></span>，<span data-katex="x-y"></span>，<span data-katex="\sqrt{x}"></span>只是部分函数，

它们的计算结果，<span data-katex="3/2"></span>，<span data-katex="4-6"></span>，<span data-katex="\sqrt{5}"></span>都不在<span data-katex="N"></span>中，于是相应定义域中的点可视为没有定义。

<br/>

为什么讨论数论函数呢，其一是因为它是一个典型数学的问题，

另外一点，则是因为我们经常把其他数学问题转换成数论问题，例如，[哥德尔编码](https://zh.wikipedia.org/wiki/%E5%93%A5%E5%BE%B7%E5%B0%94%E6%95%B0)。

本文中，使用数论函数，可以简化我们的描述方式。

<br/>

一个谓词，指的是返回布尔值的函数，

我们还可以将谓词看做值域为<span data-katex="\lbrace 0,1\rbrace "></span>的一个数论函数。

<span data-katex="0"></span>代表`True`，<span data-katex="1"></span>代表`False`。

<br/>

### 极小化算子

<br/>

![](http://upload-images.jianshu.io/upload_images/1023733-b1d4c18df4caf3bc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

在前一篇中，我们从三个初始函数出发，

通过合成运算和原始递归运算，得到了原始递归函数集，

递归函数集是相对于这两种运算封闭的。

<br/>

然而，这样定义的原始递归函数，并不能包括所有的数论函数，

一个典型的例子就是，[阿克曼函数](https://zh.wikipedia.org/zh/%E9%98%BF%E5%85%8B%E6%9B%BC%E5%87%BD%E6%95%B8)，

```
ackermann :: Int -> Int -> Int 
ackermann 0 x = x+1
ackermann k 0 = ackermann (k-1) 1
ackermann k x = ackermann (k-1) $ ackermann k x-1
```

它并不是一个原始递归函数，（证略

因此原始递归函数集并不足以表示计算机程序中的所有函数。

<br/>

为此，我们需要对原始递归函数集进行扩充，我们定义一个新的运算，称为极小化运算，

设<span data-katex="P(x_1,\cdots ,x_n,t)"></span>是一个谓词，令

<span data-katex="f(x_1,\cdots ,x_n)=min\ P(x_1,\cdots ,x_n,t)"></span>

<br/>

<span data-katex="f(x_1,\cdots ,x_n)"></span>的值，或者是使<span data-katex="P(x_1,\cdots ,x_n,t)"></span>为真的最小<span data-katex="t"></span>值，

或者无定义，此时不存在<span data-katex="t"></span>使得<span data-katex="P(x_1,\cdots ,x_n,t)"></span>为真。

这样通过<span data-katex="min"></span>得到<span data-katex="f(x_1,\cdots ,x_n)"></span>的过程称为极小化运算，

也称部分函数<span data-katex="f(x_1,\cdots ,x_n)"></span>是由谓词经过极小化运算得到的。

<br/>

以上我们给谓词定义了极小化运算，现在我们将极小化运算推广到一般的函数上面，

设<span data-katex="g(x_1,\cdots ,x_n,t)"></span>是一个<span data-katex="n+1"></span>元函数，令

<span data-katex="f(x_1,\cdots ,x_n)=min\lbrace g(x_1,\cdots ,x_n,t)=0\rbrace "></span>

则称部分函数<span data-katex="f(x_1,\cdots ,x_n)"></span>是由函数<span data-katex="g(x_1,\cdots ,x_n,t)"></span>经过极小化运算得到的。

<br/>

### 递归函数集

和定义原始递归函数集一样，我们从以下三个初始函数出发，

（1）零函数<span data-katex="n(x)=0"></span>

（2）后继函数<span data-katex="s(x)=x+1"></span>

（3）投影函数<span data-katex="u^n_i(x_1,\cdots ,x_n)=x_i"></span>，<span data-katex="i\leqslant i\leqslant n"></span>

由初始函数，经过有限次合成运算，原始递归运算，以及极小化运算，得到的函数称为递归函数。

<br/>

递归函数并不一定是全函数，因为极小化运算可能会导致结果函数在某些点无定义，

递归的部分函数称为部分递归函数。

<br/>

可以证明阿克曼函数是递归函数，但不是原始递归函数，

因此，原始递归函数集是递归函数集的真子集。

<br/>

### 递归可枚举集

<br/>

![](http://upload-images.jianshu.io/upload_images/1023733-6f7383f96e58c74e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

在具体实践中，我们经常会遇到这样的问题，

给定一个元素，我们需要判断这个元素是否属于某个集合。

这种问题，称为集合的成员资格问题。

<br/>

沿用这一思路，我们可以使用一个谓词<span data-katex="\chi _B"></span>来定义相应的集合<span data-katex="B\subseteq N"></span>，

<span data-katex="B=\lbrace x\in N|\chi _B(x)\rbrace "></span>

谓词<span data-katex="\chi _B(x)"></span>为真，则<span data-katex="x\in B"></span>。

这个谓词<span data-katex="\chi _B(x)"></span>，通常称为集合<span data-katex="B"></span>的特征函数。

<br/>

如果特征函数<span data-katex="\chi _B"></span>是第一个递归的全函数，

则我们总是可以判断<span data-katex="\chi _B(x)"></span>等于<span data-katex="0"></span>还是<span data-katex="1"></span>，

这样的集合<span data-katex="B"></span>称为递归集。

<br/>

如果存在部分递归函数<span data-katex="g"></span>，使得<span data-katex="B=\lbrace x\in N|g(x)\downarrow \rbrace"></span>，

即，<span data-katex="x\in B"></span>当且仅当<span data-katex="g"></span>在<span data-katex="x"></span>处有定义，

则称集合<span data-katex="B"></span>是一个递归可枚举集。

<br/>

因此，对于每一个自然数<span data-katex="x\in N"></span>，

我们总是可以通过递归集<span data-katex="B"></span>的特征函数<span data-katex="\chi _B"></span>，来判断<span data-katex="x"></span>是否<span data-katex="B"></span>的成员。

而对于递归可枚举集，就不容乐观了，

如果某个自然数<span data-katex="x\in N"></span>是<span data-katex="B"></span>的成员，那么我们可以断定这件事，因为<span data-katex="g(x)"></span>有定义，

但是如果某个自然数<span data-katex="y\in N"></span>不是<span data-katex="B"></span>的成员，我们就不能确定，因为这时候<span data-katex="g(x)"></span>无定义。

（<span data-katex="g(x)"></span>无定义，则它对应的图灵机不停机，后文我们详细讨论

<br/>

因此，集合<span data-katex="B"></span>是递归的当且仅当<span data-katex="B"></span>和<span data-katex="\bar{B}"></span>是递归可枚举的，

其中<span data-katex="\bar{B}"></span>为<span data-katex="B"></span>的补集。

<br/>

### 总结

本文介绍了数论函数，递归函数集，然后用递归函数分别定义了递归集和递归可枚举集，

可是为什么递归可枚举集是“可枚举”的呢？

<br/>

是因为每一个递归可枚举集可以一一对应一个自然数，这是怎样做到的呢？

这需要我们理解总共有多少个可能的程序，以及什么是通用程序。

<br/>

### 参考

[递归集](https://zh.wikipedia.org/wiki/%E9%80%92%E5%BD%92%E9%9B%86%E5%90%88)

[递归可枚举集](https://zh.wikipedia.org/wiki/%E9%80%92%E5%BD%92%E5%8F%AF%E6%9E%9A%E4%B8%BE%E9%9B%86%E5%90%88)