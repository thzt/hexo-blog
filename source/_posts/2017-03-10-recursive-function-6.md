---
layout: post
categories: Math
title: 递归函数（六）：最多有多少个程序
---

### 回顾

上一篇中，我们通过引入极小化算子定义了递归函数，

使用递归函数，我们又定义了递归集与递归可枚举集，

本文我们要讨论，为什么递归可枚举集是“可枚举”的，以及什么是可计算函数。

<br/>

### 可计算性

<br/>

![](https://raw.githubusercontent.com/thzt/hexo-blog/master/source/images/_posts/2017-03-10-recursive-function-6/1023733-3315ef8756b21619.png)

<br/>

我们听说过，现代计算机在计算能力上是与图灵机等价的，

什么叫做计算能力呢？

它指的是图灵机可计算的函数集，与现代计算机可计算的函数集是相等的。

<br/>

为了简单起见，我们不去讨论图灵机，而是从现代计算机直接说起，

设<span data-katex="\mathscr{P}"></span>是一段程序，<span data-katex="n"></span>是一个正整数，

我们称数论函数<span data-katex="\psi (x_1,x_2,\cdots ,x_n)"></span>为程序<span data-katex="\mathscr{P}"></span>所计算的<span data-katex="n"></span>元部分函数，

如果对于相同的输入，

要么：（1）程序<span data-katex="\mathscr{P}"></span>的计算可以终止，此时计算结果等于<span data-katex="\psi (x_1,x_2,\cdots ,x_n)"></span>的相应函数值；

要么：（2）程序<span data-katex="\mathscr{P}"></span>的计算不能终止，此时<span data-katex="\psi (x_1,x_2,\cdots ,x_n)"></span>无定义。

<br/>

设<span data-katex="f(x_1,x_2,\cdots ,x_n)"></span>是一个部分函数，如果存在程序<span data-katex="\mathscr{P}"></span>可计算<span data-katex="f"></span>，则称<span data-katex="f"></span>是部分可计算的。

如果一个函数，既是部分可计算的，又是全函数，则称这个函数是可计算的。

<br/>

可以证明，所有的原始递归函数和递归函数都是部分可计算的。

<br/>

### 通用程序

我们使用现代计算机进行编程的时候，并不是直接把程序的输入传给程序，

而是将程序本身以及它的输入，传给计算机，最后由计算机得到计算结果，

像这种接受任何程序和它的输入作为自己的输入，返回程序执行结果的程序，称为通用程序。

为此，通用程序需要把输入的程序进行编码。

<br/>

常用的编码方法，涉及[配对函数](https://zh.wikipedia.org/wiki/%E9%85%8D%E5%AF%B9%E5%87%BD%E6%95%B0)和[哥德尔编码](https://zh.wikipedia.org/wiki/%E5%93%A5%E5%BE%B7%E5%B0%94%E6%95%B0)。

为了不引入太多的复杂性，我们可以将程序的编码理解为存储程序的二进制数据，

不同的程序会有不同的二进制表示，每一个二进制表示可以对应一段程序（虽然可能不合法）。

哥德尔编码做的事情就是将程序和自然数集一一对应起来。

<br/>

![](https://raw.githubusercontent.com/thzt/hexo-blog/master/source/images/_posts/2017-03-10-recursive-function-6/1023733-3c5dd1454fcd0559.png)

<br/>

因此，所有程序的个数是可数的，而这些程序可计算的函数个数也一定是可数的，

它们可能是全函数，也可能是部分函数。

（其中，“可数”指的是可数集，可数集是与自然数集之间存在一一映射的集合。

<br/>

然而，自然数集上的函数全体并不可数，（证略

所以肯定存在程序不可计算的函数。

<br/>

### 集合个数的可枚举性

<br/>

![](https://raw.githubusercontent.com/thzt/hexo-blog/master/source/images/_posts/2017-03-10-recursive-function-6/1023733-a6e30544d2c6c7c3.png)

<br/>

程序<span data-katex="\mathscr{P}"></span>所计算的函数，我们可以记为<span data-katex="\psi (x_1,x_2,\cdots ,x_n)"></span>，

由此，我们可以定义通用程序<span data-katex="\Phi "></span>，则有，

<span data-katex="\Phi (x_1,x_2,\cdots ,x_n,y)=\psi (x_1,x_2,\cdots ,x_n)"></span>

其中，<span data-katex="y"></span>是程序<span data-katex="\mathscr{P}"></span>的编码。

<br/>

因为，所有的程序与自然数集一一对应，

所以，<span data-katex="\Phi (x_1,x_2,\cdots ,x_n,0),\Phi (x_1,x_2,\cdots ,x_n,1),\cdots"></span>

枚举了所有的<span data-katex="n"></span>元可计算函数。

<br/>

我们定义<span data-katex="W_y=\lbrace x\in N|\Phi(x,y)\downarrow \rbrace "></span>，

根据递归可枚举集的定义，每一个<span data-katex="W_y"></span>是一个递归可枚举集。

<br/>

又因为<span data-katex="\Phi(x,0),\Phi(x,1),\cdots "></span>枚举了所有的可计算函数，

而上一篇中我们看到，递归可枚举集是由部分递归函数（即，可计算函数）定义的，

一个部分递归函数确定出一个递归可枚举集，

所以，<span data-katex="W_0,W_1,\cdots "></span>枚举了所有的递归可枚举集。

<br/>

因此，集合<span data-katex="B"></span>是递归可枚举的，当且仅当存在<span data-katex="y\in N"></span>，使得<span data-katex="B=W_y"></span>，

称为枚举定理，这就是“枚举”的含义。

<br/>

令<span data-katex="K=\lbrace n\in N|n\in W_n\rbrace "></span>，

则<span data-katex="K"></span>是递归可枚举的，但不是递归的，（证略

因此，<span data-katex="\bar{K}"></span>不是递归可枚举的，否则<span data-katex="K"></span>就是递归集了。

（根据，集合<span data-katex="B"></span>是递归的当且仅当<span data-katex="B"></span>和<span data-katex="\bar{B}"></span>是递归可枚举的，见上一篇

<br/>

因此，我们找到了一个非递归的递归可枚举集<span data-katex="K"></span>，

以及一个非递归可枚举集<span data-katex="\bar{K}"></span>。

<br/>

### 停机问题

<br/>

![](https://raw.githubusercontent.com/thzt/hexo-blog/master/source/images/_posts/2017-03-10-recursive-function-6/1023733-1fb62dcb731ff72f.png)

<br/>

任给一个程序和一个自然数，问该程序对这个自然数输入的计算是否停止，

这个问题称为停机问题。

<br/>

我们可以用谓词<span data-katex="H(x,y)"></span>描述这个问题，

<span data-katex="H(x,y)"></span>，表示以<span data-katex="y"></span>为代码的程序对输入<span data-katex="x"></span>的计算最终停止。

那么，<span data-katex="H(x,y)"></span>是不可计算的，即，不存在一个程序来计算<span data-katex="H(x,y)"></span>。

<br/>

我们来证明一下，假设有一个程序可以计算<span data-katex="H(x,y)"></span>，

那么我们就能用它来构造一个新程序<span data-katex="\mathscr{P}"></span>，它的输入是<span data-katex="x"></span>，

这段程序当<span data-katex="H(x,x)"></span>为真时，计算不停止，而当<span data-katex="H(x,x)"></span>为假时，计算停止。

<br/>

程序<span data-katex="\mathscr{P}"></span>也可以进行编码，假设为<span data-katex="y_0"></span>，现在我们来判断<span data-katex="H(y_0,y_0)"></span>。

<br/>

如果<span data-katex="H(y_0,y_0)"></span>为真，意味着编码为<span data-katex="y_0"></span>的程序以<span data-katex="y_0"></span>作为输入最终停止，

即程序<span data-katex="\mathscr{P}"></span>，输入为<span data-katex="y_0"></span>时，最终停止，

可是根据<span data-katex="\mathscr{P}"></span>的定义，此时<span data-katex="H(x,x)=H(y_0,y_0)"></span>为假才会停止，矛盾。

<br/>

如果<span data-katex="H(y_0,y_0)"></span>为假，意味着编码为<span data-katex="y_0"></span>的程序以<span data-katex="y_0"></span>作为参数最终不会停止，

即程序<span data-katex="\mathscr{P}"></span>，输入为<span data-katex="y_0"></span>时，最终不停止，

可是根据<span data-katex="\mathscr{P}"></span>的定义，此时<span data-katex="H(x,x)=H(y_0,y_0)"></span>为真才不会停止，矛盾。

<br/>

<span data-katex="H(y_0,y_0)"></span>不能为真也不能为假，矛盾，

因此，计算<span data-katex="H(x,y)"></span>的程序不存在，我们也无法用它来构造程序<span data-katex="\mathscr{P}"></span>。

<br/>

### 可判定性

<br/>

![](https://raw.githubusercontent.com/thzt/hexo-blog/master/source/images/_posts/2017-03-10-recursive-function-6/1023733-5e01504f5037d0e0.png)

<br/>

可判定性问题，指的是一个询问真或者假的问题是否可以被回答。

如果我们总能回答出这个问题是真或者是假，就称该问题是可判定的，

如果我们只能当问题为真的时候确定为真，为假的时候所进行的计算可能不会终止，那么就称该问题是半可判定的。

<br/>

某元素是否属于一个递归集，是可判定的，

某元素是否属于一个递归可枚举集，是半可判定的。

<br/>

因为，递归集是使用一个递归的全函数定义的，

而递归可枚举集是使用第一个部分递归函数定义的，

我们无法判断某个部分递归函数，在接受某参数时，是没有定义，还是计算尚未停止。

即，判断元素是否属于某递归可枚举集的程序可能永不停机。

<br/>

### 总结

本文介绍了函数的可计算性，通用程序，以及最多有多少个程序，

还了解了停机问题和可判定性问题。

<br/>

这些都是可计算性理论的基础，我们清晰的看到了人类的计算能力，

以及用递归所能计算的函数范围，后文中我们开始讨论不动点理论，

这同样是一个有趣的话题。

- - -

### 附

配对函数和哥德尔数，是对数偶和有穷数列的一种编码方式。

<br/>

（1）配对函数

令<span data-katex="\langle x,y\rangle=2^x(2y+1)-1"></span>，称<span data-katex="\langle x,y\rangle "></span>为配对函数，它是一个原始递归函数。

任给一个数<span data-katex="z"></span>，存在唯一的一对数<span data-katex="x"></span>和<span data-katex="y"></span>，使得<span data-katex="\langle x,y\rangle =z"></span>。

<span data-katex="x"></span>是<span data-katex="z+1"></span>含有因子<span data-katex="2"></span>的个数，即使得<span data-katex="2^t|(z+1)"></span>的<span data-katex="t"></span>的最大值。

<span data-katex="(z+1)/2^x"></span>必为奇数，<span data-katex="y"></span>是<span data-katex="2y+1=(z+1)/2^x"></span>的唯一解。

一般的，记<span data-katex="l(z)=x"></span>，<span data-katex="r(z)=y"></span>，则<span data-katex="l(z)"></span>和<span data-katex="r(z)"></span>也是原始递归函数。

<br/>

（2）哥德尔数

记<span data-katex="[a_1,a_2,\cdots ,a_n]=\prod_{i=1}^{n}p_i^{a_i}"></span>，

<span data-katex="[a_1,a_2,\cdots ,a_n]"></span>称为有穷数列<span data-katex="(a_1,a_2,\cdots ,a_n)"></span>的哥德尔数。

其中，<span data-katex="p_i"></span>是第<span data-katex="i"></span>个素数。

<br/>

例如，<span data-katex="[2,0,1,3]=2^2\cdot 3^0\cdot 5^1\cdot 7^3=6860"></span>。

对于每一个固定的<span data-katex="n"></span>，<span data-katex="[a_1,a_2,\cdots ,a_n]"></span>是原始递归函数，并且这种编码具有唯一性。

- - -

### 参考

[配对函数](https://zh.wikipedia.org/wiki/%E9%85%8D%E5%AF%B9%E5%87%BD%E6%95%B0)

[哥德尔数](https://zh.wikipedia.org/wiki/%E5%93%A5%E5%BE%B7%E5%B0%94%E6%95%B0)

[可数集](https://zh.wikipedia.org/wiki/%E5%8F%AF%E6%95%B8%E9%9B%86)

[可判定性](https://zh.wikipedia.org/wiki/%E5%8F%AF%E5%88%A4%E5%AE%9A%E6%80%A7)

[康托尔定理](https://zh.wikipedia.org/zh-hans/%E5%BA%B7%E6%89%98%E5%B0%94%E5%AE%9A%E7%90%86)