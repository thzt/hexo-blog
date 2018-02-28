---
layout: post
categories: Math
title: 递归函数（七）：不动点算子
---

### 回顾

以上几篇文章中，我们讨论了可计算性理论相关的一些内容，

可计算性与递归函数论存在着千丝万缕的联系，

不动点理论也是这样的，我们定义的递归函数一定存在吗？

在什么情况下它是存在的？

<br/>

要回答以上这些问题，还要从方程，不动点，不动点算子说起。

<br/>

### 约束方程

<br/>

![](http://upload-images.jianshu.io/upload_images/1023733-c82626b07032c9e8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

在中学时代，我们学过“方程”的概念，

方程可以简单表述为含有未知数的等式，例如，<span data-katex="3x+3=2"></span>。

未知数可以同时出现在等式的两边，例如，<span data-katex="2x+3=2-x"></span>。

通过合并同类项，我们可以求解<span data-katex="x"></span>。

<br/>

在大学时代，我们还学过线性方程组和微分方程，

例如，求解矩阵的特征值和特征向量，<span data-katex="Av=\lambda v"></span>

二阶常微分方程（[贝塞尔方程](https://zh.wikipedia.org/wiki/%E8%B4%9D%E5%A1%9E%E5%B0%94%E5%87%BD%E6%95%B0)），<span data-katex="x^2y''+xy'+(x^2-\alpha ^2)y=0"></span>。

<br/>

在计算机科学中，同样的未知“数”的思想，

还出现在了类型推导（例如：[unification](https://en.wikipedia.org/wiki/Unification_(computer_science))）与递归函数的定义中。

<br/>

以上这些例子，方程是“约束”的一种表现形式。

<br/>

我们回到最简单的阶乘函数`fact`的定义式，

```
fact :: Int -> Int
fact 1 = 1
fact n = n * fact (n-1)
```

<br/>

去掉语法糖，稍微修改一下，

```
fact :: Int -> Int
fact n = case n of 
  1 -> 1
  n -> n * fact (n-1)
```

<br/>

我们发现，`fact`的定义和“方程”十分相似，`fact`同时出现在了等式的两边，

阶乘函数，就是这个“方程”的“解”。

<br/>

### 函数的不动点

<br/>

![](http://upload-images.jianshu.io/upload_images/1023733-417c44596d6f438d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

在中学数学中，我们已经学过不动点了，只是当时印象不是那么深刻，

函数的不动点，是指被这个函数映射到其自身的那些点。

例如：<span data-katex="f(x)=x^2-3x+4"></span>，

则<span data-katex="2"></span>是函数<span data-katex="f"></span>的一个不动点，<span data-katex="f(2)=2"></span>。

<br/>

并不是每一个函数都有不动点，

例如，实数域上的函数<span data-katex="f(x)=x+1"></span>，就没有不动点，对于任意实数<span data-katex="x"></span>，永远都不等于<span data-katex="x+1"></span>。

（不动点是和定义域有关的，以后我们还会重新讨论<span data-katex="f(x)=x+1"></span>的不动点。

<br/>

一般的，函数<span data-katex="f(x)"></span>的不动点，指的是这样的<span data-katex="x"></span>，使得<span data-katex="x=f(x)"></span>。

<br/>

重新温习了不动点相关的知识之后，

我们就可以对上面的阶乘函数进行改造了，

我们要把阶乘函数看做另外一个函数的不动点。

<br/>

定义函数<span data-katex="g"></span>，

```
g :: (Int -> Int) -> Int -> Int
g f n = case n of 
  1 -> 1
  n -> n * f (n-1)
```

我们可以得到，`g fact = fact`，

因此，`fact`实际上就是函数`g`的不动点。

<br/>

于是，在“方程”中求解`fact`的过程，

就转换成了求解函数`g`的不动点的过程了。

<br/>

### 不动点算子

<br/>

![](http://upload-images.jianshu.io/upload_images/1023733-6179cf69f757a05a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

我们怎样求解函数`g`的不动点呢？

在Haskell中，可以很方便的定义一个高阶函数`fix`，它可以用来求解任意函数的不动点，

```
fix :: (a -> a) -> a
fix g = let x = g x in x
```

<br/>

我们试验一下`fix`的强大威力，

```
fact 10
> 3628800

fix g 10
> 3628800
```

<br/>

注意，`fix g`得到了`g`的不动点，即`(fix g) = g (fix g)`。

<br/>

有了`fix`，我们就可以构造匿名递归函数了，

```
fact' :: Int -> Int
fact' = fix $ \fact -> \n -> case n of 
  1 -> 1
  n -> n * fact (n-1)
```

`fix`后面跟的函数没有名字，它是匿名的，但是经过`fix`作用后，可以产生一个递归函数。

也就是说，为了实现递归，函数是可以没有名字的。

<br/>

### Y组合子

<br/>

![](http://upload-images.jianshu.io/upload_images/1023733-2506f85747258985.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

Y组合子，是[Haskell B. Curry](https://zh.wikipedia.org/wiki/Haskell_Curry)在研究<span data-katex="\lambda"></span>演算时发现的，

它的表现形式如下，

<span data-katex="Y:=\lambda f.(\lambda x.(f\ (x\ x))\ \lambda x.(f\ (x\ x)))"></span>

<br/>

在<span data-katex="\lambda"></span>演算中，（<span data-katex="\alpha"></span>转换和<span data-katex="\beta"></span>规约

我们可以证明，对于任何函数`g`，<span data-katex="(Y g) = (g (Y g))"></span>。

<br/>

因此，Y组合子是一个不动点算子，它可以得到任意函数的不动点。

其他的不动点组合子还有图灵不动点组合子<span data-katex="\Theta"></span>，

<span data-katex="\Theta:=(\lambda x.\lambda y.(y\ (x\ x\ y)))\ (\lambda x.\lambda y.(y\ (x\ x\ y)))"></span>

<br/>

讨论Y组合子在Haskell中的表示方式是有趣的，因为直接翻译过去会报类型错误，

```
y :: (a -> a) -> a
y = \f -> (\x -> f (x x)) (\x -> f (x x))

-- Occurs check: cannot construct the infinite type: r0 ~ r0 -> a
-- Expected type: r0 -> a
--   Actual type: (r0 -> a) -> a
-- In the first argument of ‘x’, namely ‘x’
-- In the first argument of ‘f’, namely ‘(x x)’
```

类型系统无法确定`x`的类型。

<br/>

问题出在表达式`x x`上面，

假设`x x`的类型为`a`，则第一个`x`的类型就应该为`? -> a`，

于是，第二个`x`的类型肯定也应该是`? -> a`。（因为都是`x`

<br/>

又因为`x x`的类型为`a`，

所以第一个`x`的类型`? -> a`中，`?`的类型就应该是`? -> a`，

（因为`((? -> a) -> a)`作用到`(? -> a)`才能得到`a`

<br/>

`?`的类型是`? -> a`，因此`?`应该是一个[递归类型](https://zh.m.wikipedia.org/wiki/%E9%80%92%E5%BD%92%E7%B1%BB%E5%9E%8B)。

<br/>

下面我们来定义递归类型`Mu`，来帮助编译器进行恰当的类型推导，

```
newtype Mu a = Mu (Mu a -> a)

y :: (a -> a) -> a
y f = (\h -> h <span data-katex=" Mu h) (\x -> f . (\(Mu g) -> g) x "></span> x)
```

<br/>

最后，`fact'`就可以使用Y组合子来定义了。

```
fact' :: Int -> Int
fact' = y $ \fact -> \n -> case n of 
  1 -> 1
  n -> n * fact (n-1)
```

<br/>

### 总结

本文从简单的“方程”思想出发，引出了不动点的概念，

然后把递归函数看做了另外一个函数的不动点，

最后，我们讨论了Y组合子这样一个具体的不动点算子。

<br/>

可是，这里隐藏着一个问题，我们看到`fix`是可以求解任意函数的不动点的，

而对于以下递归函数`succ`，即<span data-katex="f(x)=x+1"></span>，

```
succ :: Int -> Int
succ n = n+1
```

在实数域上是显然没有不动点的。

<br/>

那么`fix succ`是什么呢？

这个问题，我们将在后文中继续讨论。

<br/>

### 参考

[方程](https://zh.wikipedia.org/zh-cn/%E6%96%B9%E7%A8%8B)

[特征值和特征向量](https://zh.wikipedia.org/wiki/%E7%89%B9%E5%BE%81%E5%80%BC%E5%92%8C%E7%89%B9%E5%BE%81%E5%90%91%E9%87%8F)

[微分方程](https://zh.wikipedia.org/zh/%E5%BE%AE%E5%88%86%E6%96%B9%E7%A8%8B)

[不动点](https://zh.wikipedia.org/zh-hans/%E4%B8%8D%E5%8A%A8%E7%82%B9)

[不动点组合子](https://zh.wikipedia.org/zh-hans/%E4%B8%8D%E5%8A%A8%E7%82%B9%E7%BB%84%E5%90%88%E5%AD%90)

[Haskell/Fix and recursion](https://en.wikibooks.org/wiki/Haskell/Fix_and_recursion)

[Y Combinator in Haskell](http://stackoverflow.com/questions/4273413/y-combinator-in-haskell/5885270#5885270)