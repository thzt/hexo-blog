---
layout: post
categories: Mind
title: 编程经验浅谈
---

随着科技的发展，计算机的普及，编程越来越流行起来了，

它的门槛越来越低，像Scratch这样的编程语言已经向青少年普及开了。

软件行业每年也都会有大量的新人加入，还会有很多人转行来做程序员，

编程这个行当，日趋火热，全民“健身”已是大势所趋。

<br/>

然而，高速发展带来的不仅仅是光鲜的外表，

还带来了很多隐患。

软件工具迭代的速度越来越快，已经没有人能够跟上它的更新速度了，

从事一线编程工作的程序员们，最能体会这种苦楚。

<br/>

此外，虽然友好的学习曲线和更低的门槛，可以通过更多的教程来填补。

但是，编程技能的传承却还在起步阶段。

在某一领域深耕五年的工程师是凤毛麟角，

还有不少人，虽然工作了很久，可以应付工作需要，但仍然难窥编程的精髓。

<br/>

本文尝试找出那些该被传承的技能，

我将结合自己的经验，列举出编程知识的关键点，

这些关键点，直接影响了我考虑问题的方式。

<br/>

### 总纲

我将编程技能划分到了以下几个类别中，包括，

（1）代码组织能力

（2）信息隐藏能力

（3）程序语言原理

（4）测试能力

（5）问题分析能力

（6）项目管理能力

<br/>

下面我们逐一展开讨论。

<br/>

### 代码组织能力

如果已经确定了实现方案，甚至代码已经写过一遍了，

再让我们重新编写，我们能写到什么程度。

<br/>

我们应该怎样组织这些代码，如何分层，如何分块？

哪些的抽象的，哪些是具体的。

如何复用，其中包含了哪些模式，采用了什么架构。

<br/>

这些都取决于程序员的**代码组织能力**。

我是这样组织代码的。

<br/>

**（1）先编写主流程**

这会让我们先从全局开始把握问题，

用分治思想，把问题切分成子问题。

<br/>

**（2）提取出跨项目可用的工具集**

如果能够识别出某些工具是跨项目可用的，那么就提取出来，再应用于本项目中，

这样会极大的减少当前问题的复杂度，

即使最终并没有被其他项目使用。

<br/>

**（3）构建辅助对象**

当事情比较复杂时，就不要直接实现它，

而是构建一些辅助对象/工具，让它们处理。

还要管理好这些对象的层次，不要让他们之间随意调用。

<br/>

以上三种办法，我经常使用，每个人的办法可能会有不同，

但最重要的不是方法本身，

而是要理解，**有办法更有效的组织代码**。

<br/>

### 信息隐藏能力

提到信息隐藏，其实人们最先想到的是面向对象编程，

一个类中可以包含私有字段和方法，

外部是无法访问的。

<br/>

这只是冰山之一角。

<br/>

实际上，信息隐藏和信息暴露是对立的，

**我们并不是要一味的隐藏信息，而是要有所选择。**

这一切要先从，我们要设计让用户知道什么开始。

我一般采取以下办法。

<br/>

**（1）先设计文档和用例**

在编写工具和框架的时候尤其重要，包括编写自用的辅助对象时，

我都会先设计用户该怎样使用它们，然后再去实现，

我会在API上多花费一些时间。

<br/>

这有两方面的好处，

一方面，文档和用例会帮我理清思路，

即，如果事情已经做好了，那么它如何与外界衔接起来。

另一方面，**在没有实现之前编写API，会避免“知识的诅咒”，**

实现者经常会误以为别人知道怎么用它。

<br/>

**（2）信息隐藏不是为了可替换**

在实际项目中，很少有提供某一个功能的组件，被无缝的替换成其他组件的时候，

这需要事先进行非常精密的设计，人们一般都做不到，也没有必要这样做。

<br/>

所以，信息隐藏，并不是为了可替换。

**而应该仅仅是，为了避免用户在使用时查看源码。**

即使最终不可替换，也实现了它的价值。

<br/>

**（3）文档比代码有用**

代码体现了功能是如何实现的，但是用户根本不关心这个，

文档体现了如何使用这些功能，这才是用户最关心的。

<br/>

比起“代码如文档”这种“可望而不及”的境界，

我更喜欢，给代码添加足够的注释以及文档。

道理其实很简单，**描述如何实现的文字，不太容易表达清楚为什么这样实现。**

菜谱中，也不会告诉你为什么要这样烹饪，为什么不用别的办法。

<br/>

因此，**代码编写者的动机**必须以注释和文档形式写明，

最重要的是，**功能期望如何被使用**，也必须写到文档最显然的地方，

不然没人知道怎么用更好。

<br/>

### 程序语言原理

和编程相关的理论很多，我唯独挑选了语言理论，

因为，我们必须知道编程语言是怎么工作的。

<br/>

必须知道什么是语法（编码），什么是语义（解码），

**我们看到的符号“1”，它不是自然数本身，只是它的一种编码。**

知道了这些之后，我们就会不畏惧生成代码的代码，

以及把数据当做代码执行的“引擎”了。

<br/>

此外，不了解或者盲目相信领域特定语言，都是有害的。

在某些情况下“解释器模式”的确是合适的，

但是也会很大程度上增加用户的学习成本。

<br/>

不了解编译本质的程序员，更容易迷信特定编程语言，

跨语言进行编程，就会受到种种限制。

<br/>

### 测试能力

在为什么需要测试这件事上，很多人都知其然不知其所以然，

其实是因为对代码进行静态分析，无法捕捉所有的运行时错误。

<br/>

因为有“停机问题”的缘故，

**我们不得不将代码运行一遍，才能知道它结果是否正确。**

因此，对代码各分支进行自测，是程序员职业素养的一种体现。

<br/>

除了手动运行一遍，我们还可以有很多其他手段，

包括让代码经过类型检查，排除一部分“显而易见”的错误，

或者编写单元测试，自动化计算测试覆盖率。

<br/>

代码质量和编写方式诚然有关，

但是最重要的一点还是，是否测试完全。

<br/>

### 问题分析能力

程序员新手接到一个任务，就会马上考虑如何实现它，

并不会过多考虑**这个问题是怎么来的**。

而老手就会谨慎很多。

<br/>

他们会询问来龙去脉，查看问题的背景，

查看**是什么痛点引发了这个问题**。

据我的经验，几乎一切问题这样考虑后，都会和一开始理解的不同。

<br/>

在自发的做任何一件事情之前，考虑问题的来源和事情的价值，会很有帮助。

例如，某一天我觉得某个功能“应该”被复用一下，因为有两处出现了相似的代码。

但我并不会立即动手。

<br/>

因为，它并不是那么“疼痛”。

这个问题，可能就是一个凭个人感觉的，无中生有的“洁癖”问题。

<br/>

**抛开目的看策略，往往就找不到正确的答案。**

例如，追求复用并不是百利而无一害的事情，复用会建立更多的依赖。

而依赖一旦更新就会有版本问题。

<br/>

### 项目管理能力

项目管理能力，并一定是项目经理的必备要求，

普通开发者同样也需要对个人负责。

<br/>

我们要评估自己开发内容的工期，

当项目出现进度风险时，还要及时反馈。

<br/>

项目组总共涉及到了哪些人，他们都是做什么的，

他们之间是怎么协同的，

这对理解项目全貌帮助也很大。

<br/>

整个项目在解决什么业务问题，要达成什么样的目标，

如何发布，回滚计划是什么，怎样部署。

<br/>

**理解它们，决定了以后我们能否单独被托付一个项目。**

<br/>

### 结语

有哪些编程经验是最值得分享的，本文就是我的答案。

这些想法来源于书籍，项目经验，以及我自己的反思。

<br/>

和我当时走的弯路一样，

在看任何资料的时候，都应该相信**作者对他的观点是带有强调意愿的**，

因此，会稍微有所偏见，也会误导读者错过某些有用的信息。

<br/>

例如，介绍“重构”技法的书籍，并不会过多告诉你它有什么坏处，

以避免你直接把书扔掉。

告诉你人生经验的长辈，也不会告诉你他对你的指导心里也没底，

以避免你听不进他的建议。

<br/>

所以，到底什么是对的，什么是错的，

就无所谓了，我们只当为大自然增加了一种多样性吧。

也为了在“身临其境”的时候，做到“心灵相通”。