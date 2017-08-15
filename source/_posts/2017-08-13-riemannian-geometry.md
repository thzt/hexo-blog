---
layout: post
categories: Math
title: 黎曼几何基础
---

### 可微函数

<span data-katex="n"></span>维**欧氏空间**，简记为<span data-katex="R^n"></span>，是有序的<span data-katex="n"></span>元实数组的集合，

并赋予标准的距离<span data-katex="d"></span>所构成的空间，其元素称为“点”。

<br/>

<span data-katex="R^n"></span>中任意两点<span data-katex="a=(a^1,\cdots ,a^n)"></span>，<span data-katex="b=(b^1,\cdots ,b^n)"></span>之间的距离定义为，

<span data-katex="d(a,b)=\sqrt{\displaystyle\sum_{i=1}^n (b^i-a^i)^2}"></span>。

<br/>

设<span data-katex="U"></span>是<span data-katex="R^n"></span>的一个开集，<span data-katex="r"></span>为正数，

如果<span data-katex="U"></span>上的实函数<span data-katex="f:U\rightarrow R"></span>具有直到<span data-katex="r"></span>阶的各阶连续偏导数，

则称<span data-katex="f"></span>为<span data-katex="U"></span>上的一个<span data-katex="r"></span>次**可微函数**。

<br/>

<span data-katex="U"></span>上的<span data-katex="r"></span>次可微函数的集合记为<span data-katex="C^r(U)"></span>，

依此记法，<span data-katex="U"></span>上的连续函数的集合记作<span data-katex="C^0(U)"></span>。

<br/>

给定函数<span data-katex="f:U\rightarrow R"></span>，如果对于任意的非负整数<span data-katex="r"></span>，

都有<span data-katex="f\in C^r(U)"></span>，则称函数<span data-katex="f"></span>是<span data-katex="U"></span>上的一个**光滑函数**，

<span data-katex="U"></span>上的光滑函数的集合记作<span data-katex="C^\infty (U)"></span>。

<br/>

为了方便起见，把<span data-katex="C^r(U)"></span>中的函数，称为（<span data-katex="U"></span>上的）<span data-katex="C^r"></span>函数。

### 欧氏空间之间的映射

设<span data-katex="U"></span>是<span data-katex="R^n"></span>的一个开子集，

<span data-katex="f:U\rightarrow R"></span>是从<span data-katex="U"></span>到<span data-katex="k"></span>维欧氏空间<span data-katex="R^k"></span>的映射，

显然，映射<span data-katex="f"></span>可以用<span data-katex="U"></span>上的<span data-katex="k"></span>个实函数<span data-katex="f^\alpha(1\leqslant\alpha\leqslant k)"></span>表示为，

<span data-katex="f=(f^1,\cdots ,f^k)"></span>，

其中，<span data-katex="f^\alpha(1\leqslant\alpha\leqslant k)"></span>称为映射<span data-katex="f"></span>的**分量**。

<br/>

如果对于每一个<span data-katex="\alpha(1\leqslant\alpha\leqslant k)"></span>，<span data-katex="f^\alpha"></span>都是<span data-katex="U"></span>上的<span data-katex="C^r"></span>函数，

则称映射<span data-katex="f"></span>为（从<span data-katex="U"></span>到<span data-katex="R^k"></span>的）<span data-katex="C^r"></span>映射。

<br/>

特别的，如果<span data-katex="U"></span>是<span data-katex="R"></span>的一个开区间，

则<span data-katex="C^\infty"></span>映射<span data-katex="f:U\rightarrow R^k"></span>又称为<span data-katex="R^k"></span>中的一条**光滑曲线**。

### 拓扑流形和微分流形

设<span data-katex="M"></span>是一个非空的Hausdorff空间，

如果对于每一点<span data-katex="p\in M"></span>，都存在<span data-katex="p"></span>点的开邻域<span data-katex="U\subseteq M"></span>，

以及从<span data-katex="U"></span>到<span data-katex="m"></span>维欧氏空间<span data-katex="R^m"></span>的某个开集上的同胚<span data-katex="\varphi :U\rightarrow R^m"></span>，

则称<span data-katex="M"></span>为一个<span data-katex="m"></span>维**拓扑流形**。

<br/>

上述定义中的<span data-katex="(U,\varphi)"></span>称为<span data-katex="M"></span>的一个**坐标卡**，

此时，开集<span data-katex="U"></span>称为点<span data-katex="p\in M"></span>的**坐标邻域**，<span data-katex="\varphi"></span>称为**坐标映射**。

于是，所谓的拓扑流形实际上就是在局部上同胚于<span data-katex="m"></span>维欧氏空间的Hausdorff空间，

即它的每一点都有同胚于<span data-katex="R^n"></span>中某个开集的坐标邻域。

<br/>

设<span data-katex="M"></span>是一个<span data-katex="m"></span>维拓扑流形，<span data-katex="(U,\varphi)"></span>与<span data-katex="(V,\psi)"></span>是<span data-katex="M"></span>的两个坐标卡，

如果<span data-katex="U\cap V=\varnothing"></span>，或者当<span data-katex="U\cap V\neq\varnothing"></span>时，映射

<span data-katex="\psi\circ\varphi^{-1}:\varphi(U\cap V)\rightarrow\psi(V)"></span>

和<span data-katex="\varphi\circ\psi^{-1}:\psi(U\cap V)\rightarrow\varphi(U)"></span>，

都是<span data-katex="C^r"></span>映射，则称坐标卡<span data-katex="(U,\varphi)"></span>与<span data-katex="(V,\psi)"></span>是<span data-katex="C^r"></span>**相容的**。

<br/>

显然，拓扑流形<span data-katex="M"></span>的任意两个坐标卡必定是<span data-katex="C^0"></span>相容的。

<br/>

设<span data-katex="M"></span>是一个拓扑流形，

<span data-katex="\mathscr{A}=\{(U_\alpha,\varphi_\alpha);\alpha\in I\}"></span>是<span data-katex="M"></span>的若干坐标卡构成的集合，<span data-katex="I"></span>为指标集。

如果<span data-katex="\mathscr{A}"></span>满足下列三个条件，

则称<span data-katex="\mathscr{A}"></span>为拓扑流形<span data-katex="M"></span>的一个<span data-katex="C^r"></span>**微分结构**，

（1）<span data-katex="\{U_\alpha;\alpha\in I\}"></span>是<span data-katex="M"></span>是一个开覆盖，

（2）<span data-katex="\forall\alpha,\beta\in I"></span>，<span data-katex="(U_\alpha,\varphi_\alpha)"></span>与<span data-katex="(U_\beta,\varphi_\beta)"></span>是<span data-katex="C^r"></span>相容的，

（3）<span data-katex="\mathscr{A}"></span>是**极大的**，换句话说，对于<span data-katex="M"></span>的任意一个坐标卡<span data-katex="(U,\varphi)"></span>，

如果它和<span data-katex="\mathscr{A}"></span>中的每一个成员都是<span data-katex="C^r"></span>相容的，则它一定属于<span data-katex="\mathscr{A}"></span>。

<br/>

<span data-katex="C^\infty"></span>微分结构，称为**光滑结构**。

<br/>

设<span data-katex="M"></span>是一个<span data-katex="m"></span>维拓扑流形，<span data-katex="\mathscr{A}"></span>是<span data-katex="M"></span>的一个<span data-katex="C^r"></span>微分结构，

则称<span data-katex="(M,\mathscr{A})"></span>是一个<span data-katex="m"></span>维<span data-katex="C^r"></span>**微分流形**。

此时，<span data-katex="\mathscr{A}"></span>中的坐标卡统称为<span data-katex="C^r"></span>微分流形<span data-katex="(M,\mathscr{A})"></span>的**容许坐标卡**。

<br/>

特别的，<span data-katex="C^\infty"></span>微分流形，又称为**光滑流形**。

在不引起混淆的情况下，也用<span data-katex="M"></span>表示一个<span data-katex="C^r"></span>微分流形<span data-katex="(M,\mathscr{A})"></span>。

### 局部坐标系

设<span data-katex="(U,\varphi)"></span>是<span data-katex="m"></span>维微分流形<span data-katex="M"></span>的一个容许坐标卡，

则对于<span data-katex="\forall p\in U"></span>，把<span data-katex="x=\varphi(p)"></span>在<span data-katex="R^m"></span>中的坐标<span data-katex="(x^1(p),\cdots ,x^m(p))"></span>，

称为点<span data-katex="p"></span>的**局部坐标**。

<br/>

以这样的方式，在<span data-katex="U"></span>上确定了一个坐标系，

称为<span data-katex="M"></span>在<span data-katex="p"></span>点的一个（由局部坐标卡<span data-katex="(U,\varphi)"></span>给出的）**局部坐标系**，

记为<span data-katex="(U,\varphi;x^i)"></span>，或<span data-katex="(U;x^i)"></span>，

其中，定义在<span data-katex="U"></span>上的<span data-katex="m"></span>个函数<span data-katex="x^i:U\rightarrow R\ (i=1,\cdots ,m)"></span>，

称为**（局部）坐标函数**。

<br/>

对于<span data-katex="M"></span>的任意两个<span data-katex="C^r"></span>相容的局部坐标系<span data-katex="(U,\varphi;x^i)"></span>和<span data-katex="(V,\psi;y^i)"></span>，

如果<span data-katex="U\cap V\neq\varnothing"></span>，则称映射，

<span data-katex="\psi\circ\varphi^{-1}:\varphi(U\cap V)\rightarrow\psi(U\cap V)"></span>，

为从<span data-katex="(U,\varphi;x^i)"></span>到<span data-katex="(V,\psi;y^i)"></span>的**（局部）坐标变换**，

它可以表示为，

<span data-katex="y^i=(\phi\circ\varphi^{-1})^i=y^i(x^1,\cdots ,x^m)"></span>，<span data-katex="1\leqslant i\leqslant m"></span>。

<br/>

由此所得到的<span data-katex="m"></span>阶方阵，<span data-katex="J_{x;y}=\left ( \frac{\partial y^i}{\partial x^i} \right )"></span>，

称为局部坐标变换<span data-katex="\psi\circ\varphi^{-1}"></span>的**Jacobi矩阵**，

相应的行列式称为<span data-katex="\psi\circ\varphi^{-1}"></span>的**Jacobi行列式**，

并且记，

<span data-katex="\frac{\partial (y^1,\cdots,y^m)}{\partial (x^1,\cdots,x^m)}=det\left ( \frac{\partial y^i}{\partial x^i} \right )"></span>。

### 流形间的映射

设<span data-katex="M"></span>是一个<span data-katex="m"></span>维光滑流形，<span data-katex="G"></span>为<span data-katex="M"></span>的非空子集，

<span data-katex="f:G\rightarrow R"></span>是定义在<span data-katex="G"></span>上的实值函数，

如果对于<span data-katex="M"></span>的任意一个容许坐标卡<span data-katex="(U,\varphi)"></span>，当<span data-katex="U\cap G\neq\varnothing"></span>时，

<span data-katex="f\circ\varphi^{-1}:\varphi(G\cap U)\rightarrow R"></span>，是<span data-katex="C^s"></span>函数，

则称<span data-katex="f"></span>是<span data-katex="G"></span>上的<span data-katex="C^s"></span>函数。

<span data-katex="G"></span>上的<span data-katex="C^\infty"></span>函数又称为**光滑函数**。

<br/>

开集<span data-katex="G"></span>上全体<span data-katex="C^s"></span>函数的集合记作<span data-katex="C^s(G)"></span>，

特别的，<span data-katex="M"></span>上全体光滑函数的集合记作<span data-katex="C^\infty(M)"></span>。

不难看出，<span data-katex="C^s(G)"></span>关于函数的加法和乘法构成一个环。

<br/>

设<span data-katex="M"></span>为光滑流形，<span data-katex="p\in M"></span>，<span data-katex="f"></span>是定义在<span data-katex="p"></span>点某个邻域<span data-katex="A"></span>上的函数，

如果存在<span data-katex="p"></span>的开邻域<span data-katex="U\subseteq A"></span>，使得<span data-katex="f|_U"></span>是<span data-katex="U"></span>上的<span data-katex="C^s"></span>函数，

则称<span data-katex="f"></span>是定义在<span data-katex="p"></span>点**附近**的<span data-katex="C^s"></span>函数，简称为在<span data-katex="p"></span>点的<span data-katex="C^s"></span>函数。

<br/>

全体在<span data-katex="p"></span>点的<span data-katex="C^s"></span>函数构成的集合记作<span data-katex="C^s_p"></span>，

一般的，<span data-katex="C^s_p"></span>中两个函数可以有不同的定义域，

但是它们在<span data-katex="p"></span>点的某一个开邻域上都有定义并且是<span data-katex="C^s"></span>的，

因此，<span data-katex="C^s_p"></span>中可以定义加法和乘法。

<br/>

设<span data-katex="M,N"></span>分别是<span data-katex="m,n"></span>维光滑流形，<span data-katex="f:M\rightarrow N"></span>为映射，<span data-katex="p\in M"></span>，

如果存在<span data-katex="M"></span>在点<span data-katex="p"></span>的容许坐标卡<span data-katex="(U,\varphi)"></span>，

以及<span data-katex="N"></span>在点<span data-katex="f(p)"></span>的容许坐标卡<span data-katex="(V,\psi)"></span>，使得<span data-katex="f(U)\subseteq V"></span>，

并且复合映射，<span data-katex="\tilde{f}=\psi\circ f\circ\varphi^{-1}:\varphi(U)\rightarrow\psi(V)"></span>，是<span data-katex="C^\infty"></span>映射，

则称映射<span data-katex="f"></span>在<span data-katex="p"></span>点是<span data-katex="C^\infty"></span>的（或**光滑的**）。

<br/>

通常，称映射<span data-katex="\tilde{f}"></span>为映射<span data-katex="f"></span>关于坐标卡<span data-katex="(U,\varphi)"></span>和<span data-katex="(V,\psi)"></span>的**局部表示**，

具体的写出来，它由<span data-katex="n"></span>个<span data-katex="m"></span>元实函数组成。

<br/>

设<span data-katex="f:M\rightarrow N"></span>是光滑流形<span data-katex="M,N"></span>间的映射，

如果<span data-katex="f"></span>在<span data-katex="M"></span>的每一点<span data-katex="p"></span>处都是<span data-katex="C^\infty"></span>的，

则称<span data-katex="f"></span>为<span data-katex="C^\infty"></span>映射，或**光滑映射**。

<br/>

设<span data-katex="M"></span>和<span data-katex="N"></span>是两个光滑流形，<span data-katex="f:M\rightarrow N"></span>是一个同胚，

如果<span data-katex="f"></span>及其逆映射<span data-katex="f^{-1}:N\rightarrow M"></span>都是光滑的，

则称<span data-katex="f"></span>是从<span data-katex="M"></span>到<span data-katex="N"></span>的**光滑同胚**，或**微分同胚**。

此时，也称<span data-katex="M"></span>和<span data-katex="N"></span>彼此光滑（或微分）同胚。

<br/>

如果<span data-katex="f:M\rightarrow N"></span>是一个光滑映射，并且对于每一点<span data-katex="p\in M"></span>，

都有<span data-katex="p"></span>的一个开邻域<span data-katex="U"></span>使得<span data-katex="f(U)"></span>是<span data-katex="N"></span>中的开子集，

并且，<span data-katex="f|_U:U\rightarrow f(U)"></span>是从<span data-katex="U"></span>到<span data-katex="f(U)"></span>的光滑同胚，

则称<span data-katex="f"></span>是从<span data-katex="M"></span>到<span data-katex="N"></span>的**局部光滑同胚**。

<br/>

显然，如果<span data-katex="f"></span>是从<span data-katex="M"></span>到<span data-katex="N"></span>的光滑同胚，

则<span data-katex="f^{-1}"></span>是从<span data-katex="N"></span>到<span data-katex="M"></span>的光滑同胚。

### 切向量

假定<span data-katex="M"></span>是一个<span data-katex="m"></span>维光滑流形，<span data-katex="p\in M"></span>，

<span data-katex="C^\infty_p"></span>表示在<span data-katex="p"></span>点的光滑函数的集合。

光滑流形<span data-katex="M"></span>在点<span data-katex="p\in M"></span>的一个**切向量**<span data-katex="v"></span>指的是，

满足以下两个条件的映射<span data-katex="v:C^\infty_p\rightarrow R"></span>，

（1）<span data-katex="\forall f,g\in C^\infty_p"></span>，<span data-katex="\forall\lambda\in R"></span>，<span data-katex="v(f+\lambda g)=v(f)+\lambda v(g)"></span>，

（2）<span data-katex="\forall f,g\in C^\infty_p"></span>，<span data-katex="v(fg)=v(f)g(p)+f(p)v(g)"></span>。

<br/>

设<span data-katex="(U,\varphi;x^i)"></span>是<span data-katex="p"></span>点的一个局部坐标系，

对于任意的<span data-katex="f\in C^\infty_p"></span>，记，

<span data-katex="\frac{\partial f}{\partial x^i}(p)=\frac{\partial (f\circ\varphi^{-1})}{\partial x^i}(\varphi(p))"></span>。

<br/>

设<span data-katex="M=R^m"></span>，<span data-katex="x_0\in R^m"></span>，

对于向量<span data-katex="v\in R^m"></span>，我们定义映射<span data-katex="D_v:C^\infty_{x_0}\rightarrow R"></span>如下，

对于任意的函数<span data-katex="f\in C^\infty_{x_0}"></span>，令，

<span data-katex="D_v f=\frac{df(x_0+tv)}{dt}\Big\vert_{t=0}"></span>，

则<span data-katex="D_v f"></span>是函数<span data-katex="f"></span>在点<span data-katex="x_0"></span>沿向量<span data-katex="v"></span>的**方向导数**。

<br/>

容易验证，方向导数算子<span data-katex="D_v"></span>满足切向量的条件，

所以它是<span data-katex="R^m"></span>在<span data-katex="x_0"></span>点的一个切向量。

<br/>

假定<span data-katex="v=(v^1,\cdots,v^m)"></span>，则，

<span data-katex="D_v f=\displaystyle\sum_{i=1}^m\frac{\partial f}{\partial x^i}(x_0)\cdot v^i"></span>。

因此，算子<span data-katex="D_v"></span>是由向量<span data-katex="v"></span>唯一决定的。

<br/>

反之，可以证明，如果映射<span data-katex="\sigma:C^\infty_{x_0}\rightarrow R"></span>满足切向量的条件，

则必有唯一的一个向量<span data-katex="v\in R^m"></span>，使得相应的方向导数算子<span data-katex="D_v=\sigma"></span>。

<br/>

所以，向量<span data-katex="v"></span>与方向导数算子<span data-katex="D_v"></span>是一一对应的，

这就是说，可以把<span data-katex="v"></span>和<span data-katex="D_v"></span>等同起来。

<br/>

设<span data-katex="M"></span>是一个<span data-katex="m"></span>维光滑流形，

<span data-katex="\gamma:(-\varepsilon,\varepsilon)\rightarrow M"></span>是<span data-katex="M"></span>上的一条光滑曲线，记<span data-katex="p=\gamma(0)"></span>，

利用<span data-katex="\gamma"></span>可以定义一个映射<span data-katex="v:C^\infty_p\rightarrow R"></span>如下，

对于任意的<span data-katex="f\in C^\infty_p"></span>，令，

<span data-katex="v(f)=\frac{d}{dt}\Big\vert_{t=0}f\circ\gamma(t)=\frac{df(\gamma(t))}{dt}\Big\vert_{t=0}"></span>。

<br/>

容易验证，映射<span data-katex="v:C^\infty_p\rightarrow R"></span>满足切向量的条件，

因此，<span data-katex="v"></span>是光滑流形<span data-katex="M"></span>在<span data-katex="p"></span>点的一个切向量，

称为曲线<span data-katex="\gamma"></span>在<span data-katex="t=0"></span>点处的**切向量**，记为<span data-katex="\gamma'(0)"></span>，

这样上式成为，<span data-katex="\gamma'(0)(f)=\frac{df(\gamma(t))}{dt}\Big\vert_{t=0}"></span>。

### 切空间

把光滑流形<span data-katex="M"></span>在点<span data-katex="p"></span>处的切向量构成的集合，记为<span data-katex="T_p M"></span>，

在<span data-katex="T_p M"></span>中，引入加法和数乘运算如下，

对于任意的<span data-katex="u,v\in T_p M"></span>，<span data-katex="\lambda\in R"></span>，以及<span data-katex="f\in C^\infty_p"></span>，定义，

<span data-katex="(u+v)(f)=u(f)+v(f)"></span>，

<span data-katex="(\lambda u)(f)=\lambda\cdot u(f)"></span>。

<br/>

显然，这样定义的<span data-katex="u+v"></span>和<span data-katex="\lambda u"></span>仍然是<span data-katex="M"></span>在<span data-katex="p"></span>点的切向量，

即<span data-katex="T_p M"></span>关于这样的加法和数乘运算是封闭的。

进一步可以验证，<span data-katex="T_p M"></span>关于上述的加法和数乘运算构成一个实向量空间。

<br/>

向量空间<span data-katex="T_p M"></span>，称为光滑流形<span data-katex="M"></span>在点<span data-katex="p"></span>的**切空间**。

<br/>

设<span data-katex="(U,\varphi;x^i)"></span>是<span data-katex="M"></span>在<span data-katex="p"></span>点的一个局部坐标系，

<span data-katex="x^i(p)=x^i_0"></span>，<span data-katex="1\leqslant i\leqslant m"></span>，

对于每一个<span data-katex="i"></span>，

设<span data-katex="\gamma_i:(-\varepsilon,\varepsilon)\rightarrow M"></span>是通过点<span data-katex="p"></span>的第<span data-katex="i"></span>条坐标曲线（称为<span data-katex="x^i"></span>曲线），

即对于任意的<span data-katex="t\in(-\varepsilon,\varepsilon)"></span>，

<span data-katex="\gamma_i(t)=\varphi^{-1}(x^1_0,\cdots,x^i_0+t,\cdots,x^m_0)"></span>。

<br/>

因此，<span data-katex="\gamma'_i(0)"></span>是<span data-katex="M"></span>在<span data-katex="p"></span>点的一个切向量，以后记为<span data-katex="\frac{\partial}{\partial x^i}\Big\vert_p"></span>。

由定义，对于任意的<span data-katex="f\in C^\infty_p"></span>，

<span data-katex="\frac{\partial}{\partial x^i}\Big\vert_p(f)=\frac{df(\gamma_i(t))}{dt}\Big\vert_{t=0}"></span>

<span data-katex="=\frac{d}{dt}_{t=0}f\circ\varphi^{-1}(x^1_0,\cdots,x^i_0+t,\cdots,x^m_0)"></span>

<span data-katex="=\frac{\partial(f\circ\varphi^{-1})}{\partial x^i}(\varphi(p))"></span>

<span data-katex="=\frac{\partial f}{\partial x^i}(p)"></span>。

<br/>

设<span data-katex="M"></span>是一个<span data-katex="m"></span>维光滑流形，<span data-katex="p\in M"></span>，

<span data-katex="(U;x^i)"></span>是包含<span data-katex="p"></span>点的任意一个容许的局部坐标系，

则<span data-katex="M"></span>在<span data-katex="p"></span>点的<span data-katex="m"></span>个切向量，<span data-katex="\frac{\partial}{\partial x^i}\Big\vert_p"></span>，<span data-katex="1\leqslant i\leqslant m"></span>，

构成了切空间<span data-katex="T_p M"></span>的一个基底，特别的，<span data-katex="dimT_p M=m"></span>。

<br/>

通常把基底<span data-katex="\left\{\frac{\partial}{\partial x^i}\Big\vert_p,\ 1\leqslant i\leqslant m\right\}"></span>，

称为在<span data-katex="p"></span>点处由局部坐标系<span data-katex="(U;x^i)"></span>给出的**自然基底**。

<br/>

可证，任何一个切向量<span data-katex="v"></span>，在自然基底<span data-katex="\left\{\frac{\partial}{\partial x^j}\Big\vert_p,\ 1\leqslant j\leqslant m\right\}"></span>下的分量<span data-katex="v^i"></span>，

恰好是该切向量，在第<span data-katex="i"></span>个局部坐标函数<span data-katex="x^i"></span>上作用得到的值，<span data-katex="v(x^i)"></span>，

<span data-katex="v=\displaystyle\sum_{i=1}^m v(x^i)\frac{\partial}{\partial x^i}\Big\vert_p"></span>。

### 余切向量

切空间<span data-katex="T_p M"></span>的对偶空间，称为光滑流形<span data-katex="M"></span>在<span data-katex="p"></span>点的**余切空间**，记为<span data-katex="T^*_p M"></span>，

其中的元素，即线性函数<span data-katex="\alpha:T_p M\rightarrow R"></span>，称为<span data-katex="M"></span>在<span data-katex="p"></span>点的**余切向量**。

<br/>

为了强调切空间与余切空间的对偶性，

常常把一个余切向量<span data-katex="\alpha\in T^*_p M"></span>在切向量<span data-katex="v\in T_p M"></span>上的作用记为<span data-katex="\alpha(v)=\left\langle v,\alpha\right\rangle"></span>。

由<span data-katex="(v,\alpha)\mapsto\left\langle v,\alpha\right\rangle"></span>确定的映射，

<span data-katex="\left\langle \cdot,\cdot\right\rangle:T_p M\times T^*_p M\rightarrow M"></span>，

称为<span data-katex="T_p M"></span>与<span data-katex="T^*_p M"></span>之间的**配合**。

<br/>

设<span data-katex="f\in C^\infty_p"></span>，定义映射<span data-katex="df:T_p M\rightarrow R"></span>如下，

对于任意的<span data-katex="v\in T_p M"></span>，

<span data-katex="\left\langle v,df\right\rangle=df(v)=v(f)\in R"></span>。

<br/>

显然<span data-katex="df"></span>是<span data-katex="T_p M"></span>上的线性函数，即<span data-katex="df\in T^*_p M"></span>，

有时，为了强调<span data-katex="df"></span>是在<span data-katex="p"></span>点的一个余切向量，也把<span data-katex="df"></span>记为<span data-katex="df|_p"></span>，或<span data-katex="df(p)"></span>。

<br/>

设<span data-katex="(U;x^i)"></span>是光滑流形<span data-katex="M"></span>的一个容许局部坐标系，<span data-katex="p\in U"></span>，

由于每个坐标函数都是<span data-katex="U"></span>上的光滑函数，因而<span data-katex="dx^i|_p\in T^*_p M"></span>，并且，

<span data-katex="\left\langle\frac{\partial}{\partial x^j}\Big\vert_p,dx^i|_p\right\rangle=\frac{\partial x^i}{\partial x^j}\Big\vert_p=\delta^i_j"></span>。

<br/>

由此可见，<span data-katex="\{dx^i|_p;\ 1\leqslant i\leqslant m\}"></span>是<span data-katex="T^*_p M"></span>中与自然基底

<span data-katex="\left\{\frac{\partial}{\partial x^i}\Big\vert_p;\ 1\leqslant i\leqslant m\right\}"></span>

对偶的基底。

<br/>

一般的，对于任意的<span data-katex="\alpha\in T^*_p M"></span>，有

<span data-katex="\alpha=\displaystyle\sum_{i=1}^m \alpha_idx^i|_p=\displaystyle\sum_{i=1}^m\left\langle\frac{\partial}{\partial x^i}\Big\vert_p,\alpha\right\rangle dx^i|_p"></span>，

特别的，对于任意的<span data-katex="f\in C^\infty_p"></span>，

<span data-katex="df|_p=\displaystyle\sum_{i=1}^m\frac{\partial f}{\partial x^i}(p)dx^i|_p"></span>。

因此，余切向量<span data-katex="df|_p=df(p)"></span>，也称为函数<span data-katex="f"></span>在<span data-katex="p"></span>点的**微分**。

### 切映射和余切映射

设<span data-katex="M,N"></span>分别是<span data-katex="m,n"></span>维光滑流形，<span data-katex="F:M\rightarrow N"></span>是光滑映射，<span data-katex="p\in M"></span>，

对于任意的<span data-katex="v\in T_p M"></span>，我们可以通过映射<span data-katex="F"></span>得到切向量<span data-katex="F_*(v)\in T_{F(p)}N"></span>，其定义为，

<span data-katex="F_*(v)(f)=v(f\circ F)"></span>，<span data-katex="\forall f\in C^\infty_{F(p)}"></span>。

<br/>

这样，就得到一个映射<span data-katex="F_*:T_p M\rightarrow T_{F(p)}N"></span>，

易知，<span data-katex="F_*"></span>是线性映射，称为光滑映射<span data-katex="F"></span>在<span data-katex="p"></span>点的**切映射**，或微分，

它的对偶映射<span data-katex="F^*:T^*_{F(p)}N\rightarrow T^*_p M"></span>，

称为光滑映射<span data-katex="F"></span>在<span data-katex="p"></span>点的**余切映射**，或拉回映射。

<br/>

由对偶映射的定义，余切映射<span data-katex="F^*:T^*_{F(p)}N\rightarrow T^*_p M"></span>也是线性映射，

并且对于任意的<span data-katex="\omega\in T^*_{F(p)}N"></span>，<span data-katex="F^*\omega"></span>由下式定义，

<span data-katex="(F^*\omega)(v)=\omega(F_*(v))"></span>，<span data-katex="\forall v\in T_p M"></span>。

<br/>

为了强调对于点<span data-katex="p"></span>的依赖性，

常常用<span data-katex="F_{*p}"></span>和<span data-katex="F^*_p"></span>来表示映射<span data-katex="F"></span>在<span data-katex="p"></span>点的切映射和余切映射。

### 切向量场

设<span data-katex="M"></span>是一个<span data-katex="m"></span>维光滑流形，<span data-katex="M"></span>在每一点<span data-katex="p"></span>处都有切空间<span data-katex="T_p M"></span>，记

<span data-katex="TM=\displaystyle\bigcup_{p\in M}T_p M"></span>。

<br/>

<span data-katex="M"></span>上的一个**切向量场**<span data-katex="X"></span>是指，在<span data-katex="M"></span>的每一个点<span data-katex="p"></span>处指定了<span data-katex="M"></span>在该点的一个切向量<span data-katex="X(p)"></span>，

换句话说，<span data-katex="M"></span>上的切向量场是一个映射<span data-katex="X:M\rightarrow TM"></span>，

使得对于任意一点<span data-katex="p\in M"></span>，<span data-katex="X(p)\in T_p M"></span>。

<br/>

比如，在<span data-katex="M"></span>的任意一个容许局部坐标系<span data-katex="(U;x^i)"></span>下，

<span data-katex="\frac{\partial}{\partial x^i}"></span>是<span data-katex="U"></span>上的切向量场，

特别的，这样一组切向量场在<span data-katex="U"></span>中每一点<span data-katex="p"></span>处的值，构成该点的切空间<span data-katex="T_p M"></span>的一个基底。

通常称这样一组切向量场为<span data-katex="U"></span>上的一个**标架场**，

为了叙述的方便，以后把<span data-katex="\left\{\frac{\partial}{\partial x^i}\Big\vert_p\right\}"></span>称为，

<span data-katex="M"></span>在局部坐标系<span data-katex="(U;x^i)"></span>下的**自然标架场**。

<br/>

设<span data-katex="X:M\rightarrow TM"></span>是<span data-katex="m"></span>维光滑流形<span data-katex="M"></span>上的切向量场，

如果对于每一点<span data-katex="p\in M"></span>，存在<span data-katex="p"></span>点的容许局部坐标系<span data-katex="(U;x^i)"></span>，

使得<span data-katex="X"></span>限制在<span data-katex="U"></span>上的局部坐标表达式，

<span data-katex="X|_U=\displaystyle\sum_{i=1}^m X^i\frac{\partial}{\partial x^i}"></span>

中的分量<span data-katex="X^i"></span>都是<span data-katex="U"></span>上的光滑函数（<span data-katex="1\leqslant i\leqslant m"></span>），

则称<span data-katex="X"></span>是<span data-katex="M"></span>上的**光滑切向量场**。

<br/>

由定义和局部坐标系的<span data-katex="C^\infty"></span>相容性可得，

<span data-katex="M"></span>上的一个切向量场<span data-katex="X"></span>为光滑切向量场

<span data-katex="\Leftrightarrow"></span><span data-katex="X"></span>关于每一个自然标架场的分量是光滑函数

<span data-katex="\Leftrightarrow"></span><span data-katex="X"></span>在每一个容许坐标系<span data-katex="(U;x^i)"></span>上的限制<span data-katex="X|_U"></span>是<span data-katex="U"></span>上的光滑切向量场。

<br/>

<span data-katex="M"></span>上光滑切向量场的集合，记为<span data-katex="\mathscr{X}(M)"></span>，

显然，<span data-katex="\mathscr{X}(M)"></span>关于加法和数乘是封闭的，因而它是一个向量空间。

### 张量场

<span data-katex="M"></span>在点<span data-katex="p"></span>处的一个<span data-katex="(r,s)"></span>型张量<span data-katex="\tau"></span>，是指一个<span data-katex="r+s"></span>重线性映射，

<span data-katex="r:T^*_p M\times\cdots\times T^*_p M\times T_p M\times\cdots\times T_p M\rightarrow R"></span>，

其中，<span data-katex="T^*_p M"></span>有<span data-katex="r"></span>个，称为**反变阶数**，<span data-katex="T_p M"></span>有<span data-katex="s"></span>个，称为**协变阶数**。

<br/>

若以<span data-katex="T^r_s(p)"></span>表示<span data-katex="M"></span>在<span data-katex="p"></span>点的所有<span data-katex="(r,s)"></span>型张量构成的集合，则有，

<span data-katex="T^r_s(p)=\mathscr{L}(T^*_p M,\cdots,T^*_p M,T_p M,\cdots,T_p M;R)"></span>。

<br/>

不难看出，<span data-katex="T^r_s(p)"></span>是一个<span data-katex="m^{r+s}"></span>维向量空间，

并且，在<span data-katex="p"></span>点的容许局部坐标系<span data-katex="(U;x^i)"></span>下，<span data-katex="T^r_s(p)"></span>有一个自然基底，即，

<span data-katex="\frac{\partial}{\partial x^{i_1}}\Big\vert_p\otimes\cdots\otimes\frac{\partial}{\partial x^{i_r}}\Big\vert_p\otimes dx^{j_1}|_p\otimes\cdots\otimes dx^{j_s}|_p"></span>，

<span data-katex="1\leqslant i_1,\cdots,i_r,j_1,\cdots,j_s\leqslant m"></span>。

<br/>

由此可见，<span data-katex="T^r_s(p)=T_p M\otimes\cdots\otimes T_p M\otimes T^*_p M\otimes\cdots\otimes T^*_p M"></span>，

其中<span data-katex="T_p M"></span>有<span data-katex="r"></span>个，<span data-katex="T^*_p M"></span>有<span data-katex="s"></span>个。

<br/>

令，<span data-katex="T^r_s(M)=\displaystyle\bigcup_{p\in M}T^r_s(p)"></span>，

光滑流形<span data-katex="M"></span>上的一个<span data-katex="(r,s)"></span>型**张量场**<span data-katex="\tau"></span>，

是指从<span data-katex="M"></span>到<span data-katex="T^r_s(M)"></span>的一个映射<span data-katex="\tau:M\rightarrow T^r_s(M)"></span>，

使得对于任意的<span data-katex="p\in M"></span>，都有<span data-katex="\tau(p)\in T^r_s(p)"></span>。

<br/>

<span data-katex="M"></span>上的<span data-katex="(r,0)"></span>型和<span data-katex="(0,s)"></span>型张量场，分别称为<span data-katex="r"></span>阶反变张量场和<span data-katex="s"></span>阶协变张量场。

<br/>

光滑流形<span data-katex="M"></span>上的一个<span data-katex="(r,s)"></span>型张量场<span data-katex="\tau:M\rightarrow T^r_s(M)"></span>称为**光滑的**，

如果对于任意的<span data-katex="p\in M"></span>，存在<span data-katex="p"></span>点的容许局部坐标系<span data-katex="(U;x^i)"></span>，

使得<span data-katex="\tau"></span>在<span data-katex="U"></span>上的限制具有如下局部表达式，

<span data-katex="\tau|_U=\tau^{i_1\cdots i_r}_{j_1\cdots j_s}\frac{\partial}{\partial x^{i_1}}\otimes\cdots\otimes\frac{\partial}{\partial x^{i_r}}\otimes dx^{j_1}\otimes\cdots\otimes dx^{j_s}"></span>，

其中，<span data-katex="\tau^{i_1\cdots i_r}_{j_1\cdots j_s}"></span>是<span data-katex="U"></span>上的光滑函数。

<br/>

<span data-katex="M"></span>上光滑的<span data-katex="(r,s)"></span>型张量场构成的集合记作<span data-katex="\mathscr{J}^r_s(M)"></span>，特别的，

<span data-katex="\mathscr{J}^1_0(M)=\mathscr{X}(M)"></span>，<span data-katex="\mathscr{J}^0_0(M)=C^\infty(M)"></span>。

<br/>

在集合<span data-katex="\mathscr{J}^r_s(M)"></span>中有自然的加法，数乘等运算，

任意两个光滑张量场能够逐点作张量积运算，另外，张量场还可以与光滑函数相乘，

使得<span data-katex="\mathscr{J}^r_s(M)"></span>成为一个<span data-katex="C^\infty(M)"></span>-模。

<br/>

光滑的一阶协变张量场（即余切向量场），又称为**1次微分式**。

把光滑流形<span data-katex="M"></span>上的1次微分式的集合记为<span data-katex="A^1(M)"></span>，即<span data-katex="A^1(M)=\mathscr{J}^0_1(M)"></span>。

### 外微分

光滑流形<span data-katex="M"></span>上的一个光滑的<span data-katex="r"></span>阶协变张量场<span data-katex="\varphi"></span>是**反对称的**，

如果它作为映射，<span data-katex="\varphi:\mathscr{X}(M)\times\cdots\times\mathscr{X}(M)\rightarrow C^\infty(M)"></span>，

关于所有的自变量是反对称的，即交换任意两个自变量的位置，所得的值反号。

或等价的说，在任意的局部坐标系下，<span data-katex="\varphi"></span>的分量关于下指标是反对称的。

<br/>

光滑流形<span data-katex="M"></span>上的一个光滑的<span data-katex="r"></span>阶反对称协变张量场<span data-katex="\varphi"></span>，

称为<span data-katex="M"></span>上的一个<span data-katex="r"></span>次**外微分式**。

同时，还约定，<span data-katex="M"></span>上的1次外微分式，就是<span data-katex="M"></span>上的1次微分式，即光滑的一阶协变张量场。

<span data-katex="M"></span>上的0次外微分式，指的是<span data-katex="M"></span>上的光滑函数。

<br/>

<span data-katex="M"></span>上的<span data-katex="r"></span>次外微分式的集合记作<span data-katex="A^r(M)"></span>，特别的，

<span data-katex="A^1(M)=\mathscr{J}^0_1(M)"></span>，<span data-katex="A^0(M)=C^\infty(M)"></span>。

<br/>

由定义可知，若<span data-katex="\varphi\in A^r(M)"></span>，则在每一点<span data-katex="p\in M"></span>，

<span data-katex="\varphi(p)"></span>是<span data-katex="T_p M"></span>上的一个<span data-katex="r"></span>次外形式，

即，<span data-katex="\varphi(p):T_p M\times\cdots\times T_p M\rightarrow R"></span>，

是一个反对称的<span data-katex="r"></span>重线性函数。

<br/>

此外，每一个<span data-katex="r"></span>次外微分式<span data-katex="\varphi"></span>，可以等同于反对称的<span data-katex="r"></span>重<span data-katex="C^\infty(M)"></span>-线性映射，

<span data-katex="\varphi:\mathscr{X}(M)\times\cdots\times\mathscr{X}(M)\rightarrow C^\infty(M)"></span>。

<br/>

通过逐点定义的方式，可以引入外微分式的加法，数乘和外积运算，

比如，外积的定义如下，<span data-katex="\forall \varphi\in A^r(M),\psi\in A^s(M)"></span>，

<span data-katex="(\varphi\wedge\psi)(p)=\varphi(p)\wedge\psi(p)"></span>

<span data-katex="=\frac{(r+s)!}{r!s!}A_{r+s}(\varphi(p)\otimes\psi(p))"></span>

<span data-katex="=\frac{(r+s)!}{r!s!}A_{r+s}(\varphi\otimes\psi)(p)"></span>，<span data-katex="\forall p\in M"></span>。

<br/>

即有，<span data-katex="\varphi\wedge\psi=\frac{(r+s)!}{r!s!}A_{r+s}(\varphi\otimes\psi)"></span>，

这里的<span data-katex="A_{r+s}"></span>是反对称化算子。

<br/>

进而，若令<span data-katex="A(M)=\displaystyle\bigoplus_{r=0}^m A^r(M)"></span>，<span data-katex="m=dim\ M"></span>，

则在<span data-katex="A(M)"></span>上可以引入外微分运算。

<br/>

设<span data-katex="M"></span>是<span data-katex="m"></span>维光滑流形，则存在唯一的一个映射，<span data-katex="d:A(M)\rightarrow A(M)"></span>，

使得对于任意的非负整数<span data-katex="r"></span>，有<span data-katex="d(A^r(M))\subseteq A^{r+1}(M)"></span>，

并且满足以下条件，

（1）<span data-katex="d"></span>是线性的，即对于任意的<span data-katex="\varphi,\psi\in A(M)"></span>，<span data-katex="\lambda\in R"></span>，有，

<span data-katex="d(\varphi+\lambda\cdot\psi)=d\varphi+\lambda d\psi"></span>，

（2）<span data-katex="\forall\varphi\in A^r(M),\psi\in A(M)"></span>，有，

<span data-katex="d(\varphi\wedge\psi)=d\varphi\wedge\psi+(-1)^r\varphi\wedge d\psi"></span>，

（3）<span data-katex="\forall f\in A^0(M)"></span>，<span data-katex="df"></span>是<span data-katex="f"></span>的微分，

（4）<span data-katex="d^2=d\circ d=0"></span>。

这样的映射<span data-katex="d"></span>，称为**外微分（算子）**。

<br/>

外微分算子<span data-katex="d"></span>满足<span data-katex="d\circ d=0"></span>，

这意味着<span data-katex="d:A^r(M)\rightarrow A^{r+1}(M)"></span>可以看做拓扑学忠的上边缘算子，

在这里，<span data-katex="A^r(M)"></span>被看做加法群。

<br/>

令<span data-katex="Z^r(M)=\{\alpha\in A^r(M):d\alpha=0\}"></span>，

<span data-katex="B^r(M)=d(A^{r-1}(M))=\{\alpha\in A^r(M):\exists\beta\in A^{r-1}(M),\alpha=d\beta\}"></span>，

<span data-katex="Z^r(M)"></span>中的元素称为<span data-katex="M"></span>上的<span data-katex="r"></span>次**闭微分式**，

<span data-katex="B^r(M)"></span>中的元素称为<span data-katex="M"></span>上的**恰当微分式**，

这样，性质<span data-katex="d\circ d=0"></span>，表明<span data-katex="B^r(M)"></span>是<span data-katex="Z^r(M)"></span>的子群。

<br/>

商群<span data-katex="H^r(M)=Z^r(M)/B^r(M)"></span>称为光滑流形<span data-katex="M"></span>上的第<span data-katex="r"></span>个**de Rham上同调群**。

<br/>

应该注意的是，de Rham上同调群<span data-katex="H^r(M)"></span>是光滑流形的光滑结构的产物，

但是，著名的de Rham定理说，当<span data-katex="M"></span>是紧致光滑流形时，de Rham上同调群<span data-katex="H^r(M)"></span>与<span data-katex="M"></span>的第<span data-katex="r"></span>个实系数上同调群是同构的，

由此可见，de Rham上同调群<span data-katex="H^r(M)"></span>是流形<span data-katex="M"></span>的拓扑不变量。

### 向量丛

设<span data-katex="E,M"></span>是两个光滑流形，<span data-katex="\pi:E\rightarrow M"></span>是一个光滑的满映射，

<span data-katex="V=R^q"></span>是<span data-katex="q"></span>维向量空间，如果在<span data-katex="M"></span>上存在一个开覆盖<span data-katex="\{U_\alpha;\alpha\in I\}"></span>，

以及一组映射<span data-katex="\{\psi_\alpha;\alpha\in I\}"></span>，它们满足下列条件，

（1）<span data-katex="\forall\alpha\in I"></span>，映射<span data-katex="\psi_\alpha"></span>是从<span data-katex="U_\alpha\times R^q"></span>到<span data-katex="\pi^{-1}(U)"></span>的光滑同胚，

并且对于任意的<span data-katex="p\in U_\alpha"></span>，<span data-katex="y\in R^q"></span>有，

<span data-katex="\pi\circ\psi_\alpha(p,y)=p"></span>。

（2）对于任意固定的<span data-katex="p\in U_\alpha"></span>，令，

<span data-katex="\psi_{\alpha,p}(y)=\psi_\alpha(p,y)"></span>，<span data-katex="\forall y\in R^q"></span>，

则映射<span data-katex="\psi_{\alpha,p}:R^q\rightarrow\pi^{-1}(p)"></span>是同胚，

而当<span data-katex="p\in U_\alpha\cap U_\beta\neq\varnothing"></span>时，

映射<span data-katex="g_{\beta\alpha}(p)=\pi^{-1}_{\beta,p}\circ\psi_{\alpha,p}:R^q\rightarrow R^p"></span>，

是线性同构，即<span data-katex="g_{\beta\alpha}(p)\in GL(q)"></span>。

（3）当<span data-katex="U_\alpha\cap U_\beta\neq\varnothing"></span>时，

映射<span data-katex="g_{\beta\alpha}:U_\alpha\cap U_\beta\rightarrow GL(q)"></span>是光滑的。

<br/>

则称<span data-katex="(E,M,\pi)"></span>为光滑流形<span data-katex="M"></span>上的秩为<span data-katex="q"></span>的**向量丛**，

其中，<span data-katex="E"></span>称为**丛空间**，<span data-katex="M"></span>称为**底流形**，

映射<span data-katex="\pi:E\rightarrow M"></span>称为**丛投影**。

<br/>

为了方便，以后也把向量丛<span data-katex="(E,M,\pi)"></span>，记为<span data-katex="\pi:E\rightarrow M"></span>，或<span data-katex="E"></span>。

<br/>

易证，对于任意的<span data-katex="p\in M"></span>，在<span data-katex="\pi^{-1}(p)"></span>上具有自然的线性结构，

使得映射<span data-katex="\psi_{\alpha,p}:R^q\rightarrow\pi^{-1}(p)"></span>为线性同构，

以后把<span data-katex="\pi^{-1}(p)"></span>称为向量丛<span data-katex="E"></span>在点<span data-katex="p\in M"></span>的**纤维**，也记为<span data-katex="E_p"></span>。

<br/>

由此可见，向量丛<span data-katex="\pi:E\rightarrow M"></span>，

是一簇“栽种在”光滑流形<span data-katex="M"></span>上的<span data-katex="q"></span>维向量空间。

映射<span data-katex="\psi_\alpha:U_\alpha\times R^q\rightarrow\pi^{-1}(U_\alpha)"></span>，

称为向量丛<span data-katex="E"></span>的**局部平凡化**。

<br/>

<span data-katex="\pi:TM\rightarrow M"></span>是<span data-katex="M"></span>上秩为<span data-katex="m"></span>的向量丛，

称为光滑流形<span data-katex="M"></span>上的**切向量丛**，简称为<span data-katex="M"></span>的**切丛**。

<br/>

设<span data-katex="\pi:E\rightarrow M"></span>是光滑流形<span data-katex="M"></span>上的向量丛，<span data-katex="U\subseteq M"></span>为开集，

若有光滑映射<span data-katex="s:U\rightarrow E"></span>，使得，

<span data-katex="\pi\circ s=id:U\rightarrow U"></span>，

则称<span data-katex="s"></span>为向量丛<span data-katex="(E,M,\pi)"></span>的定义在<span data-katex="U"></span>上的一个**光滑截面**，

特别的，当<span data-katex="U=M"></span>时，则称<span data-katex="s"></span>为向量丛<span data-katex="E"></span>的一个光滑截面。

<br/>

向量丛<span data-katex="\pi:E\rightarrow M"></span>的光滑截面的集合记为<span data-katex="\Gamma(E)"></span>，

不难验证，集合<span data-katex="\Gamma(E)"></span>是一个<span data-katex="C^\infty(M)"></span>-模，

因而也是<span data-katex="R"></span>上的向量空间，

一般而言，<span data-katex="\Gamma(E)"></span>作为实向量空间是无限维的。

<br/>

因此，流形<span data-katex="M"></span>上的光滑切向量场，是切丛<span data-katex="TM"></span>的光滑截面，

反之亦然，因此<span data-katex="\mathscr{X}(M)=\Gamma(TM)"></span>。

<br/>

设<span data-katex="\pi:E\rightarrow M"></span>是光滑流形<span data-katex="M"></span>上秩为<span data-katex="q"></span>的向量丛，<span data-katex="U\subseteq M"></span>，

如果存在<span data-katex="q"></span>个局部光滑截面，<span data-katex="s_a\in\Gamma(U)"></span>，<span data-katex="1\leqslant a\leqslant q"></span>，

使得<span data-katex="\{s_a\}"></span>是处处线性无关的，即对于任意的<span data-katex="p\in U"></span>，

<span data-katex="\{s_a(p)\}"></span>构成向量空间<span data-katex="\pi^{-1}(p)"></span>的一个基底，

则称<span data-katex="\{s_a\}"></span>是向量丛<span data-katex="E"></span>的（定义在<span data-katex="U"></span>上的）一个**局部标架场**。

<br/>

特别的，当<span data-katex="U=M"></span>时，称<span data-katex="\{s_a\}"></span>是大范围的定义在<span data-katex="M"></span>上的标架场。

一般来说，向量丛的定义在整个底流形上的标架场未必是存在的，

而局部标架场总是存在的。

### 对偶丛

设<span data-katex="\pi:E\rightarrow M"></span>是光滑流形<span data-katex="M"></span>上的秩为<span data-katex="q"></span>的向量丛，

对于任意的<span data-katex="p\in M"></span>，用<span data-katex="E^*_p=(E_p)^*"></span>表示<span data-katex="q"></span>维实向量空间<span data-katex="E_p"></span>的对偶空间，

并记<span data-katex="E^*=\displaystyle\bigcup_{p\in M}E^*_p"></span>，

再定义映射<span data-katex="\tilde{\pi}:E^*\rightarrow M"></span>，使得，

<span data-katex="\tilde{\pi}(\omega)=p"></span>，<span data-katex="\forall\omega\in E^*_p"></span>，于是，

<span data-katex="\tilde{\pi}^{-1}(p)=E^*_p"></span>。

<br/>

假定<span data-katex="\psi_\alpha:U_\alpha\times R^q\rightarrow\pi^{-1}(U_\alpha)"></span>，<span data-katex="\alpha\in I"></span>，

是向量丛<span data-katex="(E,M,\pi)"></span>的局部平凡化，且<span data-katex="\{U_\alpha;\alpha\in I\}"></span>是<span data-katex="M"></span>的一个开覆盖，

取定<span data-katex="R^q"></span>的一个标准基底<span data-katex="\delta=\{\delta_a;a=1,\cdots,q\}"></span>，它的对偶基底记作<span data-katex="\delta^*=\{\delta^a\}"></span>，

对于任意的<span data-katex="\alpha\in I"></span>，设<span data-katex="E"></span>在<span data-katex="U_\alpha"></span>上的局部截面<span data-katex="e_{\alpha,a}"></span>由

<span data-katex="e_{\alpha,a}=\psi_\alpha(p,\delta^a)"></span>确定，

<span data-katex="\forall p\in U_\alpha"></span>，用<span data-katex="\{e^a_\alpha(p)\}"></span>表示<span data-katex="\{e_{\alpha,a}(p)\}"></span>在纤维<span data-katex="\tilde{\pi}^{-1}(p)"></span>中的对偶基底。

于是，可以定义映射，

<span data-katex="\tilde{\psi}_\alpha:U_\alpha\times R^q\rightarrow\tilde{\pi}^{-1}(U_\alpha)"></span>，

使得，

<span data-katex="\tilde{\psi}_\alpha(p,y)\displaystyle\sum_a y_ae^a_\alpha(p)"></span>，<span data-katex="\forall p\in U_\alpha"></span>，

<span data-katex="y=y_a\delta^a\in(R^q)^*=R^q"></span>。

<br/>

类似于切丛的构造方法，在<span data-katex="E^*"></span>中可以引入微分结构，使得<span data-katex="E^*=(E^*,M,\tilde{\pi})"></span>成为秩是<span data-katex="q"></span>的向量丛，

而<span data-katex="\{\tilde{\psi}_\alpha\}"></span>就是它的局部平凡化。

新构造出的向量丛<span data-katex="E^*"></span>称为已知向量丛<span data-katex="E"></span>的**对偶丛**。

<br/>

特别的，光滑流形<span data-katex="M"></span>的切丛<span data-katex="TM"></span>的对偶丛<span data-katex="(TM)^*"></span>，

就是<span data-katex="M"></span>上的所有余切向量构成的向量丛，

称为<span data-katex="M"></span>的**余切向量丛**，或**余切丛**，并记为<span data-katex="T^*M"></span>，

<span data-katex="T^*M"></span>的（局部）标架场，称为**（局部）余切标架场**。

### 向量丛的直和与张量积

设<span data-katex="\pi:E\rightarrow M"></span>和<span data-katex="\tilde{\pi}:\tilde{E}\rightarrow M"></span>是光滑流形<span data-katex="M"></span>上的两个向量丛，它们的秩分别是<span data-katex="q"></span>和<span data-katex="\tilde{q}"></span>，

则由<span data-katex="E"></span>和<span data-katex="\tilde{E}"></span>，可以构造出**向量丛的直和**<span data-katex="E\oplus\tilde{E}"></span>，

和**张量积**<span data-katex="E\otimes\tilde{E}"></span>，具体做法如下。

<br/>

<span data-katex="\forall p\in M"></span>，向量丛<span data-katex="E"></span>和<span data-katex="\tilde{E}"></span>在<span data-katex="p"></span>点的纤维，

分别记为<span data-katex="E_p"></span>和<span data-katex="\tilde{E}_p"></span>，

它们是两个实向量空间，并且<span data-katex="dim\ E_p=q"></span>，<span data-katex="dim\ \tilde{E}_p=\tilde{q}"></span>，令，

<span data-katex="E\oplus\tilde{E}=\displaystyle\bigcup_{p\in M}E_p\oplus\tilde{E}_p"></span>，

<span data-katex="E\otimes\tilde{E}=\displaystyle\bigcup_{p\in M}E_p\otimes\tilde{E}_p"></span>。

<br/>

可以自然的引入投影映射，

<span data-katex="\pi_1:E\oplus\tilde{E}\rightarrow M"></span>，

和<span data-katex="\pi_2:E\otimes\tilde{E}\rightarrow M"></span>，

以及相应的微分构造，使得，

<span data-katex="(E\oplus\tilde{E},M,\pi_1)"></span>，

和<span data-katex="(E\otimes\tilde{E},M,\pi_2)"></span>

分别成为秩是<span data-katex="q+\tilde{q}"></span>和<span data-katex="q\tilde{q}"></span>的向量丛，

称为向量丛<span data-katex="E"></span>和<span data-katex="\tilde{E}"></span>的直和及张量积。

<br/>

特别的，光滑流形<span data-katex="M"></span>的<span data-katex="r"></span>个切丛<span data-katex="TM"></span>，和<span data-katex="s"></span>个余切丛<span data-katex="T^*M"></span>的张量积，

<span data-katex="T^r_s(M)=TM\otimes\cdots\otimes TM\otimes T^*M\otimes\cdots\otimes T^*M"></span>，

是由<span data-katex="M"></span>上在各点处的<span data-katex="(r,s)"></span>型张量构成的集合，

它是秩为<span data-katex="m^{r+s}"></span>的向量丛，即有，

<span data-katex="T^r_s(M)=\displaystyle\bigcup_{p\in M}T^r_s(p)"></span>，

其中，<span data-katex="T^r_s(p)=T_p M\otimes\cdots\otimes T_p M\otimes T^*_p M\otimes\cdots\otimes T^*_p M"></span>，

是流形<span data-katex="M"></span>在一点<span data-katex="p"></span>处的<span data-katex="(r,s)"></span>型张量空间。

<br/>

向量丛<span data-katex="T^r_s(M)"></span>称为光滑流形<span data-katex="M"></span>上的<span data-katex="(r,s)"></span>型**张量丛**，

它的光滑截面就是<span data-katex="M"></span>上的光滑张量场。

<br/>

类似的，对于任意的<span data-katex="p\in M"></span>，若以<span data-katex="\bigwedge^r T^*_p M"></span>表示<span data-katex="M"></span>在点<span data-katex="p"></span>的<span data-katex="r"></span>次外形式空间，

并设<span data-katex="\bigwedge^r T^* M=\displaystyle\bigcup_{p\in M}\bigwedge^r T^*_p M"></span>，

则<span data-katex="\bigwedge^r T^* M"></span>也是一个向量丛，称为<span data-katex="M"></span>上的<span data-katex="r"></span>次**外形式丛**。

<br/>

外形式丛的光滑截面是<span data-katex="M"></span>上的外微分式，

于是有<span data-katex="\Gamma(\bigwedge^r T^* M)=A^r(M)"></span>。

### 黎曼向量丛

设<span data-katex="\pi:E\rightarrow M"></span>是光滑流形<span data-katex="M"></span>上的一个向量丛，

如果对于每一点<span data-katex="p\in M"></span>，在纤维<span data-katex="\pi^{-1}"></span>上指定了一个欧氏内积<span data-katex="\left\langle\cdot,\cdot\right\rangle_p"></span>，

并且<span data-katex="\left\langle\cdot,\cdot\right\rangle_p"></span>光滑的依赖于点<span data-katex="p"></span>，

则称<span data-katex="\left\langle\cdot,\cdot\right\rangle_p"></span>是向量丛<span data-katex="(E,M,\pi)"></span>上的一个**黎曼结构**，

指定了一个黎曼结构的向量丛，称为**黎曼向量丛**。

### 内积

在<span data-katex="n"></span>维向量空间<span data-katex="V"></span>上，**内积**是指满足下列条件的双线性形式，

<span data-katex="\left\langle\cdot,\cdot\right\rangle:V\times V\rightarrow R"></span>，

（1）对称性：<span data-katex="\left\langle u,v\right\rangle=\left\langle v,u\right\rangle"></span>，<span data-katex="\forall u,v\in V"></span>，

（2）正定性：<span data-katex="\forall u\in V"></span>，<span data-katex="\left\langle u,u\right\rangle\geqslant 0"></span>，其中等号成立当且仅当<span data-katex="u=0"></span>。

<br/>

换句话说，<span data-katex="V"></span>上的一个内积，就是<span data-katex="V"></span>上的一个对称，正定的二阶协变张量，

指定了一个内积的向量空间<span data-katex="V"></span>，称为**欧氏向量空间**，

在这样的空间中，能够定义向量的长度以及向量之间的夹角。

<br/>

设<span data-katex="M"></span>是一个<span data-katex="m"></span>维光滑流形，<span data-katex="g"></span>是<span data-katex="M"></span>上的一个光滑的二阶协变张量场，

如果<span data-katex="g"></span>是对称，正定的，即对于每一点<span data-katex="p\in M"></span>，<span data-katex="g(p)"></span>是切空间<span data-katex="T_p M"></span>上的一个对称，正定的二阶协变张量，

则称<span data-katex="g"></span>是<span data-katex="M"></span>上的一个**黎曼度量**，

指定了一个黎曼度量<span data-katex="g"></span>的光滑流形<span data-katex="M"></span>，称为**黎曼流形**，

记为<span data-katex="(M,g)"></span>，或简记为<span data-katex="M"></span>。

<br/>

根据定义，<span data-katex="g(p)"></span>是<span data-katex="T_p M"></span>上的内积（<span data-katex="\forall p\in M"></span>），

所以光滑流形<span data-katex="M"></span>上的黎曼度量，就是以光滑的依赖于点<span data-katex="p"></span>的方式，

在每一点<span data-katex="p\in M"></span>的切空间<span data-katex="T_p M"></span>上，指定一个内积，使之成为欧氏向量空间。

特别的，每一个欧氏向量空间，都是黎曼流形。

<br/>

设<span data-katex="(U;x^i)"></span>是<span data-katex="M"></span>的一个容许的局部坐标系，则黎曼度量<span data-katex="g"></span>有局部坐标表达式，

<span data-katex="g|_U=g_{ij}dx^i\otimes dx^j"></span>，

其中<span data-katex="g_{ij}=g\left(\frac{\partial}{\partial x^i},\frac{\partial}{\partial x^j}\right)\in C^\infty(U)"></span>，<span data-katex="g_{ij}=g_{ji}"></span>，

d定义，在每一点<span data-katex="p\in U"></span>，<span data-katex="(g_{ij}(p))"></span>都是正定矩阵，

如果引入对称化的乘积（对称张量积），

<span data-katex="dx^idx^j=\frac{1}{2}(dx^i\otimes dx^j+dx^j\otimes dx^i)"></span>，

则<span data-katex="g|_U"></span>可以写成二次微分形式，<span data-katex="g|_U=g_{ij}dx^idx^j"></span>。

### 弧长

设<span data-katex="\gamma:[a,b]\rightarrow M"></span>是<span data-katex="M"></span>中一条光滑曲线，令，

<span data-katex="L(\gamma)=\int_{a}^{b}|\gamma'(t)|dt=\int_{a}^{b}\sqrt{\left\langle\gamma'(t),\gamma'(t)\right\rangle}dt"></span>，

并称之为曲线<span data-katex="\gamma"></span>的**弧长**（长度）。

<br/>

如果<span data-katex="\gamma([a,b])"></span>落在区域<span data-katex="U"></span>内，则它可用局部坐标表示为，

<span data-katex="x^i(t)=x^i(\gamma(t))"></span>，<span data-katex="1\leqslant i\leqslant m"></span>，

因而，<span data-katex="L(\gamma)=\int_{a}^{b}\sqrt{g_{ij}(\gamma(t))\frac{dx^i}{dt}\frac{dx^j}{dt}}dt"></span>，

曲线的弧长与曲线的正则参数变换无关，也与光滑流形的局部坐标系的取法无关。

### 协变微分

设<span data-katex="(M,g)"></span>是一个<span data-katex="m"></span>维黎曼流形，<span data-katex="X\in\mathscr{X}(M)"></span>，

如果<span data-katex="(U;x^i)"></span>是<span data-katex="M"></span>的一个容许坐标系，并且<span data-katex="X|_U=X^i\frac{\partial}{\partial x^i}"></span>，则，

<span data-katex="D(X|_U)=(dX^i+X^j\Gamma^i_{jk}dx^k)\otimes\frac{\partial}{\partial x^i}"></span>

<span data-katex="=\left(\frac{\partial X^i}{\partial x^k}+X^j\Gamma^i_{jk}\right)dx^k\otimes\frac{\partial}{\partial x^i}"></span>，

是与局部坐标系的选取无关的<span data-katex="(1,1)"></span>型光滑张量场。

<br/>

于是，如果令<span data-katex="(DX)|_U=D(X|_U)"></span>，则<span data-katex="DX"></span>是大范围定义在<span data-katex="M"></span>上的<span data-katex="(1,1)"></span>型光滑张量场。

<span data-katex="DX"></span>称为光滑向量场<span data-katex="X"></span>的**协变微分**，或绝对微分，

相应的映射<span data-katex="D:\mathscr{X}(M)\rightarrow\mathscr{J}^1_1(M)"></span>，

称为黎曼流形<span data-katex="(M,g)"></span>上的**协变微分算子**，或绝对微分算子。

<br/>

设<span data-katex="X,Y\in\mathscr{X}(M)"></span>，

<span data-katex="D_YX=C^1_1(Y\otimes DX)"></span>，称为光滑切向量场<span data-katex="X"></span>沿<span data-katex="Y"></span>的**协变导数**，或协变微商，

其中<span data-katex="C^1_1"></span>是指张量场关于第一个反变指标和第一个协变指标的缩并运算。

<br/>

在局部坐标系<span data-katex="(U;x^i)"></span>下，<span data-katex="(D_YX)|_U"></span>有如下的局部坐标表达式，

<span data-katex="(D_YX)|_U=Y^k\left(\frac{\partial X^i}{\partial x^k}+X^j\Gamma^i_{jk}\right)\frac{\partial}{\partial x^i}"></span>。

<br/>

由此可见，协变微分算子<span data-katex="D"></span>又可视为映射<span data-katex="D:\mathscr{X}(M)\times\mathscr{X}(M)\rightarrow\mathscr{X}(M)"></span>，

其定义是，对于任意的<span data-katex="X,Y\in\mathscr{X}(M)"></span>，<span data-katex="D(X,Y)=D_YX\in\mathscr{X}(M)"></span>。

### 联络

设<span data-katex="M"></span>是<span data-katex="m"></span>维光滑流形，<span data-katex="M"></span>上的一个**联络**<span data-katex="D"></span>，是指满足下列条件的映射，

<span data-katex="D:\mathscr{X}(M)\times\mathscr{X}(M)\rightarrow\mathscr{X}(M)"></span>，

（1）<span data-katex="D_{Y+fZ}X=D_YX+fD_ZX"></span>，

（2）<span data-katex="D_Y(X+\lambda Z)=D_YX+\lambda D_YZ"></span>，

（3）<span data-katex="D_Y(fX)=Y(f)X+fD_YX"></span>

其中，<span data-katex="D_YX=D(X,Y)"></span>，<span data-katex="X,Y,Z\in\mathscr{X}(M)"></span>，<span data-katex="\lambda\in R"></span>，<span data-katex="f\in C^\infty(M)"></span>。

<br/>

黎曼流形<span data-katex="(M,g)"></span>上的协变微分算子<span data-katex="D"></span>是光滑流形<span data-katex="M"></span>上的一个联络，

由于在满足第二可数公理的光滑流形<span data-katex="M"></span>上黎曼度量总是存在的，

因而<span data-katex="M"></span>上的联络也是存在的。

不过，一般说来，光滑流形上的联络不是唯一的。

<br/>

指定了一个联络<span data-katex="D"></span>的光滑流形<span data-katex="(M,D)"></span>，称为一个**仿射联络空间**，

在这样的空间里，可以对光滑切向量场求协变微分和协变导数，

比如，对于任意的<span data-katex="X,Y\in\mathscr{X}(M)"></span>，

光滑切向量场<span data-katex="D_YX"></span>称为向量场<span data-katex="X"></span>沿<span data-katex="Y"></span>的**协变导数**，或协变微商。

<br/>

设<span data-katex="(M,g)"></span>是<span data-katex="m"></span>维黎曼流形，则在<span data-katex="M"></span>上存在唯一的一个与度量<span data-katex="g"></span>相容的无挠联络<span data-katex="D"></span>，

称为<span data-katex="(M,g)"></span>的**黎曼联络**，或Levi-Civita联络。

### 微分算子

设<span data-katex="X\in\mathscr{X}(M)"></span>，则<span data-katex="DX"></span>是<span data-katex="M"></span>上的<span data-katex="(1,1)"></span>型光滑张量场，

讲<span data-katex="DX"></span>进行缩并，便得到<span data-katex="M"></span>上的光滑函数，称它为光滑切向量场<span data-katex="X"></span>的**散度**，

并记作<span data-katex="div\ X"></span>，即有<span data-katex="div\ X=C^1_1(DX)"></span>。

<br/>

由<span data-katex="X\mapsto div\ X"></span>所确定的线性映射<span data-katex="div:\mathscr{X}(M)\rightarrow C^\infty(M)"></span>，

称为黎曼流形<span data-katex="(M,g)"></span>上的**散度算子**。

<br/>

设<span data-katex="f\in C^\infty(M)"></span>，则<span data-katex="df\in A^1(M)=\mathscr{J}^0_1(M)"></span>，

借助黎曼度量<span data-katex="g"></span>，<span data-katex="df"></span>对应<span data-katex="M"></span>上一个光滑切向量场，记为<span data-katex="\triangledown f"></span>，

使得对于任意的<span data-katex="X\in\mathscr{X}(M)"></span>有，<span data-katex="g(\triangledown f,X)=df(X)=X(f)"></span>，

切向量场<span data-katex="\triangledown f"></span>称为光滑函数<span data-katex="f"></span>在黎曼度量<span data-katex="g"></span>下的**梯度**，

有时也用<span data-katex="grad\ f"></span>或<span data-katex="grad_g\ f"></span>表示光滑函数<span data-katex="f"></span>的梯度。

<br/>

显然，由<span data-katex="f\mapsto \triangledown f"></span>确定的映射<span data-katex="\triangledown:C^\infty(M)\rightarrow\mathscr{X}(M)"></span>，

是作用在光滑函数上的一阶线性微分算子，称为黎曼流形<span data-katex="(M,g)"></span>上的**梯度算子**。

<br/>

把梯度算子<span data-katex="\triangledown"></span>与散度算子<span data-katex="div"></span>复合起来，便得到一个新的线性映射，

<span data-katex="\triangle=div\circ\triangledown:C^\infty(M)\rightarrow C^\infty(M)"></span>，

称为黎曼流形<span data-katex="(M,g)"></span>上的**Beltrami-Laplace算子**。

### 平行移动

设<span data-katex="(M,D)"></span>是一个<span data-katex="m"></span>维仿射联络空间，<span data-katex="\gamma:[a,b]\rightarrow M"></span>是<span data-katex="M"></span>中的一条光滑曲线，

<span data-katex="X\in\mathscr{X}(M)"></span>，如果沿曲线<span data-katex="\gamma"></span>有，

<span data-katex="D_{\gamma'(t)}X=0"></span>，<span data-katex="\forall t\in [a,b]"></span>，

则称切向量场<span data-katex="X"></span>沿曲线<span data-katex="\gamma"></span>是**平行**的，

或称<span data-katex="X"></span>是沿曲线<span data-katex="\gamma"></span>的**平行向量场**。

<br/>

设<span data-katex="\gamma:[a,b]\rightarrow M"></span>是光滑流形<span data-katex="M"></span>上的一条连续曲线，

如果存在区间<span data-katex="[a,b]"></span>的一个划分，<span data-katex="a=t_0<t_1<\cdots<t_{r-1}<t_r=b"></span>，

使得对于每一个<span data-katex="i"></span>，<span data-katex="1\leqslant i\leqslant r"></span>，

<span data-katex="\gamma|_{[t_{i-1},t_i]}:[t_{i-1},t_i]\rightarrow M"></span>是<span data-katex="M"></span>上的光滑曲线，

则称<span data-katex="\gamma"></span>是<span data-katex="M"></span>上的一条**分段光滑曲线**。

<br/>

此时<span data-katex="\gamma(t_i)"></span>，<span data-katex="(1\leqslant i\leqslant r-1)"></span>称为曲线<span data-katex="\gamma"></span>的**顶点**，

向量<span data-katex="\displaystyle\lim_{t\rightarrow t^-_i}\gamma'(t)"></span>与<span data-katex="\displaystyle\lim_{t\rightarrow t^+_i}\gamma'(t)"></span>，

之间的夹角称为曲线<span data-katex="\gamma"></span>在顶点<span data-katex="\gamma(t_i)"></span>处的**转角**。

<br/>

上述定义中的划分，称为分段光滑曲线<span data-katex="\gamma"></span>的一个**光滑划分**。

<br/>

设<span data-katex="\gamma"></span>是<span data-katex="M"></span>上的一条分段光滑曲线，<span data-katex="X"></span>是<span data-katex="M"></span>上沿曲线<span data-katex="\gamma"></span>定义的连续切向量场，

如果存在<span data-katex="\gamma"></span>的一个光滑划分，<span data-katex="a=t_0<t_1<\cdots<t_{N-1}<t_N=b"></span>，

使得<span data-katex="X"></span>在每一个小区间<span data-katex="[t_{i-1},t_i]"></span>上的限制都光滑的依赖于自变量<span data-katex="t"></span>，

则称<span data-katex="X"></span>是沿曲线<span data-katex="\gamma"></span>定义的**分段光滑（切）向量场**。

<br/>

如果对于任意的<span data-katex="i"></span>，<span data-katex="X"></span>沿光滑曲线段<span data-katex="\gamma_{[t_{i-1},t_i]}"></span>都是平行的，

则称切向量场<span data-katex="X"></span>沿<span data-katex="\gamma"></span>是平行的，

或称<span data-katex="X"></span>是沿<span data-katex="\gamma"></span>的**（分段光滑的）平行向量场**。

<br/>

设<span data-katex="(M,D)"></span>是一个<span data-katex="m"></span>维仿射联络空间，<span data-katex="p\in M"></span>，

<span data-katex="\gamma:[0,b]\rightarrow M"></span>是从点<span data-katex="p=\gamma(0)"></span>出发的一条分段光滑曲线，

则对于任意的<span data-katex="X_0\in T_p M"></span>，沿曲线<span data-katex="\gamma"></span>存在唯一的一个分段光滑平行向量场<span data-katex="X=X(t)"></span>，

满足初始条件<span data-katex="X(0)=X_0"></span>。

<br/>

因此，沿分段光滑曲线<span data-katex="\gamma"></span>的平行向量场的集合，构成一个与<span data-katex="T_pM"></span>同构的向量空间，

特别的，对于任意取定的<span data-katex="t"></span>，<span data-katex="0\leqslant t\leqslant b"></span>，

沿<span data-katex="\gamma"></span>的平行向量场给出了从<span data-katex="T_pM"></span>到<span data-katex="T_{\gamma(t)}M"></span>的线性同构，

<span data-katex="P^t_0:T_pM\rightarrow T_{\gamma(t)}M"></span>，

称为沿曲线<span data-katex="\gamma"></span>从<span data-katex="t=0"></span>到<span data-katex="t"></span>的**平行移动**。

<br/>

这样，由切向量<span data-katex="X_0\in T_pM"></span>确定的沿曲线<span data-katex="\gamma"></span>平行的向量场<span data-katex="X"></span>可以表示为，

<span data-katex="X(t)=P^t_0(X_0)"></span>，<span data-katex="0\leqslant t\leqslant b"></span>。

<br/>

总之，在光滑流形上只要指定了联络，就可以建立平行移动的概念，

反过来，切向量场的协变导数（联络）也可以借助平行移动来得到。

<br/>

设<span data-katex="(M,D)"></span>是一个<span data-katex="m"></span>维仿射联络空间，<span data-katex="\gamma:[0,b]\rightarrow M"></span>，

是<span data-katex="M"></span>中任意一条光滑曲线，则对于任意的<span data-katex="X\in\mathscr{X}(M)"></span>，

<span data-katex="D_{\gamma'(t)}X=\displaystyle\lim_{\Delta t\rightarrow 0}\frac{P^t_{t+\Delta t}(X\circ\gamma(t+\Delta t))-X\circ\gamma(t)}{\Delta t}"></span>。

### 曲率张量场

设<span data-katex="(M,D)"></span>是<span data-katex="m"></span>维仿射联络空间，对于任意的<span data-katex="X,Y\in\mathscr{X}(M)"></span>，

定义映射<span data-katex="\mathscr{R}:\mathscr{X}(M)\rightarrow\mathscr{X}(M)"></span>如下，

<span data-katex="\mathscr{R}(X,Y)Z=D_XD_YZ-D_YD_XZ-D_{[X,Y]}Z"></span>，<span data-katex="\forall Z\in\mathscr{X}(M)"></span>，

并称<span data-katex="\mathscr{R}(X,Y)"></span>为仿射联络空间<span data-katex="(M,D)"></span>关于光滑切向量场<span data-katex="X,Y"></span>的**曲率算子**。

<br/>

由曲率算子可以定义如下三重线性映射，

<span data-katex="\mathscr{R}:\mathscr{X}(M)\times\mathscr{X}(M)\times\mathscr{X}(M)\rightarrow\mathscr{X}(M)"></span>，

<span data-katex="(Z,X,Y)\mapsto\mathscr{R}(X,Y)Z"></span>，<span data-katex="\forall X,Y,Z\in\mathscr{X}(M)"></span>。

可知，<span data-katex="\mathscr{R}"></span>对于每一个自变量都是<span data-katex="C^\infty(M)"></span>-线性的，

故<span data-katex="\mathscr{R}"></span>是<span data-katex="M"></span>上的<span data-katex="(1,3)"></span>型光滑张量场，

称为仿射联络空间<span data-katex="(M,D)"></span>的**曲率张量（场）**。

<br/>

作为张量场，<span data-katex="\mathscr{R}"></span>在每一点<span data-katex="p\in M"></span>给出一个<span data-katex="(1,3)"></span>型张量，

<span data-katex="\mathscr{R}_p:T_p M\times T_p M\times T_p M\rightarrow T_p M"></span>，

使得<span data-katex="(w,u,v)\mapsto\mathscr{R}(u,v)w"></span>，<span data-katex="\forall u,v,w\in T_p M"></span>。

<span data-katex="\mathscr{R}_p"></span>称为<span data-katex="(M,D)"></span>在<span data-katex="p"></span>点的**曲率张量**。

<br/>

利用<span data-katex="D"></span>在局部坐标系下的联络系数，可以算出曲率张量<span data-katex="\mathscr{R}"></span>的分量。

<span data-katex="\mathscr{R}=R^l_{kij}dx^k\otimes\frac{\partial}{\partial x^l}\otimes dx^i\otimes d^j"></span>，

其中，<span data-katex="R^l_{kij}=\frac{\partial\Gamma^l_{kj}}{\partial x^i}-\frac{\partial\Gamma^l_{ki}}{\partial x^j}+\Gamma^h_{jk}\Gamma^l_{hi}-\Gamma^h_{ki}\Gamma^l_{hj}"></span>。

<br/>

因此，对于任意的<span data-katex="X,Y\in\mathscr{X}(M)"></span>，如果

<span data-katex="X=X^i\frac{\partial}{\partial x^i}"></span>，<span data-katex="Y=Y^j\frac{\partial}{\partial x^j}"></span>，

则作为<span data-katex="(1,1)"></span>型张量场的曲率算子<span data-katex="\mathscr{R}(X,Y)"></span>有下述局部坐标表达式，

<span data-katex="\mathscr{R}(X,Y)=X^iY^jR^l_{kij}dx^k\otimes\frac{\partial}{\partial x^l}"></span>。

<br/>

特别的，对于黎曼流形<span data-katex="(M,g)"></span>来说，它具有唯一确定的黎曼联络<span data-katex="D"></span>，

它的曲率张量称为黎曼流形<span data-katex="(M,g)"></span>或度量<span data-katex="g"></span>的曲率张量。

在局部坐标系<span data-katex="(U;x^i)"></span>下，黎曼流形<span data-katex="(M,g)"></span>的曲率张量的分量，让然由上式给出，

只是其中的联络系数<span data-katex="\Gamma^k_{ij}"></span>是度量张量的分量，

<span data-katex="g_{ij}=g\left(\frac{\partial}{\partial x^i},\frac{\partial}{\partial x^j}\right)"></span>

的Christoffel记号。

<br/>

设<span data-katex="(M,g)"></span>是黎曼流形，令

<span data-katex="R(X,Y,Z,W)=g(\mathscr{R}(Z,W)X,Y)"></span>，<span data-katex="\forall X,Y,Z,W\in\mathscr{X}(M)"></span>，

则得到一个四重线性映射，

<span data-katex="R:\mathscr{X}(M)\times\mathscr{X}(M)\times\mathscr{X}(M)\times\mathscr{X}(M)\rightarrow C^\infty(M)"></span>。

显然<span data-katex="R"></span>对每一个自变量是<span data-katex="C^\infty(M)"></span>-线性的，

因此，<span data-katex="R"></span>是<span data-katex="M"></span>上的四阶协变张量场，称为黎曼流形<span data-katex="(M,g)"></span>的**黎曼曲率张量（场）**。