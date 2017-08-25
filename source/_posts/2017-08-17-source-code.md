---
layout: post
categories: Design
title: 源码的误区
---

当我们还是小孩子的时候，就有了强烈的好奇心，

我们经常摆弄一些精致的小玩具，

总想拆开它们，看清里面的巧妙构造。

<br/>

这种探究内部运行机制的好奇心，是人们研究大自然的源动力，

物理学家观测分析自然现象，

总结规律，然后进行预测指导实践。

<br/>

软件工程师也是这样的，

当他们使用了一个设计精巧的类库的时候，

就总是禁不住这种诱惑，去熟读源码，想搞清楚到底别人是怎么实现的。

<br/>

无疑，这是一件值得赞赏的事情。

然而，却包含了一个不容易觉察的误区。

<br/>

那就是，

**好用的东西，其实主要并不在于内部结构的精巧，**

**而在于用户界面设计的友好。**

<br/>

实际上，大部分类库在源码级别，会屏蔽一些脏乱细节，

源码看起来并不是那么优美，

可是，最终会给用户提供优雅一致的接口（界面）。

<br/>

### 不要让用户关心细节

我们在编码的时候，如果只是为了**功能性**的目的来实现它，

那么，用户在使用的时候，就会感到非常难受。

他们不得不转换思维，将已有知识用我们提供的接口（界面）来表示，

甚至不得不搞清楚我们到底做了什么，才能猜到它的用法。

<br/>

我们先暂时岔开话题，

我们知道，汇编语言具备与现代高级语言一样的图灵完备性，

是编译器或解释器提高了语言的易用性，减小了[Semantic Gap](https://en.wikipedia.org/wiki/Semantic_gap)。

<br/>

用户使用高级语言，或者DSL，来描述领域知识，

然后计算机将它们翻译成可执行的过程。

<br/>

因此，程序语言的设计目的之一，

是为了对知识进行更直接的表述，而不需要过多的转换。

<br/>

当我们编写软件时，是处于用户与已有系统的中间位置，

一方面，我们为用户屏蔽了实现细节，

另一方面，在实现这些功能的时候，我们也不用考虑更底层的细节。

<br/>

一个软件系统，

如果必须通过阅读源码，才可以被正确使用，

那就是非常危险的，很容易被误用。

<br/>

因此，我们应该将注意力聚焦在接口（界面）上，

关注用户应该**怎样使用**这些功能。

至于实现手段，却是灵活多样的，也是用户不必关心的。

<br/>

### 源码并不是那么重要

软件业是一个年轻的行业，也是一个高速发展的行业，

这使得软件行业的从业者们，普遍缺乏经验，

浮躁和唯利是图，让好的编程方式，难以传承。

<br/>

如果说阅读源码，可以学习功能的实现方式，我觉得这并不为过。

但是，软件设计的精髓，我认为并不在实现细节上，

而在于**用户接口（界面）的设计**上。

<br/>

过多的关注源码，往往会忽视重点。

我们会看到，作者实现的太巧妙了，内部结构太优雅了，

却没有看到，同样的功能，作者居然可以提供这种方式让用户使用。

<br/>

例如：这个前端日志库，[log](https://github.com/adamschwartz/log)

```
log('this is *italic*')
log('this word _bold_')
log('this word `code`')
```

将会在控制台上，分别打印斜体，粗体和代码片段。

还提供了这样的语法，让用户编写自定义样式，

```
log('this is [c="color: red"]red[c]')
```

<br/>

提供一套类似[markdown](https://en.wikipedia.org/wiki/Markdown)的语法，是非常漂亮直接的，

而原生的`console.log`写法就比较麻烦。

```
console.log('%c error ','color:#fff;background:red;')
```

<br/>

所以，一个简单的类库，稍有经验的开发者，都可以实现出来，

但是，并不是每个人都能想出好的办法，让用户易于使用。

<br/>

### 用户接口（界面）的设计之道

现在我们知道用户接口（界面）的重要性了。

那么，到底应该如何设计一个好用的用户接口（界面）呢？

<br/>

这需要我们先理解“**知识的诅咒**”，这一[认知偏误](https://zh.wikipedia.org/wiki/%E8%AA%8D%E7%9F%A5%E5%81%8F%E8%AA%A4)，

它指的是，懂得多的人，通常难以从懂得少的人的角度思考问题。

<br/>

例如，专家常用术语交谈，却丧失了与非专业人士的沟通能力，

又例如，程序员们写的代码和文档，自己明白，但是别人读起来却很困难，

或者，我们设计的用户接口（界面），自己会用，但是别人却不知道如何下手。

<br/>

这些都是“知识的诅咒”。

为了避免这个问题，我们必须想办法让自己站在初学者的角度，重新考虑问题。

<br/>

下面我们介绍三个常用的办法，**（1）不要假设别人知道**。

<br/>

对于引入的每一个概念，我们必须小心谨慎，

从背景和动机开始，像讲故事一样的说清楚。

<br/>

经常性的写文章，是一种很好的锻炼方式，

写代码和写文章是一脉相承的。

<br/>

另一个办法是，为我们设计的接口（界面）**（2）编写丰富的文档**，

因为不介绍如何使用，就没有人知道如何正确使用它，通读源码也不行。

没有文档，就不能判定使用方式是否作者预期的。

<br/>

最后，要**（3）多向别人分享和介绍**自己学会的知识，

通过不断的磨炼，揣摩听众的反应，会掌握一些技巧，

学会如何吸引别人的注意力，以及学会如何简洁清晰的表达一个论点。

<br/>

能把事情讲明白，是一件不容易的事情。

<br/>

### 结语

以上提到的三点，看起来和代码没有什么关系，

是因为，设计接口（界面）并不是一个编码过程，

而是一个**知识传递**过程。

<br/>

我们必须为用户筛选出期望他们了解的知识，

像电影一样，调动观众情绪的一个重要手段，就是信息配比（[框视觉](https://www.zhihu.com/question/39947219/answer/214338328)），

即，导演对“信息露出”和“信息隐藏”的控制。

<br/>

在阅读源码时，聚焦到每一段的代码中，人们很容易忽视整体性，

会重点考虑功能的**实现方式**，而非**提供方式**，

这正是阅读源码的常见误区所在。

<br/>

所以，除了看别人如何**达成目标**之外，还要看别人是如何**确定目标**的，

阅读源码是很重要，会让我们学会很多技巧，

但是它却对确定一个更好的目标毫无帮助。

<br/>

虽然，可维护性和可扩展性也是重要的，关系到我们对代码的维护成本，

但这是我们自己的问题，不是用户的问题。

用户不会关心他们是怎么实现的，何况又是我们故意隐藏起来的。

<br/>

用户只关心我们有没有解决他们的问题，

有没有**给他们提供**一种低成本的方式来解决，

至于要降低我们自己成本的诉求，只好会心一笑了。