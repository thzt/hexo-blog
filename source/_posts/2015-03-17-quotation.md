---
layout: post
categories: Lisp
title: Lisp语言中的引用
---

在lisp语言中，引用（quotation）是一个很独特的概念。

这与按引用传参（call by reference）完全是两码事。

<br/>

至于引用（quote）的含义是什么，

为什么要有这个概念，

刚开始学lisp时，很容易感到迷惑。

<br/>

既然如此，

我们不妨一起探险吧。

<br/>

## **程序执行就是一系列表达式的求值过程**

lisp程序中没有语句，只有表达式。

程序执行过程，就是一系列表达式的求值过程。

<br/>

这句话再强调几次都不为过，是初学者最容易忽视的一句话。

它指出了理解程序执行的必要条件。

每当我们不知道下一步该如何进行时，都可以问自己，表达式的值是什么。

<br/>

我们用x => 1来表示，表达式x的值是1，或者说（表达式）x求值为1。

<br/>

例如：

(define add1

&nbsp;&nbsp;&nbsp;&nbsp;(lambda (x)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(+ x 1)))

<br/>

(add1 2)

<br/>

我们仔细考虑一下(add1 2)。这段程序怎么执行呢？

我们问自己，(add1 2)的值是什么呢？

<br/>

这是一个函数调用表达式，求值规则如下：

函数调用表达式的值等于函数体的值。

而函数体中形参的值等于实参的值。

<br/>

所以，求(add1 2)的值就转换成了求add1的函数体(+ x 1)的值，x是形参。

<br/>

从一开始，我们就将实参和实参的值进行区分，是很重要的。

对于(add1 2)来说，实参是2，实参的值是2的值。

而2是一个数字，数字是自求值对象，所以2的值还是2。

（多此一举是必要的）

<br/>

因此，形参x的值就是2了。x => 2

<br/>

我们来求值函数体，(+ x 1)

(+ x 1)又是一个函数调用表达式，

只不过+是一个内置函数，我们看不到它的函数体。

我们只知道加法的结果是两个加数之和。

<br/>

于是，x的值是2，2+1=3。

对吗？

<br/>

结果对了，但是执行过程不对，缺少对1这个实参的求值过程。

<br/>

根据函数调用表达式的求值规则，(+ x 1)的值是x的值与1的值相加的结果。

x => 2，1 => 1

所以，结果为2+1=3

<br/>

这样繁琐有什么用呢？

那不妨分析一下(= 1 '1) => #t

<br/>

引用出现了，其中'1是(quote 1)的简写。

1和(quote 1)为什么相等的呢？

其实是，它们两个不相等，它们的值相等。

<br/>

在函数=调用之前，实参1和(quote 1)都要先求值。

1 => 1，(quote 1) => 1

因此，(= 1 (quote 1)) => #t

<br/>

## **从求值的角度理解quote**

怎样理解(quote 1) => 1呢？

<br/>

其实，我们只是遵循了quote表达式的求值规则而已，

(quote a) => a

<br/>

那么a是什么呢？

<br/>

其实这个问题提的不合理。

因为，在lisp程序执行过程中，我们不关心“xxx是什么”，我们只关心“xxx的值是什么”。

<br/>

那么a的值是什么呢？

<br/>

这个问题在这种情况下提的也不合理。

因为，我们需要求值的是(quote a)，我们已经知道了它的值是a，就不必再求a的值了。

<br/>

例如：

(define a 1)

(list a 'a) => (1 a)

<br/>

我们来分析一下，程序的执行过程。

问程序怎么执行，就是问(list a 'a)的值是什么，

而(list a 'a)是函数调用，list是内置函数，结果值是用实参值拼成的一个列表。

<br/>

根据函数调用规则，首先我们要求实参的值。

a => 1，因为(define a 1)就是定义a的值为1

'a => a，根据quote表达式的求值规则(quote a) => a

<br/>

所以(list a 'a) => (1 a)

这里我们看到了实参与实参值的区别。

我们也看到了，在调用函数之前，要先求值实参。

<br/>

回顾一下，这其实是拿着一堆符号在玩而已。

求值，就是进行符号替换罢了。

<br/>

对的，

lisp语言的计算模型是建立在lambda演算基础上的。

而lambda演算就是一个使用符号进行计算的形式系统。

函数调用在lambda演算中称为beta归约。

<br/>

## **编码一致性**

我们已经知道了quote表达式的求值规则了。

相信判断程序的执行过程，已经难不倒我们了。

<br/>

可是，为什么要有引用这个概念呢？

<br/>

这其实是为了将数据和程序进行统一编码。

lisp程序中，我们知道(+ 1 2)是一个加法调用，

但是它也可以表示由3个符号+，1和2构成的列表

<br/>

列表是数据，加法调用是程序，

它们采用了相同的编码。

我们没有办法区分。

<br/>

首先想到的，就是让它们采用不同的编码。

例如：

我们把函数调用编码为+[1;2]，而列表编码为(+ 1 2)

<br/>

看起来不错，

人们一开始也是这么做的，

+[1;2]称为M表达式。

(+ 1 2)称为S表达式。

<br/>

可是，后来人们发现，如果用lisp语言来处理lisp程序文本时，

不同的编码，会增加难度。

<br/>

又因为，程序主要是由函数调用组成的。

所以，人们进行了以下编码，

函数调用编码为(+ 1 2)

而列表编码为(quote (+ 1 2))

<br/>

即，(+ 1 2)求值，会导致函数调用。

(quote (+ 1 2))求值，会得到一个列表。

于是，我们就统一的用S表达式，完成了对程序和数据的相同编码。

<br/>

也正因为有这样的一致性。

在进行元编程时，相比其他语言，lisp宏的威力才更强大。

<br/>

## **结语**

lisp语言中的引用，是一个很深刻的概念。

远不是通常想像的那么简单。

<br/>

比如，我们如何判断两个引用相等呢？

从符号的角度来看，似乎很简单，

但是从实现的角度来看，我们就需要在程序执行之前，让引用指向相同的位置。

<br/>

然而，这样对于引用的列表来说，就是个问题。

如果程序执行过程中，修改了列表元素，其他引用也会受到影响。

<br/>

类似的问题还有很多。

因此，Scheme和Common Lisp规范都建议不要修改引用返回的值。

应该只把它当做一个常量来使用。
















