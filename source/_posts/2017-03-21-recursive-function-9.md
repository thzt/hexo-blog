---
layout: post
categories: Math
title: 递归函数（九）：最小不动点定理
---

### 回顾

上文我们讨论了集合上的偏序结构，之所以谈论它们是因为，

完全偏序集上的连续函数具有最小不动点，这称之为最小不动点定理，

除了集合论的一些知识之外，我们还要讨论到底什么是连续函数，以及什么是完全偏序集。

<br/>

### 有向子集与完全偏序

偏序集<span data-katex="(D,\leqslant )"></span>的非空子集<span data-katex="S\subseteq D"></span>叫做有向子集（directed subset），

当且仅当，对于<span data-katex="S"></span>中的任意元素<span data-katex="a,b\in S"></span>，

存在<span data-katex="S"></span>中的一个元素<span data-katex="c"></span>，有<span data-katex="a\leqslant c"></span>且<span data-katex="b\leqslant c"></span>。

<br/>

如果一个偏序集<span data-katex="(D,\leqslant )"></span>的每个有向子集<span data-katex="S\subseteq D"></span>都有上确界（记为<span data-katex="\bigvee S"></span>）

就称它是一个有向完全偏序集，

此外，如果它还有最小元，就称它是一个完全偏序集。

<br/>

注意，完全偏序集并不是每一个子集都有上确界，

而是它的每一个有向子集都有上确界。

<br/>

### 连续函数

假设<span data-katex="(D,\leqslant )"></span>与<span data-katex="(E,\leqslant )"></span>是完全偏序集，

<span data-katex="f:D\rightarrow E"></span>是集合上定义的一个函数，

如果，<span data-katex="S\subseteq D"></span>，则<span data-katex="f(S)"></span>为<span data-katex="E"></span>的子集，

其中<span data-katex="f(S)=\lbrace f(d)|\ d\in S \rbrace"></span>。

<br/>

对于任意的<span data-katex="d,d'\in D"></span>，如果<span data-katex="d\leqslant d'"></span>就有<span data-katex="f(d)\leqslant f(d')"></span>，

我们就说<span data-katex="f"></span>是单调的。

可以看出，如果<span data-katex="f"></span>是单调的，且<span data-katex="S"></span>是<span data-katex="D"></span>的有向子集，那么<span data-katex="f(S)"></span>也是<span data-katex="E"></span>的有向子集。

<br/>

如果<span data-katex="f"></span>是单调的，且对于任意有向子集<span data-katex="S\subseteq D"></span>，

有<span data-katex="f(\bigvee S)=\bigvee f(S)"></span>，就称<span data-katex="f"></span>是连续的。

<br/>

### 连续函数集上的偏序结构

完全偏序集<span data-katex="(D,\leqslant )"></span>和<span data-katex="(E,\leqslant )"></span>上的连续也可以定义偏序结构，

我们称<span data-katex="f\leqslant g"></span>，当且仅当对于每一个<span data-katex="d\in D"></span>，我们有<span data-katex="f(d)\leqslant g(d)"></span>。

这样我们就得到了一个元素为连续函数的偏序集，<span data-katex="(D\rightarrow E,\leqslant )"></span>。

可以证明，<span data-katex="(D\rightarrow E,\leqslant )"></span>也是一个完全偏序集。（证略

<br/>

### 最小不动点定理

如果<span data-katex="(D,\leqslant )"></span>是一个完全偏序集，且<span data-katex="f:D\rightarrow D"></span>是连续的，

则<span data-katex="f"></span>有最小不动点，<span data-katex="fix_D\ f=\bigvee \lbrace f^n(\perp )|\ n\geqslant 0 \rbrace "></span>。

<br/>

因为<span data-katex="\perp "></span>是<span data-katex="D"></span>中的最小元，且<span data-katex="f(\perp )\in D"></span>，所以，<span data-katex="\perp \leqslant f(\perp )"></span>，

因为<span data-katex="f"></span>是连续的，所以<span data-katex="f"></span>也一定是单调的，所以，<span data-katex="f(\perp )\leqslant f^2(\perp )"></span>，

继而，<span data-katex="f^n(\perp )\leqslant f^{n+1}(\perp )"></span>，对于任意的<span data-katex="n\geqslant 0"></span>都成立。

<br/>

<span data-katex="\lbrace f^n(\perp )|\ n\geqslant 0 \rbrace"></span>构成了一个全序集，

所以，它是完全偏序集<span data-katex="(D\rightarrow E,\leqslant)"></span>的一个有向子集，必有上确界。

<br/>

设<span data-katex="a"></span>是上确界，<span data-katex="a=\bigvee \lbrace f^n(\perp )|\ n\geqslant 0 \rbrace "></span>，

首先<span data-katex="a"></span>是<span data-katex="f"></span>的不动点，因为，由<span data-katex="f"></span>的连续性，

<span data-katex="f(a)=f(\bigvee \lbrace f^n(\perp )|\ n\geqslant 0 \rbrace )"></span>

<span data-katex="f(a)=\bigvee \lbrace f^{(n+1)}(\perp )|\ n\geqslant 0 \rbrace "></span>，

但是由于<span data-katex="\lbrace f^n(\perp ) \rbrace"></span>与<span data-katex="\lbrace f^{(n+1)}(\perp ) \rbrace"></span>，有同样的上确界，

所以，<span data-katex="f(a)=a"></span>。

<br/>

其次，<span data-katex="a"></span>是<span data-katex="f"></span>的最小不动点，

假设<span data-katex="b=f(b)"></span>是<span data-katex="f"></span>的任意不动点，因为<span data-katex="\perp \leqslant b"></span>，所以<span data-katex="f(\perp )\leqslant f(b)"></span>，

类似的，对于任意的<span data-katex="n\geqslant 0"></span>，<span data-katex="f^n(\perp )\leqslant f^n(b)"></span>。

但是，由于<span data-katex="b"></span>是<span data-katex="f"></span>的不动点，所以<span data-katex="f^n(b)=b"></span>，

因此<span data-katex="b"></span>是集合<span data-katex="\lbrace f^n(\perp )|\ n\geqslant 0 \rbrace"></span>的上界。

由于集合的最小上界是<span data-katex="a"></span>，所以有<span data-katex="a\leqslant b"></span>。

<br/>

### 后继函数的不动点

```
succ :: Int -> Int
succ n = n+1
```

<br/>

在第七篇中，我们说`fix`可以得到任意函数的不动点，

那么这个`succ`函数呢？它有没有不动点？

`fix succ`是什么？

<br/>

现在我们有了最小不动点定理，

就得验证`succ`所指称的数学函数，是不是一个完全偏序集上的连续函数，

如果是的话，它就有不动点。

<br/>

在第四篇为了表示计算的不可终止性，我们对自然数集进行了扩充，<span data-katex="N\cup \lbrace \perp \rbrace"></span>，

然后用这个集合作为程序中`Int`类型的值的解释。

<br/>

然而，<span data-katex="N\cup \lbrace \perp \rbrace"></span>不是一个完全偏序集，原因是它没有上界，

如果我们额外加入一个比其他的自然都大的元素<span data-katex="+\infty "></span>，

则我们就得到了一个完全偏序集，<span data-katex="N\cup \lbrace \perp \rbrace\cup \lbrace +\infty \rbrace"></span>。

<br/>

然后，我们看`succ`连续吗？

首先，它是单调的，如果我们再定义<span data-katex="succ(+\infty )=+\infty "></span>，

就有<span data-katex="succ(\bigvee N)=\bigvee succ(N)"></span>，

因此，`succ`是一个连续函数。

<br/>

根据最小不动点定理，`succ`的最小不动点是，<span data-katex="fix\ succ=\bigvee \lbrace succ^n(\perp )|\ n\geqslant 0 \rbrace "></span>。

<br/>

由于<span data-katex="succ(\perp )=\perp "></span>，即对于非终止的输入`succ`的计算也不会终止，

所以<span data-katex="succ^n(\perp )=\perp "></span>，

因此，<span data-katex="fix\ succ=\bigvee \lbrace succ^n(\perp )|\ n\geqslant 0 \rbrace =\perp "></span>，

即，`succ`的最小不动点是<span data-katex="\perp "></span>，`fix succ`的计算不会终止。

<br/>

### 求解阶乘函数

上一篇中，我们证明了阶乘函数`fact`是以下函数的不动点，`fact = fix g`，

```
g :: (Int -> Int) -> Int -> Int
g f n = case n of
  1 -> 1
  _ -> n * f (n-1)
```

<br/>

现在我们来看一下，如何运用最小不动点定理来得到这个答案。

为了避免篇幅过长，关于`g`函数的连续性证明暂略，

我们直接使用公式，

<span data-katex="fix\ g=\bigvee \lbrace g^n(\perp )|\ n\geqslant 0 \rbrace "></span>，

即，`g`函数的最小不动点，就是集合<span data-katex="D=\lbrace g^n(\perp )|\ n\geqslant 0 \rbrace"></span>的上确界。

<br/>

我们先来看一下这个集合<span data-katex="D"></span>中有哪些元素，

其中，<span data-katex="g(\perp )\in D"></span>，我们将<span data-katex="\perp "></span>传入<span data-katex="g"></span>中，看看会得到什么，

```
f1 = \n -> case n of 
  1 -> 1
  _ -> ...
```

这个函数能计算`f1 1`，但是不能计算`f1 2`，恰好是`fact`函数有限展开的一阶项。

<br/>

我们再来看<span data-katex="g^2(\perp )\in D"></span>，它等于<span data-katex="g(f1)"></span>，

```
f2 = \n -> case n of 
  1 -> 1
  _ -> n * f1 (n-1)
```

这个函数能计算`f2 1`以及`f2 2`，但是不能计算`f2 3`，恰好是`fact`函数展开的二阶项。

<br/>

由此，我们看出了规律，

<span data-katex="g^n(\perp )\in D"></span>就是`fact`函数有限展开的第<span data-katex="n"></span>阶项。

上一篇中，我们已经证明了，当<span data-katex="n\rightarrow \infty"></span>时，它就是`fact`函数，

考虑到<span data-katex="f1,f2,\cdots"></span>这些函数的序关系，

因此，我们有<span data-katex="fact=\bigvee \lbrace g^n(\perp )|\ n\geqslant 0 \rbrace "></span>。

<br/>

即，`fact`函数就是`g`函数的最小不动点。

<br/>

### 总结

到此为止，我想这个系列的文章已经讨论完了，

本系列文章一直围绕着递归函数和不动点进行分析，

在内容上可以分为两个部分，前半部分主要与可计算性理论有关，

后半部分与不动点定理有关，希望对大家有所帮助。

<br/>

### 参考

[有向集合](https://zh.wikipedia.org/wiki/%E6%9C%89%E5%90%91%E9%9B%86%E5%90%88)

[完全偏序](https://zh.wikipedia.org/wiki/%E5%AE%8C%E5%85%A8%E5%81%8F%E5%BA%8F)

[Kleene fixed-point theorem](https://en.wikipedia.org/wiki/Kleene_fixed-point_theorem)

[Foundations for Programming Languages](https://book.douban.com/subject/1761918/)