---
layout: post
categories: Math
title: 递归函数（八）：偏序结构
---

### 回顾

上一篇我们介绍了不动点算子和Y组合子，以及Y组合子的具体表现形式，

这一篇我们根据不动点算子的性质来证明`fact`函数就是`g`函数的不动点。

随后，我们回归到了数学中，讨论集合上的一种偏序结构，

这为下文完全偏序集，以及完全偏序集上连续函数的不动点定理做好准备。

<br/>

### 不动点算子的性质

<br/>

![](http://upload-images.jianshu.io/upload_images/1023733-a8ca5067e631ea34.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

上文我们介绍了不动点算子`fix`，

它可以用来求取任意函数的不动点。

<br/>

```
fix :: (a -> a) -> a
fix f = let x = f x in x
```

<br/>

并且我们说以下函数的不动点为`fact = fix g`，

```
g :: (Int -> Int) -> Int -> Int
g f n = case n of
  1 -> 1
  _ -> n * f (n-1)
```

<br/>

但是上文中，我们只是对它们的计算结果进行比对，

并没有对它进行证明。

<br/>

考虑到`fix`的性质，`fix g = g (fix g)`，

（因为`fix g`是`g`的不动点，令`h = fix g`，上式为`h = g h`

我们可以使用数学归纳法，证明对于任意的自然数<span data-katex="n"></span>，`fact n = fix g n`。

<br/>

我们先证初始条件，

```
fix g 1 
= g (fix g) 1 
= case 1 of 
    1 -> 1
    _ -> ...
= 1
= fact 1
```

<br/>

然后再证递推条件，假设`fact k = fix g k`，

我们要推出`fact (k+1) = fix g (k+1)`，其中，<span data-katex="k &gt; 0"></span>。

```
fix g (k+1)
= g (fix g) (k+1)
= case (k+1) of 
    1 -> 1
    _ -> (k+1) * (fix g) k
= (k+1) * (fix g) k
= (k+1) * fact k
= fact (k+1)
```

<br/>

因此，对于任意的自然数<span data-katex="n"></span>，`fact n = fix g n`。

即，`fact = fix g`。

<br/>

### 不动点算子的有限展开

<br/>

![](http://upload-images.jianshu.io/upload_images/1023733-0a009ed0d24a4df6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

根据上一节`fact = fix g`的证明，我们看到，

每一步递推，我们都使用了不动点算子`fix`的性质`fix g = g (fix g)`，

但是对于一个具有有限存储空间的机器来说，递推的步骤不可能是无限的，

为了界定最多使用多少次递推，我们定义，<span data-katex="fix^{[n+1]}\ g = g\ (fix^{[n]} g)"></span>。

并且认为<span data-katex="fix^{[0]}\ g"></span>对于任意的<span data-katex="n"></span>无定义。

<br/>

因此，<span data-katex="fix^{[1]}\ g\ 1 = 1"></span>，而<span data-katex="fix^{[1]}\ g\ n"></span>在<span data-katex="n &gt; 1"></span>时没有定义。

<span data-katex="fix^{[2]}\ g\ 1 = 1"></span>，<span data-katex="fix^{[2]}\ g\ 2 = 2"></span>，而<span data-katex="fix^{[2]}\ g\ n"></span>在<span data-katex="n &gt; 2"></span>时没有定义。

<br/>

所以，<span data-katex="fix^{[n]}\ g"></span>是一个部分函数，且，

<span data-katex="fix^{[n+1]}\ g"></span>所表示的函数，总是比<span data-katex="fix^{[n]}\ g"></span>的计算能力更强一些，离`fact`更近一些。

当<span data-katex="n\rightarrow \infty "></span>时，<span data-katex="fix^{[\infty ]}\ g"></span>就是阶乘函数`fact`。

<br/>

即，<span data-katex="\lbrace fix^{[n]} g|\ n\geqslant 0 \rbrace"></span>的最小上界，就是`g`的不动点。

那么，什么样的`g`才能保证这个集合具有最小上界呢？

[序理论](https://zh.wikipedia.org/wiki/%E5%BA%8F%E7%90%86%E8%AE%BA)指出，完全偏序集上的序保持自映射具有最小不动点。

<br/>

为此，我们需要先认识什么是偏序集，什么是连续函数。

使用完全偏序集上的连续函数解释程序中函数的方式，称为[域论模型](https://zh.wikipedia.org/wiki/%E5%9F%9F%E7%90%86%E8%AE%BA)。

<br/>

### 偏序集与哈斯图

<br/>

![](http://upload-images.jianshu.io/upload_images/1023733-548b287983ed9034.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

在第三篇中，我们讨论过[偏序关系](https://zh.wikipedia.org/wiki/%E5%81%8F%E5%BA%8F%E5%85%B3%E7%B3%BB)，

一个偏序集<span data-katex="(D,\leqslant )"></span>是一个集合<span data-katex="D"></span>，

并且在这个集合上定义了一个偏序关系<span data-katex="\leqslant "></span>。

<br/>

设<span data-katex="A"></span>为实数集的一个非空子集，我们定义<span data-katex="A"></span>上的偏序关系为<span data-katex="\leqslant "></span>，

<span data-katex="x\leqslant y"></span>当且仅当<span data-katex="x"></span>是小或等于<span data-katex="y"></span>的实数。

则，<span data-katex="(A,\leqslant )"></span>是一个偏序集。

<br/>

偏序集反映了集合上的一种偏序结构，它比我们想象中的更为常见，

例如，一个集合<span data-katex="A"></span>，对于任意两个元素<span data-katex="x,y\in A"></span>，我们定义<span data-katex="x\leqslant y"></span>当且仅当<span data-katex="x=y"></span>。

那么<span data-katex="(A,\leqslant )"></span>是一个偏序集。

因此，如果某个集合构成了一个偏序集，这完全取决于我们怎样定义偏序关系。

<br/>

设<span data-katex="(D,\leqslant )"></span>是一个偏序集，

对于任意的<span data-katex="x,y\in D"></span>，如果总是有<span data-katex="x\leqslant y"></span>或者<span data-katex="y\leqslant x"></span>成立，

则称<span data-katex="x"></span>和<span data-katex="y"></span>是可比的。

<br/>

<span data-katex="x\leqslant y"></span>，且<span data-katex="x\neq y"></span>，则记为<span data-katex="x<y"></span>。

如果<span data-katex="x"></span>和<span data-katex="y"></span>是可比的，且<span data-katex="x<y"></span>，如果不存在<span data-katex="z\in D"></span>，使得<span data-katex="x<z<y"></span>，则称<span data-katex="y"></span>覆盖<span data-katex="x"></span>。

<br/>

根据可比性和覆盖性，我们就可以将偏序关系用无向图表示出来了，

其中，顶点表示元素，边表示覆盖关系，并且省去图中每个顶点处的环，

<span data-katex="y"></span>覆盖<span data-katex="x"></span>就将代表<span data-katex="y"></span>的顶点放在代表<span data-katex="x"></span>的顶点之上，并在<span data-katex="x"></span>和<span data-katex="y"></span>之间连线，

如果<span data-katex="x<y"></span>，但是<span data-katex="y"></span>不覆盖<span data-katex="x"></span>，就省掉<span data-katex="x"></span>与<span data-katex="y"></span>之间的连线。

<br/>

这样用来表示有限偏序集的无向图，称为[哈斯图](https://zh.wikipedia.org/wiki/%E5%93%88%E6%96%AF%E5%9C%96)。

<br/>

例如，易证整除关系是整数集上的一种偏序关系，

我们可以画出偏序集<span data-katex="\lbrace 1,2,3,4,5,6,9,10,15 \rbrace"></span>对应的哈斯图，如下，

![](http://upload-images.jianshu.io/upload_images/1023733-3619f4e73479ac87.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

### 全序集与拟序集

<br/>

![](http://upload-images.jianshu.io/upload_images/1023733-69bf19c128135d6a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

设<span data-katex="(D,\leqslant )"></span>是一个偏序集，如果对于任意<span data-katex="x,y\in D"></span>，<span data-katex="x"></span>和<span data-katex="y"></span>都可比，

则称<span data-katex="\leqslant "></span>为<span data-katex="D"></span>上的全序关系，此时称<span data-katex="(D,\leqslant )"></span>为全序集。

<br/>

可见，实数集以及实数集上的小于等于关系<span data-katex="\leqslant "></span>，构成了一个全序集。

哈斯图为从下至上的“一条线”，是全序集的充要条件。

<br/>

设<span data-katex="R"></span>是非空集合<span data-katex="A"></span>上的，反自反的和传递的二元关系，

则称<span data-katex="R"></span>为<span data-katex="A"></span>上的拟序关系，常将拟序关系记为<span data-katex="<"></span>，并称<span data-katex="(A,<)"></span>为拟序集。

拟序关系自然具有反对称性。

其中，反自反关系，指的是不存在<span data-katex="x\in A"></span>，使得<span data-katex="x<x"></span>。

<br/>

拟序关系与偏序关系的哈斯图在画法上完全相同，只是拟序关系的哈斯图的各顶点都没有环。

<br/>

设<span data-katex="(A,<)"></span>是一个拟序集，如果对于任意的<span data-katex="x,y\in A"></span>，

<span data-katex="x<y"></span>，<span data-katex="x=y"></span>，<span data-katex="y<x"></span>三式有且仅有一式成立，则称<span data-katex="<"></span>具有三歧性，

这样的拟序关系<span data-katex="<"></span>，称为拟全序关系，这样的拟序集<span data-katex="(A,<)"></span>，称为拟全序集。

拟全序集的哈斯图也是“一条线”。

<br/>

### 最小元与上确界

<br/>

![](http://upload-images.jianshu.io/upload_images/1023733-848d5a4650be6c32.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

对于偏序集<span data-katex="(D,\leqslant )"></span>，以及它的一个子集<span data-katex="S\subseteq D"></span>，

如果存在<span data-katex="y\in S"></span>，且对于任意的<span data-katex="x\in S"></span>，有<span data-katex="y\leqslant x"></span>，

则称<span data-katex="y"></span>为<span data-katex="S"></span>的最小元。（相似的我们可以定义最大元

<br/>

如果存在<span data-katex="y\in S"></span>，对于任意的<span data-katex="x\in S"></span>，

如果<span data-katex="x\leqslant y"></span>那么就有<span data-katex="x=y"></span>，

则称<span data-katex="y"></span>为<span data-katex="S"></span>的极小元。（相似的我们可以定义极大元

<br/>

如果<span data-katex="S"></span>是有穷集，则<span data-katex="S"></span>的极小元一定存在，并且可能有多个，

但是最小元却不一定存在。

<br/>

上文中，我们画出了偏序集<span data-katex="A=\lbrace 1,2,3,4,5,6,9,10,15 \rbrace"></span>对应的哈斯图，

我们取<span data-katex="B_1=\lbrace 1,2,3 \rbrace"></span>，<span data-katex="B_1=\lbrace 3,5,15 \rbrace"></span>，<span data-katex="B_3=A"></span>，

则<span data-katex="1"></span>是<span data-katex="B_1"></span>的最小元，也是极小元，<span data-katex="2,3"></span>是<span data-katex="B_1"></span>的极大元，但<span data-katex="B_1"></span>没有最大元。

<span data-katex="3,5"></span>是<span data-katex="B_2"></span>的极小元，但<span data-katex="B_2"></span>没有最小元，<span data-katex="15"></span>是<span data-katex="B_2"></span>的最大元，也是极大元。

<span data-katex="1"></span>是<span data-katex="B_3"></span>的最小元，也是极小元，<span data-katex="4,6,9,10,15"></span>是<span data-katex="B_3"></span>的极大元，但是<span data-katex="B_3"></span>没有最大元。

<br/>

对于偏序集<span data-katex="(D,\leqslant )"></span>，以及它的一个子集<span data-katex="S\subseteq D"></span>，

如果存在<span data-katex="y\in D"></span>，（注意，不一定是<span data-katex="y\in S"></span>

使得对于任意的<span data-katex="x\in S"></span>，<span data-katex="x\leqslant y"></span>，则称<span data-katex="y"></span>为<span data-katex="S"></span>的上界，

如果<span data-katex="S"></span>的所有上界存在最小元，则称它为<span data-katex="S"></span>最小上界，或上确界。

（相似的可以定义下确界

<br/>

<span data-katex="S"></span>的上界和下界不一定存在，即使存在，上确界和下确界也不一定存在。

<br/>

设<span data-katex="(A,<)"></span>是一个拟全序集，如果对于<span data-katex="A"></span>中的任何非空子集<span data-katex="S"></span>都有最小元，

则称<span data-katex="<"></span>是一个良序关系，<span data-katex="(A,<)"></span>是一个良序集。

例如，自然数集以及自然数集上的小于关系，构成了一个良序集<span data-katex="(N,<)"></span>，

但是，整数集以及整数集上的小于关系，并不构成良序集，而仅仅是一个拟全序集。

<br/>

### 总结

本文从一个证明出发，我们了解了不动点算子的工作原理，

然后引出了一些数学概念，序关系在不动点算子理论中占有很重要的地位，

所以，这里给出了详细的介绍，下文我们开始讨论最小不动点定理。

<br/>

### 参考

[序理论](https://zh.wikipedia.org/wiki/%E5%BA%8F%E7%90%86%E8%AE%BA)

[域论模型](https://zh.wikipedia.org/wiki/%E5%9F%9F%E7%90%86%E8%AE%BA)

[偏序关系](https://zh.wikipedia.org/wiki/%E5%81%8F%E5%BA%8F%E5%85%B3%E7%B3%BB)

[离散数学教程](https://book.douban.com/subject/1230394/)

