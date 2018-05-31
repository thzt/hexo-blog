---
layout: post
categories: Logic
title: Dynamic Typing
---

最近看了一篇文章，[TypeScript: Static or Dynamic? The war is over.](https://medium.com/@gaperton/typescript-static-or-dynamic-64bceb50b93e)，

它提到了TypeScript是具有[gradual typing](https://en.wikipedia.org/wiki/Gradual_typing)的编程语言。

<br/>

所谓gradual typing，维基百科上是这么解释的，

> Gradual typing is a type system in which some variables and expressions may be given types and the correctness of the typing is checked at compile-time (which is static typing) and some expressions may be left untyped and eventual type errors are reported at run-time (which is dynamic typing). 

<br/>

编程语言如果具有gradual typing，

它就融合了static typing和dynamic typing双方的特点，

具有gradual typing的语言，也称其类型系统是[hybrid](http://movep.lif.univ-mrs.fr/documents/lopes-slides.pdf)的。

<br/>

看到这里，我发现自己对dynamic typing的理解还不清晰，

于是就翻开了[PFPL](https://www.cs.cmu.edu/~rwh/pfpl/2nded.pdf)，

想把相关的概念重新梳理一下。

<br/>

- - -

#### 1. 阶段

大部分程序被编写完之后，直到被运行完，一般会经历如下两个**阶段**（phase），

**static阶段**，和**dynamic阶段**。

<br/>

在static阶段中，我们会对程序进行语法解析，

然后经过类型检查（type checking），以确保程序是良类型的（良构的 well-formed）。

最后在dynamic phase中，执行这些良类型的程序。

<br/>

—— P35

- - -

#### 2. 静态特性

对程序进行的类型检查，由一些断言（typing judgments）组成，

每一条断言，断定特定规则组成的程序，将具有相应的类型，

这通常被称为**语言的静态特性**（statics）。

<br/>

—— P35

- - -

#### 3. 动态特性

**语言的动态特性**（dynamics），描述了程序在执行过程中应该符合的限制条件，

有多种方式描述语言的动态特性。

<br/>

（1）structural dynamics方法

它定义了一个转换系统（transition system），归纳的定义了程序的逐步执行方式。

<br/>

（2）contextual dynamics方法

和转换系统类似，只不过转换规则的描述方式有些不同。

<br/>

（3）equational dynamics方法

它由一些定义了程序等价性（deﬁnitionally equivalent）的规则组成。

<br/>

—— P41

- - -

#### 4. PCF的静态特性和动态特性

我们以PCF为例，了解一下语言静态特性和动态特性的描述方式，

<br/>

（1）静态特性

![syntax](https://upload-images.jianshu.io/upload_images/1023733-76516c26c946e26f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![statics](https://upload-images.jianshu.io/upload_images/1023733-b2524f862bce05ff.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

（2）动态特性

![](https://upload-images.jianshu.io/upload_images/1023733-0a872566e08756d9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

上图定义了闭值（closed value）<span data-katex="e val"></span>应当满足的推导规则。

第二个推导规则的前提中，中括号<span data-katex="[e val]"></span>表明<span data-katex="s(e)"></span>对它的参数<span data-katex="e"></span>是立即求值（eager）的，

如果省略中括号，则表示是惰性求值（lazy）。

<br/>

![](https://upload-images.jianshu.io/upload_images/1023733-f10a451ba1ab1180.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

上图定义了转化（transition）<span data-katex="e\mapsto e'"></span>应该满足的推导规则。

<br/>

—— P167-P168

- - -

#### 5. untyped <span data-katex="\lambda"></span> calculus的静态特性和动态特性

再看看untyped <span data-katex="\lambda"></span> calculus，

<br/>

（1）静态特性

![syntax](https://upload-images.jianshu.io/upload_images/1023733-0facb126c43e9845.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![statics](https://upload-images.jianshu.io/upload_images/1023733-bcd68eea45cdf560.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

（2）动态特性

![](https://upload-images.jianshu.io/upload_images/1023733-a369f8de52cff04e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

与PCF不同的是，这里用了equational dynamics方法进行描述。

<br/>

—— P185-P186

- - -

#### 6. untyped means uni-typed 

如果支持递归类型，那么untyped <span data-katex="\lambda"></span> calculus可以看成是，

具有**统一类型**（uni-typed）<span data-katex="\lambda"></span> calculus的类型化版本。

<br/>

我们可以定义一个这样的递归类型，

![](https://upload-images.jianshu.io/upload_images/1023733-112b868d0efd3ecb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

因此，函数的参数和函数本身将具有统一的类型（uni-typed）<span data-katex="D"></span>。

<br/>

—— P190

- - -

#### 7. dynamic typing

下面开始介绍dynamic typing了。

<br/>

将具有dynamic typed的语言，与static typed的语言对立起来看待，是有问题的。

我们可以换一个角度来看，我们说具有dynamic typed的语言，

是static typed的语言的一种特殊情况（special case）——它只有一个递归类型。

<br/>

—— P193

- - -

#### 8. DPCF的静态特性和动态特性

我们来看DPCF（dynamically Typed PCF）的静态特性和动态特性，

<br/>

（1）静态特性

![syntax](https://upload-images.jianshu.io/upload_images/1023733-5ecbbb7286459ea4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

我们看到，DPCF的值被划分成了两个**类别**（classes），一个是<span data-katex="number"></span>，另一个是<span data-katex="fun"></span>。

<br/>

![statics](https://upload-images.jianshu.io/upload_images/1023733-42bb48f24773362c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

它表明，如果<span data-katex="d"></span>包含自由变量，<span data-katex="x_1,\cdots,x_n"></span>，

则若这些自由变量是良类型的，<span data-katex="d"></span>就是良类型的。

<br/>

（2）动态特性

![](https://upload-images.jianshu.io/upload_images/1023733-274721e24c279f6d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1023733-0bb8c9fad3b39efe.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1023733-f9e834d474d2a247.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1023733-1ed071b445e2e78c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1023733-0b6351d4fadbff13.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

其中涉及到的符号解释如下，

![](https://upload-images.jianshu.io/upload_images/1023733-dd13ebebc2bd66ad.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

—— P194-196

- - -

#### 9. hybrid

一个hybrid的语言，指的是它在类型系统中混合了static typing和dynamic typing，

它为static typing语言增加了一个<span data-katex="dyn"></span>类型，该类型的值需要满足语言动态特性的要求。

<br/>

DPCF可以嵌入到一个static typed的语言中，被视为一个hybrid的语言。

只需要在static typed的语言中增加一个类型<span data-katex="dyn"></span>，

可以说，dynamic typing只是static typing的一种特定用法（a mode of use）。

<br/>

因此，static typing和dynamic typing并不是对立的，

他们可以和谐共存（coexist harmoniously）。

<br/>

—— P203

- - -

#### 10. HPCF的静态特性和动态特性

我们来看HPCF（hybrid PCF）的静态特性和动态特性，

<br/>

（1）静态特性
![syntax](https://upload-images.jianshu.io/upload_images/1023733-66cd2c00ccd7eb68.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

其中，类型<span data-katex="dyn"></span>中包含了所有具有动态类型的值。

<span data-katex="new"></span>构造器（constructor），会在值上附加一个类别描述符（classifer），以表明它所属的动态类别（class）。

<br/>

![statics - 1](https://upload-images.jianshu.io/upload_images/1023733-47e6c1dc31ee881c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![statics - 2](https://upload-images.jianshu.io/upload_images/1023733-a42aa87a1c3239b0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

以上类型断言，保证了表达式具有正确的类型。

<br/>

（2）动态特性

![](https://upload-images.jianshu.io/upload_images/1023733-3ac3c225c1ebf153.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

不同类别的值之间进行转换<span data-katex="cast"></span>，会产生运行时错误。

<br/>

—— P203-P204

- - -

#### 11. 动态类型与静态类型

dynamic语言和static语言的一些异同点。

<br/>

（1）dynamic语言将类别（class）关联到值（value）上，

而static语言将类型（type）关联到变量（variable）/表达式上。

<br/>

与dynamic语言相关的概念是类别（class），而不是类型（type），

例如<span data-katex="num"></span>，<span data-katex="fun"></span>，它们可以视为值的标签（tag）。

<br/>

（2）dynamic语言在运行时（run-time）进行类别检查（class checking），

而static语言在编译时（compile time）进行类型检查（type checking）。

<br/>

dynamic语言可以看做一类特殊的static语言——该语言中只有一个递归类型。

<br/>

—— P208
