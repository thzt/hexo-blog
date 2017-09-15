---
layout: post
categories: Logic
title: Hilbert-style和Gentzen-style演绎系统
---

### 1. Proof calculus

在数理逻辑（mathematical logic）中，

证明演算（proof calculus）界定了形式系统（formal system）的不同风格（style）。

最主流的两种风格（style）为，

希尔伯特风格（Hilbert style）和甘岑风格（Gentzen style）。

<br/>

#### 1.1 Hilbert style

希尔伯特风格（Hilbert style）的证明演算（proof calculus），

其断言（judgement）由不包含条件的（unconditional）重言式（tautology）构成，

称为，希尔伯特系统（Hilbert system）。

<br/>

#### 1.2 Gentzen style

甘岑风格（Gentzen style）的证明演算（proof calculus），

其断言（judgement）由包含条件的（unconditional）重言式（tautology）构成。

包括，自然演绎（Natural deduction）和相继式演算（Sequent calculus）。

<br/>

（1）自然演绎（Natural deduction）系统，

断言（judgement）的结论（conclusion）中，

只包含一个命题（propostion）。

<br/>

（2）相继式演算（Sequent calculus）系统，

断言（judgement）的结论（conclusion）中，

可以包含零个或多个命题（propostion）。

<br/>

### 2. Hilbert system

观察系统中断言（judgement）的形式，

是区分演绎系统（deduction system）风格（style）的一种常用方法。

<br/>

希尔伯特系统（Hilbert system）中的断言（judgement）是最简单的，其形式为，

<span data-katex="B"></span>

用以表示任何逻辑系统（logic）中的公式（formula）。

<br/>

例如，一阶逻辑（first-order logic），命题逻辑（propositional logic），

高阶逻辑（higher-order logic），或者模态逻辑（modal logic）。

<br/>

希尔伯特系统（Hilbert system）中的定理（theorem），

指的是一段有效证明（valid proof）的最终结论（concluding judgement）。

<br/>

### 3. Natural deduction

自然演绎（Natural deduction）系统中，其断言（judgement）形式如下，

<span data-katex="A_1,A_2,\cdots,A_n\vdash B"></span>

<br/>

其中，<span data-katex="A_1,A_2,\cdots,A_n"></span>和<span data-katex="B"></span>都是公式（formula），<span data-katex="n\geqslant 0"></span>，

<span data-katex="A_1,A_2,\cdots,A_n"></span>的顺序是无关紧要的。

<br/>

自然演绎（Natural deduction）系统中的定理（theorem），

指的是这样的公式（formula）<span data-katex="B"></span>，

其中，<span data-katex="\vdash B"></span>是一段有效证明（valid proof）的最终结论（concluding judgement）。

<br/>

公式（formula）<span data-katex="A_1,A_2,\cdots,A_n\vdash B"></span>的语义（semantics）如下，

如果每一个<span data-katex="A_1,A_2,\cdots,A_n"></span>成立，那么<span data-katex="B"></span>也成立。

<br/>

### 4.Sequent calculus

相继式演算（Sequent calculus）系统，将自然演绎（Natural deduction）一般化了，

其断言（judgement）的形式如下，

<span data-katex="A_1,A_2,\cdots,A_n\vdash B_1,B_2,\cdots,B_k"></span>

<br/>

其中，<span data-katex="A_1,A_2,\cdots,A_n"></span>称为前项（antecedent），

<span data-katex="B_1,B_2,\cdots,B_k"></span>称为后项（succedent/consequent），

它们合起来称为一个序列（sequent）。

<br/>

和自然演绎（Natural deduction）系统相似，

<span data-katex="A_1,A_2,\cdots,A_n"></span>和<span data-katex="B_1,B_2,\cdots,B_k"></span>都是公式（formula），

<span data-katex="n"></span>和<span data-katex="k"></span>都是非负整数，即断言（judgement）的左右两边都可以为空。

<br/>

相继式演算（Sequent calculus）系统中的定理（theorem），

指的是这样的公式（formula）<span data-katex="B"></span>，

其中，<span data-katex="\vdash B"></span>是一段有效证明（valid proof）的最终结论（concluding judgement）。

<br/>

公式（formula）<span data-katex="A_1,A_2,\cdots,A_n\vdash B_1,B_2,\cdots,B_k"></span>的语义（semantics）如下，

如果每一个<span data-katex="A_1,A_2,\cdots,A_n"></span>成立，那么<span data-katex="B_1,B_2,\cdots,B_k"></span>中至少有一个成立。

<br/>

### Reference

[Proof calculus](https://en.wikipedia.org/wiki/Proof_calculus)

[Hilbert system](https://en.wikipedia.org/wiki/Hilbert_system)

[Natural deduction](https://en.wikipedia.org/wiki/Natural_deduction)

[Sequent calculus](https://en.wikipedia.org/wiki/Sequent_calculus)

