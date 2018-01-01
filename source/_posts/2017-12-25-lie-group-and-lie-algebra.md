---
layout: post
categories: Math
title: 李群和李代数
---

### 群论

集合<span data-katex="G"></span>，配以满足以下条件的映射<span data-katex="G\times G\to G"></span>（群乘法），称为**群**：

（a）<span data-katex="(g_1g_2)g_3=g_1(g_2g_3)"></span>，<span data-katex="\forall g_1,g_2,g_3\in G"></span>

（b）存在恒等元<span data-katex="e\in G"></span>，使得<span data-katex="eg=ge=g"></span>，<span data-katex="\forall g\in G"></span>

（c）<span data-katex="\forall g\in G"></span>，存在逆元<span data-katex="g^{-1}\in G"></span>，使得<span data-katex="g^{-1}g=gg^{-1}=e"></span>

<br/>

乘法满足交换律的群，称为**阿贝尔群**，

只含有有限个元素的群，叫做**有限群**，否则叫做**无限群**。

<br/>

群<span data-katex="G"></span>的子集<span data-katex="H"></span>称为<span data-katex="G"></span>的**子群**，

如果<span data-katex="H"></span>用<span data-katex="G"></span>的乘法为乘法也构成群。

<br/>

**同态**

设<span data-katex="G"></span>和<span data-katex="G'"></span>是群，映射<span data-katex="\mu:G\to G'"></span>叫做**同态**，

若<span data-katex="\mu(g_1g_2)=\mu(g_1)(g_2)"></span>，<span data-katex="\forall g_1,g_2\in G"></span>。

<br/>

同态映射<span data-katex="\mu:G\to G'"></span>有以下性质：

（a）若<span data-katex="e,e'"></span>分别为<span data-katex="G,G'"></span>的恒等元，则<span data-katex="\mu(e)=e'"></span>

（b）<span data-katex="\mu(g^{-1})=\mu(g)^{-1}"></span>，<span data-katex="\forall g\in G"></span>

（c）<span data-katex="\mu[G]"></span>是<span data-katex="G'"></span>的子群

<br/>

一一到上的同态映射称为**同构**，

同构<span data-katex="\mu:G\to G"></span>称为群<span data-katex="G"></span>上的**自同构**。

<br/>

<span data-katex="\forall g\in G"></span>，可以构造一个自同构映射，

记为<span data-katex="I_g:G\to G"></span>，

定义为<span data-katex="I_g(h):=ghg^{-1}"></span>，<span data-katex="\forall h\in G"></span>，

称为**伴随同构**，或称**内自同构**。

<br/>

**直积群**

群<span data-katex="G"></span>和<span data-katex="G'"></span>（看做两个集合），它们的卡氏积<span data-katex="G\times G'"></span>，

按下列乘法构成的群，称为<span data-katex="G"></span>和<span data-katex="G'"></span>的**直积群**，

<span data-katex="(g_1,g'_1)(g_2,g'_2):=(g_1g_2,g'_1,g'_2)"></span>，

<span data-katex="\forall g_1,g_2\in G,g'_1,g'_2\in G'"></span>

<br/>

**左陪集**

设<span data-katex="H"></span>是群<span data-katex="G"></span>的子群，<span data-katex="g\in G"></span>，

则<span data-katex="gH\equiv \{gh|h\in H\}"></span>称为<span data-katex="H"></span>的含<span data-katex="g"></span>的**左陪集**，

类似的可以定义**右陪集**。

<br/>

如果子群<span data-katex="H"></span>的两个左陪集有交，则两者必相等。

<br/>

群<span data-katex="G"></span>的子群<span data-katex="H"></span>称为**正规子群**，或**不变子群**，

若<span data-katex="ghg^{-1}\in H"></span>，<span data-katex="\forall g\in G,h\in H"></span>。

<br/>

设<span data-katex="G"></span>是群，则<span data-katex="A(G)\equiv \{\mu:G\to G\}"></span>，<span data-katex="\mu"></span>为自同构映射，

<span data-katex="A(G)"></span>以映射的复合为群乘法构成群，称为群<span data-katex="G"></span>的**自同构群**。

<br/>

以<span data-katex="A_I(G)"></span>代表<span data-katex="G"></span>上全体内自同构映射的集合，

即<span data-katex="A_I(G)\equiv \{I_g:G\to G|g\in G\}\subset A(G)"></span>，

则<span data-katex="A_I(G)"></span>是群<span data-katex="A(G)"></span>的一个正规子群。

<br/>

**半直积群**

设<span data-katex="H"></span>和<span data-katex="K"></span>是群，且存在同态映射<span data-katex="\mu:K\to A(H)"></span>，

并且<span data-katex="\forall k\in K"></span>，把<span data-katex="\mu(k)\in A(H)"></span>简记为<span data-katex="\mu_k"></span>，

则<span data-katex="G\equiv H\times K"></span>配以下式定义的群乘法，

<span data-katex="(h,k)(h',k'):=(h\mu_k(h'),kk')"></span>，

<span data-katex="\forall h,h'\in H,k,k'\in K"></span>，

所构成的群称为<span data-katex="H"></span>和<span data-katex="K"></span>的**半直积群**，记为<span data-katex="G\equiv H\bigotimes_S K"></span>。

<br/>

### 李群

若<span data-katex="G"></span>既是<span data-katex="n"></span>维（实）流形又是群，其群乘映射<span data-katex="G\times G\to G"></span>，

和求逆映射<span data-katex="G\to G"></span>，都是<span data-katex="C^\infty"></span>的，

则<span data-katex="G"></span>叫做**<span data-katex="n"></span>维（实）李群**。

<br/>

李群<span data-katex="G"></span>和<span data-katex="G'"></span>之间的<span data-katex="C^\infty"></span>同态映射<span data-katex="\mu:G\to G'"></span>，称为**李群同态**。

李群同态<span data-katex="\mu"></span>称为**李群同构**，若<span data-katex="\mu"></span>为微分同胚。

<br/>

李群<span data-katex="G"></span>的子集<span data-katex="H"></span>称为<span data-katex="G"></span>的**李子群**，

若<span data-katex="H"></span>既是<span data-katex="G"></span>的子流形，又是<span data-katex="G"></span>的子群。

<br/>

**左平移**

<span data-katex="\forall g\in G"></span>，映射<span data-katex="L_g:h\mapsto gh"></span>，<span data-katex="\forall h\in G"></span>，

叫做由<span data-katex="g"></span>生成的**左平移**。

<br/>

以下讨论经常涉及<span data-katex="G"></span>的一点的矢量，和<span data-katex="G"></span>的一个子集上的矢量场，

我们将用<span data-katex="A,B,\cdots"></span>代表一点的矢量，

用<span data-katex="\bar{A},\bar{B},\cdots"></span>代表矢量场，

用<span data-katex="\bar{A}_g"></span>代表矢量场<span data-katex="\bar{A}"></span>在点<span data-katex="g\in G"></span>的值。

<br/>

<span data-katex="G"></span>上矢量场<span data-katex="\bar{A}"></span>，叫做**左不变的**，

若<span data-katex="L_{g*}\bar{A}=\bar{A}"></span>，<span data-katex="\forall g\in G"></span>，

其中<span data-katex="L_{g*}"></span>是由左平移映射<span data-katex="L_g:G\to G"></span>诱导的推前映射。

<br/>

考虑到微分同胚<span data-katex="\phi:M\to N"></span>，它诱导的推前映射<span data-katex="\phi_*"></span>把<span data-katex="M"></span>上的矢量场<span data-katex="\bar{A}"></span>，

映射为<span data-katex="N"></span>上的矢量场<span data-katex="\phi_*(\bar{A})"></span>，

满足<span data-katex="(\phi_*\bar{A})|_{\phi(p)}=\phi_*(\bar{A}|_p)"></span>，<span data-katex="\forall p\in M"></span>。

令<span data-katex="M=N=G"></span>，<span data-katex="\phi=L_g"></span>，<span data-katex="p=h"></span>，

我们有<span data-katex="(L_{g*}\bar{A})_{gh}=L_{g*}(\bar{A}_h)"></span>。

<br/>

取左不变矢量场定义中的等式在<span data-katex="gh"></span>处的值，可得，

<span data-katex="(L_{g*}\bar{A})_{gh}=\bar{A}_{gh}"></span>，<span data-katex="\forall g,h\in G"></span>，

因此，我们得到了一个**左不变矢量场的等价定义**，

<span data-katex="\bar{A}_{gh}=L_{g*}(\bar{A}_h)"></span>。

<br/>

左不变矢量场之和，以及左不变矢量场乘以常数，仍为左不变矢量场，

因此所有左不变矢量场的集合<span data-katex="\mathscr{L}\equiv \{\bar{A}\}"></span>是一个**矢量空间**。

<br/>

<span data-katex="G"></span>上全体左不变矢量场的集合<span data-katex="\mathscr{L}"></span>，

与<span data-katex="G"></span>的恒等元<span data-katex="e"></span>的切空间<span data-katex="V_e"></span>，（作为两个矢量空间）同构。

<br/>

### 李代数

在矢量空间<span data-katex="\mathscr{V}"></span>上定义某种称为“乘法”的映射，就得到一个**代数**。

<br/>

一种重要的乘法叫做**李括号**，记做<span data-katex="[,]:\mathscr{V}\times\mathscr{V}\to\mathscr{V}"></span>，

它是满足以下两个条件的双线性映射：

（a）<span data-katex="[A,B]=-[B,A]"></span>，<span data-katex="\forall A,B\in\mathscr{V}"></span>

（b）<span data-katex="[A,[B,C]]+[C,[A,B]]+[B,[C,A]]=0"></span>，<span data-katex="\forall A,B,C\in\mathscr{V}"></span>

条件（b）称为**雅可比恒等式**。

<br/>

定义了李括号的矢量空间，称为**李代数**，

任意两个元素的李括号都为零的李代数，称为**阿贝尔李代数**。

<br/>

<span data-katex="G"></span>上全体左不变矢量场的集合<span data-katex="\mathscr{L}"></span>是李代数。

<br/>

**李代数同态**

设<span data-katex="\mathscr{V}"></span>和<span data-katex="\mathscr{W}"></span>是李代数，

线性映射<span data-katex="\beta:\mathscr{V}\to\mathscr{W}"></span>称为**李代数同态**，

若它保李括号，即<span data-katex="\beta([A,B])=[\beta(A),\beta(B)]"></span>，<span data-katex="\forall A,B\in\mathscr{V}"></span>。

<br/>

李代数同态<span data-katex="\beta:\mathscr{V}\to\mathscr{W}"></span>称为**李代数同构**，

若<span data-katex="\beta"></span>是一一到上映射。

<br/>

**李群的李代数**

对李群<span data-katex="G"></span>的恒等元<span data-katex="e"></span>的切空间<span data-katex="V_e"></span>用下式定义李括号，

<span data-katex="[A,B]:=[\bar{A},\bar{B}]_e"></span>，<span data-katex="\forall A,B\in V_e"></span>，

其中<span data-katex="\bar{A},\bar{B}"></span>分别是<span data-katex="A,B"></span>对应的左不变矢量场。

则<span data-katex="V_e"></span>成为李代数，称为**李群<span data-katex="G"></span>的李代数**，记为<span data-katex="\mathscr{G}"></span>。

<br/>

给定一个李代数，总可以找到唯一的单联通李群，

它以所给李代数为李代数。

<br/>

设<span data-katex="\mathscr{G}"></span>和<span data-katex="\hat{\mathscr{G}}"></span>分别是李群<span data-katex="G"></span>和<span data-katex="\hat{G}"></span>的李代数，

<span data-katex="\rho:G\to\hat{G}"></span>是同态映射，

则<span data-katex="\rho"></span>在点<span data-katex="e\in G"></span>诱导的推前映射<span data-katex="\rho_*:\mathscr{G}\to\hat{\mathscr{G}}"></span>，

是李代数同态。

<br/>

**李子代数**

李代数<span data-katex="\mathscr{G}"></span>的子空间<span data-katex="\mathscr{H}"></span>，称为<span data-katex="\mathscr{G}"></span>的**李子代数**，

若<span data-katex="[A,B]\in\mathscr{H}"></span>，<span data-katex="\forall A,B\in\mathscr{H}"></span>。

其中<span data-katex="[A,B]"></span>是把<span data-katex="A,B"></span>看做<span data-katex="\mathscr{G}"></span>的元素时的李括号，

现在也称为子代数<span data-katex="\mathscr{H}"></span>的李括号。

<br/>

设<span data-katex="H"></span>是李群<span data-katex="G"></span>的李子群，

则<span data-katex="H"></span>的李代数<span data-katex="\mathscr{H}"></span>是<span data-katex="\mathscr{G}"></span>的李子代数。

<br/>

李代数<span data-katex="\mathscr{G}"></span>的子代数<span data-katex="\mathscr{H}"></span>称为<span data-katex="\mathscr{G}"></span>的**理想**，

若<span data-katex="[A,\mu]\in\mathscr{H}"></span>，<span data-katex="\forall A\in\mathscr{G},\mu\in\mathscr{H}"></span>。

<br/>

设<span data-katex="\mathscr{H}\subset\mathscr{G}"></span>是理想，

<span data-katex="\mathscr{G}/\mathscr{H}"></span>代表以等价类为元素的集合，

（<span data-katex="A,B\in\mathscr{G}"></span>叫做等价的，若<span data-katex="A-B\in\mathscr{H}"></span>）

则<span data-katex="\mathscr{G}/\mathscr{H}"></span>是李代数，称为**商李代数**。

<br/>

李代数<span data-katex="\mathscr{G}"></span>为**单李代数**，若它不是阿贝尔李代数，

而且除<span data-katex="\mathscr{G}"></span>及<span data-katex="\{0\}"></span>外不含理想。

<span data-katex="\mathscr{G}"></span>称为**半单李代数**，若它不含非零的阿贝尔理想。

<br/>

相应的，李群<span data-katex="G"></span>称为**单李群**，若它不是阿贝尔群，

而且除<span data-katex="G"></span>外不含正规子群。

<span data-katex="G"></span>称为**半单李群**，若它不含阿贝尔正规子群。

- - -

### 参考

[微分几何入门与广义相对论（中册） - 附录G](https://book.douban.com/subject/3613832/)
