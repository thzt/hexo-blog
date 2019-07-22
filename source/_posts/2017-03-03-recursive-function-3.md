---
layout: post
categories: Math
title: 递归函数（三）：归纳原理
---

### 自然数归纳法

<br/>

https://raw.githubusercontent.com/thzt/hexo-blog/master/source/images/_posts/2017-03-03-recursive-function-3/1023733-b5630d6350cb8d0f.png

<br/>

自然数归纳法，是一种数学证明方法，通常被用于证明某个给定命题在整个（或者局部）自然数范围内成立。

它可以用一个有限的方式写出一个无限的证明。

后续文章中我们会看到，这种用有限表示无限的方法，其实是有局限性的，并不能用来解决所有的问题，

它能处理的只是无限中的一个子集罢了。

<br/>

自然数归纳法，我们可以描述如下：

为证明对每一个自然数<span data-katex="n"></span>，命题<span data-katex="P(n)"></span>为真，只需要证明两件事，

（1）对于自然数<span data-katex="1"></span>，命题<span data-katex="P(1)"></span>为真

（2）如果对于自然数<span data-katex="m"></span>，命题<span data-katex="P(m)"></span>为真，那么对于自然数<span data-katex="m+1"></span>，命题<span data-katex="P(m+1)"></span>也为真

<br/>

其中，第(1)条称为起始条件，第(2)条称为递推条件，或者称为归纳步骤。

第(2)条中，为了证明<span data-katex="P(m+1)"></span>而假设的<span data-katex="P(m)"></span>，称为归纳假设。

<br/>

这似乎是很显然的事情，我们可以在一张无限长的纸带开头写上初始条件<span data-katex="P(1)"></span>，

接着根据递推条件，由<span data-katex="P(1)"></span>我们可以证明<span data-katex="P(2)"></span>成立，

重复这种思想，我们可以由<span data-katex="P(2)"></span>证明<span data-katex="P(3)"></span>成立，如此不断的进行下去，

最终，对于每个自然数<span data-katex="n"></span>，我们都能证明<span data-katex="P(n)"></span>成立。

<br/>

但是，这样并不算是一个有效的证明。

要证明自然数归纳法的正确性，我们还需要补充一些集合论方面的知识。

然而，在此之前，我们还是先来看自然数归纳法的一个例子吧。

<br/>

### 例子

<br/>

https://raw.githubusercontent.com/thzt/hexo-blog/master/source/images/_posts/2017-03-03-recursive-function-3/1023733-a8ad53859d33e161.png

<br/>

在上一篇，我们在定义递归函数`fact`的时候，

先找到了“递推式”，再找到了“终止条件”，然后写出了`fact`的定义：

```
fact :: Int -> Int
fact 1 = 1
fact n = n * fact (n-1)
```

<br/>

我们还提到，有一个步骤是必不可少的，

那就是证明`fact`的正确性，即证明这样定义的`fact`就是阶乘函数<span data-katex="f(n)=n!"></span>。

<br/>

现在，我们正好可以用自然数归纳法来证明它。

我们假设命题<span data-katex="P(n)"></span>为：`fact n`的值为<span data-katex="n!"></span>

<br/>

（1）对于自然数<span data-katex="1"></span>，命题<span data-katex="P(1)"></span>：`fact 1`的值为<span data-katex="1!=1"></span>，成立

（2）假设对于自然数<span data-katex="m"></span>，命题<span data-katex="P(m)"></span>：`fact m`的值为<span data-katex="m!"></span>，成立；

那么，我们可以得到`fact (m+1) = (m+1) * fact m`，值为<span data-katex="(m+1)*m!=(m+1)!"></span>，也成立。

<br/>

所以，对于任意自然数（<span data-katex="n\geqslant 1"></span>），`fact n`的值就是<span data-katex="n!"></span>。

于是，我们证明了`fact`就是阶乘函数<span data-katex="f(n)=n!"></span>。

<br/>

自然数归纳法还有另外一种等价形式，

如果要证明<span data-katex="P(n)"></span>对每一个自然数<span data-katex="n"></span>为真，

只要证明对于任意自然数<span data-katex="m"></span>，如果<span data-katex="P(i)"></span>当<span data-katex="i<m"></span>为真，那么<span data-katex="P(m)"></span>也为真。

<br/>

### 集合上的关系

<br/>

https://raw.githubusercontent.com/thzt/hexo-blog/master/source/images/_posts/2017-03-03-recursive-function-3/1023733-eec07e9f1d1ccdb2.png

<br/>

关系是一个日常生活用语，例如，“同学关系”，“我们的关系很好”之类的。

然而，它也是一个集合论中的概念，这给我们带来了很多困扰。

为了避免歧义，本文中从这里开始，我们开始谈论数学，我们要对集合上的“关系”进行定义。

<br/>

直观的说，集合<span data-katex="A"></span>的元素和集合<span data-katex="B"></span>的元素之间的关系是一个二元性质<span data-katex="R"></span>，

使得对于每个<span data-katex="a\in A"></span>和<span data-katex="b\in B"></span>而言，<span data-katex="R(a,b)"></span>要么为真，要么为假。

<br/>

关系通常表示为一个集合，它是笛卡尔积的子集，即，

集合<span data-katex="A"></span>和集合<span data-katex="B"></span>之间的关系<span data-katex="R"></span>是它们笛卡尔积的一个子集<span data-katex="R\subseteq A\times B"></span>。

如果序对<span data-katex="(a,b)"></span>属于子集<span data-katex="R"></span>，则认为<span data-katex="a"></span>与<span data-katex="b"></span>之间的关系为真，否则认为<span data-katex="a"></span>与<span data-katex="b"></span>之间的关系为假。

通常关系直接描述为<span data-katex="R(a,b)"></span>，或者<span data-katex="aRb"></span>，而不用<span data-katex="(a,b)\in R"></span>。

<br/>

除了二元关系之外，对任何正整数<span data-katex="k"></span>，还可以定义<span data-katex="k"></span>元关系。

如果<span data-katex="A_1,\cdots,A_k"></span>为集合，则在<span data-katex="A_1,\cdots,A_k"></span>上的<span data-katex="k"></span>元关系是笛卡尔积<span data-katex="A_1\times \cdots \times A_k"></span>的一个子集。

<br/>

某个集合上的二元关系有很多性质，例如自反性，对称性，反对称性，传递性。

一个关系<span data-katex="R\subseteq A\times A"></span>是自反的，如果<span data-katex="R(a,a)"></span>对于所有的<span data-katex="a\in A"></span>成立；

是对称的，如果<span data-katex="R(a,b)"></span>就有<span data-katex="R(b,a)"></span>，对于所有的<span data-katex="a,b\in A"></span>都成立；

是反对称的，如果<span data-katex="R(a,b)"></span>且<span data-katex="R(b,a)"></span>，则<span data-katex="a,b"></span>是同一个元素，对于所有的<span data-katex="a,b\in A"></span>都成立；

是传递的，如果<span data-katex="R(a,b)"></span>和<span data-katex="R(b,c)"></span>能推出<span data-katex="R(a,c)"></span>，对于所有的<span data-katex="a,b,c\in A"></span>都成立。

（注意，反对称性不是对称性的否定。

<br/>

等价关系是同时具有自反性，对称性和传递性的关系。

偏序关系是具有自反性，反对称性和传递性的关系。

等价关系的一个例子就是相等性，相等性关系<span data-katex="R(a,b)"></span>当且仅当<span data-katex="a,b"></span>是同一个元素。

偏序关系，例如通常的序关系<span data-katex="R\subseteq N\times N"></span>，<span data-katex="R(a,b)"></span>当且仅当<span data-katex="a\leqslant b"></span>。

<br/>

### 良基关系

<br/>

https://raw.githubusercontent.com/thzt/hexo-blog/master/source/images/_posts/2017-03-03-recursive-function-3/1023733-cde531c9f6d2cab2.png

<br/>

归纳法有各种各样的形式，自然数归纳法只是其中的一种应用，

在数理逻辑和形式语言理论中，用的最多的是结构归纳法，在树形结构上进行归纳，后续文章中我们会提到。

<br/>

人们总结了各种归纳法的共性，提出了良基关系的概念，

于是，自然数归纳法和结构归纳法都变成了在良基关系上通用归纳法的具体应用了。

<br/>

集合<span data-katex="A"></span>上的良基关系（well-founded relation），是<span data-katex="A"></span>上的一个二元关系<span data-katex="\prec "></span>，

如果不存在无限下降序列（infinite descending sequence）<span data-katex="a_0\succ a_1\succ a_2\cdots"></span>。

例如，自然数上的关系<span data-katex="<"></span>，就是一个良基关系。

但是<span data-katex="\leqslant "></span>却不是，因为存在一个无限下降序列<span data-katex="a_0\geqslant a_1\geqslant a_2\cdots"></span>。

<br/>

根据良基关系，我们可以定义集合中的最小元，

<span data-katex="a\in A"></span>为最小元，如果不存在<span data-katex="a'\in A"></span>，使得<span data-katex="a'\prec a"></span>。

<br/>

对于良基关系，有一个等价的定义，

<span data-katex="A"></span>上的二元关系<span data-katex="\prec "></span>是良基的，当且仅当<span data-katex="A"></span>的每一个非空子集<span data-katex="B"></span>有最小元。

<br/>

我们可以证明一下这两种说法等价性。

要证当且仅当，我们需要证明充分性和必要性，

（1）充分性：

要证：<span data-katex="A"></span>上的二元关系<span data-katex="\prec "></span>是良基的，则<span data-katex="A"></span>的每一个非空子集<span data-katex="B"></span>有最小元。

使用反证法，如果<span data-katex="B"></span>没有最小元，则对于每个<span data-katex="a\in B"></span>，总可以找到<span data-katex="a'\in B"></span>，使得<span data-katex="a'\prec a"></span>。

但是，如果这样的话，我们就可以对任何<span data-katex="a_0\in B"></span>，以<span data-katex="a_0"></span>开始构造一个无限下降序列<span data-katex="a_0\succ a_1\succ a_2\cdots"></span>，

这与<span data-katex="\prec "></span>是一个良基关系矛盾。充分性证毕。

<br/>

（2） 必要性：

要证：如果<span data-katex="A"></span>的每一个非空子集<span data-katex="B"></span>都有最小元，则<span data-katex="A"></span>上用于比较的二元关系<span data-katex="\prec "></span>是良基的。

由于<span data-katex="A"></span>的每一个非空子集<span data-katex="B"></span>都有最小元，则不可能存在无限下降序列<span data-katex="a_0\succ a_1\succ a_2\cdots"></span>，

因此，<span data-katex="\prec "></span>是良基的。必要性证毕。

<br/>

因此，<span data-katex="A"></span>上的二元关系<span data-katex="\prec "></span>是良基的，当且仅当<span data-katex="A"></span>的每一个非空子集<span data-katex="B"></span>有最小元。

<br/>

### 良基归纳法

<br/>

https://raw.githubusercontent.com/thzt/hexo-blog/master/source/images/_posts/2017-03-03-recursive-function-3/1023733-b14783f3b0cddba1.png

<br/>

设<span data-katex="\prec "></span>为集合<span data-katex="A"></span>上的良基二元关系，并且设<span data-katex="P"></span>为关于<span data-katex="A"></span>中元素的某个命题，

如果<span data-katex="P(b)"></span>对于所有的<span data-katex="b\prec a"></span>成立，就必然有<span data-katex="P(a)"></span>成立，

那么<span data-katex="P(a)"></span>就对所有的<span data-katex="a\in A"></span>成立。

<br/>

我们看到<span data-katex="<"></span>确实是自然数集上的良基关系，因此自然数归纳法只是良基归纳法的一种特例。

<br/>

现在我们有了足够的能力来证明自然数归纳法的正确性了，

只要我们证明了良基归纳法是正确的。

<br/>

还是用反证法：

我们期望证明，

前提：如果<span data-katex="P(b)"></span>对于所有的<span data-katex="b\prec a"></span>成立，必然有<span data-katex="P(a)"></span>成立，

结论：那么对于所有的<span data-katex="a\in A"></span>，<span data-katex="P(a)"></span>都成立。

<br/>

如若不然，假设存在<span data-katex="x\in A"></span>，使得<span data-katex="P(x)"></span>不成立，

则集合<span data-katex="B=\{a\in A\ |\ \neg P(a)\}"></span>非空，

因此根据良基关系的等价定义，集合<span data-katex="B"></span>必有最小元<span data-katex="m\prec B\subseteq A"></span>，

而且，<span data-katex="\neg P(m)"></span>成立。

<br/>

则根据前提的逆否命题，一定存在<span data-katex="b\prec m"></span>，使得<span data-katex="\neg P(b)"></span>成立，

所以，我们有<span data-katex="b\in B"></span>，且<span data-katex="b \prec m"></span>，与<span data-katex="m"></span>是<span data-katex="B"></span>的最小元矛盾。

<br/>

证毕。

<br/>

由此，我们证明了良基归纳法的正确性。

理解良基关系和偏序关系，是理解递归和不动点算子的第一步。

<br/>

### 总结

<br/>

https://raw.githubusercontent.com/thzt/hexo-blog/master/source/images/_posts/2017-03-03-recursive-function-3/1023733-7e329a3fec9f7a22.png

<br/>

本文从自然数归纳法出发，补充了一些集合论方面的知识，

让我们熟悉了集合上的几种常用关系，例如，等价关系，偏序关系和良基关系，

这些关系在以后的文章中还会被再次提到。

<br/>

最后，我们证明了良基归纳法，从而证明了自然数归纳法的正确性。

不知道是否很明显了，递归的步骤和归纳的步骤，简直是太像了，

这一定不是偶然。

<br/>

在[The Little Prover](https://book.douban.com/subject/26429992/)一书中，为了证明递归函数是否全函数（total function），

作者使用了测度（measure）的概念，这实际上定义了参数集上的一个良基关系。

全函数是可计算理论中一个很重要的概念，

到底什么是全函数，什么是测度？下文我们再详细讨论。

<br/>

### 参考

[维基百科 - 数学归纳法](https://zh.wikipedia.org/zh-hans/%E6%95%B0%E5%AD%A6%E5%BD%92%E7%BA%B3%E6%B3%95)

[维基百科 - 二元关系](https://zh.wikipedia.org/wiki/%E4%BA%8C%E5%85%83%E5%85%B3%E7%B3%BB)

[维基百科 - 良基关系](https://zh.wikipedia.org/wiki/%E8%89%AF%E5%9F%BA%E5%85%B3%E7%B3%BB)

[程序设计语言的形式语义](https://book.douban.com/subject/1144542/)