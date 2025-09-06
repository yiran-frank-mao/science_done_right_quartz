---
created: 2024-03-05
updated: 2025-09-01
completed: true
---
## Naturals and Integers

>[!definition] Natural Numbers
>We define the set of natural numbers $\require{mhchem}\newcommand{\R}{\mathbb{R}}\newcommand{\N}{\mathbb{N}}\newcommand{\Z}{\mathbb{Z}}\newcommand{\Q}{\mathbb{Q}} \N$ by the following Peano axioms with successor function $S\colon \N \to \N$.
>- $0$ is a natural number.
>- For every natural number $n$, $S(n)$ is a natural number. That is, the natural numbers are closed under $S$.
>- For all natural numbers $m$ and $n$, if $S(m) = S(n)$, then $m = n$. That is, $S$ is injective.
>- There is no natural number whose successor is $0$.
>- If $M$ is a set such that $0\in M$, and for every $n\in \N$, $n\in M \implies S(n)\in M$, then $M$ contains every natural number. That is the successor function generates all the natural numbers different from $0$.
>$\quad$ ^b4eff7

> [!definition] Addition on Naturals
> Addition is a function $+\colon \N \times\N \to \N$, defined recursively by $$a+0=a,\quad a+S(b)=S(a+b)$$

> [!definition] Multiplication on Naturals
> Multiplication is a function $\times\colon \N \times\N \to \N$. Given addition, it is defined recursively as: $$a\times0 = 0, \quad a\times S(b)=a+(a\times b)$$

> [!proposition]
> $S(0)$ is the multiplicative identity.

> [!definition] Total Order on Naturals
> The standard total order relation $≤$ on natural numbers can be defined as follows,$$a\leq b \text{ if } \exists c\in\N \text{ s.t. } a+c=b.$$

>[!definition] Integers
>We define the integers $\Z$ as a [[Ring, Field and Integral Domain#^575174|field]] of equivalence classes:$$\Z = (\N \times \N) / \sim$$where $\sim$ is an [[Relations and Functions#^14741d|equivalence relation]] defined on $\N \times \N$ as $$(a,b)\sim (c,d) \iff a+d=b+c$$We write $[(a,b)]_{\Z}$ as the corresponding equivalence class. And define $$[(a,b)]_{\Z}+[(c,d)]_{\Z}=[(a+c,b+d)]_{\Z}, \quad [(a,b)]_{\Z}\cdot[(c,d)]_{\Z}=[(ac+bd,ad+bc)]_{\Z}.$$ ^25bad2

## Rationals

>[!definition] Rational Numbers
>We define the rational numbers $\Q$ as a [[Ring, Field and Integral Domain#^575174|field]] of equivalence classes:$$\Q = (\Z \times \Z) / \mathord{\sim}$$where $\sim$ is an [[Relations and Functions#^14741d|equivalence relation]] defined on $\Z \times \Z$ as $$(a,b)\sim (c,d) \iff ad=bc$$We write $[(a,b)]_{\Q}$ as the corresponding equivalence class. And thus define $$\begin{aligned}[]
>[(a,b)]_{\Q}+[(c,d)]_{\Q}=[(ad+bc,bd)]_{\Q}\\
>[(a,b)]_{\Q} \cdot [(c,d)]_{\Q}=[(ac,bd)]_{\Q}\\
>0_{\Q} = [(0,1)]_{\Q}\\
>1_{\Q} = [(1,1)]_{\Q}\\
>[(a,b)]_{\Q}\leq [(c,d)]_{\Q} \text{ if }  (bc-ad)bd \geq 0
>\end{aligned}$$ ^e8a24a

## Reals

>[!definition] $\Q$-Cauchy Equivalence
>For two sequences $(a_n)$ and $(b_n)$ in $\Q$, we say that $(a_n)$ and $(b_{n})$ are $\Q$-Cauchy equivalent if$$\forall \varepsilon>0\in\Q.\exists N\in \N.\quad n\geq N\implies |a_{n}-b_{n}|<\varepsilon$$

> [!proposition]
> $\Q$-Cauchy equivalence is an [[Relations and Functions#^14741d|equivalence relation]].

*Proof*  Clearly it is reflexive as $|a_{n}-a_{n}|=0<\varepsilon$. It is symmetric since$$|a_{n}-b_{n}|<\varepsilon \iff |b_{n}-a_{n}|<\varepsilon$$Suppose $(a_{n})\sim(b_{n})$ and $(b_{n})\sim (c_n)$. For all $\varepsilon>0$, exists $N_{1},N_{2}\in \N$ such that$$\begin{aligned} n\geq N_{1}\implies |a_{n}-b_{n}|<\frac\varepsilon2 \\ n\geq N_{2}\implies |b_{n}-c_{n}|<\frac\varepsilon2\end{aligned}$$Let $N= \max\{N_{1},N_{2}\}$. Suppose $n\geq N$, we have:$$|a_{n}-c_n|\leq|a_{n}-b_{n}|+|b_{n}-c_{n}|<\frac{\varepsilon}{2}+\frac{\varepsilon}{2} = \varepsilon$$Hence $(a_{n})\sim(c_{n})$, proved transitivity. $\square$

>[!definition] Real Numbers
>The real numbers $\R$ is defined as a [[Ring, Field and Integral Domain#^575174|field]] of [[Relations and Functions#^973688|equivalence classes]] of $\Q$-Cauchy sequences. We write $[(a_{n})]_{\R}$ as the corresponding equivalence class. And thus define: $$[(a_{n})_{\R}]\geq [(b_{n})_{\R}] \text{ if } \exists N\in \N \text{ s.t. } a_{n}\geq b_{n} \text{ for all } n>N.$$ ^5fea5c

> [!proposition]
> Every [[Complete Metric Space#^179eeb|Cauchy sequence]] of real numbers converges to a real number.

>[!definition] Interval
>A set $I ⊂\R$ is an (closed) interval if $a,b∈I$, and $a<x <b$ imply $x ∈I$. ^fd03c6

## Archimedean Property

>[!definition] Archimedean Property
>In any [[Ring, Field and Integral Domain#^43843e|ordered field]] $F$, define $f\colon F \to \Q$ such that $$0_{F}\mapsto 0, 1_{F}\mapsto 1$$respect $+,\times$ and order in $\Q$. We say that it has Archimedean property if one of the following equivalent properties hold:
>- $\N$ is not bounded above by any element of $f(F)$.
>- For all $y\in F$ with $y>_{F}0_{F}$, there is $n\in \mathbb{N}$ such that $\frac{1}{n}<_{\Q}f(y)$.
>- For all $x, y \in F$ with $y>_{F}0_{F}$, then there is $n\in \mathbb{N}$ such that $n f(y)>_{\Q}f(x)$.
>$\quad$

We shall check they are equivalent.

*Proof*  $(1)\implies (2)$ Suppose  is not bounded above in $F$. Let $y \in F$ with $y > 0_F$. This implies that $y^{-1}$ is also positive. Since $\mathbb{N}$ is not bounded above, there must exist an integer $n \in \mathbb{N}$ such that $n > y^{-1}$. As , we can multiply both sides by $y$ to get $n \cdot y > 1$. Then, since $n$ is a positive integer, $n^{-1} = \frac{1}{n}$ exists and is positive, so we can multiply by $n^{-1}$ to obtain $y > \frac{1}{n}$.
$(2)\implies (3)$ Suppose that for any $z \in F$ with $z > 0_F$, there exists an $n \in \mathbb{N}$ such that $\frac{1}{n} < z$. Now, consider any $x, y \in F$ where $y > 0_F$.
* If $x \le 0_F$, we can choose $n=1$. Then $n \cdot y = 1 \cdot y = y > 0_F \ge x$, so the property holds.
* If $x > 0_F$, then the element $y \cdot x^{-1}$ is also positive. By our assumption (2), there must be an integer  such that $\frac{1}{n} < y \cdot x^{-1}$. Since both $n$ and $x$ are positive, we can multiply the inequality by $n \cdot x$ to get $x < n \cdot y$.

$(3)\implies (1)$
Suppose that for all $x, y \in F$ with $y > 0_F$, there is an $n \in \mathbb{N}$ such that $n \cdot y > x$. To show that $\mathbb{N}$ is not bounded above, we must show that for any arbitrary element $M \in F$, there is a natural number $k$ such that $k > M$. Let $x=M$ and $y=1_F$. Since $1_F > 0_F$, our assumption (iii) guarantees the existence of a $k \in \mathbb{N}$ such that $k \cdot 1_F > M$. Since $M$ was an arbitrary element of $F$, no upper bound for $\mathbb{N}$ can exist in $F$. $\square$

> [!proposition] 
> The Field of Rational Numbers $\mathbb{Q}$ is Archimedean.

*Proof*  By property (1), we must show that $\mathbb{N}$ is unbounded in $\mathbb{Q}$. For all $[(a,b)] \in \mathbb{Q}$, with $[(a,b)] > 0$, pick a representative $(c,d) \in [a,b)]$ with $d > 0$ in $\mathbb{Z}$. By Archimedean property of $\mathbb{Z}$, there exists $m, n \in \mathbb{N}$ such that $1/m < c$ and $n > d$. Thus $$(mnc-d)mnd> (n - d)mnd > 0.$$Therefore $[(1, mn)] < [(c,d)]$, that is $\frac{1}{m n} < [(a,b)]$. Hence $\Q$ has the Archimedean property. $\square$

>[!proposition]
> Archimedean property holds for $\R$.

*Proof* Suppose $\varphi\colon \R\to\Q$ is the canonical map such that $[(x_{n})]_{\R}$ maps to the limit value of $(x_n)$ in $\mathbb{R}$ if it is convergent. Clearly $\varphi$ is surjective. By Archimedean property of $\Q$, $\N$ is not bounded by $\Q$, thus not bounded by $\varphi(\R)$. Therefore Archimedean property holds for $\R$ as well by (2). $\square$

> [!remark]+
> The Archimedean property is often taken as an axiom for $\mathbb{R}$. For any $y \in \mathbb{R}$ with $y > 0$, the value $1/y$ is a positive real number. A basic property of the real number system is that for any real number, there is a greater integer. Thus, there exists an integer $n > 1/y$.
> 

## Complex Numbers

Although $\R$ is good enough, it is not quite sufficient, for example, it is not [[Fields Construction#^5b9555|algebraically closed]]. So complex numbers come into play. There are mainly two ways to construct complex numbers. The first one is to define them as pairs of real numbers (See [[Complex Numbers#^a81924|here]]), and the second one is to define them as equivalence classes of polynomials (See [[Relations and Maximal Ideals#^a4b259|here]]). The first one is more intuitive (geometric), while the second one is more algebraic.

Following convention, we take the first as our definition:

![[Complex Numbers#^a81924]]

