---
layout: post
categories: Mind
title: 如何像十个人一样工作
---

和其他行业一样，编程行业中不同从业者的生产率是有差别的，

《[人月神话](https://book.douban.com/subject/4908230/)》中提到过一项调查，

> 同样有两年经验而且在受到同样的培训的情况下，优秀的专业程序员的工作效率是较差程序员的十倍。

<br/>

[乔布斯](https://zh.wikipedia.org/zh-hans/%E5%8F%B2%E8%92%82%E5%A4%AB%C2%B7%E4%B9%94%E5%B8%83%E6%96%AF)也注意到了这一现象，他在[遗失的访谈](https://movie.douban.com/subject/6974319/)中谈到，

> 最棒的司机与普通司机之间的差距大概是30%，最好的与普通之间的差距有多大呢？20%？

> 最好的CD机与普通CD机的差距有多大？20%？这种差距很少超过两倍。

> 但是在软件行业，还有硬件行业，这种差距有可能超过15倍，甚至100倍。

<br/>

这就是十倍效率程序员的传说。

那么，怎样才能做到十倍开发效率，像十个人一样工作呢？

<br/>

本文总结了一些“可行的”办法，茶余饭后来看下，止增笑耳。

<br/>

### 分工

根据[康威定律](https://en.wikipedia.org/wiki/Conway%27s_law)，产品结构与设计该产品组织的沟通结构是一致的，

因此，为了让工作看起来像十个人完成的，首先就要进行分工，

强行把功能划分成十个模块，不多不少。

<br/>

这十个模块必须足够隔离，互相不能过问任何实现细节。

即使是一个人来编写他们，也不能知道。

<br/>

至于这十个模块以后怎么集成起来，那是后期的事情，

记住，要想看起来像十个人开发的，早期就不要考虑集成的问题。

<br/>

### 接口

完成模块划分之后，接下来的事情，就是约定接口了，

即使是一个人，也要腼腆一些，

尽量不要对其他模块过问太多，以免打扰到其他模块的正常开发工作。

<br/>

这是面向对象开发中，[信息隐藏](https://zh.wikipedia.org/zh-hans/%E4%BF%A1%E6%81%AF%E9%9A%90%E8%97%8F)思想的绝好实践。

<br/>

凭借当前模块对其他模块的猜测，

每一个模块都要独立写出它期望其他模块应该提供的接口，

并且不能告诉这些模块的实现者。

<br/>

要做到看起来像十个人一样在开发，就得这么干。

<br/>

### mock数据

有了接口约定，并不代表着这些接口可用啊，

没问题，

我们现在要开始mock数据了。

<br/>

所谓mock数据，指的是造一份假的数据，让接口看起来是好的。

这当然是一种高效的做法，

这样做可以让实现接口的模块，对接口做出随意的修改。

<br/>

当接口做出变更的时候，切记不要更改mock数据，

不然这样看起来就不像十个人在开发了，

mock数据和实际返回的数据一定要有所不同。

<br/>

对了，如果时间比较紧急的话，最好再开发一个接口管理平台，

这样可以提高效率。

<br/>

### 联调

一定要在每个模块的功能实现完之前启动联调，我们的时间很紧急，不是么，

提前启动联调可以发现更多的问题。

<br/>

在联调的过程中，可不能为了接口的稳定，而不做出任何修改，

应该采用[敏捷开发方法](https://book.douban.com/subject/1140457/)，在依赖者人工[测试的覆盖下](https://book.douban.com/subject/1230036/)，[持续重构](https://book.douban.com/subject/4262627/)，

用大步快跑的方式，迭代开发。

<br/>

如果有日常部署环境，那就更好了，

必须可以随时重启服务器，让依赖方经常性的无缘无故的挂掉，

已测试它的[可靠性](https://baike.baidu.com/item/%E8%BD%AF%E4%BB%B6%E5%8F%AF%E9%9D%A0%E6%80%A7)。

<br/>

这是一项看起来像十个人一样开发的重要法则。

<br/>

### 异常

由于功能被划分成了十个模块，它们之间有一些依赖关系，

如果服务发生异常怎么办？

<br/>

怎么可能要让服务发生异常。

这样太不专业了。

<br/>

每个模块最外层，在暴露接口的地方，

一定要放一个大大的try-catch，

注意，在catch中不要做任何事情，就让它失效好了。

<br/>

这是软件工程的一项最佳实践。

<br/>

它会促使调用方更好的理解[业务](https://zh.wikipedia.org/zh-hans/%E4%B8%9A%E5%8A%A1)，只传递符合业务逻辑的参数，

传错了，那是你的问题，

反正我没有报错，返回null已经暗示了这一点，请注意判断。

<br/>

### 文档

为了秉持好的代码本身就是文档的指导原则，

我们在代码中绝对不能出现一行注释，否则就不是好代码了。

<br/>

此外，接口文档必须能自动生成，否则人工写文档的方式太落伍了，

为此，我们要有能力导出所有源码给依赖方，

让他自己根据源码推敲接口的返回值。

<br/>

毕竟文档总有实时性问题，人们经常说，

> Talk is cheap, show me the code.

<br/>

就是这个含义。

### 测试

这十个模块必须先经过独立测试，然后才能集成到一起，

因此，每个模块必须先写[单元测试](https://zh.wikipedia.org/zh-hans/%E5%8D%95%E5%85%83%E6%B5%8B%E8%AF%95)，保证[单测覆盖率](https://zh.wikipedia.org/zh-hans/%E4%BB%A3%E7%A2%BC%E8%A6%86%E8%93%8B%E7%8E%87)。

<br/>

为了单测覆盖率，我们必须手动调用其他模块一次，将返回值完全贴到单元测试中，

这样是效率最高的办法，也能保证覆盖掉处理逻辑的所有分支，

何乐而不为呢？

<br/>

如果当前服务不可用呢？

让测试给他，不对，就是我自己负责的那个模块，提个bug。

<br/>

值得一提的，在修复bug的时候，为了降低平均修复时间，

一定要先fix，再改代码，

当测试问起的时候，就说是缓存问题，让他刷新一下。

<br/>

### 上线

为了快速上线，让用户更早的用上产品，

我们应当在测试完所有功能之前的一个深夜发布产品。

<br/>

开发者，我，必须看起来像十个人一样，忙得焦头烂额，

在不同的电脑，不同的模块间，忙的团团转，

一点点的排查问题，以示严谨。

<br/>

当我在线上机器中改完最后一行代码之后，

就完成了发布。

<br/>

长舒一口气之后，赶紧把手机关掉，回家睡觉。

<br/>

### 反馈

为了表明我们团队有十个人，或者说我拥有十倍效率开发者的体质，

在接到用户反馈的时候，一定要花十倍的时间去定位问题。

<br/>

并且还要采用多种办法证明自己足够专业，

例如，当客户提出问题的时候，一定要先确保用户和开发环境一致，让他去重装系统。

或者是，多次负责任的登录到服务器上，手动替换编译后的动态链接库，增加调试log。

<br/>

当一切修复妥当，

必须对用户坦言相告，这是一个实习生造成的错误，

以求谅解。

<br/>

这是十倍效率程序员的最后秘诀。

<br/>

### 结语

本文展示了，为了让自己看起来像十个人一样开发，必须制造的问题，

在中国古代，人们已经看到这一点了，

> 善战者无赫赫之功，赤忠者无夸夸之言，善医者无煌煌之名。

<br/>

自古以来都是如此，没有纷争，就没有英雄。

<br/>

所以要想让一个人看起来像十个人，就必须解决十个人才能遇到的问题，

放心，没有人能够证明这些问题是你造成的，

因为软件过程是不可重现的。

<br/>

做到了这一点之后，你的用户才会佩服你，

你老板才会赏识你，你的同事才会赞许你，

你的粉丝才会膜拜你。

<br/>

你的腰包才会鼓鼓的，你的江湖地位才会如日中天。

<br/>

### 参考

[卓有成效的程序员](https://book.douban.com/subject/4214142/)

[人月神话](https://book.douban.com/subject/4908230/)

[高效能程序员的修炼](https://book.douban.com/subject/24868904/)

[遗失的访谈](https://movie.douban.com/subject/6974319/)

[程序员的呐喊](https://book.douban.com/subject/25884108/)

[程序员的职业素养](https://book.douban.com/subject/11614538/)

[程序开发心理学](https://book.douban.com/subject/26419766/)

[程序员修炼之道](https://book.douban.com/subject/21323647/)

[构建之法](https://book.douban.com/subject/27069503/)

[测试驱动开发](https://book.douban.com/subject/2208597/)

[重构](https://book.douban.com/subject/4262627/)

[黑客与画家](https://book.douban.com/subject/6021440/)

[极客与团队](https://book.douban.com/subject/21372237/)

[敏捷软件开发](https://book.douban.com/subject/1140457/)