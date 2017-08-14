---
layout: post
categories: Math
title: 微分几何考古
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

容易验证，方向导数算子$D_v f$满足切向量的条件，
所以它是$R^m$在$x_0$点的一个切向量。

假定$v=(v^1,\cdots,v^m)$，则，
$D_v f=\displaystyle\sum_{i=1}^m\frac{\partial f}{\partial x^i}(x_0)\cdot v^i$。
因此，算子$D_v$是由向量$v$决定的。（可证是唯一决定的。）

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

**定理：**
设$M$是一个$m$维光滑流形，$p\in M$，
$(U;x^i)$是包含$p$点的任意一个容许的局部坐标系，
则$M$在$p$点的$m$个切向量，$\frac{\partial}{\partial x^i}\Big\vert_p$，$1\leqslant i\leqslant m$，
构成了切空间$T_p M$的一个基底，特别的，$dimT_p M=m$。

通常把基底$\left\{\frac{\partial}{\partial x^i}\Big\vert_p,\ 1\leqslant i\leqslant m\right\}$，
称为在$p$点处由局部坐标系$(U;x^i)$给出的**自然基底**。

可证，任何一个切向量$v$，在自然基底$\left\{\frac{\partial}{\partial x^j}\Big\vert_p,\ 1\leqslant j\leqslant m\right\}下的分量$v^i$，
恰好是该切向量，在第$i$个局部坐标函数$x^i$上作用得到的值，$v(x^i)$，
$v=\displaystyle\sum_{i=1}^m v(x^i)\frac{\partial}{\partial x^i}\Big\vert_p$。

