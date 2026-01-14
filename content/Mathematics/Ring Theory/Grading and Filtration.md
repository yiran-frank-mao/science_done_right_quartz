---
updated: 2025-02-09
tags:
  - algebra
completed: true
---
## Graded Algebra and Filtered Algebra

> [!definition] Graded Algebra
> A *graded algebra* is an [[Non-Commutative Rings#^2c3d07|algebra]] $A$ with a linear decomposition $A=\bigoplus_{n=0}^{\infty} A_{n}$ such that
> - each $A_{n}$ is a subspace of $A$,
> - $a\in A_{k}$, $b\in A_{l}$ implies $ab \in A_{k+l}$,
>
> We call all $a\in A_{k}$ homogeneous (elements) of degree $k$.
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/graded_algebra.svg" alt="graded_algebra" style="width:60%;">
> Suppose $A$ and $B$ are graded algebras, then a map $f\colon A\to B$ between graded algebras is a graded homomorphism if $f(A_{n})\subseteq B_{n}$.
> Hence we have a [[Structure of Categories#^2f5c3a|category]] of graded algebras $\mathsf{GrAlg}$. ^9b78c3

> [!definition] Degree Completed Graded Algebra
> A degree completed graded algebra is a degree completion of a graded algebra $A$ by taking the [[Limits and Colimits#^24df42|inverse limit]].

> [!remark] Direct sum vs. Direct product
> As vector spaces, the only difference is that the former consists of finite linear combinations of homogeneous elements, whilst in the latter, we also have infinite linear combinations: think power series versus polynomials.

> [!warning]
> We will allow a graded algebra to be either a direct sum, or a direct product, and will restrict to graded algebras which are direct products (degree completed graded algebra), and just call it graded algebra, as this is the most common case in knot theory.

<u><b>e.g.</b></u>  Suppose $\newcommand{\C}{\mathbb{C}}A=\C[x_{1},x_{2},\dots,x_{r}]$ is polynomials in $r$ variables, then $$A_{n}=\{\text{homogeneous degree $n$ polynomials}\}$$

> [!remark]
> Graded algebra is good in the sense that:
> - degree is a notion of complexity (of computation).
> - easy to deal with computation (degree by degree or up to degree $n$)
> - can apply induction on degree
>$\quad$

> [!definition] Filtered Algebra
> A *filtered algebra* is an [[Non-Commutative Rings#^2c3d07|algebra]] $A$ with a sequence of nested [[Homomorphisms and Ideals#^395472|ideals]]: $$A=F_{0} \supseteq F_{1} \supseteq F_{2} \supseteq F_{3} \supseteq \dots$$such that $a\in F_{i}$, $b\in F_{j}$ implies $ab\in F_{i+j}$.
> Suppose $A=F_{0} \supseteq F_{1} \supseteq F_{2} \supseteq \dots$ and $B=G_{0} \supseteq G_{1} \supseteq G_{2} \supseteq \dots$ are filtered algebras, then an algebra homomorphism $f\colon A\to B$ between filtered algebras is a filtered homomorphism if $f(F_{i})\subseteq G_{i}$.
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/filtered_algebra.svg" alt="graded_algebra" style="width:30%;">
> Hence we have a [[Structure of Categories#^2f5c3a|category]] of filtered algebras $\mathsf{FiltAlg}$.

> [!remark]
> This is not as good as graded algebra because, for instance, though $a\in F_{2}$, $b\in F_{3}$ implies $ab\in F_{5}$, as $F_{5}\supseteq F_{6}\dots$, $ab$ could actually be in $F_{100}$.

<u><b>e.g.</b></u>  Any graded algebra is a filtered algebra, since we can take $F_{i}:=\prod_{j\geq i} A_{j}$. And $F_{i}$ is an ideal because any $a\in F_{k}$ and $b\in F_{i}$ implies $ab\in F_{k+i}\subseteq F_{i}$.

## The Associated Graded Functor

> [!definition] Associated Graded Algebra
> Given a filtered algebra $F_{0} \supseteq F_{1} \supseteq F_{2}\supseteq\dots$, we can define a graded algebra by taking $A_{n}:=F_{n}/F_{n+1}$. We denote this graded algebra as $\newcommand{\gr}{\operatorname{gr}} \gr A:=\prod_{n} F_{n}/F_{n+1}$, and define the multiplication of components by $$(a+F_{k+1})(b+F_{l+1}):=ab+F_{k+l+1},$$and extend to all elements of $\gr A$ via Cauchy product formula: $$ (ab)_{n} = \sum_{i=0}^{n} a_{i} b_{n-i} $$for all $a,b\in \gr A$.
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/associated_graded_algebra.svg" alt="" style="width:65%;"> ^ce0272

> [!proposition]
> $\gr$ forms a [[Functoriality and Naturality#^653948|functor]] from $\mathsf{FiltAlg}$ to $\mathsf{GrAlg}$.

*Proof*  Suppose $A=F_{0} \supseteq F_{1} \supseteq F_{2}\supseteq\cdots$ and $B=G_{0} \supseteq G_{1} \supseteq G_{2}\supseteq\cdots$ are filtered algebras, and $f\colon A\to B$ is a filtered homomorphism. Then we have a graded homomorphism $\gr f\colon \gr A\to \gr B$ defined by $$ \gr f (a_{0}+F_{1},a_{1}+F_{2},\cdots) := (f(a_{0})+G_{1},f(a_{2})+G_{2},\cdots).$$It is clear that $\gr f$ is graded, because $f(F_{n})\subseteq G_{n}$. Moreover, $\gr$ is a functor because it preserves composition and identity. $\square$

> [!proposition]
> A quotient of a graded algebra is graded precisely when the ideal is homogeneous (i.e., $J=\bigoplus_{i=0}^{n}(A_{i}\cap J)$). 
> A quotient of a filtered algebra is always filtered.
> 

## The Pro-Unipotent Filtration

In this section we define a famous filtration on the [[Non-Commutative Rings#^a15722|group algebra]] $\newcommand{\F}{\mathbb{F}}\F G$, called the pro-unipotent filtration, studied extensively in group theory and algebraic geometry.

> [!definition] Augmentation Map
> The augmentation map $\iota\colon \F G\to \F$ is defined by sending each group element to $1$: $$ \iota \left( \sum_{g\in G} c_{g} g \right) = \sum_{g\in G} c_{g} $$where $c_{g}\in \F$ and $g\in G$.

*Proof*  The augmentation map is clearly an algebra homomorphism because $\iota(gh)=1=\iota(g)\iota(h)$. $\square$

> [!definition] Augmentation Ideal
> An augmentation ideal $I\triangleleft \C G$ is the kernel of the augmentation map. That is, the set of elements of $\F G$ whose coefficients sum to zero.

> [!proposition]
> The product of augmentation ideal for $k$ times is an ideal of the algebra. i.e. $I^{k}\triangleleft \C G$.

*Proof*  For all $a\in \C G$, we have $aI^{k}=(aI)I^{k-1}=II^{k-1}=I^{k}$. $\square$

> [!definition]  Pro-unipotent Filtration
> The pro-unipotent (a.k.a $I$-adic) filtration of a an algebra $A$ is the sequence of ideals: $$A= I^{0}\supseteq I^{1}\supseteq I^{2}\supseteq \cdots$$ where $I^{k}$ is the product of augmentation ideal for $k$ times, that is the ideal generated by products of $k$ elements of $I$.

<u><b>e.g.</b></u>  Consider $\newcommand{\Z}{\mathbb{Z}}\C\Z=\left\{ \sum_{i=-\infty}^{\infty} c_{i}x^{i}\mid c_{i}\in \C, \text{finitely many } c_{i}\neq 0 \right\}$, which is the set of Laurent polynomials, where we identify $\Z=\langle x \rangle$ by convention. Then the augmentation ideal $I$ is the [[Homomorphisms and Ideals#^4a3278|principle ideal]] generated by $x-1$. Because we can write any element in $I$ as $$ \sum_{i=-\infty}^{\infty} c_{i}x^{i} = \sum_{i=-\infty}^{\infty} c_{i}(x^{i}-1), $$which is a linear combination of $x^{i}-1$ for $i\in\Z$. Hence as an ideal, $I$ is generated by $x-1$. And thus one can easily show that $I^{k} = \left\langle (x-1)^{k} \right\rangle$. And it turns out that$$ \gr \C \Z \cong \C [\![   x-1 ]\!] $$ is the ring of formal power series in $x-1$.
