---
layout: post
categories: Math
title: Pumping Lemma
---

## 1. Regular Languages

### 1.1 Definition of a DFA

A **deterministic finite automaton** consist of:

(1) A finite set of **states**, often denoted <span data-katex="Q"></span>.

(2) A finite set of **input symbols**, often denoted <span data-katex="\Sigma"></span>.

(3) A **transition function** that takes as arguments a state and an input symbol and return a state. The transition function will commonly be denoted <span data-katex="\delta"></span>. In our informal graph representation of automata, <span data-katex="\delta"></span> was represented by arcs between states and the labels on the arcs. If <span data-katex="q"></span> is a state, and <span data-katex="a"></span> is an input symbol, then <span data-katex="\delta(q,a)"></span> is that state <span data-katex="p"></span> such that there is an arc labeled <span data-katex="a"></span> from <span data-katex="q"></span> to <span data-katex="p"></span>.

(4) A **start state**, one of the states in <span data-katex="Q"></span>.

(5) A set of **final** or **accepting** states <span data-katex="F"></span>. The set <span data-katex="F"></span> is subset of <span data-katex="Q"></span>.

<br/ >

A deterministic finite automaton will often be referred to by its acronym: DFA. The most succinct representation of a DFA is a listing of the five components above. In proofs we often talk about a DFA in "five-tuple" notation:

<span data-katex="A=(Q,\Sigma ,\delta ,q_0,F)"></span>

where <span data-katex="A"></span> is the name of the DFA, <span data-katex="Q"></span> is its set of states, <span data-katex="\Sigma"></span> its input symbols, <span data-katex="\delta"></span> its transition function, <span data-katex="q_0"></span> its start state, and <span data-katex="F"></span> its set of accepting states.

<br/ >

### 1.2 Extended transition function

Now we need to make the notion of the language of a DFA precise. To do so, we define an **extended transition function** that describes what happens when we start in any state and follow any sequence of inputs. If <span data-katex="\delta"></span> is our transition function, then the extended transition function constructed from <span data-katex="\delta"></span> will be called <span data-katex="\hat{\delta}"></span>. The extended transition function is a function that takes a state <span data-katex="q"></span> and a string <span data-katex="w"></span> and returns a state <span data-katex="p"></span> -- the state that the automaton reaches when starting in state <span data-katex="q"></span> and processing the sequence of inputs <span data-katex="w"></span>. We define <span data-katex="\hat{\delta}"></span> by induction on the length of the input string, as follows:

<br/ >

**Basic:** <span data-katex="\hat{\delta}(q,\epsilon)"></span>. That is, if we are in state <span data-katex="q"></span> and read no inputs, then we are still in state <span data-katex="q"></span>.

<br/ >

**Induction:** Suppose <span data-katex="w"></span> is a string of form <span data-katex="xa"></span>; that is, <span data-katex="a"></span> is the last symbol of <span data-katex="w"></span>, and <span data-katex="x"></span> is the string consisting of all but the last symbol. For example, <span data-katex="w=1101"></span> is broken into <span data-katex="x=110"></span> and <span data-katex="a=1"></span>. Then

<span data-katex="\hat{\delta}(q,w)=\delta(\hat{\delta}(q,x),a)"></span>

<br/ >

### 1.3 The Pumping Lemma for Regular Languages

Let <span data-katex="L"></span> be a regular language. Then there exists a constants <span data-katex="n"></span> (which depends on <span data-katex="L"></span>) such that for every string <span data-katex="w"></span> in <span data-katex="L"></span> such that <span data-katex="|w|\geqslant n"></span>, we can break <span data-katex="w"></span> into three strings, <span data-katex="w=xyz"></span>, such that:

(1) <span data-katex="y\neq \epsilon"></span>

(2) <span data-katex="|xy|\leqslant n"></span>

(3) For all <span data-katex="k\geqslant 0"></span>, the string <span data-katex="xy^kz"></span> is also in <span data-katex="L"></span>.

<br/ >

That is, we can always find a nonempty string <span data-katex="y"></span> not too far from the beginning of <span data-katex="w"></span> that can be "pumped"; that is, repeating <span data-katex="y"></span> any number of times, or deleting it (the case <span data-katex="k=0"></span>), keeps the resulting string in the language <span data-katex="L"></span>.

<br/ >

**Proof:**
Suppose <span data-katex="L"></span> is regular. Then <span data-katex="L=L(A)"></span> for some DFA <span data-katex="A"></span>. Suppose <span data-katex="A"></span> has <span data-katex="n"></span> states. Now, consider any string <span data-katex="w"></span> of length <span data-katex="n"></span> or more, say <span data-katex="w=a_1a_2\cdots a_m"></span>, where <span data-katex="m\geqslant n"></span> and each <span data-katex="a_i"></span> in an input symbol. For <span data-katex="i=0,1,\cdots ,n"></span> define state <span data-katex="p_i"></span> to be <span data-katex="\hat{\delta}(q_0,a_1a_2\cdots a_i)"></span>, where <span data-katex="\delta"></span> is the transition function of <span data-katex="A"></span>, and <span data-katex="q_0"></span> is the start state of <span data-katex="A"></span>. That is, <span data-katex="p_i"></span> is the state <span data-katex="A"></span> is in in after reading the first <span data-katex="i"></span> symbols of <span data-katex="w"></span>. Note that <span data-katex="p_0=q_0"></span>.

<br/ >

By the [pigeonhole principle](https://en.wikipedia.org/wiki/Pigeonhole_principle), it is not possible for the <span data-katex="n+1"></span> different <span data-katex="p_i"></span>'s for <span data-katex="i=0,1,\cdots ,n"></span> to be distinct, since there are only <span data-katex="n"></span> different states. Thus, we can find two different integers <span data-katex="i"></span> and <span data-katex="j"></span>, with <span data-katex="0\leqslant i\leqslant j\leqslant n"></span>, such that <span data-katex="p_i=p_j"></span>. Now, we can break <span data-katex="w=xyz"></span> as follows:

(1) <span data-katex="x=a_1a_2\cdots a_i"></span>

(2) <span data-katex="y=a_{i+1}a_{i+2}\cdots a_j"></span>

(3) <span data-katex="z=a_{j+1}a_{j+2}\cdots a_m"></span>

<br/ >

That is, <span data-katex="x"></span> takes us to <span data-katex="p_i"></span> once; <span data-katex="y"></span> takes us from <span data-katex="p_i"></span> back to <span data-katex="p_i"></span> (since <span data-katex="p_i"></span> is also <span data-katex="p_j"></span>), and <span data-katex="z"></span> is the balance of <span data-katex="w"></span>. The relationships among the strings and states are suggested by Figure below. Note that <span data-katex="x"></span> may be empty, in the case that <span data-katex="i=0"></span>. Also, <span data-katex="z"></span> may be empty if <span data-katex="j=n=m"></span>. However, <span data-katex="y"></span> can not be empty, since <span data-katex="i"></span> is strictly less than <span data-katex="j"></span>.

<br/ >

![](http://upload-images.jianshu.io/upload_images/1023733-43bdf83dc793438f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Figure: Every string longer than the number of states must cause a state to repeat.

<br/ >

Now, consider what happens if the automaton <span data-katex="A"></span> receives the input <span data-katex="xy^kz"></span> for any <span data-katex="k\geqslant 0"></span>. If <span data-katex="k=0"></span>, then the automaton goes from the start state <span data-katex="q_0"></span> (which is also <span data-katex="p_0"></span>) to <span data-katex="p_i"></span> on input <span data-katex="x"></span>. Since <span data-katex="p_i"></span> is also <span data-katex="p_j"></span>, it must be that <span data-katex="A"></span> goes from <span data-katex="p_i"></span> to the accepting state shown in Figure above on input <span data-katex="z"></span>. Thus <span data-katex="A"></span> accepts <span data-katex="xz"></span>.

<br/ >

If <span data-katex="k\geqslant 0"></span>, then <span data-katex="A"></span> goes from <span data-katex="q_0"></span> to <span data-katex="p_i"></span> on input <span data-katex="x"></span>, circles from <span data-katex="p_i"></span> to <span data-katex="p_i"></span> <span data-katex="k"></span> times on input <span data-katex="y^k"></span>, and then goes to the accepting state on input <span data-katex="z"></span>. Thus, for any <span data-katex="k\geqslant 0"></span>, <span data-katex="xy^kz"></span> is also accepted by <span data-katex="A"></span>; that is, <span data-katex="xy^kz"></span> is in <span data-katex="L"></span>.

<br/ >

## 2. Context-Free Languages

### 2.1 Definition of Context-Free Grammars

There are four important components in a grammatical description of a language:

(1) There is a finite set of symbols that form the strings of the language being defined. We call this alphabet the **terminals**, or **terminal symbols**.

(2) There is a finite set of **variables**, also called sometimes **nonterminals** or **syntactic categories**. Each variable represent a language; i.e., a set of strings.

(3) One of the variables represents the language being defined; it is called the **start symbol**. Other variables represent auxiliary classes of strings that are used to help define the language of the start symbol.

(4) There is a finite set of **productions** or **rules** that represent the recursive definition of a languages. Each production consists of:

a) A variable that is being (partially) defined by the production. This variable is often called the **head** of the produciton.

b) The production symbol <span data-katex="\rightarrow"></span>.

c) A string of zero or more terminals and variables. This string, called the body of the production, represents one way to form strings in the languages of the variables of the head. In so doing, we leave terminals unchanged and substitue for each variable of the body any string that is known to be in the language of that variable.

<br/ >

The four components just described form a **context-free grammar**, or just **grammar**, or CFG. We shall represent a CFG <span data-katex="G"></span> by its four components, that is, <span data-katex="G=(V,T,P,S)"></span>, where <span data-katex="V"></span> is the set of variables, <span data-katex="T"></span> the terminals, <span data-katex="P"></span> the set of productions, and <span data-katex="S"></span> the start symbol.

<br/ >

### 2.2 Chomsky Normal Form

**Theorem**

If <span data-katex="G"></span> is a CFG generating a language that contains at least one string other than <span data-katex="\epsilon"></span>, then there is another CFG <span data-katex="G_1"></span> such that <span data-katex="L(G_1)=L(G)-\{\epsilon\}"></span>, and <span data-katex="G_1"></span> has no <span data-katex="\epsilon"></span>-productions, unit productions, or useless symbols.

<br/ >

We complete our study of grammatical simplifications by showing that every nonemtpy CFL without <span data-katex="\epsilon"></span> has a grammar <span data-katex="G"></span> in which all productions are in one of two simple forms, either:

(1) <span data-katex="A\rightarrow BC"></span>, where <span data-katex="A"></span>, <span data-katex="B"></span> and <span data-katex="C"></span>, are each variables, or 

(2) <span data-katex="A\rightarrow a"></span>, where <span data-katex="A"></span> is a variable and <span data-katex="a"></span> is a terminal.

<br/ >

Further, <span data-katex="G"></span> has no useless symbols. Such a grammar is said to be in **Chomsky Normal Form**, or CNF.

<br/ >

**Theorem**

If <span data-katex="G"></span> is a CFG whose language contains at least one string other than <span data-katex="\epsilon"></span>, then there is a grammar <span data-katex="G_1"></span> in Chomsky Normal Form, such that <span data-katex="L(G_1)=L(G)-\{\epsilon\}"></span>.

<br/ >

### 2.3 Parse Trees

Let <span data-katex="G=(V,T,P,S)"></span> be a CFG. If the recursive inference procedure tells us that terminal string <span data-katex="w"></span> is in the language of variable <span data-katex="A"></span>, then there is a parse tree with root <span data-katex="A"></span> and yield <span data-katex="w"></span>.

![](http://upload-images.jianshu.io/upload_images/1023733-2c93eb7c6f29be7c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/ >

**Theorem**

Suppose we have a parse tree according to a Chomsky-Normal-Form grammar <span data-katex="G=(V,T,P,S)"></span>, and suppose that the yield of the tree is a terminal string <span data-katex="w"></span>. If the length of the longest path is <span data-katex="n"></span>, then <span data-katex="|w|\leqslant 2^{n-1}"></span>.

<br/ >

### 2.4 The Pumping Lemma for Context-Free Languages

The pumping lemma for CFL's is quite similar to the pumping lemma for regular languages, but we break each string <span data-katex="z"></span> in the CFL <span data-katex="L"></span> into five parts, and we pump the second and fourth, in tandem.

<br/ >

Let <span data-katex="L"></span> be a CFL. Then there exists a constant <span data-katex="n"></span> such that if <span data-katex="z"></span> is any string in <span data-katex="L"></span> such that <span data-katex="|z|"></span> is at least <span data-katex="n"></span>, then we can write <span data-katex="z=uvwxy"></span>, subject to the following conditions:

(1) <span data-katex="|vwx|\leqslant n"></span>. That is, the middle portion is not too long.

(2) <span data-katex="vx\neq \epsilon"></span>. Since <span data-katex="v"></span> and <span data-katex="x"></span> are the pieces to be "pumped", this condition says that at least one of the strings we pump must not be empty.

(3) For all <span data-katex="i\geqslant 0"></span>, <span data-katex="uv^iwx^iy"></span> is in <span data-katex="L"></span>. That is, the two string <span data-katex="v"></span> and <span data-katex="x"></span> may be "pumped" any number of times, including <span data-katex="0"></span>, and the resulting string will still be a member of <span data-katex="L"></span>.

<br/ >

**Proof:**
Our first step is to find a Chomsky-Normal-Form grammar <span data-katex="G"></span> for <span data-katex="L"></span>. Technically, we cannot find such a grammar if <span data-katex="L"></span> is the CFL <span data-katex="\varnothing"></span> or <span data-katex="\{\epsilon \}"></span>. However, if <span data-katex="L=\varnothing"></span> then the statement of the theorem, which talks about a string <span data-katex="z"></span> in <span data-katex="L"></span> surely cannot be violated, since there is no such <span data-katex="z"></span> in <span data-katex="\varnothing"></span>. Also, the CNF grammar <span data-katex="G"></span> will actually generate <span data-katex="L-\{\epsilon\}"></span>, but that is again not of importance, since we shall surely pick <span data-katex="n>0"></span>, in which case <span data-katex="z"></span> cannot be <span data-katex="\epsilon"></span> anyway.

<br/ >

Now, starting with a CNF grammar <span data-katex="G=(V,T,P,S)"></span> such that <span data-katex="L(G)=L=\{\epsilon\}"></span>, let <span data-katex="G"></span> have <span data-katex="m"></span> variables. Choose <span data-katex="n=2^m"></span>. Next suppose that <span data-katex="z"></span> in <span data-katex="L"></span> is of length at least <span data-katex="n"></span>. Because any parse tree whose longest path is of length <span data-katex="m"></span> or less must have a yield of length <span data-katex="2^{m-1}=n/2"></span> or less. Such a parse tree cannot have yield <span data-katex="z"></span>, because <span data-katex="z"></span> is too long. Thus, any parse tree with yield <span data-katex="z"></span> has a path of length at least <span data-katex="m+1"></span>.

<br/ >

![](http://upload-images.jianshu.io/upload_images/1023733-67178ea72804bcbb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Figure above suggests the longest path in the tree for <span data-katex="z"></span>, where <span data-katex="k"></span> is at least <span data-katex="m"></span> and the path is of length <span data-katex="k+1"></span>. Since <span data-katex="k\geqslant m"></span>, there are at least <span data-katex="m+1"></span> occurrences of variables <span data-katex="A_0,A_1,\cdots ,A_k"></span> on the path. As there are only <span data-katex="m"></span> different variables in <span data-katex="V"></span>, at least two of the last <span data-katex="m+1"></span> variables on the path (that is, <span data-katex="A_{k-m}"></span> through <span data-katex="A_k"></span>, inclusive) must be the same variable. Suppose <span data-katex="A_i=A_j"></span>, where <span data-katex="k-m\leqslant i<j\leqslant k"></span>.

<br/ >

Then it is possible to divide the tree as shown in Figure bellow.

![](http://upload-images.jianshu.io/upload_images/1023733-a7391506188759fe.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/ >

String <span data-katex="w"></span> is the yield of the subtree rooted at <span data-katex="A_j"></span>. String <span data-katex="v"></span> and <span data-katex="x"></span> are the strings to the left and right, repectively, of <span data-katex="w"></span> in the yield of the larger subtree rooted at <span data-katex="A_i"></span>. Note that, since there are no unit productions, <span data-katex="v"></span> and <span data-katex="x"></span> could not both be <span data-katex="\epsilon"></span>, although one could be. Finally, <span data-katex="u"></span> and <span data-katex="y"></span> are those portions of <span data-katex="z"></span> that are to the left and right, respectively, of the subtree rooted at <span data-katex="A_i"></span>.

<br/ >

If <span data-katex="A_i=A_j=A"></span>, then we can construct new parse trees from the original tree, as suggested in Figure bellow (a). First we may replace the subtree rooted at <span data-katex="A_i"></span>, which has yield <span data-katex="vwx"></span>, by the subtree rooted at <span data-katex="A_j"></span>, which has yield <span data-katex="w"></span>. The reason we can do so is that both of these trees have root labeled <span data-katex="A"></span>. The resulting tree is suggested in Figure bellow (b); it has yield <span data-katex="uwy"></span> and corresponds to the case <span data-katex="i=0"></span> in the pattern of strings <span data-katex="uv^iwx^iy"></span>.

![](http://upload-images.jianshu.io/upload_images/1023733-b043df1df50b4bad.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/ >

Another option is suggested by Figure bellow. There, we have replaced the subtree rooted at <span data-katex="A_j"></span> by the entire subtree rooted at <span data-katex="A_i"></span>. Again, the justification is that we are substituting one tree with root labeled <span data-katex="A"></span> for another tree with the same root label. The yield of this tree is <span data-katex="uv^2wx^2y"></span>. Were we to then replace the subtree of Figure below with yield <span data-katex="w"></span> by the largar subtree with yield <span data-katex="vwx"></span>, we would have a tree with yield <span data-katex="uv^3wx^3y"></span>, and so on, for any exponent <span data-katex="i"></span>. Thus, there are parse trees in <span data-katex="G"></span> for all strings of the form <span data-katex="uv^iwx^iy"></span>, and we have almost proved the pumping lamma.

![](http://upload-images.jianshu.io/upload_images/1023733-ae51262c073baa7d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

<br/ >

The remaining detail is condition (1), which says that <span data-katex="|vwx|\leqslant n"></span>. However, we picked <span data-katex="A_i"></span> to be close to the buttom of the tree; that is <span data-katex="k-i\leqslant m"></span>. Thus, the longest path in the subtree rooted at <span data-katex="A_i"></span> is no greater than <span data-katex="m+1"></span>. Because the subtree rooted at <span data-katex="A_i"></span> has a yield whose length is no greater than <span data-katex="2^m=n"></span>.

<br/ >

## Reference
[Introduction to Automata Theory Languages and Computation](https://book.douban.com/subject/2249114/)
