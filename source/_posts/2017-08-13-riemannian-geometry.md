---
layout: post
categories: Math
title: 黎曼几何基础
---

**可微函数**
$n$维**欧氏空间**，简记为$R^n$，是有序的$n$元实数组的集合，
并赋予标准的距离$d$所构成的空间，其元素称为“点”。

$R^n$中任意两点$a=(a^1,\cdots ,a^n)$，$b=(b^1,\cdots ,b^n)$之间的距离定义为，
$d(a,b)=\sqrt{\displaystyle\sum_{i=1}^n (b^i-a^i)^2}$。

设$U$是$R^n$的一个开集，$r$为正数，
如果$U$上的实函数$f:U\rightarrow R$具有直到$r$阶的各阶连续偏导数，
则称$f$为$U$上的一个$r$次**可微函数**。

$U$上的$r$次可微函数的集合记为$C^r(U)$，
依此记法，$U$上的连续函数的集合记作$C^0(U)$。

给定函数$f:U\rightarrow R$，如果对于任意的非负整数$r$，
都有$f\in C^r(U)$，则称函数$f$是$U$上的一个**光滑函数**，
$U$上的光滑函数的集合记作$C^\infty (U)$。

为了方便起见，把$C^r(U)$中的函数，称为（$U$上的）$C^r$函数。

**欧氏空间之间的映射**
设$U$是$R^n$的一个开子集，
$f:U\rightarrow R$是从$U$到$k$维欧氏空间$R^k$的映射，
显然，映射$f$可以用$U$上的$k$个实函数$f^\alpha(1\leqslant\alpha\leqslant k)$表示为，
$f=(f^1,\cdots ,f^k)$，
其中，$f^\alpha(1\leqslant\alpha\leqslant k)$称为映射$f$的**分量**。

如果对于每一个$\alpha(1\leqslant\alpha\leqslant k)$，$f^\alpha$都是$U$上的$C^r$函数，
则称映射$f$为（从$U$到$R^k$的）$C^r$映射。

特别的，如果$U$是$R$的一个开区间，
则$C^\infty$映射$f:U\rightarrow R^k$又称为$R^k$中的一条**光滑曲线**。

**拓扑流形和微分流形**
设$M$是一个非空的Hausdorff空间，
如果对于每一点$p\in M$，都存在$p$点的开邻域$U\subseteq M$，
以及从$U$到$m$维欧氏空间$R^m$的某个开集上的同胚$\varphi :U\rightarrow R^m$，
则称$M$为一个$m$维**拓扑流形**。

上述定义中的$(U,\varphi)$称为$M$的一个**坐标卡**，
此时，开集$U$称为点$p\in M$的**坐标邻域**，$\varphi$称为**坐标映射**。
于是，所谓的拓扑流形实际上就是在局部上同胚于$m$维欧氏空间的Hausdorff空间，
即它的每一点都有同胚于$R^n$中某个开集的坐标邻域。

设$M$是一个$m$维拓扑流形，$(U,\varphi)$与$(V,\psi)$是$M$的两个坐标卡，
如果$U\cap V=\varnothing$，或者当$U\cap V\neq\varnothing$时，映射
$\psi\circ\varphi^{-1}:\varphi(U\cap V)\rightarrow\psi(V)$
和$\varphi\circ\psi^{-1}:\psi(U\cap V)\rightarrow\varphi(U)$，
都是$C^r$映射，则称坐标卡$(U,\varphi)$与$(V,\psi)$是$C^r$**相容的**。

显然，拓扑流形$M$的任意两个坐标卡必定是$C^0$相容的。

设$M$是一个拓扑流形，
$\mathscr{A}=\{(U_\alpha,\varphi_\alpha);\alpha\in I\}$是$M$的若干坐标卡构成的集合，$I$为指标集。
如果$\mathscr{A}$满足下列三个条件，
则称$\mathscr{A}$为拓扑流形$M$的一个$C^r$**微分结构**，
（1）$\{U_\alpha;\alpha\in I\}$是$M$是一个开覆盖，
（2）$\forall\alpha,\beta\in I$，$(U_\alpha,\varphi_\alpha)$与$(U_\beta,\varphi_\beta)$是$C^r$相容的，
（3）$\mathscr{A}$是**极大的**，换句话说，对于$M$的任意一个坐标卡$(U,\varphi)$，
如果它和$\mathscr{A}$中的每一个成员都是$C^r$相容的，则它一定属于$\mathsrc{A}$。

$C^\infty$微分结构，称为**光滑结构**。

设$M$是一个$m$维拓扑流形，$\mathscr{A}$是$M$的一个$C^r$微分结构，
则称$(M,\mathscr{A})$是一个$m$维$C^r$**微分流形**。
此时，$\mathscr{A}$中的坐标卡统称为$C^r$微分流形$(M,\mathscr{A})$的**容许坐标卡**。

特别的，$C^\infty$微分流形，又称为**光滑流形**。
在不引起混淆的情况下，也用$M$表示一个$C^r$微分流形$(M,\mathscr{A})$。

**局部坐标系**
设$(U,\varphi)$是$m$维微分流形$M$的一个容许坐标卡，
则对于$\forall p\in U$，把$x=\varphi(p)$在$R^m$中的坐标$(x^1(p),\cdots ,x^m(p))$，
称为点$p$的**局部坐标**。

以这样的方式，在$U$上确定了一个坐标系，
称为$M$在$p$点的一个（由局部坐标卡$(U,\varphi)$给出的）**局部坐标系**，
记为$(U,\varphi;x^i)$，或$(U;x^i)$，
其中，定义在$U$上的$m$个函数$x^i:U\rightarrow R\ (i=1,\cdots ,m)$，
称为**（局部）坐标函数**。

对于$M$的任意两个$C^r$相容的局部坐标系$(U,\varphi;x^i)$和$(V,\psi;y^i)$，
如果$U\cap V\neq\varnothing$，则称映射，
$\psi\circ\varphi^{-1}:\varphi(U\cap V)\rightarrow\psi(U\cap V)$，
为从$(U,\varphi;x^i)$到$(V,\psi;y^i)$的**（局部）坐标变换**，
它可以表示为，
$y^i=(\phi\circ\varphi^{-1})^i=y^i(x^1,\cdots ,x^m)$，$1\leqslant i\leqslant m$。

由此所得到的$m$阶方阵，$J_{x;y}=\left ( \frac{\partial y^i}{\partial x^i} \right )$，
称为局部坐标变换$\psi\circ\varphi^{-1}$的**Jacobi矩阵**，
相应的行列式称为$\psi\circ\varphi^{-1}$的**Jacobi行列式**，
并且记，
$\frac{\partial (y^1,\cdots,y^m)}{\partial (x^1,\cdots,x^m)}=det\left ( \frac{\partial y^i}{\partial x^i} \right )$。

**流形间的映射**
设$M$是一个$m$维光滑流形，$G$为$M$的非空子集，
$f:G\rightarrow R$是定义在$G$上的实值函数，
如果对于$M$的任意一个容许坐标卡$(U,\varphi)$，当$U\cap G\neq\varnothing$时，
$f\circ\varphi^{-1}:\varphi(G\cap U)\rightarrow R$，是$C^s$函数，
则称$f$是$G$上的$C^s$函数。
$G$上的$C^\infty$函数又称为**光滑函数**。

开集$G$上全体$C^s$函数的集合记作$C^s(G)$，
特别的，$M$上全体光滑函数的集合记作$C^\infty(M)$。
不难看出，$C^s(G)$关于函数的加法和乘法构成一个环。

设$M$为光滑流形，$p\in M$，$f$是定义在$p$点某个邻域$A$上的函数，
如果存在$p$的开邻域$U\subseteq A$，使得$f|_U$是$U$上的$C^s$函数，
则称$f$是定义在$p$点**附近**的$C^s$函数，简称为在$p$点的$C^s$函数。

全体在$p$点的$C^s$函数构成的集合记作$C^s_p$，
一般的，$C^s_p$中两个函数可以有不同的定义域，
但是它们在$p$点的某一个开邻域上都有定义并且是$C^s$的，
因此，$C^s_p$中可以定义加法和乘法。

设$M,N$分别是$m,n$维光滑流形，$f:M\rightarrow N$为映射，$p\in M$，
如果存在$M$在点$p$的容许坐标卡$(U,\varphi)$，
以及$N$在点$f(p)$的容许坐标卡$(V,\psi)$，使得$f(U)\subseteq V$，
并且复合映射，$\tilde{f}=\psi\circ f\circ\varphi^{-1}:\varphi(U)\rightarrow\psi(V)$，是$C^\infty$映射，
则称映射$f$在$p$点是$C^\infty$的（或**光滑的**）。

通常，称映射$\tilde{f}$为映射$f$关于坐标卡$(U,\varphi)$和$(V,\psi)$的**局部表示**，
具体的写出来，它由$n$个$m$元实函数组成。

设$f:M\rightarrow N$是光滑流形$M,N$间的映射，
如果$f$在$M$的每一点$p$处都是$C^\infty$的，
则称$f$为$C^\infty$映射，或**光滑映射**。

设$M$和$N$是两个光滑流形，$f:M\rightarrow N$是一个同胚，
如果$f$及其逆映射$f^{-1}:N\rightarrow M$都是光滑的，
则称$f$是从$M$到$N$的**光滑同胚**，或**微分同胚**。
此时，也称$M$和$N$彼此光滑（或微分）同胚。

如果$f:M\rightarrow N$是一个光滑映射，并且对于每一点$p\in M$，
都有$p$的一个开邻域$U$使得$f(U)$是$N$中的开子集，
并且，$f|_U:U\rightarrow f(U)$是从$U$到$f(U)$的光滑同胚，
则称$f$是从$M$到$N$的**局部光滑同胚**。

显然，如果$f$是从$M$到$N$的光滑同胚，
则$f^{-1}$是从$N$到$M$的光滑同胚。

**切向量**
假定$M$是一个$m$维光滑流形，$p\in M$，
$C^\infty_p$表示在$p$点的光滑函数的集合。
光滑流形$M$在点$p\in M$的一个**切向量**$v$指的是，
满足以下两个条件的映射$v:C^\infty_p\rightarrow R$，
（1）$\forall f,g\in C^\infty_p$，$\forall\lambda\in R$，$v(f+\lambda g)=v(f)+\lambda v(g)$，
（2）$\forall f,g\in C^\infty_p$，$v(fg)=v(f)g(p)+f(p)v(g)$。

设$(U,\varphi;x^i)$是$p$点的一个局部坐标系，
对于任意的$f\in C^\infty_p$，记，
$\frac{\partial f}{\partial x^i}(p)=\frac{\partial (f\circ\varphi^{-1})}{\partial x^i}(\varphi(p))$。

设$M=R^m$，$x_0\in R^m$，
对于向量$v\in R^m$，我们定义映射$D_v:C^\infty_{x_0}\rightarrow R$如下，
对于任意的函数$f\in C^\infty_{x_0}$，令，
$D_v f=\frac{df(x_0+tv)}{dt}\Big\vert_{t=0}$，
则$D_v f$是函数$f$在点$x_0$沿向量$v$的**方向导数**。

容易验证，方向导数算子$D_v$满足切向量的条件，
所以它是$R^m$在$x_0$点的一个切向量。

假定$v=(v^1,\cdots,v^m)$，则，
$D_v f=\displaystyle\sum_{i=1}^m\frac{\partial f}{\partial x^i}(x_0)\cdot v^i$。
因此，算子$D_v$是由向量$v$唯一决定的。

反之，可以证明，如果映射$\sigma:C^\infty_{x_0}\rightarrow R$满足切向量的条件，
则必有唯一的一个向量$v\in R^m$，使得相应的方向导数算子$D_v=\sigma$。

所以，向量$v$与方向导数算子$D_v$是一一对应的，
这就是说，可以把$v$和$D_v$等同起来。

设$M$是一个$m$维光滑流形，
$\gamma:(-\varepsilon,\varepsilon)\rightarrow M$是$M$上的一条光滑曲线，记$p=\gamma(0)$，
利用$\gamma$可以定义一个映射$v:C^\infty_p\rightarrow R$如下，
对于任意的$f\in C^\infty_p$，令，
$v(f)=\frac{d}{dt}\Big\vert_{t=0}f\circ\gamma(t)=\frac{df(\gamma(t))}{dt}\Big\vert_{t=0}$。

容易验证，映射$v:C^\infty_p\rightarrow R$满足切向量的条件，
因此，$v$是光滑流形$M$在$p$点的一个切向量，
称为曲线$\gamma$在$t=0$点处的**切向量**，记为$\gamma'(0)$，
这样上式成为，$\gamma'(0)(f)=\frac{df(\gamma(t))}{dt}\Big\vert_{t=0}$。

**切空间**
把光滑流形$M$在点$p$处的切向量构成的集合，记为$T_p M$，
在$T_p M$中，引入加法和数乘运算如下，
对于任意的$u,v\in T_p M$，$\lambda\in R$，以及$f\in C^\infty_p$，定义，
$(u+v)(f)=u(f)+v(f)$，
$(\lambda u)(f)=\lambda\cdot u(f)$。

显然，这样定义的$u+v$和$\lambda u$仍然是$M$在$p$点的切向量，
即$T_p M$关于这样的加法和数乘运算是封闭的。
进一步可以验证，$T_p M$关于上述的加法和数乘运算构成一个实向量空间。

向量空间$T_p M$，称为光滑流形$M$在点$p$的**切空间**。

设$(U,\varphi;x^i)$是$M$在$p$点的一个局部坐标系，
$x^i(p)=x^i_0$，$1\leqslant i\leqslant m$，
对于每一个$i$，
设$\gamma_i:(-\varepsilon,\varepsilon)\rightarrow M$是通过点$p$的第$i$条坐标曲线（称为$x^i$曲线），
即对于任意的$t\in(-\varepsilon,\varepsilon)$，
$\gamma_i(t)=\varphi^{-1}(x^1_0,\cdots,x^i_0+t,\cdots,x^m_0)$。

因此，$\gamma'_i(0)$是$M$在$p$点的一个切向量，以后记为$\frac{\partial}{\partial x^i}\Big\vert_p$。
由定义，对于任意的$f\in C^\infty_p$，
$\frac{\partial}{\partial x^i}\Big\vert_p(f)=\frac{df(\gamma_i(t))}{dt}\Big\vert_{t=0}$
$=\frac{d}{dt}_{t=0}f\circ\varphi^{-1}(x^1_0,\cdots,x^i_0+t,\cdots,x^m_0)$
$=\frac{\partial(f\circ\varphi^{-1})}{\partial x^i}(\varphi(p))$
$=\frac{\partial f}{\partial x^i}(p)$。

设$M$是一个$m$维光滑流形，$p\in M$，
$(U;x^i)$是包含$p$点的任意一个容许的局部坐标系，
则$M$在$p$点的$m$个切向量，$\frac{\partial}{\partial x^i}\Big\vert_p$，$1\leqslant i\leqslant m$，
构成了切空间$T_p M$的一个基底，特别的，$dimT_p M=m$。

通常把基底$\left\{\frac{\partial}{\partial x^i}\Big\vert_p,\ 1\leqslant i\leqslant m\right\}$，
称为在$p$点处由局部坐标系$(U;x^i)$给出的**自然基底**。

可证，任何一个切向量$v$，在自然基底$\left\{\frac{\partial}{\partial x^j}\Big\vert_p,\ 1\leqslant j\leqslant m\right\}下的分量$v^i$，
恰好是该切向量，在第$i$个局部坐标函数$x^i$上作用得到的值，$v(x^i)$，
$v=\displaystyle\sum_{i=1}^m v(x^i)\frac{\partial}{\partial x^i}\Big\vert_p$。

**余切向量**
切空间$T_p M$的对偶空间，称为光滑流形$M$在$p$点的**余切空间**，记为$T^*_p M$，
其中的元素，即线性函数$\alpha:T_p M\rightarrow R$，称为$M$在$p$点的**余切向量**。

为了强调切空间与余切空间的对偶性，
常常把一个余切向量$\alpha\in T^*_p M$在切向量$v\in T_p M$上的作用记为$\alpha(v)=\left\langle v,\alpha\right\rangle$。
由$(v,\alpha)\mapsto\left\langle v,\alpha\right\rangle$确定的映射，
$\left\langle \cdot,\cdot\right\rangle:T_p M\times T^*_p M\rightarrow M$，
称为$T_p M$与$T^*_p M$之间的**配合**。

设$f\in C^\infty_p$，定义映射$df:T_p M\rightarrow R$如下，
对于任意的$v\in T_p M$，
$\left\langle v,df\right\rangle=df(v)=v(f)\in R$。

显然$df$是$T_p M$上的线性函数，即$df\in T^*_p M$，
有时，为了强调$df$是在$p$点的一个余切向量，也把$df$记为$df|_p$，或$df(p)$。

设$(U;x^i)$是光滑流形$M$的一个容许局部坐标系，$p\in U$，
由于每个坐标函数都是$U$上的光滑函数，因而$dx^i|_p\in T^*_p M$，并且，
$\left\langle\frac{\partial}{\partial x^j}\Big\vert_p,dx^i|_p\right\rangle=\frac{\partial x^i}{\partial x^j}\Big\vert_p=\delta^i_j$。

由此可见，$\{dx^i|_p;\ 1\leqslant i\leqslant m\}$是$T^*_p M$中与自然基底
$\left\{\frac{\partial}{\partial x^i}\Big\vert_p;\ 1\leqslant i\leqslant m\right\}$
对偶的基底。

一般的，对于任意的$\alpha\in T^*_p M$，有
$\alpha=\displaystyle\sum_{i=1}^m \alpha_idx^i|_p=\displaystyle\sum_{i=1}^m\left\langle\frac{\partial}{\partial x^i}\Big\vert_p,\alpha\right\rangle dx^i|_p$，
特别的，对于任意的$f\in C^\infty_p$，
$df|_p=\displaystyle\sum_{i=1}^m\frac{\partial f}{\partial x^i}(p)dx^i|_p$。
因此，余切向量$df|_p=df(p)$，也称为函数$f$在$p$点的**微分**。

**切映射和余切映射**
设$M,N$分别是$m,n$维光滑流形，$F:M\rightarrow N$是光滑映射，$p\in M$，
对于任意的$v\in T_p M$，我们可以通过映射$F$得到切向量$F_*(v)\in T_{F(p)}N$，其定义为，
$F_*(v)(f)=v(f\circ F)$，$\forall f\in C^\infty_{F(p)}$。

这样，就得到一个映射$F_*:T_p M\rightarrow T_{F(p)}N$，
易知，$F_*$是线性映射，称为光滑映射$F$在$p$点的**切映射**，或微分，
它的对偶映射$F^*:T^*_{F(p)}N\rightarrow T^*_p M$，
称为光滑映射$F$在$p$点的**余切映射**，或拉回映射。

由对偶映射的定义，余切映射$F^*:T^*_{F(p)}N\rightarrow T^*_p M$也是线性映射，
并且对于任意的$\omega\in T^*_{F(p)}N$，$F^*\omega$由下式定义，
$(F^*\omega)(v)=\omega(F_*(v))$，$\forall v\in T_p M$。

为了强调对于点$p$的依赖性，
常常用$F_{*p}$和$F^*_p$来表示映射$F$在$p$点的切映射和余切映射。

**切向量场**
设$M$是一个$m$维光滑流形，$M$在每一点$p$处都有切空间$T_p M$，记
$TM=\displaystyle\bigcup_{p\in M}T_p M$。

$M$上的一个**切向量场**$X$是指，在$M$的每一个点$p$处指定了$M$在该点的一个切向量$X(p)$，
换句话说，$M$上的切向量场是一个映射$X:M\rightarrow TM$，
使得对于任意一点$p\in M$，$X(p)\in T_p M$。

比如，在$M$的任意一个容许局部坐标系$(U;x^i)$下，
$\frac{\partial}{\partial x^i}$是$U$上的切向量场，
特别的，这样一组切向量场在$U$中每一点$p$处的值，构成该点的切空间$T_p M$的一个基底。
通常称这样一组切向量场为$U$上的一个**标架场**，
为了叙述的方便，以后把$\left\{\frac{\partial}{\partial x^i}\Big\vert_p\right\}$称为，
$M$在局部坐标系$(U;x^i)$下的**自然标架场**。

设$X:M\rightarrow TM$是$m$维光滑流形$M$上的切向量场，
如果对于每一点$p\in M$，存在$p$点的容许局部坐标系$(U;x^i)$，
使得$X$限制在$U$上的局部坐标表达式，
$X|_U=\displaystyle\sum_{i=1}^m X^i\frac{\partial}{\partial x^i}$
中的分量$X^i$都是$U$上的光滑函数（$1\leqslant i\leqslant m$），
则称$X$是$M$上的**光滑切向量场**。

由定义和局部坐标系的$C^\infty$相容性可得，
$M$上的一个切向量场$X$为光滑切向量场
$\Leftrightarrow$$X$关于每一个自然标架场的分量是光滑函数
$\Leftrightarrow$$X$在每一个容许坐标系$(U;x^i)$上的限制$X|_U$是$U$上的光滑切向量场。

$M$上光滑切向量场的集合，记为$\mathscr{X}(M)$，
显然，$\mathscr{X}(M)$关于加法和数乘是封闭的，因而它是一个向量空间。

**张量场**
$M$在点$p$处的一个$(r,s)$型张量$\tau$，是指一个$r+s$重线性映射，
$r:T^*_p M\times\cdots\timesT^*_p M\times T_p M\times\cdots\times T_p M\rightarrow R$，
其中，$T^*_p M$有$r$个，称为**反变阶数**，$T_p M$有$s$个，称为**协变阶数**。

若以$T^r_s(p)$表示$M$在$p$点的所有$(r,s)$型张量构成的集合，则有，
$T^r_s(p)=\mathscr{L}(T^*_p M,\cdots,T^*_p M,T_p M,\cdots,T_p M;R)$。

不难看出，$T^r_s(p)$是一个$m^{r+s}$维向量空间，
并且，在$p$点的容许局部坐标系$(U;x^i)$下，$T^r_s(p)$有一个自然基底，即，
$\frac{\partial}{\partial x^{i_1}}\Big\vert_p\otimes\cdots\otimes\frac{\partial}{\partial x^{i_r}}\Big\vert_p\otimes dx^{j_1}|_p\otimes\cdots\otimes dx^{j_s}|_p$，
$1\leqslant i_1,\cdots,i_r,j_1,\cdots,j_s\leqslant m$。

由此可见，$T^r_s(p)=T_p M\otimes\cdots\otimes T_p M\otimes T^*_p M\otimes\cdots\otimes T^*_p M$，
其中$T_p M$有$r$个，$T^*_p M$有$s$个。

令，$T^r_s(M)=\displaystyle\bigcup_{p\in M}T^r_s(p)$，
光滑流形$M$上的一个$(r,s)$型**张量场**$\tau$，
是指从$M$到$T^r_s(M)$的一个映射$\tau:M\rightarrow T^r_s(M)$，
使得对于任意的$p\in M$，都有$\tau(p)\in T^r_s(p)$。

$M$上的$(r,0)$型和$(0,s)$型张量场，分别称为$r$阶反变张量场和$s$阶协变张量场。

光滑流形$M$上的一个$(r,s)$型张量场$\tau:M\rightarrow T^r_s(M)$称为**光滑的**，
如果对于任意的$p\in M$，存在$p$点的容许局部坐标系$(U;x^i)$，
使得$\tau$在$U$上的限制具有如下局部表达式，
$\tau|_U=\tau^{i_1\cdots i_r}_{j_1\cdots j_s}\frac{\partial}{\partial x^{i_1}}\otimes\cdots\otimes\frac{\partial}{\partial x^{i_r}}\otimes dx^{j_1}\otimes\cdots\otimes dx^{j_s}$，
其中，$\tau^{i_1\cdots i_r}_{j_1\cdots j_s}$是$U$上的光滑函数。

$M$上光滑的$(r,s)$型张量场构成的集合记作$\mathscr{J}^r_s(M)$，特别的，
$\mathscr{J}^1_0(M)=\mathscr{X}(M)$，$\mathscr{J}^0_0(M)=C^\infty(M)$。

在集合$\mathscr{J}^r_s(M)$中有自然的加法，数乘等运算，
任意两个光滑张量场能够逐点作张量积运算，另外，张量场还可以与光滑函数相乘，
使得$\mathscr{J}^r_s(M)$成为一个$C^\infty(M)$-模。

光滑的一阶协变张量场（即余切向量场），又称为**1次微分式**。
把光滑流形$M$上的1次微分式的集合记为$A^1(M)$，即$A^1(M)=\mathscr{J}^0_1(M)$。

**外微分**
光滑流形$M$上的一个光滑的$r$阶协变张量场$\varphi$是**反对称的**，
如果它作为映射，$\varphi:\mathscr{X}(M)\times\cdots\times\mathscr{X}(M)\rightarrow C^\infty(M)$，
关于所有的自变量是反对称的，即交换任意两个自变量的位置，所得的值反号。
或等价的说，在任意的局部坐标系下，$\varphi$的分量关于下指标是反对称的。

光滑流形$M$上的一个光滑的$r$阶反对称协变张量场$\varphi$，
称为$M$上的一个$r$次**外微分式**。
同时，还约定，$M$上的1次外微分式，就是$M$上的1次微分式，即光滑的一阶协变张量场。
$M$上的0次外微分式，指的是$M$上的光滑函数。

$M$上的$r$次外微分式的集合记作$A^r(M)$，特别的，
$A^1(M)=\mathscr{J}^0_1(M)$，$A^0(M)=C^\infty(M)$。

由定义可知，若$\varphi\in A^r(M)$，则在每一点$p\in M$，
$\varphi(p)$是$T_p M$上的一个$r$次外形式，
即，$\varphi(p):T_p M\times\cdots\times T_p M\rightarrow R$，
是一个反对称的$r$重线性函数。

此外，每一个$r$次外微分式$\varphi$，可以等同于反对称的$r$重$C^\infty(M)$-线性映射，
$\varphi:\mathscr{X}(M)\times\cdots\times\mathscr{X}(M)\rightarrow C^\infty(M)$。

通过逐点定义的方式，可以引入外微分式的加法，数乘和外积运算，
比如，外积的定义如下，$\forall \varphi\in A^r(M),\psi\in A^s(M)$，
$(\varphi\wedge\psi)(p)=\varphi(p)\wedge\psi(p)$
$=\frac{(r+s)!}{r!s!}A_{r+s}(\varphi(p)\otimes\psh(p))$
$=\frac{(r+s)!}{r!s!}A_{r+s}(\varphi\otimes\psi)(p)$，$\forall p\in M$。

即有，$\varphi\wedge\psi=\frac{(r+s)!}{r!s!}A_{r+s}(\varphi\otimes\psi)$，
这里的$A_{r+s}$是反对称化算子。

进而，若令$A(M)=\displaystyle\bigoplus_{r=0}^m A^r(M)$，$m=dim\ M$，
则在$A(M)$上可以引入外微分运算。

设$M$是$m$维光滑流形，则存在唯一的一个映射，$d:A(M)\rightarrow A(M)$，
使得对于任意的非负整数$r$，有$d(A^r(M))\subseteq A^{r+1}(M)$，
并且满足以下条件，
（1）$d$是线性的，即对于任意的$\varphi,\psi\in A(M)$，$\lambda\in R$，有，
$d(\varphi+\lambda\cdot\psi)=d\varphi+\lambda d\psi$，
（2）$\forall\varphi\in A^r(M),\psi\in A(M)$，有，
$d(\varphi\wedge\psi)=d\varphi\wedge\psi+(-1)^r\varphi\wedge d\psi$，
（3）$\forall f\in A^0(M)$，$df$是$f$的微分，
（4）$d^2=d\circ d=0$。
这样的映射$d$，称为**外微分（算子）**。

外微分算子$d$满足$d\circ d=0$，
这意味着$d:A^r(M)\rightarrow A^{r+1}(M)$可以看做拓扑学忠的上边缘算子，
在这里，$A^r(M)$被看做加法群。

令$Z^r(M)=\{\alpha\in A^r(M):d\alpha=0\}$，
$B^r(M)=d(A^{r-1}(M))=\{\alpha\in A^r(M):\exists\beta\in A^{r-1}(M),\alpha=d\beta\}$，
$Z^r(M)$中的元素称为$M$上的$r$次**闭微分式**，
$B^r(M)$中的元素称为$M$上的**恰当微分式**，
这样，性质$d\circ d=0$，表明$B^r(M)$是$Z^r(M)$的子群。

商群$H^r(M)=Z^r(M)/B^r(M)$称为光滑流形$M$上的第$r$个**de Rham上同调群**。

应该注意的是，de Rham上同调群$H^r(M)$是光滑流形的光滑结构的产物，
但是，著名的de Rham定理说，当$M$是紧致光滑流形时，de Rham上同调群$H^r(M)$与$M$的第$r$个实系数上同调群是同构的，
由此可见，de Rham上同调群$H^r(M)$是流形$M$的拓扑不变量。

- - -

**内积**
在$n$维向量空间$V$上，**内积**是指满足下列条件的双线性形式，
$\left\langle\cdot,\cdot\right\rangle:V\times V\rightarrow R$，
（1）对称性：$\left\langle u,v\right\rangle=\left\langle v,u\right\rangle$，$\forall u,v\in V$，
（2）正定性：$\forall u\in V$，$\left\langle u,u\right\rangle\geqslant 0$，其中等号成立当且仅当$u=0$。

换句话说，$V$上的一个内积，就是$V$上的一个对称，正定的二阶协变张量，
指定了一个内积的向量空间$V$，称为**欧氏向量空间**，
在这样的空间中，能够定义向量的长度以及向量之间的夹角。

设$M$是一个$m$维光滑流形，$g$是$M$上的一个光滑的二阶协变张量场，
如果$g$是对称，正定的，即对于每一点$p\in M$，$g(p)$是切空间$T_p M$上的一个对称，正定的二阶协变张量，
则称$g$是$M$上的一个**黎曼度量**，
指定了一个黎曼度量$g$的光滑流形$M$，称为**黎曼流形**，
记为$(M,g)$，或简记为$M$。

根据定义，$g(p)$是$T_p M$上的内积（$\forall p\in M$），
所以光滑流形$M$上的黎曼度量，就是以光滑的依赖于点$p$的方式，
在每一点$p\in M$的切空间$T_p M$上，指定一个内积，使之成为欧氏向量空间。
特别的，每一个欧氏向量空间，都是黎曼流形。

设$(U;x^i)$是$M$的一个容许的局部坐标系，则黎曼度量$g$有局部坐标表达式，
$g|_U=g_{ij}dx^i\otimes dx^j$，
其中$g_{ij}=g\left(\frac{\partial}{\partial x^i},\frac{\partial}{\partial x^j}\right)\in C^\infty(U)$，$g_{ij}=g_{ji}$，
d定义，在每一点$p\in U$，$(g_{ij}(p))$都是正定矩阵，
如果引入对称化的乘积（对称张量积），
$dx^idx^j=\frac{1}{2}(dx^i\otimes dx^j+dx^j\otimes dx^i)$，
则$g|_U$可以写成二次微分形式，$g|_U=g_{ij}dx^idx^j$。

**弧长**
设$\gamma:[a,b]\rightarrow M$是$M$中一条光滑曲线，令，
$L(\gamma)=\int_{a}^{b}|\gamma'(t)|dt=\int_{a}^{b}\sqrt{\left\langle\gamma'(t),\gamma'(t)\right\rangle}dt$，
并称之为曲线$\gamma$的**弧长**（长度）。

如果$\gamma([a,b])$落在区域$U$内，则它可用局部坐标表示为，
$x^i(t)=x^i(\gamma(t))$，$1\leqslant i\leqslant m$，
因而，$L(\gamma)=\int_{a}^{b}\sqrt{g_{ij}(\gamma(t))\frac{dx^i}{dt}\frac{dx^j}{dt}}dt$，
曲线的弧长与曲线的正则参数变换无关，也与光滑流形的局部坐标系的取法无关。

**协变微分**
设$(M,g)$是一个$m$维黎曼流形，$X\in\mathscr{X}(M)$，
如果$(U;x^i)$是$M$的一个容许坐标系，并且$X|_U=X^i\frac{\partial}{\partial x^i}$，则，
$D(X|_U)=(dX^i+X^j\Gamma^i_{jk}dx^k)\otimes\frac{\partial}{\partial x^i}$
$=\left(\frac{\partial X^i}{\partial x^k}+X^j\Gamma^i_{jk}\right)dx^k\otimes\frac{\partial}{\partial x^i}$，
是与局部坐标系的选取无关的$(1,1)$型光滑张量场。

于是，如果令$(DX)|_U=D(X|_U)$，则$DX$是大范围定义在$M$上的$(1,1)$型光滑张量场。
$DX$称为光滑向量场$X$的**协变微分**，或绝对微分，
相应的映射$D:\mathscr{X}(M)\rightarrow\mathscr{J}^1_1(M)$，
称为黎曼流形$(M,g)$上的**协变微分算子**，或绝对微分算子。

设$X,Y\in\mathscr{X}(M)$，
$D_YX=C^1_1(Y\otimes DX)$，称为光滑切向量场$X$沿$Y$的**协变导数**，或协变微商，
其中$C^1_1$是指张量场关于第一个反变指标和第一个协变指标的缩并运算。

在局部坐标系$(U;x^i)$下，$(D_YX)|_U$有如下的局部坐标表达式，
$(D_YX)|_U=Y^k\left(\frac{\partial X^i}{\partial x^k}+X^j\Gamma^i_{jk}\right)\frac{\partial}{\partial x^i}$。

由此可见，协变微分算子$D$又可视为映射$D:\mathscr{X}(M)\times\mathscr{X}(M)\rightarrow\mathscr{X}(M)$，
其定义是，对于任意的$X,Y\in\mathscr{X}(M)$，$D(X,Y)=D_YX\in\mathscr{X}(M)$。

**联络**
设$M$是$m$维光滑流形，$M$上的一个**联络**$D$，是指满足下列条件的映射，
$D:\mathscr{X}(M)\times\mathscr{X}(M)\rightarrow\mathscr{X}(M)$，
（1）$D_{Y+fZ}X=D_YX+fD_ZX$，
（2）$D_Y(X+\lambda Z)=D_YX+\lambda D_YZ$，
（3）$D_Y(fX)=Y(f)X+fD_YX$
其中，$D_YX=D(X,Y)$，$X,Y,Z\in\mathscr{X}(M)$，$\lambda\in R$，$f\in C^\infty(M)$。

黎曼流形$(M,g)$上的协变微分算子$D$是光滑流形$M$上的一个联络，
由于在满足第二可数公理的光滑流形$M$上黎曼度量总是存在的，
因而$M$上的联络也是存在的。
不过，一般说来，光滑流形上的联络不是唯一的。

指定了一个联络$D$的光滑流形$(M,D)$，称为一个**仿射联络空间**，
在这样的空间里，可以对光滑切向量场求协变微分和协变导数，
比如，对于任意的$X,Y\in\mathscr{X}(M)$，
光滑切向量场$D_YX$称为向量场$X$沿$Y$的**协变导数**，或协变微商。

**黎曼几何基本定理**
设$(M,g)$是$m$维黎曼流形，则在$M$上存在唯一的一个与度量$g$相容的无挠联络$D$，
称为$(M,g)$的**黎曼联络**，或Levi-Civita联络。

**微分算子**
设$X\in\mathscr{X}(M)$，则$DX$是$M$上的$(1,1)$型光滑张量场，
讲$DX$进行缩并，便得到$M$上的光滑函数，称它为光滑切向量场$X$的**散度**，
并记作$div\ X$，即有$div\ X=C^1_1(DX)$。

由$X\mapsto div\ X$所确定的线性映射$div:\mathscr{X}(M)\rightarrow C^\infty(M)$，
称为黎曼流形$(M,g)$上的**散度算子**。

设$f\in C^\infty(M)$，则$df\in A^1(M)=\mathscr{J}^0_1(M)$，
借助黎曼度量$g$，$df$对应$M$上一个光滑切向量场，记为$\triangledown f$，
使得对于任意的$X\in\mathscr{X}(M)$有，$g(\triangledown f,X)=df(X)=X(f)$，
切向量场$\triangledown f$称为光滑函数$f$在黎曼度量$g$下的**梯度**，
有时也用$grad\ f$或$grad_g\ f$表示光滑函数$f$的梯度。

显然，由$f\mapsto \triangledown f$确定的映射$\triangledown:C^\infty(M)\rightarrow\mathscr{X}(M)$，
是作用在光滑函数上的一阶线性微分算子，称为黎曼流形$(M,g)$上的**梯度算子**。

把梯度算子$\triangledown$与散度算子$div$复合起来，便得到一个新的线性映射，
$\triangle=div\circ\triangledown:C^\infty(M)\rightarrow C^\infty(M)$，
称为黎曼流形$(M,g)$上的**Beltrami-Laplace算子**。

- - -

**曲率张量场**
设$(M,D)$是$m$维仿射联络空间，对于任意的$X,Y\in\mathscr{X}(M)$，
定义映射$\mathscr{R}:\mathscr{X}(M)\rightarrow\mathscr{X}(M)$如下，
$\mathscr{R}(X,Y)Z=D_XD_YZ-D_YD_XZ-D_{[X,Y]}Z$，$\forall Z\in\mathscr{X}(M)$，
并称$\mathscr{R}(X,Y)$为仿射联络空间$(M,D)$关于光滑切向量场$X,Y$的**曲率算子**。

由曲率算子可以定义如下三重线性映射，
$\mathscr{R}:\mathscr{X}(M)\times\mathscr{X}(M)\times\mathscr{X}(M)\rightarrow\mathscr{X}(M)$，
$(Z,X,Y)\mapsto\mathscr{R}(X,Y)Z$，$\forall X,Y,Z\in\mathscr{X}(M)$。
可知，$\mathscr{R}$对于每一个自变量都是$C^\infty(M)$-线性的，
故$\mathsrc{R}$是$M$上的$(1,3)$型光滑张量场，
称为仿射联络空间$(M,D)$的**曲率张量（场）**。

作为张量场，$\mathscr{R}$在每一点$p\in M$给出一个$(1,3)$型张量，
$\mathscr{R}_p:T_p M\times T_p M\times T_p M\rightarrow T_p M$，
使得$(w,u,v)\mapsto\mathscr{R}(u,v)w$，$\forall u,v,w\in T_p M$。
$\mathscr{R}_p$称为$(M,D)$在$p$点的**曲率张量**。

利用$D$在局部坐标系下的联络系数，可以算出曲率张量$\mathscr{R}$的分量。
$\mathscr{R}=R^l_{kij}dx^k\otimes\frac{\partial}{\partial x^l}\otimes dx^i\otimes d^j$，
其中，$R^l_{kij}=\frac{\partial\Gamma^l_{kj}}{\partial x^i}-\frac{\partial\Gamma^l_{ki}}{\partial x^j}+\Gamma^h_{jk}\Gamma^l_{hi}-\Gamma^h_{ki}\Gamma^l_{hj}$。

因此，对于任意的$X,Y\in\mathscr{X}(M)$，如果
$X=X^i\frac{\partial}{\partial x^i}$，$Y=Y^j\frac{\partial}{\partial x^j}$，
则作为$(1,1)$型张量场的曲率算子$\mathscr{R}(X,Y)$有下述局部坐标表达式，
$\mathscr{R}(X,Y)=X^iY^jR^l_{kij}dx^k\otimes\frac{\partial}{\partial x^l}$。

特别的，对于黎曼流形$(M,g)$来说，它具有唯一确定的黎曼联络$D$，
它的曲率张量称为黎曼流形$(M,g)$或度量$g$的曲率张量。
在局部坐标系$(U;x^i)$下，黎曼流形$(M,g)$的曲率张量的分量，让然由上式给出，
只是其中的联络系数$\Gamma^k_{ij}$是度量张量的分量，
$g_{ij}=g\left(\frac{\partial}{\partial x^i},\frac{\partial}{\partial x^j}\right)$
的Christoffel记号。

设$(M,g)$是黎曼流形，令
$R(X,Y,Z,W)=g(\mathscr{R}(Z,W)X,Y)$，$\forall X,Y,Z,W\in\mathscr{X}(M)$，
则得到一个四重线性映射，
$R:\mathscr{X}(M)\times\mathscr{X}(M)\times\mathscr{X}(M)\times\mathscr{X}(M)\rightarrow C^\infty(M)$。
显然$R$对每一个自变量是$C^\infty(M)$-线性的，
因此，$R$是$M$上的四阶协变张量场，称为黎曼流形$(M,g)$的**黎曼曲率张量（场）**。

