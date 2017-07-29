---
layout: post
categories: Math
title: 良基归纳法
katex: true
---

### 极小元与最小元

设<span data-katex="(A,\leqslant)"></span>是偏序集，<span data-katex="Q\subseteq A"></span>，<span data-katex="y\in Q"></span>，

<br/>

如果<span data-katex="\forall x\in Q"></span>，<span data-katex="x\leqslant y\Rightarrow x=y"></span>，

则称<span data-katex="y"></span>为<span data-katex="Q"></span>的**极小元**。

<br/>

如果<span data-katex="\forall x\in Q"></span>，<span data-katex="y\leqslant x"></span>，

则称<span data-katex="y"></span>为<span data-katex="Q"></span>的**最小元**。

<br/>

注意极小元与最小元的区别，

最小元是集合中最小的元素，它与集合中其他元素都可比，

而极小元不一定与集合中其他元素都可比，

只要没有比它小的元素，它就是极小元。

<br/>

对于有穷集合，极小元一定存在，但最小元不一定存在，

最小元如果存在一定是唯一的，但极小元可能有多个。

<br/>

### 良基关系

设<span data-katex="\prec"></span>是集合<span data-katex="A"></span>上的二元关系，

如果不存在由<span data-katex="A"></span>中的元素构成的**无穷下降链**，

<span data-katex="\cdots\prec a_i\prec\cdots\prec a_1\prec a_0"></span>，

则称<span data-katex="\prec"></span>为良基关系（well-founded relation）。

<br/>

若<span data-katex="a\prec b"></span>，则称<span data-katex="a"></span>是<span data-katex="b"></span>的**前趋**。

<br/>

良基关系一定是**非自反的**，也就是说<span data-katex="a\prec a"></span>不成立，

否则就会有一条无穷下降链，<span data-katex="\cdots\prec a\prec\cdots\prec a\prec a"></span>。

<br/>

一般我们用<span data-katex="\preceq"></span>来表示关系<span data-katex="\prec"></span>的自反闭包，即，

<span data-katex="a\preceq b"></span>，当且仅当，<span data-katex="a=b"></span>或<span data-katex="a\prec b"></span>。

<br/>

良基关系<span data-katex="\prec"></span>的传递闭包<span data-katex="\prec^+"></span>是一个良基关系。

它的自反传递闭包<span data-katex="\prec^*"></span>是一个偏序关系。

<br/>

### 良基性质

有时还可以用极小元的概念来定义良基关系。

<br/>

设<span data-katex="\prec"></span>是集合<span data-katex="A"></span>上的二元关系，称关系<span data-katex="\prec"></span>是**良基的**，

当且仅当，<span data-katex="A"></span>的所有非空子集<span data-katex="Q"></span>都含有一个极小元<span data-katex="m\in Q"></span>，

即，<span data-katex="\forall b\prec m"></span>，<span data-katex="b\notin Q"></span>。

<br/>

**（1）充分性**

如果<span data-katex="\prec"></span>是集合<span data-katex="A"></span>上的良基关系，

则我们可以通过以下方法找出集合<span data-katex="A"></span>的任一子集<span data-katex="Q"></span>中的极小元。

<br/>

取<span data-katex="a_0"></span>为<span data-katex="Q"></span>中的任一元素，

假设<span data-katex="Q"></span>中已经构造了一条链<span data-katex="a_n\prec\cdots\prec a_0"></span>，

则在<span data-katex="Q"></span>中，或者存在<span data-katex="b\prec a_n"></span>，或者不存在这样的<span data-katex="b"></span>。

<br/>

如果<span data-katex="Q"></span>中不存在这样的<span data-katex="b"></span>，则停止链的构造，<span data-katex="a_n"></span>就是<span data-katex="Q"></span>的极小元，

否则，取<span data-katex="a_{n+1}=b"></span>，由于<span data-katex="\prec"></span>是良基的，

所以，链<span data-katex="\cdots\prec a_i\prec\cdots\prec a_1\prec a_0"></span>的长度是有限的，

最左边的元素，就是<span data-katex="Q"></span>的极小元。

<br/>

**（2）必要性**

如果集合<span data-katex="A"></span>的所有非空子集都有极小元，

那么必定不存在一条无穷下降链，<span data-katex="\cdots\prec a_i\prec\cdots\prec a_1\prec a_0"></span>，

否则<span data-katex="Q=\{a_i|i=0,1,\cdots\}"></span>，就是集合<span data-katex="A"></span>的一个不含极小元的非空子集，与前提矛盾。

<br/>

### 良基归纳法

设<span data-katex="\prec"></span>是集合<span data-katex="A"></span>上的良基关系，<span data-katex="P"></span>是某一性质，

则<span data-katex="\forall a\in A.\ P(a)"></span>，当且仅当，

<span data-katex="\forall x\in A.\ ([\forall y\prec x.\ P(y)]\Rightarrow P(x))"></span>。

<br/>

良基归纳法说的是，

要证明集合上的所有元素都满足某一性质，只要证明，

对于任意元素<span data-katex="x"></span>，如果它的所有前趋该性质都成立，必有对<span data-katex="x"></span>来说该性质也成立。

<br/>

**（1）充分性**

如果<span data-katex="\forall a\in A.\ P(a)"></span>，

则<span data-katex="\forall x\in A.\ (\forall y\prec x.\ P(y))"></span>，且<span data-katex="\forall x\in A.\ P(x)"></span>，

因此，<span data-katex="\forall x\in A.\ ([\forall y\prec x.\ P(y)]\Rightarrow P(x))"></span>。

<br/>

**（2）必要性**

假设<span data-katex="\forall x\in A.\ ([\forall y\prec x.\ P(y)]\Rightarrow P(x))"></span>，

但是<span data-katex="\exists z\in A"></span>，使得<span data-katex="\neg P(z)"></span>。

<br/>

那么，我们就可以构造出一个集合<span data-katex="Q=\{z\in A|\neg P(z)\}"></span>，满足<span data-katex="Q\subseteq A"></span>，<span data-katex="Q\neq\varnothing"></span>，

因此，根据良基关系的性质，<span data-katex="Q"></span>必有极小元<span data-katex="m"></span>，<span data-katex="\neg P(m)"></span>为真。

<br/>

但是根据前提，<span data-katex="\forall x\in A.\ ([\forall y\prec x.\ P(y)]\Rightarrow P(x))"></span>，

我们有，<span data-katex="(\forall y\prec m.\ P(y))\Rightarrow P(m)"></span>，

由于<span data-katex="\neg P(m)"></span>为真，所以一定<span data-katex="\exists y\prec m.\ \neg P(y)"></span>，<span data-katex="y\in A"></span>，

所以，<span data-katex="y\in Q"></span>，且<span data-katex="y\prec m"></span>，这与<span data-katex="m"></span>为<span data-katex="Q"></span>的极小元矛盾。

<br/>

因此，不存在<span data-katex="z\in A"></span>，使得<span data-katex="\neg P(z)"></span>，

即，<span data-katex="\forall a\in A.\ P(a)"></span>。

<br/>

### 参考

[二元关系](https://zh.wikipedia.org/wiki/%E4%BA%8C%E5%85%83%E5%85%B3%E7%B3%BB)

[偏序关系](https://zh.wikipedia.org/zh-cn/%E5%81%8F%E5%BA%8F%E5%85%B3%E7%B3%BB)

[良基关系](https://zh.wikipedia.org/wiki/%E8%89%AF%E5%9F%BA%E5%85%B3%E7%B3%BB)

[极小元](https://zh.wikipedia.org/zh-hans/%E6%9E%81%E5%B0%8F%E5%85%83)

[最小元](https://zh.wikipedia.org/wiki/%E6%9C%80%E5%B0%8F%E5%85%83)

[数学归纳法](https://zh.wikipedia.org/zh-hans/%E6%95%B0%E5%AD%A6%E5%BD%92%E7%BA%B3%E6%B3%95)

[程序设计语言的形式语义](https://book.douban.com/subject/1144542/)