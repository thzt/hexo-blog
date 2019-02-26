---
layout: post
categories: Math
title: Algebraic Effects 是什么鬼

---

### 背景

[React 16.8.0](https://github.com/facebook/react/releases/tag/v16.8.0)开始已经支持 [Hooks](https://reactjs.org/docs/hooks-intro.html)了，

传言 Hooks 受到了[Algebraic Effects](https://github.com/reactjs/rfcs/blob/master/text/0068-react-hooks.md#credits-and-prior-art)的启发，

毕竟React团队有不少[OCaml](https://github.com/ocamllabs/ocaml-effects-tutorial#2-effectful-computations-in-a-pure-setting)开发者。

<br/>

> OCaml with support for (unchecked) algebraic effects and handlers. 

> Effects and handlers provide concurrency and compose part of [Multicore OCaml](https://github.com/ocamllabs/ocaml-multicore).

> —— [Algebraic Effects and Handlers](http://ocamllabs.io/doc/effects.html)

<br/>

以下我将algebraic effects当做专题来进行了调研，其中涉及了很多能力之外的知识，

因此，出现理解上的错误是不可避免的。

就当是阶段性的总结吧，读者还请注意分辨，茶余饭后止增笑耳。

### 1. delimited continuation

但是究竟什么是Algebraic Effects，查了很多资料都没找到答案，

Sam Galson有一篇文章[Continuations, coroutines, fibers, effects](https://medium.com/yld-engineering-blog/continuations-coroutines-fibers-effects-e163dda9dedc)从JS的角度介绍了react的理论基础，

里面提到了[Delimited Continuation](https://en.wikipedia.org/wiki/Delimited_continuation)，它可用来实现各种effects。

<br/>

![](https://upload-images.jianshu.io/upload_images/1023733-9631b2677b32eaaa.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

其中[Continuation](https://en.wikipedia.org/wiki/Continuation)应该是一个很熟悉的概念了，

current continuation（当前位置的continuation）表示程序从某个位置开始，之后到程序结束所有后续的计算，

Scheme中的`call/cc`就可以用来获取当前位置的 continuation。

<br/>

至于Delimited Continuation则表示“有界的” continuation，它需要两个操作符，

例如在Racket中，它们是`reset`和`shift`，

（1）`shift`用来捕获当前位置的continuation

（2）`reset`用来表示`shift`生效的时间范围（调用顺序）

<br/>

```
(* 2 
  (reset 
    (+ 1 
      (shift k (k 5))
    )
  )
)
```

以上代码中，`shift`捕获了当前位置的continuation，并绑定到`k`上，

这个continuation是以`reset`开始调用时未界限的，即，这个continuation可以表示为`(+ 1 [*])`，

其中的`*`为continuation中待填充的值。

<br/>

后面的`* 2`在`reset`调用之前，因此不包含在`shift`捕获的continuation中。

这种截止到`reset`为止的continuation，就是**delimited continuation**。

<br/>

下面我们来看下执行逻辑，

（1）`shift`中直接调用了`(k 5)`，它会调用continuation，

（2）最后`shift`的返回值将作为`reset`的值。

<br/>

所以，以上代码相当于，

```
(* 2 
  (+ 1 5)
)
```

更多例子，可参考[Delimited Continuation](https://en.wikipedia.org/wiki/Delimited_continuation)，

与一般的Continuation（undelimited continuation）不同的是，

delimited continuation可以看做是一个函数调用，它是有返回值的。

<br/>

多个`shift`的场景，`k`里面又有`shift`，

第二个`shift`返回并不会导致`reset`结束，

```
(reset
   (begin
     (shift k (cons 1 (k (void))))
     (shift k (cons 2 (k (void))))
     null))
```

### 2. 模拟 generator

有了delimited continuation我们就可以实现很多常见的effects了，

包括IO操作，yield，try/catch等等，

<br/>

下面直接引用这篇文章中的例子，[Continuations, coroutines, fibers, effects](https://medium.com/yld-engineering-blog/continuations-coroutines-fibers-effects-e163dda9dedc)

```
const octuple = n =>
  reset(() => {
    const continueWith = shift(cont => {
      const doubled = cont(n);
      const quadrupled = cont(doubled);
      return cont(quadrupled);
    });
    return continueWith * 2;
  });
```

<br/>

其中`shift`中的`cont`，表示从`shift`开始截止到`reset`为止的delimited continuation，即，

```
x => x * 2
```

并且`shift`中对`cont`调用了好几次，`shift`的返回值将作为`reset`的值。

因此，`return continueWith * 2;`是当做`cont`执行的，而不是执行完`shift`再`return continueWith * 2;`。

`shift`中`return cont(quadrupled);`的时候，`reset`就返回了。

<br/>

有了delimited continuation我们就可以事先generator了，

```
const getAddressByUsername = username =>
  reset(() => {
    const userId = shift(getUserId.bind(username));
    const address = shift(getUserAddressById.bind(userId));
    /* continue with address */
  });
```

其中`getUserId`中会调用`cont`，而这个`cont`则是，

```
userId => {
    const address = shift(getUserAddressById.bind(userId));
    /* continue with address */
}
```

所以调用`cont`的时候，会导致第二个`shift`执行，

第二个`shift`又产生一个新的`cont`，表示第二个`shift`之后的continuation。

<br/>

我们看到有了delimited continuation，很多复杂的控制结构都可以用它来实现了，

甚至try/catch都可以。

<br/>

通过改写`shift`的写法，我们将它放到`reset`尾部，

```
onst hello = () =>
  reset(() => {
    const continueWith = shift()
    return continueWith + 'world';
  }, cont => {
    return cont('hello');
  });
```

<br/>

然后将`reset`改成`handle`，将`shift`改成`effect`，

并且为了区分其他的`handle`调用，把`effect`写为`handle`的形参。

<br/>

```
const hello = () =>
  handle((effect) => {
    const continueWith = effect(false)
    return continueWith + 'world';
  }, (isShy, cont) => {
    return isShy ? cont('goodbye') : cont('hello');
  });
```

### 3. algebraic? effects?

但是，为什么`shift`是一种`effect`呢？

这个`effect`为什么又是`algebraic`的呢？

<br/>

要揭开这个谜题还得去啃论文了。

#### 3.1 model effects

首先在[Algebraic Effects for Functional Programming](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/08/algeff-tr-2016-v2.pdf)中，作者Daan Leijen提到，

> Algebraic effect handlers, are recently gaining in popularity as a purely functional approach to modeling effects. 

> In this article, we give an end-to-end overview of practical algebraic effects in the context of a compiled implementation in the Koka language.

<br/>

所以，`algebraic effect handlers`是一种model（建模） effect的方式。

作者在`Koka`语言中，实践了一把`algebraic effects`。

<br/>

后文作者还说，

> Algebraic effects (introduced by Plotkin and Power in 2002 [34]) and algebraic effect handlers (introduced by Plotkin and Pretnar in 2009 [33]), are recently gaining in popularity as a purely functional approach to modeling effects.

<br/>

因此，引文[34]中肯定提到了Algebraic effects和algebraic effect handlers，

他们都是建模effect的手段。

#### 3.2 computational λ-calculus

我们找到了这篇文献，[Algebraic Operations and Generic Effects](http://homepages.inf.ed.ac.uk/gdp/publications/alg_ops_gen_effects.pdf)，作者Gordon Plotkin and John Power是这么说的，

> Eugenio Moggi, in [13, 15], introduced the idea of giving a uniﬁed category theoretic semantics for computational eﬀects, ... 

> Examples of such eﬀects are: nondeterminism, probabilistic nonde-terminism, exceptions, interactive input/output, side-eﬀects, and continuations with, ...

<br/>

作者说Eugenio Moggi从category theory出发，给computational effects提供了统一的语义（这个理论模型叫computational λ-calculus），

这些effects可以涵盖 nondeterminism, probabilistic nonde-terminism, exceptions, interactive input/output, side-eﬀects, and continuations，这么多场景。

也就是这些东西可以用统一的框架来解释。

<br/>

作者还说，Eugenio Moggi发明的computational λ-calculus其实跟类型化 λ-calculus差不多，

> The computational λ-calculus is essentially the same as the simply typed λ-calculus except for making a careful systematic distinction between computations and values.

唯一不同的是，computational λ-calculus严格区分的values和computations。

<br/>

> However, the calculus does not contain operations, the constructs that actually create the eﬀects. 

不过computational λ-calculus也有缺陷，它不包含operations。

而所谓operations，就是那些可以产生effects的东西。

<br/>

但是，Eugenio Moggi还是很强的，虽然computational λ-calculus不包含operations，但是computational metalanguage包含了，

> Moggi’s computational metalanguage does contain operations, and his paper [14] includes semantics for them, but he only demanded naturality of the operations in C, and he did not develop a body of theory in support of that semantics. Here, by demanding the stronger coherence condition of parametrised naturality in CT , 

> we provide a notion of algebraic operations, which we support by equivalence theorems to indicate deﬁnitiveness of the axioms, and which are further supported by our development of a uniﬁed operational semantics in [20].

只是语义方面，Eugenio Moggi做的还不够。

<br/>

因此，作者发明了一个概念称为algebraic operations，来在语义层面进行统一。

所谓，algebraic operations，说白了不过是，

> Algebraic operations are, in the sense we shall make precise, a natural generalisation, from Set to an arbitrary symmetric monoidal V-category C with cotensors, of the usual operations of universal algebra, taking T to be a strong V-monad on C.

<br/>

当然新概念总是会有定义的，

![](https://upload-images.jianshu.io/upload_images/1023733-200782f6dccd0c8b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

所以，`algebraic operations`主要还是从语义角度来看的。

它给computational λ-calculus扩充了operation，还给这些operation选了一个catetory theory的语义。

<br/>

至于computational λ-calculus的细节，可以查阅这几篇，

[Notions of computation and monads](https://core.ac.uk/download/pdf/21173011.pdf)

[Computational Lambda-Calculus and Monads](https://www.irif.fr/~mellies/mpri/mpri-ens/articles/moggi-computational-lambda-calculus-and-monads.pdf)

[An Abstract View of Programming Languages](https://www.ics.uci.edu/~jajones/INF102-S18/readings/09_Moggi.pdf)

#### 3.3 operations vs effects

以上提到了computational effects，algebraic operation，

怎么就变成algebraic effects了呢？

<br/>

这个名词来自这篇文献，[Adequacy for Algebraic Eﬀects](http://homepages.inf.ed.ac.uk/gdp/publications/Op_Sem_Comp_Lam.pdf)，它是上一篇文献的引文，作者还是Gordon Plotkin and John Power

> Moggi proposed a monadic account of computational eﬀects. He also presented the computational λ-calculus ... a core call-by-value functional programming language for eﬀects; the eﬀects are obtained by adding appropriate operations.

嗯嗯，跟我们理解的一致。

<br/>

> The question arises as to whether one can give a corresponding treatment of operational semantics. 

> In this paper we give such a treatment in the case of algebraic eﬀects where the operations are given by a single-sorted algebraic signature Σ; semantically such an n-ary operation f is taken to denote a family of morphisms fx : T(x) n −→ T(x) parametrically natural with respect to morphisms in the Kleisli category C T ; T is then said to support the family f x .

<br/>

这里它把operation的语法用single-sorted sigma代数来描述，

而这些operation的语义用category进行解释。

<br/>

所以，operation是一个语法概念，effects是语义概念。

从 [An Introduction to Algebraic Eﬀects and Handlers](https://www.eff-lang.org/handlers-tutorial.pdf)这篇文献中我们可以看出来，

![](https://upload-images.jianshu.io/upload_images/1023733-b653060aab9f0da8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

> Algebraic eﬀects are an approach to computational eﬀects based on a premise that impure behaviour arises from a set of operations such as get & set for mutable store, read & print for interactive input & output, or raise for exceptions [16,18]. 

> This naturally gives rise to handlers not only of exceptions, but of any other eﬀect, yielding a novel concept that, amongst others, can capture stream redirection, backtracking, co-operative multi-threading, and delimited continuations [21,22,5].

#### 3.4 handler

原来加入到computational λ-calculus中的operation，其语义是algebraic的，而且为了表示effects的

所以，称为algebraic effects还是挺合适的，只不过algebraic太笼统了，容易让人产生其他联系。

把algebraic effects理解为algebraic operation的定义还是比较合适的。

<br/>

[An Introduction to Algebraic Eﬀects and Handlers](https://www.eff-lang.org/handlers-tutorial.pdf)后文还介绍了用delimited continuation实现各种effects的方法，

例如，对于input/output

![](https://upload-images.jianshu.io/upload_images/1023733-b9b39c23f7786869.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

对于exception，

![](https://upload-images.jianshu.io/upload_images/1023733-ad3d214f7968ef96.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

对于non-determinism

![](https://upload-images.jianshu.io/upload_images/1023733-1ec0cf263b903d6e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/>

等等等等，还有好多，毕竟computational λ-calculus中的operation就是为了建模各种effects的。

![](https://upload-images.jianshu.io/upload_images/1023733-4ef97b9314b0222c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

出自[Notions of computation and monads](https://core.ac.uk/download/pdf/21173011.pdf)

- - -

### 结语

1. λ calculus 只建模了values不包含computaion。
2. Eugenio Moggi发明了computational λ-calculus基于category theory建模了values和computation。
3. 作为扩展Gordon Plotkin and John Power为computational λ-calculus增加了operation用来建模effect。
4. operation的语法用a single-sorted algebraic signature Σ表示，语义用a family of morphisms（algebraic operation）表示。
5. 由于operation可以表示effect，所以这样的algebraic operation，又称为algebraic effects。
6. nondeterminism, probabilistic nonde-terminism, exceptions, interactive input/output, side-eﬀects, and continuations 都是effects。
7. 它们都可以用delimited continuation实现。

<br/>

暂且这么理解吧，中间肯定会有很多理解不当之处，

因为我个人也不是学习这个方向的，所以阅读者还请多多见谅，

有专业人士路过的话，请不吝指正。

- - -

### 参考
[React 16.8.0](https://github.com/facebook/react/releases/tag/v16.8.0)

[Hooks](https://reactjs.org/docs/hooks-intro.html)

[github: reactjs/rfcs](https://github.com/reactjs/rfcs/blob/master/text/0068-react-hooks.md)

[OCaml: Concurrent Programming with Effect Handlers](https://github.com/ocamllabs/ocaml-effects-tutorial#2-effectful-computations-in-a-pure-setting)

[Multicore OCaml](https://github.com/ocamllabs/ocaml-multicore)

[Algebraic Effects and Handlers](http://ocamllabs.io/doc/effects.html)

[Continuations, coroutines, fibers, effects](https://medium.com/yld-engineering-blog/continuations-coroutines-fibers-effects-e163dda9dedc)

[Delimited Continuation](https://en.wikipedia.org/wiki/Delimited_continuation)

[Continuation](https://en.wikipedia.org/wiki/Continuation)

<br/>

[Algebraic Effects for Functional Programming](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/08/algeff-tr-2016-v2.pdf)

[Algebraic Operations and Generic Effects](http://homepages.inf.ed.ac.uk/gdp/publications/alg_ops_gen_effects.pdf)

[Notions of computation and monads](https://core.ac.uk/download/pdf/21173011.pdf)

[Computational Lambda-Calculus and Monads](https://www.irif.fr/~mellies/mpri/mpri-ens/articles/moggi-computational-lambda-calculus-and-monads.pdf)

[An Abstract View of Programming Languages](https://www.ics.uci.edu/~jajones/INF102-S18/readings/09_Moggi.pdf)

[Adequacy for Algebraic Eﬀects](http://homepages.inf.ed.ac.uk/gdp/publications/Op_Sem_Comp_Lam.pdf)

[An Introduction to Algebraic Eﬀects and Handlers](https://www.eff-lang.org/handlers-tutorial.pdf)
