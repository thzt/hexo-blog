---
layout: post
categories: Math
title: 递归函数（二）：编写递归函数的思路和技巧
---

![](http://upload-images.jianshu.io/upload_images/1023733-497eef3766876271.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

递归，是一个熟悉而陌生的概念，说它熟悉，是因为人们经常提起它，

而说它陌生，指的是人们在实际编程中几乎不会主动使用它。

<br/>

给定一个问题，如果本质上它能看做一个调用自身的规模较小的一个子问题来求解，

那么给出一个递归的算法解，就是很自然的。

然而，即使是这样，编制一个递归函数也是一件令人头疼的事情。

<br/>

本系列文章的目的，可能并不局限于指出如何编写一个递归函数，

而是期望想从递归函数开始，了解它相关的科学知识，以达到对不同领域触类旁通的效果。

<br/>

### 1. 从一个简单的例子开始

首先，我们来重温一下递归的概念，

维基百科上是这样描述的，

> 递归（recursion），在数学与计算机科学中，是指在函数的定义中使用函数自身的方法。

<br/>

我们来看一个简单的例子吧。（[Haskell](https://www.haskell.org/)代码

```
fact :: Int -> Int
fact 1 = 1
fact n = n * fact (n-1)
```

<br/>

在这个例子中，

第一行`fact :: Int -> Int`表示了`fact`函数的类型，

第二行和第三行定义了函数`fact`，

我们看到第三行，在对`fact`函数定义的时候，等式右边又出现了`fact`，

这样定义的函数`fact`是递归的。

<br/>

我们调用一下`fact`，来看看结果，

```
fact 10
3628800
```

<br/>

嗯嗯，`fact`就是阶乘函数。

<br/>

### 2. 写递归函数的步骤

那么，给定一个问题，我们编写一个递归函数，要如何开始呢？

<br/>

####（1）递推式

首先，我们要找到“递推式”。

<br/>

例如，在数学上阶乘的定义是，<span data-katex="f(n)=n!"></span>，这样的表述形式，不具有递推性。

我们先要想办法把<span data-katex="f(n)"></span>用<span data-katex="f(n-1)"></span>表示出来。

<br/>

经过思考之后，我们可以证明，<span data-katex="f(n)=n*f(n-1)"></span>，

于是，我们就走出了关键的第一步，得到了“递推式”。

<br/>

####（2）找出终止条件

有了“递推式”还不行，我们还需要确定递推在什么时候终止。

我们知道<span data-katex="f(1)=1"></span>，<span data-katex="f(2)=2*f(1)"></span>，<span data-katex="f(3)=3*f(2)"></span>，等等，

因此，我们只需要指定<span data-katex="f(1)=1"></span>，那么递推就会在<span data-katex="f(n)"></span>，当<span data-katex="n=1"></span>的时候终止了。

<br/>

终止，就是不再调用规模更小的问题了。

这时，终止条件是<span data-katex="f(1)=1"></span>。

<br/>

####（3）用数学归纳法证明解的正确性

这一步是很重要的，有很多人都缺少证明递推式正确性的环节，

但是，考虑到介绍[数学归纳法](https://zh.wikipedia.org/wiki/%E6%95%B0%E5%AD%A6%E5%BD%92%E7%BA%B3%E6%B3%95)及其扩展会占用不少篇幅，

这里先略去，下一篇我们再回来讨论它。

<br/>

这里，我们先假定，根据“递推式”和“终止条件”，使用数学归纳法，

我们已经证明了这样定义的<span data-katex="f(n)"></span>就是<span data-katex="n!"></span>。

<br/>

####（4）根据递推式和终止条件，编写程序

有了“递推式”和“终止条件”，再编写程序就水到渠成了。

很多人一上来就开始编码，就会感觉毫无头绪。

<br/>

我们再来看下那段程序，

```
fact :: Int -> Int
fact 1 = 1
fact n = n * fact (n-1)
```

<br/>

这不就是“递推式”和“终止条件”的忠实表示吗？

我们用`fact 1 = 1`表示了<span data-katex="f(1)=1"></span>，

用`fact n = n * fact (n-1)`表示了<span data-katex="f(n)=n*f(n-1)"></span>。

<br/>

### 3. 小技巧

我们再看个复杂一点的例子。

<br/>

在实际项目中，我们可能会遇到循环n次的场景，

在循环过程中，我们会根据索引进行运算，然后将某些符合条件的运算放到最终的结果中。

<br/>

例如，我们选择10以内的所有偶数，

```
[x|x <- [0..9], x `mod` 2 == 0]
[0,2,4,6,8]
```

使用以上列表解析（[list comprehension](http://www.haskell.org/haskellwiki/List_comprehension)）的方法，我们可以快速得到结果。

但是这里，我们想要拿它来举例，介绍一个编写递归函数常用的小技巧。

<br/>

为了通用性，我们考虑循环`n`次，将索引传入函数`fn`，根据`fn`的返回值，将结果放入一个列表中。

<br/>

####（1）困境

根据前文介绍的编写步骤，我们需要先找到“递推式”和“终止条件”。

<br/>

“终止条件”怎么写呢？

假如我们定义的递归函数称为`myLoop`，那么<span data-katex="myLoop(0,fn)"></span>就是终止条件，它应该返回一个列表。

但是这个列表在参数中没有，它随着递归调用的过程“积累”得到的。

<br/>

好吧，那我们看“递推式”。

<span data-katex="myLoop(n,fn)"></span>要用<span data-katex="myLoop(n-1,fn)"></span>的结果计算出来，

我们需要先用索引调用`fn`，然后再根据`fn`的返回值，放入结果列表，再继续调用<span data-katex="myLoop(n-1,fn)"></span>。

可是，索引从哪来呢？（`n`不是索引，因为索引从0开始，而n是逐渐变小的。

<br/>

这是两个典型的困难，

其一，我们在递归的过程中“积累”了某些东西，

其二，我们需要传递和递归过程相关的“索引”。

<br/>

####（2）解法

这时候，我们的小技巧就有用武之地了。

> 我们可以编写一个辅助的递归函数，通过增加参数的办法，提高灵活性。

<br/>

例如，我们可以编写一个辅助函数`myLoop'`，然后用`myLoop'`来实现`myLoop`。

<br/>

```
myLoop :: Int -> (Int -> Maybe a) -> [a]
myLoop n fn = myLoop' n 0 fn []

myLoop' :: Int -> Int -> (Int -> Maybe a) -> [a] -> [a]
myLoop' 0 i fn lst = lst
myLoop' n i fn lst = case fn i of
  Just x -> myLoop' (n-1) (i+1) fn (lst++[x])
  Nothing -> myLoop' (n-1) (i+1) fn lst
```

<br/>

以上，我们为`myLoop'`增加了参数`i`和`lst`，分别表示“索引”和“积累”的列表。

然后，`myLoop`就可以用`myLoop'`来实现了。

<br/>

别忘了测试一下最终的结果，

```
myLoop 10 (\x -> if x `mod` 2 == 0 then Just x else Nothing)
[0,2,4,6,8]
```

<br/>

####（3）其他考虑

合理的利用递归函数的返回值，会减少附加参数的数量，例如，

```
myLoop :: Int -> (Int -> Maybe a) -> [a]
myLoop n fn = myLoop' n 0 fn

myLoop' :: Int -> Int -> (Int -> Maybe a) -> [a]
myLoop' 0 i fn = []
myLoop' n i fn = case fn i of
  Just x -> x:(myLoop' (n-1) (i+1) fn)
  Nothing -> myLoop' (n-1) (i+1) fn
```

<br/>

但最终得到的递归函数就不是[尾递归](https://zh.wikipedia.org/wiki/%E5%B0%BE%E8%B0%83%E7%94%A8)了，

关于尾递归，我们将在后续文章中讨论它。

<br/>

### 参考

[维基百科 - 递归](https://zh.wikipedia.org/wiki/%E9%80%92%E5%BD%92)

[维基百科 - 递推关系式](https://zh.wikipedia.org/wiki/%E9%81%9E%E8%BF%B4%E9%97%9C%E4%BF%82%E5%BC%8F)