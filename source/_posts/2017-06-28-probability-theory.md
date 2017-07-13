---
layout: post
categories: Math
title: 概率论的数学基础
---

### 外测度

设<span data-katex="E\subseteq R^n"></span>，如果<span data-katex="\{I_k\}"></span>是<span data-katex="R^n"></span>中的可数个开矩体，

且有<span data-katex="E\subseteq\;{\tiny\begin{matrix}\\ \normalsize \cup \\ ^{\scriptsize k\geqslant 1}\end{matrix}}\;I_k"></span>，

则称<span data-katex="\{I_k\}"></span>为<span data-katex="E"></span>的一个**<span data-katex="L"></span>-覆盖**。

<br/>

显然这样的覆盖有很多，且每一个<span data-katex="L"></span>-覆盖<span data-katex="\{I_k\}"></span>确定了一个非负广义实值<span data-katex="\;{\tiny\begin{matrix}\infty\\ \tiny \sum \\ ^{\tiny k\geqslant 1}\end{matrix}}\; |I_k|"></span>，

（可以是<span data-katex="+\infty"></span>，<span data-katex="|I_k|"></span>表示<span data-katex="I_k"></span>的体积），

我们称，<span data-katex="m^*(E)=inf\{ \;{\tiny\begin{matrix}\infty\\ \tiny \sum \\ ^{\tiny k\geqslant 1}\end{matrix}}\; |I_k| \}"></span>，

为点集<span data-katex="E"></span>的**Lebesgue外测度**。

<br/>

<span data-katex="R^n"></span>中点集的外测度具有以下性质：

（1）非负性：<span data-katex="m^*(E)\geqslant 0"></span>，<span data-katex="m^*(\varnothing)=0"></span>

（2）单调性：如果<span data-katex="E_1\subseteq E_2"></span>，那么<span data-katex="m^*(E_1)\leqslant m^*(E_2)"></span>

（3）次可加性：<span data-katex="m^*( \;{\tiny\begin{matrix}\infty\\ \normalsize \cup \\ ^{\scriptsize k=1}\end{matrix}}\;E_k )\leqslant \;{\tiny\begin{matrix}\infty\\ \tiny \sum \\ ^{\scriptsize k=1}\end{matrix}}\; m^*(E_k)"></span>

<br/>

现在我们把外测度的概念，从<span data-katex="R^n"></span>扩展到任意非空集合<span data-katex="X"></span>上，

设<span data-katex="X"></span>是一个非空集合，<span data-katex="\mu^*"></span>是定义在幂集<span data-katex="\mathscr{P}(X)"></span>上的一个取广义实值的集合函数，且满足，

（1）<span data-katex="\mu^*(\varnothing)=0"></span>，<span data-katex="\mu^*(E)\geqslant 0,\ E\subseteq X"></span>

（2）如果<span data-katex="E_1,E_2\subseteq X"></span>，<span data-katex="E_1\subseteq E_2"></span>，那么<span data-katex="\mu^*(E_1)\leqslant\mu^*(E_2)"></span>

（3）如果<span data-katex="\{E_n\}"></span>是<span data-katex="X"></span>的子集列，则有<span data-katex="\mu^*( \;{\tiny\begin{matrix}\infty\\ \normalsize \cup \\ ^{\scriptsize n=1}\end{matrix}}\;E_n )\leqslant \;{\tiny\begin{matrix}\infty\\ \tiny \sum \\ ^{\scriptsize n=1}\end{matrix}}\; \mu^*(E_n)"></span>

那么我们就称<span data-katex="\mu^*"></span>是<span data-katex="X"></span>上的一个**外测度**。

<br/>

### 可测集

设<span data-katex="E\subseteq R^n"></span>，如果对于任意的点集<span data-katex="T\subseteq R^n"></span>，有

<span data-katex="m^*(T)=m^*(T\cap E)+m^*(T\cap \overline{E})"></span>，

则称<span data-katex="E"></span>为Lebesgue可测集，简称**可测集**，

可测集的全体称为可测集类<span data-katex="\mathscr{M}"></span>。

<br/>

可测集具有以下性质：

（1）<span data-katex="\varnothing\in\mathscr{M}"></span>

（2）如果<span data-katex="E\in\mathscr{M}"></span>，则<span data-katex="\overline{E}\in\mathscr{M}"></span>

（3）如果<span data-katex="E_1\in\mathscr{M}"></span>，<span data-katex="E_2\in\mathscr{M}"></span>，则<span data-katex="E_1\cup E_2"></span>，<span data-katex="E_1\cap E_2"></span>，以及<span data-katex="E_1 \backslash E_2"></span>都属于<span data-katex="\mathscr{M}"></span>

（4）如果<span data-katex="E_i\in\mathscr{M},i=1,2,\cdots"></span>，则其并集也属于<span data-katex="\mathscr{M}"></span>

如果进一步有<span data-katex="E_i\cap E_j=\varnothing,i\neq j"></span>，则

<span data-katex="m^*( \;{\tiny\begin{matrix}\infty\\ \normalsize \cup \\ ^{\scriptsize i=1}\end{matrix}}\;E_i )= \;{\tiny\begin{matrix}\infty\\ \tiny \sum \\ ^{\scriptsize i=1}\end{matrix}}\; m^*(E_i)"></span>，

即<span data-katex="m^*"></span>在<span data-katex="\mathscr{M}"></span>上满足**可数可加性**（或称**<span data-katex="\sigma"></span>-可加性**）。

<br/>

<span data-katex="R^n"></span>中的可测集类<span data-katex="\mathscr{M}"></span>构成了一个<span data-katex="\sigma"></span>-代数，

对于可测集<span data-katex="E"></span>，其外测度称为**测度**，记为<span data-katex="m(E)"></span>，

这就是通常所说的<span data-katex="R^n"></span>上的**Lebesgue测度**。

<br/>

### <span data-katex="\sigma"></span>代数

设<span data-katex="\mathscr{F}"></span>是由集合<span data-katex="\Omega"></span>中的一些子集所构成的集合族，

且满足下述条件：

（1）<span data-katex="\varnothing\in\mathscr{F}"></span>

（2）如果<span data-katex="A\in\mathscr{F}"></span>，则<span data-katex="\overline{A}\in\mathscr{F}"></span>

（3）如果<span data-katex="A_n\in\mathscr{F},n=1,2,\cdots"></span>，则<span data-katex="\;{\tiny\begin{matrix}\infty\\ \normalsize \cup \\ ^{\scriptsize n=1}\end{matrix}}\;A_n\in\mathscr{F}"></span>

这时我们称<span data-katex="\mathscr{F}"></span>是一个**<span data-katex="\sigma"></span>-代数**。

<br/>

设<span data-katex="\mathscr{M}"></span>是集合<span data-katex="\Omega"></span>中一些子集所构成的集合族，

我们称<span data-katex="\sigma"></span>-代数<span data-katex="\mathscr{F}"></span>**包含**<span data-katex="\mathscr{M}"></span>，

如果对于任意的<span data-katex="A\in\mathscr{M}"></span>，都有<span data-katex="A\in\mathscr{F}"></span>。

<br/>

我们称<span data-katex="\mathscr{F}"></span>为包含<span data-katex="\mathscr{M}"></span>的**最小<span data-katex="\sigma"></span>-代数**，

如果对于任意的包含<span data-katex="\mathscr{M}"></span>的<span data-katex="\sigma"></span>-代数<span data-katex="\mathscr{F'}"></span>，

如果<span data-katex="A\in\mathscr{F}"></span>，那么<span data-katex="A\in\mathscr{F'}"></span>。

<br/>

包含<span data-katex="\mathscr{M}"></span>的最小<span data-katex="\sigma"></span>-代数<span data-katex="\mathscr{F}"></span>，记为<span data-katex="\sigma(\mathscr{M})"></span>，

称为**由<span data-katex="\mathscr{M}"></span>生成的<span data-katex="\sigma"></span>-代数**。

<br/>

### 可测空间

集合<span data-katex="\Omega"></span>连同其子集的<span data-katex="\sigma"></span>-代数<span data-katex="\mathscr{F}"></span>一起，称为**可测空间**，记为<span data-katex="(\Omega,\mathscr{F})"></span>。

三元组<span data-katex="(\Omega,\mathscr{F},\mu)"></span>称为**测度空间**，其中，<span data-katex="\mu"></span>为定义在<span data-katex="(\Omega,\mathscr{F})"></span>上的测度。

如果<span data-katex="N\in\mathscr{F}"></span>，且<span data-katex="\mu(N)=0"></span>，则称<span data-katex="N"></span>为<span data-katex="\mu"></span>的**零测集**。

<br/>

如果测度空间<span data-katex="(X,\mathscr{F},\mathbf{P})"></span>满足<span data-katex="\mathbf{P}(X)=1"></span>，

则称它为**概率空间**，对应的<span data-katex="\mathbf{P}"></span>称为**概率测度**。

在概率空间<span data-katex="(X,\mathscr{F},\mathbf{P})"></span>中，<span data-katex="\mathscr{F}"></span>中的集合<span data-katex="A"></span>称为**事件**，

<span data-katex="\mathbf{P}(A)"></span>称为**事件<span data-katex="A"></span>发生的概率**。

<br/>

### Borel集

由<span data-katex="R^n"></span>中一切开集构成的开集族所生成的<span data-katex="\sigma"></span>-代数，

称为**Borel <span data-katex="\sigma"></span>-代数**，记为<span data-katex="\mathscr{B}=\mathscr{B}(R^n)"></span>，

<span data-katex="\mathscr{B}"></span>中的元素称为**Borel集**。

<br/>

我们可以将Borel集的概念扩展到拓扑空间，

拓扑空间<span data-katex="(X,\mathscr{O})"></span>，其中<span data-katex="\mathscr{O}"></span>是拓扑空间的开集族，

我们称<span data-katex="\mathscr{B}=\sigma(\mathscr{O})"></span>为<span data-katex="X"></span>上的**Borel集合族**，

其中的集合称为<span data-katex="X"></span>中的**Borel集**，而<span data-katex="(X,\mathscr{B})"></span>称为**拓扑可测空间**。

<br/>

可以证明，任一Borel集都是可测集。

<br/>

### 随机变量

设<span data-katex="(\Omega,\mathscr{F})"></span>和<span data-katex="(S,\mathscr{B})"></span>是可测空间，

如果映射<span data-katex="X:\Omega\rightarrow S"></span>满足，<span data-katex="X^{-1}(\mathscr{B})\subseteq\mathscr{F}"></span>，

就称它是**<span data-katex="\mathscr{F}|\mathscr{B}"></span>-可测的**，记为<span data-katex="X\in\mathscr{F}|\mathscr{B}"></span>。

即，对于任意的<span data-katex="B\in\mathscr{B}"></span>，由<span data-katex="X^{-1}(B):=\{\omega:X(\omega)\in B\}\in\mathscr{F}"></span>。

<br/>

在概率论中，<span data-katex="\mathscr{F}|\mathscr{B}"></span>-可测映射，通常称为**随机元**，或取值于<span data-katex="S"></span>的**随机变量**。

当<span data-katex="S=R^k"></span>（具有欧氏距离），<span data-katex="\mathscr{B}=\mathscr{B}(R^k),k>1"></span>，（Borel集）

随机元<span data-katex="X"></span>（<span data-katex="X"></span>是<span data-katex="\mathscr{F}|\mathscr{B}"></span>-可测的）称为**随机向量**。

<br/>

可测映射可以将测度由已知的空间导向另一个空间，

设<span data-katex="(\Omega,\mathscr{F})"></span>和<span data-katex="(S,\mathscr{B})"></span>是可测空间，

并且在<span data-katex="(\Omega,\mathscr{F})"></span>上给定某个概率测度<span data-katex="\mathbf{P}"></span>，

设<span data-katex="X:\Omega\rightarrow S"></span>是<span data-katex="\mathscr{F}|\mathscr{B}"></span>-可测映射。

在<span data-katex="\mathscr{B}"></span>上的测度称作随机元<span data-katex="X"></span>的**概率分布**或分布，用<span data-katex="\mathbf{P}_X"></span>表示，

如果<span data-katex="\mathbf{P}_X"></span>满足以下条件，<span data-katex="\mathbf{P}_X(B):=\mathbf{P}(X^{-1}(B)),\ B\in\mathscr{B}"></span>。

测度<span data-katex="\mathbf{P}_X"></span>称为在可测映射<span data-katex="X"></span>下，测度<span data-katex="\mathbf{P}"></span>的**像**。

<br/>

可证，在<span data-katex="(S,\mathscr{B})"></span>上的任意概率测度<span data-katex="\mathbf{Q}"></span>都可以看做某个随机元<span data-katex="X"></span>的分布。

<br/>

### 随机过程

在某个可测空间<span data-katex="(\Omega,\mathscr{F})"></span>上，对每个<span data-katex="t\in T"></span>给定随机元<span data-katex="X(t)"></span>，

则随机元族<span data-katex="X=\{X(t),t\in T\}"></span>，称为**随机函数**。

<br/>

这里需要解释一下，在上述定义中，

所有的随机元<span data-katex="X(t),t\in T"></span>都是定义在同一个可测空间<span data-katex="(\Omega,\mathscr{F})"></span>上，

但是，为了有利于研究，经常认为随机元<span data-katex="X(t),t\in T"></span>的值域可以是不同的。

准确的说，给定一个可测空间族<span data-katex="(S_t,\mathscr{B}_t),t\in T"></span>，这时，引进的随机元族<span data-katex="X=\{X(t),t\in T\}"></span>，

可以看做是定义在<span data-katex="T\times\Omega"></span>上的函数<span data-katex="X=X(t,\omega)"></span>，

并且对每个<span data-katex="t\in T"></span>取值于<span data-katex="S_t"></span>，同时是<span data-katex="\mathscr{F}|\mathscr{B}_t"></span>-可测映射（<span data-katex="X(t,\cdot):\Omega\rightarrow S_t"></span>）。

<br/>

对固定的<span data-katex="\omega"></span>，函数<span data-katex="X(\cdot,\omega)"></span>或<span data-katex="X(t,\omega),t\in T"></span>，称作**轨道**，**实现**或**样本函数**。

<br/>

在随机函数的符号中，一般来说要省略自变量<span data-katex="\omega"></span>，简写为<span data-katex="X(t)"></span>，或<span data-katex="X_t"></span>，

这两种简写的利用要根据具体情况而定。

如果<span data-katex="T\subseteq R=(-\infty,+\infty)"></span>，则参数<span data-katex="t\in T"></span>可以解释为时间，而随机函数称作**随机过程**。

<br/>

当集合<span data-katex="T"></span>为直线，半直线，线段，区间或半区间，则说是**连续时间的随机过程**，

而当<span data-katex="T\subseteq Z=\{\cdots,-1,0,1,\cdots\}"></span>，则说是**离散时间随机过程**或**随机序列**，

如果<span data-katex="T\subseteq R^d,d>1"></span>，则<span data-katex="X"></span>称为**随机场**。