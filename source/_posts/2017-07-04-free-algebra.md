---
layout: post
categories: Math
title: Free Algebra
katex: true
---

### functor

函子（functor）就是范畴（category）间的态射（morphism）。

<br/>

设有范畴<span data-katex="D"></span>和<span data-katex="C"></span>，一个**函子**（functor）<span data-katex="U:D\rightarrow C"></span>由两部分组成，

（1）作用在对象上的函数，它将<span data-katex="D"></span>中的每一个对象<span data-katex="d"></span>，映射为<span data-katex="C"></span>中的一个对象<span data-katex="Ud"></span>

（2）作用在箭头上的函数，它将<span data-katex="D"></span>中的每一个箭头<span data-katex="g:d\rightarrow d'"></span>，映射为<span data-katex="C"></span>中的一个箭头<span data-katex="Ug:Ud\rightarrow Ud'"></span>

并且，这两个函数使得以下等式成立，

<span data-katex="U(1_d)=1_{Ud}"></span>

<span data-katex="U(h\circ g)=Uh\circ Ug"></span>

<br/>

### forgetful functor

一个函子可能会“遗忘”范畴中的部分（或全部）结构，这样的函子称为**遗忘函子**（forgetful functor）。

例如，遗忘函子<span data-katex="U:Grp\rightarrow Set"></span>，将范畴<span data-katex="Grp"></span>中的每一个群<span data-katex="g"></span>，映射为一个由群<span data-katex="g"></span>的所有元素组成的集合<span data-katex="Ug"></span>，

（“遗忘”了建立在群乘法之上的群结构，）

并且将范畴<span data-katex="Grp"></span>中的任意两个群之间的群同态<span data-katex="\varphi:g\rightarrow g'"></span>，映射为两个集合之间的函数<span data-katex="\phi"></span>。

<br/>

一个函子<span data-katex="U:D\rightarrow C"></span>称为**完全的**（full），

如果对于<span data-katex="D"></span>中的任意两个对象<span data-katex="d,d'"></span>，以及对应<span data-katex="C"></span>中的箭头<span data-katex="f:Ud\rightarrow Ud'"></span>，

存在<span data-katex="B"></span>的箭头<span data-katex="g:d\rightarrow d'"></span>，使得<span data-katex="f=Ug"></span>。

<br/>

一个函子<span data-katex="U:D\rightarrow C"></span>称为**忠实的**（faithful），

如果对于<span data-katex="D"></span>中的任意两个对象<span data-katex="d,d'"></span>，以及<span data-katex="D"></span>中的任意两个箭头<span data-katex="g_1,g_2:d\rightarrow d'"></span>，

如果<span data-katex="Ug_1=Ug_2"></span>，就有<span data-katex="g_1=g_2"></span>。

<br/>

### hom-set

以上两个概念（完全的，忠实的），可以使用hom-set术语重新描述，

设<span data-katex="D"></span>中有两个对象<span data-katex="d,d'"></span>，函子<span data-katex="U:D\rightarrow C"></span>，

将<span data-katex="D"></span>中每一个箭头<span data-katex="g:d\rightarrow d'"></span>映射为<span data-katex="C"></span>中的一个箭头<span data-katex="Ug:Ud\rightarrow Ud'"></span>，

这样就定义了一个函数<span data-katex="U_{d,d'}"></span>，<span data-katex="U_{d,d'}:hom(d,d')\rightarrow hom(Ud,Ud')"></span>，

我们说函子<span data-katex="U"></span>是完全的，如果<span data-katex="U_{d,d'}"></span>是一个满射（surjective），

我们说函子<span data-katex="U"></span>是忠实的，如果<span data-katex="U_{d,d'}"></span>是一个单射（injective）。

<br/>

其中，<span data-katex="hom(d,d')"></span>表示所有从对象<span data-katex="d"></span>到对象<span data-katex="d'"></span>的箭头所构成的集合，

<span data-katex="hom(d,d')=\{g|g\ in\ D,\ dom\ g=c,\ cod g=c'\}"></span>

<span data-katex="dom"></span>表示箭头<span data-katex="g"></span>的始端，<span data-katex="cod"></span>表示箭头<span data-katex="g"></span>的终端。

<br/>

如果一个函子既是完全的，又是忠实的，我们就说它是完全忠实的，这时<span data-katex="U_{d,d'}"></span>是一个双射（bijection）。

<br/>

### comma category

给定范畴<span data-katex="E,C,D"></span>和函子<span data-katex="T,S"></span>，<span data-katex="E\;{\tiny\begin{matrix}^{\normalsize T}\\ \normalsize \rightarrow \\ ^{\scriptsize}\end{matrix} }\;C\;{\tiny\begin{matrix}^{\normalsize S}\\ \normalsize \leftarrow \\ ^{\scriptsize}\end{matrix} }\;D"></span>，

**逗号范畴**（comma category）<span data-katex="(T\downarrow S)"></span>，由以下对象和箭头组成，

它的对象为三元组<span data-katex="\left\langle e,d,f\right\rangle"></span>，

其中，<span data-katex="e"></span>是<span data-katex="E"></span>中的对象，<span data-katex="d"></span>是<span data-katex="D"></span>中的对象，<span data-katex="f:Te\rightarrow Sd"></span>是<span data-katex="C"></span>中的箭头，

它的箭头为二元组<span data-katex="\left\langle k,h\right\rangle:\left\langle e,d,f\right\rangle\rightarrow\left\langle e',d',f'\right\rangle"></span>，

其中，<span data-katex="k:e\rightarrow e'"></span>，<span data-katex="h:d\rightarrow d'"></span>，并且满足，<span data-katex="f'\circ Tk=Sh\circ f"></span>。

<br/>

### coslice category

取<span data-katex="C"></span>中的某个元素<span data-katex="c_0"></span>，它唯一对应一个函子<span data-katex="T:1\rightarrow C"></span>，

在这种情况下逗号范畴<span data-katex="(T\downarrow S)"></span>，记为<span data-katex="(c_0\downarrow S)"></span>，称为**余切片范畴**（coslice category）。

<br/>

它的对象是，<span data-katex="\left\langle d,f\right\rangle"></span>，

其中，<span data-katex="d"></span>是<span data-katex="D"></span>中的对象，<span data-katex="f:c_0\rightarrow Sd"></span>是<span data-katex="C"></span>中的箭头。

它的箭头是，<span data-katex="h:\left\langle d,f\right\rangle\rightarrow\left\langle d',f'\right\rangle"></span>，

其中，<span data-katex="h:d\rightarrow d'"></span>，并且满足，<span data-katex="f'=Sh\circ f"></span>。

<br/>

如果<span data-katex="S:D\rightarrow C"></span>是一个单位函子（identity functor），

那么<span data-katex="(c_0\downarrow S)"></span>，还可以写为<span data-katex="(c_0\downarrow C)"></span>。

<br/>

### slice category

同理，我们可以定义**切片范畴**（slice category）<span data-katex="(C\downarrow c_0)"></span>，

只需要取<span data-katex="T"></span>为单位函子，<span data-katex="S"></span>为函子<span data-katex="S:1\rightarrow C"></span>即可。

<br/>

### initial object & terminal object

设<span data-katex="C"></span>是一个范畴，<span data-katex="c"></span>是它的一个对象，如果对于<span data-katex="C"></span>中的任意对象<span data-katex="x"></span>，存在唯一的箭头<span data-katex="c\rightarrow x"></span>，

就称<span data-katex="c"></span>是范畴<span data-katex="C"></span>的**始对象**（initial object）。

<br/>

同理，如果对于<span data-katex="C"></span>中的任意对象<span data-katex="x"></span>，存在唯一的箭头<span data-katex="x\rightarrow c"></span>，

则称<span data-katex="c"></span>是范畴<span data-katex="C"></span>的**终对象**（terminal object）。

<br/>

### initial morphism & terminal morphism

设<span data-katex="D,C"></span>是范畴，<span data-katex="U:D\rightarrow C"></span>是函子，<span data-katex="c"></span>是范畴<span data-katex="C"></span>中的一个对象，

根据始对象的定义，余切片范畴<span data-katex="(c\downarrow U)"></span>的始对象<span data-katex="\left\langle d,f\right\rangle"></span>，满足以下条件，

对于范畴中的任意对象，<span data-katex="\left\langle d',f'\right\rangle"></span>，

存在唯一的箭头，<span data-katex="h:d\rightarrow d'"></span>，使得<span data-katex="f'=Uh\circ f"></span>。

<br/>

该条件称为，**初始性质**（initial property），

始对象<span data-katex="\left\langle d,f\right\rangle"></span>，称为从对象<span data-katex="c"></span>到函子<span data-katex="U"></span>的**始态射**（initial morphism）。

<br/>

同理，我们把切片范畴<span data-katex="(U\downarrow c)"></span>的终对象，

定义为从函子<span data-katex="U"></span>到对象<span data-katex="c"></span>的**终态射**（terminal morphism），

终对象所满足的性质，称为**终止性质**（terminal property）。

<br/>

在不引起歧义的情况下，

我们将始态射和终态射统称为**泛态射**（universal morphism）。

<br/>

### adjoint functor

设<span data-katex="D,C"></span>是范畴，<span data-katex="U:D\rightarrow C"></span>是函子，<span data-katex="c_1,c_2"></span>是范畴<span data-katex="C"></span>中的对象，

<span data-katex="\left\langle d_1,f_1\right\rangle"></span>是从对象<span data-katex="c_1"></span>到函子<span data-katex="U"></span>的始态射，<span data-katex="f_1:c_1\rightarrow U(d_1)"></span>，

<span data-katex="\left\langle d_2,f_2\right\rangle"></span>是从对象<span data-katex="c_2"></span>到函子<span data-katex="U"></span>的始态射，<span data-katex="f_2:c_2\rightarrow U(d_2)"></span>，

根据初始性质（initial property），

对于<span data-katex="C"></span>中的箭头<span data-katex="h:c_1\rightarrow c_2"></span>，存在<span data-katex="D"></span>中唯一的箭头<span data-katex="g:d_1\rightarrow d_2"></span>，

使得，<span data-katex="f_2\circ h=Ug\circ f_1"></span>。

<br/>

以上定义了一个从范畴<span data-katex="C"></span>到<span data-katex="D"></span>的一个对应关系，

我们把范畴<span data-katex="C"></span>中的对象<span data-katex="c_1,c_2"></span>，分别对应到了范畴<span data-katex="D"></span>的对象<span data-katex="d_1,d_2"></span>上，

把范畴<span data-katex="C"></span>中的箭头<span data-katex="h:c_1\rightarrow c_2"></span>，对应到了范畴<span data-katex="D"></span>的箭头<span data-katex="g:d_1\rightarrow d_2"></span>上。

<br/>

如果范畴<span data-katex="C"></span>中的任意对象都满足这个条件（初始性质），

我们就找到了一个从范畴<span data-katex="C"></span>到范畴<span data-katex="D"></span>的函子，<span data-katex="F:C\rightarrow D"></span>，

<span data-katex="F"></span>称为<span data-katex="U"></span>的**左伴随函子**（left adjoint），<span data-katex="U"></span>称为<span data-katex="F"></span>的**右伴随函子**（right adjoint），记为<span data-katex="F\dashv U"></span>。

<br/>

范畴<span data-katex="C"></span>中的一族箭头<span data-katex="f_1,f_2,\cdots"></span>，构成了一个自然变换，<span data-katex="N:id_C\rightarrow U\circ F"></span>，其中<span data-katex="id_C"></span>是范畴<span data-katex="C"></span>的单位自函子。

<br/>

伴随函子的概念还可以用hom-set来描述，

设<span data-katex="D"></span>和<span data-katex="C"></span>都是范畴，<span data-katex="U:D\rightarrow C"></span>，<span data-katex="F:C\rightarrow D"></span>是函子，如果<span data-katex="F\dashv U"></span>，

那么，对于<span data-katex="D"></span>中的任意对象<span data-katex="d"></span>，<span data-katex="C"></span>中的任意对象<span data-katex="c"></span>，<span data-katex="\varphi:hom_D(Fc,d)\rightarrow hom_C(c,Ud)"></span>是一个双射，

且对于任意的<span data-katex="k,f\in hom_D(Fc,d),h\in hom_C(c,Ud)"></span>，有<span data-katex="\varphi(k\circ f)=Uk\circ\varphi f"></span>，<span data-katex="\varphi(f\circ Fh)=\varphi f\circ h"></span>。

<br/>

### algebra

在泛代数（universal algebra）中，一个**代数**（algebra）或者说一个代数结构（algebra structure），

由一个集合<span data-katex="A"></span>以及集合<span data-katex="A"></span>上是一系列运算构成。

集合<span data-katex="A"></span>上的<span data-katex="n"></span>元运算是一个函数，它将<span data-katex="A"></span>中的<span data-katex="n"></span>个元素，映射为一个，

代数中所有运算的集合记为<span data-katex="\Omega"></span>，我们称该代数是一个**<span data-katex="\Omega"></span>类型的代数**。

<br/>

在泛代数和伴随函子之间有紧密的联系，

假设范畴<span data-katex="Alg_\tau"></span>，由所有<span data-katex="\tau"></span>类型的代数构成，

遗忘函子<span data-katex="G:Alg_\tau\rightarrow Set"></span>，具有左伴随函子<span data-katex="F"></span>，

则对于范畴<span data-katex="Set"></span>中的任意集合<span data-katex="S"></span>，<span data-katex="FS"></span>给出了由<span data-katex="S"></span>生成的，类型为<span data-katex="\tau"></span>的**自由代数**（free algebra），

自由代数中的对象，称为**自由对象**（free object）。

<br/>

### Kleene closure

集合<span data-katex="V"></span>的**克林闭包**（Kleene closure）由下式定义，

<span data-katex="V^*=\;{\tiny\begin{matrix}^{\scriptsize}\\ \normalsize \cup \\ ^{\scriptsize i\in N}\end{matrix} }\;V_i=V_0\cup V_1\cup V_2\cup\cdots"></span>

其中，<span data-katex="V_0=\{\epsilon\}"></span>，<span data-katex="V_1=V"></span>，<span data-katex="V_{i+1}=\{uv:u\in V_i,v\in V\}"></span>。

<br/>

<span data-katex="V^*"></span>中的元素称为**字符串**（string），<span data-katex="V_{i+1}"></span>定义中的<span data-katex="uv"></span>称为字符串的**连接**操作。

<br/>

### free monoid

<span data-katex="V^*"></span>中所有的字符串，以空串<span data-katex="\{\epsilon\}"></span>作为单位元，以连接操作作为群乘法，构成了一个幺半群（monoid），

称为由<span data-katex="V"></span>生成的**自由幺半群**（free monoid）。

<br/>

设范畴<span data-katex="Mon"></span>为所有的幺半群构成的范畴，它的对象为具体的某个幺半群，它的箭头为幺半群之间的群同态。

设范畴<span data-katex="Set"></span>为所有的集合构成的范畴，它的对象为具体的某个集合，它的箭头由集合之间的映射。

<br/>

设<span data-katex="U:Mon\rightarrow Set"></span>为范畴<span data-katex="Mon"></span>到<span data-katex="Set"></span>之间的遗忘函子，我们定义，

它将范畴<span data-katex="Mon"></span>中的幺半群，映射为其元素集合，

它将范畴<span data-katex="Mon"></span>中的群同态，映射为群元素集合之间的映射。

则<span data-katex="Set"></span>中某集合<span data-katex="\Sigma"></span>上的自由幺半群<span data-katex="\Sigma^*"></span>，就是由该集合生成的自由代数。

<br/>

### proof

要证<span data-katex="\Sigma^*"></span>是一个由<span data-katex="\Sigma"></span>生成的自由代数，

只需证明<span data-katex="\left\langle\Sigma^*,f\right\rangle"></span>是对象<span data-katex="\Sigma"></span>到函子<span data-katex="U"></span>的始态射，

其中，<span data-katex="f"></span>是范畴<span data-katex="Set"></span>中的箭头（集合间的映射）<span data-katex="f:\Sigma\rightarrow\Sigma^*"></span>。

<br/>

始态射<span data-katex="\left\langle\Sigma^*,f\right\rangle"></span>是余切片范畴<span data-katex="(\Sigma\downarrow Mon)"></span>的始对象，且满足初始性质，

对于范畴<span data-katex="Mon"></span>中的任意幺半群<span data-katex="(M,*)"></span>，给定范畴<span data-katex="Set"></span>中的任意箭头（集合间的映射）<span data-katex="h:\Sigma\rightarrow M"></span>，

存在唯一的<span data-katex="Mon"></span>中的箭头（群同态）<span data-katex="g:\Sigma^*\rightarrow M"></span>，使得，<span data-katex="h=Ug\circ f"></span>，

因为，群同态<span data-katex="g:\Sigma^*\rightarrow M"></span>已经表示成集合的映射了，所以，<span data-katex="Ug"></span>可以表示为<span data-katex="g"></span>。

<br/>

即，需要证明集合<span data-katex="\Sigma"></span>到<span data-katex="M"></span>函数<span data-katex="h:\Sigma\rightarrow M"></span>，决定了一个唯一群同态<span data-katex="g:\Sigma^*\rightarrow M"></span>。

<br/>

我们使用数学归纳法进行证明，

因为<span data-katex="\Sigma^*"></span>由多个不相交的子集<span data-katex="\Sigma_i"></span>构成，

<span data-katex="g"></span>可以看做从由多个分量组成，<span data-katex="g_i:\Sigma_i\rightarrow M"></span>。

<br/>

根据<span data-katex="\Sigma_1"></span>的定义，<span data-katex="\Sigma_1=\Sigma"></span>，所以<span data-katex="g_1:\Sigma\rightarrow M"></span>是唯一确定的，只能是<span data-katex="h"></span>，

又<span data-katex="\Sigma_0=\{\epsilon\}"></span>，所以<span data-katex="g_0:\{\epsilon\}\rightarrow M"></span>，如果<span data-katex="g_0"></span>是群同态，则必须<span data-katex="g_0(\epsilon)=e"></span>，其中<span data-katex="e"></span>为<span data-katex="M"></span>的单位元，所以<span data-katex="g_0"></span>也是唯一确定的。

此外，要想<span data-katex="g_{i+1}"></span>是群同态，必须有<span data-katex="g_{i+1}(uv)=g_i(u)g(v)"></span>，其中<span data-katex="uv\in\Sigma_{i+1},u\in\Sigma_i,v\in\Sigma"></span>，所以<span data-katex="g_{i+1}:\Sigma_{i+1}\rightarrow M"></span>也是唯一确定的。

<br/>

因此，<span data-katex="g"></span>如果是一个群同态，就可以由<span data-katex="h"></span>唯一确定。

<br/>

总之，函数<span data-katex="h:\Sigma\rightarrow M"></span>确定了唯一的群同态<span data-katex="g:\Sigma^*\rightarrow M"></span>，

使得<span data-katex="h=g\circ f"></span>，其中<span data-katex="f:\Sigma\rightarrow M"></span>，

因此，<span data-katex="\Sigma^*"></span>就是由<span data-katex="\Sigma"></span>生成的自由代数。

<br/>

### note

<span data-katex="\Sigma^*"></span>实际上是一个集合，它连同字符串的连接操作构成了一个自由幺半群，

这个自由幺半群在遗忘函子<span data-katex="U:Mon\rightarrow Set"></span>中的像是集合<span data-katex="\Sigma^*"></span>，

<span data-katex="\Sigma"></span>也在范畴<span data-katex="Set"></span>中，但不是自由幺半群在<span data-katex="Set"></span>中的像，它们之间的箭头是<span data-katex="f:\Sigma\rightarrow\Sigma^*"></span>。

<br/>

自由幺半群是一个自由代数，它的生成集是<span data-katex="\Sigma"></span>，而不是它在<span data-katex="Set"></span>中的像<span data-katex="\Sigma^*"></span>。

指的是，对于任意的从生成集<span data-katex="\Sigma"></span>到其他集合<span data-katex="M"></span>的映射<span data-katex="h:\Sigma\rightarrow M"></span>，

存在唯一的群同态<span data-katex="g:\Sigma^*\rightarrow M"></span>（这里用映射表示了群同态），使得初始性质（initial property）成立。

<br/>

同理，**自由单子**（free monad）是由自函子范畴<span data-katex="Functor"></span>生成的单子范畴<span data-katex="Monad"></span>，

自函子范畴<span data-katex="Functor"></span>中的对象是自函子，箭头是自函子之间的自然变换，

单子范畴<span data-katex="Monad"></span>中的对象是单子（由自函子构成的幺半群），箭头是幺半群同态。

<br/>

其中，遗忘函子<span data-katex="U:Monad\to Functor"></span>，

将每一个单子范畴<span data-katex="Monad"></span>中的单子，映射成自函子范畴<span data-katex="Functor"></span>中的函子，

将每一个单子范畴<span data-katex="Monad"></span>中的幺半群同态，映射为自函子范畴<span data-katex="Functor"></span>中的自然变换。

### reference

[Categories for the Working Mathematician 2nd](https://book.douban.com/subject/1823110/)

[Category theory for computer science](http://www.math.mcgill.ca/triples/Barr-Wells-ctcs.pdf)

[A Course in Universal Algebra](https://book.douban.com/subject/1823106/)

<br/>

[Wikipedia: Universal Algebra](https://en.wikipedia.org/wiki/Universal_algebra)

[Wikipedia: Forgetful functor](https://en.wikipedia.org/wiki/Forgetful_functor)

[Wikipedia: Initial and terminal objects](https://en.wikipedia.org/wiki/Initial_and_terminal_objects)

[Wikipedia: Comma Category](https://en.wikipedia.org/wiki/Comma_category)

[Wikipedia: Universal Property](https://en.wikipedia.org/wiki/Universal_property)

[Wikipedia: Adjoint Functor](https://en.wikipedia.org/wiki/Adjoint_functors)

[Wikipedia: Free Object](https://en.wikipedia.org/wiki/Free_object)

[Wikipedia: Free Algebra](https://en.wikipedia.org/wiki/Free_algebra)

<br/>

[Wikipedia: Free Monoid](https://en.wikipedia.org/wiki/Free_monoid)

[Stack Exchange: Why is the free monoid free?](https://math.stackexchange.com/questions/58553/why-is-the-free-monoid-free)

<br/>

[Wikipedia: Free Monad](https://en.wikipedia.org/wiki/Monad_(functional_programming)#Free_monads)
