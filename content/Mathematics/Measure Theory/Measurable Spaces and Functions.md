---
created: 2024-08-17
updated: 2024-10-07
tags: []
---
## Measurable Spaces

>[!definition] $\sigma$-Algebra and Measurable Spaces
>Suppose $X$ is a set and $\mathcal{S}$ is a set of subsets of $X$. Then $\mathcal{S}$ is called a *$\sigma$-algebra* on $X$ if it is closed under countable [[Construction of Sets#^678b42|unions]], countable [[Construction of Sets#^408460|intersections]], and complements:
>1. $\emptyset \in \mathcal{S}$;
>2. if $Y\in \mathcal{S}$, then $X\setminus Y\in \mathcal{S}$;
>3. if $Y_{1}, Y_{2}, \dots \in \mathcal{S}$, then $\bigcup_{i=1}^{\infty} Y_{i}\in\mathcal{S}$.
>
> We call such elements of $\mathcal{S}$ *measurable*.
> A *measurable space* is an ordered pair of a set and an associated $\sigma$-algebra $(X, \mathcal{S})$. An element of $\mathcal{S}$ is called an *$\mathcal{S}$-measurable set*, or just a *measurable set*. ^60a516

> [!remark]
> Note that the closedness on countable intersections comes freely from (2) and (3).
> 

<u><b>e.g.</b></u>  
- The standard $\sigma$-algebra on $\R$ is the [[Borel Sets and Real Valued Measurable Functions#^47dc88|Borel $\sigma$-algebra]].
- The following $\sigma$-algebra on $X$ is called the *countable–cocountable $\sigma$-algebra*: $$\mathcal{S}=\{A\subseteq X \mid  A \text{ is countable or } A^{c} \text{ is countable} \}$$This is clearly a $\sigma$-algebra because a countable union of countable sets is still countable. When $X=\R$, every singleton set $\{x\}\in\mathcal{S}$, but their uncountable union in $[0,1]$, which is simply $[0,1]$, is not measurable. This is an example that an uncountable union of sets is not in the $\sigma$-algebra. ^401f01
- For any set $X$, its power set $\mathcal{P}(X)$ is a $\sigma$-algebra on $X$.
- The trivial $\sigma$-algebra on $X$ is $\{\emptyset, X\}$.
$\quad$

> [!proposition]
> Suppose $X$ is a set and $\mathcal{A}$ is a set of subsets of $X$. Then the intersection of all $\sigma$-algebras on $X$ that contain $\mathcal{A}$ is a $\sigma$-algebra on $X$.

*Proof*  Suppose $\mathcal{S}$ is the intersection of all $\sigma$-algebras on $X$ that contain $\mathcal{A}$. Clearly $\emptyset\in \mathcal{S}$. Now for any $Y_{1},Y_{2},\cdots \in\mathcal{S}$, $Y_{1},Y_{2},\cdots$ are in every $\sigma$-algebra that contains $\mathcal{A}$, thus $X\setminus Y_{i}$ and $\bigcup_{i=1}^{\infty} Y_{i}$ are also in every such $\sigma$-algebra. Therefore, $X\setminus Y_{i}\in \mathcal{S}$ and $\bigcup_{i=1}^{\infty} Y_{i}\in \mathcal{S}$. $\square$

## Measurable Functions

> [!definition] Measurable Function
> Suppose $(X, \mathcal{S})$ and $(Y,\mathcal{T})$ are measurable spaces. A function $f \colon X → Y$ is an measurable function if $$f^{-1}(E) \in \mathcal{S}\quad \text{for all } E\in \mathcal{T}.$$
> We usually consider the case where $Y$ is simply $\mathbb{R}$ endowed with the Borel $\sigma$-algebra. In such case, we call $f$ *$\mathcal{S}$-measurable*. ^11c83a

> [!definition] Essential Range
> The essential range of a measurable function $f\colon (X,\mathcal{S})\to (Y,\mathcal{T})$ is the set $$\mathrm{ess\,range}(f):=\{y\in Y\mid \forall U\in \mathcal{T} \text{ with }y\in U, \mu(f^{-1}(U))>0\},$$where $\mu$ is a measure on $(X,\mathcal{S})$.

> [!definition] Convergence in Measure
> Let $(X,\sigma,\mu)$ be a measure space and let $f_{n},f:X\to\mathbb{R}$ (or into a metric space) be measurable. We say that $f_{n}$​ *converges in measure* to $f$ if, for every $\varepsilon>0$,
> $$\mu\left(\{x\in X:|f_n(x)-f(x)|>\varepsilon\}\right)\longrightarrow0 \quad\text{as }n\to\infty.$$
> 

## Measure Spaces

> [!definition] Measure
> Suppose $(X, \mathcal{S})$ is a [[Measurable Spaces and Functions#^60a516|measurable space]]. A *measure* $\mu$ on $(X, \mathcal{S})$ is a function $\mu \colon \mathcal{S} → [0,\infty]$ such that: $\mu(\emptyset)=0$ and $$\mu\left(\bigcup_{k=1}^\infty E_k\right)=\sum_{k=1}^\infty\mu(E_k)$$for any countable collection $\{E_k\}_{k=1}^\infty$ of disjoint sets in $\mathcal{S}$. In this case, we call $(X, \mathcal{S}, \mu)$ a *measure space*. ^c2e020

<u><b>e.g.</b></u>  
- If $X$ is a set, then *counting measure* is the measure $μ$ defined on the $σ$-algebra of all subsets of $X$ by setting $μ(E) = n$ if $E$ is a finite set containing exactly $n$ elements and $μ(E) = ∞$ if $E$ is not a finite set.
- Suppose $X$ is a set, $\mathcal{S}$ is a $σ$-algebra on $X$, and $c ∈ X$. The *Dirac measure* $δ_{c}$ on $(X,\mathcal{S})$ is $$\delta_{c}(E)=\begin{cases}1 \quad \text{if }c\in E, \\ 0 \quad \text{otherwise}.\end{cases}$$
- Consider the countable-cocountable $\sigma$-algebra on $X$. Define a measure on $X$ by $$\mu(E)=\begin{cases}0 \quad \text{if }E\text{ is countable}, \\ 3 \quad \text{otherwise}.\end{cases}$$
- The outer measure is **not** a measure on $(\R,\mathcal{P}(\R))$, but is indeed a measure on $(\R,\mathcal{B})$.
$\quad$

> [!proposition]
> For a measure $\mu$ defined on a measurable space $(X,\mathcal{S})$, the following properties hold:
> - Monotonicity: $\mu(E)\leq \mu(F)$ for $E\subseteq F$;
> - $\mu(F\setminus E)=\mu(F)-\mu(E)$ for $E\subseteq F$ and $\mu(E)<\infty$;
> - Subadditivity: $\mu\left(\bigcup_{i=1}^{\infty} E_{i}\right)\leq \sum^{\infty}_{i}\mu(E_{i})$.
> $\quad$

*Proof*  Observe that for any $E\subset F$, $E$ and $F\setminus E$ are disjoint, and $F=E\cup (F\setminus E)$, thus $$\mu(F)=\mu(E)+\mu(F\setminus E)\geq \mu(E).$$For subadditivity, we can divide the union into disjoint sets. Suppose $G_{n}=\bigcup_{i=1}^{n} E_{i}$, let $F_{1}:=E_{1}$, and $F_{i}:=E_{i}\setminus G_{i-1}$ for $i\geq 2$. Then each $F_{i}$ is disjoint, and we have $$\mu\left(\bigcup_{i=1}^{\infty} E_{i}\right)=\mu\left(\bigcup_{i=1}^{\infty} F_{i}\right)= \sum_{i=1}^{\infty} \mu(F_{i})\leq \sum_{i=1}^{\infty}\mu(E_{i}),$$where the last inequality follows from monotonicity. $\square$

> [!proposition] Measure of Increasing Union
> Suppose $(X,\mathcal{S},\mu)$ is a measure space and $E_{1}\subseteq E_{2}\subseteq \cdots$ is an increasing sequence of sets in $\mathcal{S}$, then $$\mu\left(\bigcup_{k=1}^{\infty} E_{k}\right)=\lim_{k\to \infty} \mu(E_{k}).$$
> 

*Proof*  If $\mu(E_{k})=\infty$ for some $k$, then the both sides are $\infty$. Otherwise, let $E_{0}:=\emptyset$, then $$\mu\left(\bigcup_{k=1}^{\infty} E_{k}\right)=\mu\left(\bigcup_{k}^{\infty}E_{k}\setminus E_{k-1}\right)=\sum_{k=1}^{\infty}\mu(E_{k}\setminus E_{k-1})=\lim_{n\to \infty}\left(\sum_{k=1}^{n} \mu(E_{n})-\mu(E_{n-1})\right)=\lim_{n\to \infty}\mu(E_{n}).$$ $\square$

> [!proposition] Measure of Decreasing Intersection
> Suppose $(X, S, μ)$ is a measure space and $E_{1} ⊇ E_{2} ⊇ \cdots$ is a decreasing sequence of sets in $\mathcal{S}$, with $μ(E_{1}) < \infty$. Then $$\mu\left(\bigcap_{k=1}^\infty E_k\right)=\lim_{k\to\infty}\mu(E_k).$$
> ^9a0cff

*Proof*  By the De Morgan’s Law, we have $$E_1\setminus\bigcap_{k=1}^\infty E_k=\bigcup_{k=1}^\infty(E_1\setminus E_{k}).$$Then we can utilise the above proposition. $\square$

> [!remark]
> Note that if $\mu(E_{1})=\infty$, this may not be true. Consider the standard $(\R,\mathcal{B},  m_{*})$ and the sequence $E_{i}=\R\setminus[-i,i]$. Then $m_{*}(E_{i})=\infty$ for all $i$, so the limit is $\infty$, while the intersection of all these sets is empty, which has zero measure.
> 

> [!proposition]
> Suppose $(X, S, μ)$ is a measure space and $D, E ∈ \mathcal{S}$, with $μ(D ∩ E) < ∞$. Then $$\mu(D\cup E)=\mu(D)+\mu(E)-\mu(D\cap E).$$
> 

*Proof*  We have $$D\cup E=\left(D\setminus(D\cap E)\right)\cup \left(E\setminus(D\cap E)\right)\cup (D\cap E),$$where the right hand side is a disjoint union. Hence, $$\begin{aligned}\mu(D\cup E)&=\mu\left(D\setminus(D\cap E)\right)+\mu\left(E\setminus(D\cap E)\right)+\mu\left(D\cap E\right)\\&=\left(\mu(D)-\mu(D\cap E)\right)+\left(\mu(E)-\mu(D\cap E)\right)+\mu(D\cap E)\\&=\mu(D)+\mu(E)-\mu(D\cap E),\end{aligned}$$as desired. $\square$

> [!definition] $\sigma$-Finite Measure
> A measure space $(X, \mathcal{S},\mu)$ is *$\sigma$-finite* if there exists a countable collection $\{A_{i}\}_{i=1}^{\infty}$ of finitely measurable sets covers $X$. That is, $X=\bigcup_{i=1}^{\infty} A_{i}$, and $\mu(A_{i})<\infty$ for all $i$. ^a59ebb

<u><b>e.g.</b></u>  
- The Lebesgue measure on $\R$ is $\sigma$-finite because $\R=\bigcup_{i=1}^{\infty} [-i,i]$.
- The counting measure on $\R$ is not $\sigma$-finite, because one cannot decompose $\R$ into a countable union of sets with finite [[Cardinality#^1fd903|cardinality]].
$\quad$

A set of measure zero is “negligible” for integration and probability, but it may have highly nontrivial—or even nonmeasurable—subsets. *Completeness* ensures that changing a measurable function on a null set still leaves a measurable function, which makes “almost everywhere” statements behave cleanly.

> [!definition] Complete Measure
> A measure space $(X,\mathcal{S},\mu)$ is *complete* if for all $F\in\mathcal{S}$ that $\mu(F)=0$ and $E\subset F$ implies $E\in \mathcal{S}$. 
> 

<u><b>e.g.</b></u>  The Lebesgue measure on $\R$ is complete: every subset of a Lebesgue-null set, such as the [[Cantor Set#^d4ff78|Cantor set]], has measure zero and is [[Lebesgue Measurability#^b5a209|Lebesgue measurable]].

## Exterior Measure and Carathéodory Theorem

> [!definition] Exterior (Outer) Measure
> Let $X$ be a set. The *exterior measure* $\mu_{*}$ on $X$ is defined on all subsets of $X$ to $[0,\infty]$ such that 
> - $\mu_{*}(\emptyset)=0$;
> - $\mu_{*}(A) \leq \mu_{*}(B)$ if $A\subseteq B$;
> - $\mu_{*}(\bigcup_{i=1}^{\infty} A_{i}) \leq \sum_{i=1}^{\infty} \mu_{*}(A_{i})$.
>$\quad$ ^bb3d18

> [!definition] Carathéodory Measurable
> Suppose $\mu_{*}$ is an exterior measure. A set $E$ in $X$ is *Carathéodory measurable* or simply measurable if one has $$\mu_*(A)=\mu_*(E\cap A)+\mu_*(E^c\cap A)\quad\text{ for every }A\subset X.$$ ^6580a8

> [!theorem] Carathéodory Theorem
> Given an exterior measure $\mu_{*}$ on a set $X$, the collection $\mathcal{M}$ of Carathéodory measurable sets forms a $\sigma$-algebra. Moreover, $\mu_{*}$ restricted to $\mathcal{M}$ is a measure.

*Proof*  Clearly, $\emptyset$ and $X$ belong to $\mathcal{M}$ and $\mu_{*}(\emptyset)=0$, 

One of the most important examples of exterior measure is the exterior measure on metric spaces, which is defined as follows:

> [!definition] Metric Exterior Measure
> An exterior measure $\mu_{*}$ on a metric space $(X,d)$ is called a metric exterior measure if it satisfies $$\mu_{*}(A\cup B)=\mu_{*}(A)+\mu_{*}(B),\quad\text{whenever } d(A,B)>0.$$

This property plays a crucial role in the case of exterior Lebesgue measure.

> [!theorem]
> If $\mu_{*}$ is a metric exterior measure on a metric space $(X,d)$, then the Borel sets in $X$ are measurable. Hence $\mu_{*}$ restricted to the Borel sets is a measure.

## The Extension Theorem

> [!definition] Boolean Algebra
> Let $X$ be a set. A *boolean algebra* $\mathcal{A}$ on $X$ is a nonempty collection of subsets satisfies
> - $\emptyset\in X$,
> - If $E\in\mathcal{A}$, then $X\setminus E = E^{c}\in A$,
> - If $E$ and $F$ are elements of $\mathcal{A}$, then $E\cup F\in \mathcal{A}$.
> 
> In other words, $\mathcal{A}$ is closed under complements, finite unions, and finite intersections.

> [!definition] Premeasure
> A premeasure on a boolean algebra $\mathcal{A}$ over a set $X$, is a function $\mu\colon\mathcal{A}\to [0,\infty]$ such that 
> - $\mu(\emptyset)=0$.
> - If $E_{1},E_{2},\dots$ is a countable collection of disjoint sets in $\mathcal{A}$ with $\bigcup_{i=1}^{\infty} E_{i} \in \mathcal{A}$, then $$\mu\left(\bigcup_{i=1}^{\infty} E_{i}\right)=\sum_{i=1}^{\infty}\mu(E_{i}).$$
> $\quad$
> 

Premeasures give rise to exterior measures in a natural way:

> [!lemma] 
> If $\mu$ is a premeasure on a boolean algebra $\mathcal{A}$ over $X$, define $\mu_{*}$ on any subset $E\subseteq X$ by $$\mu_{*}(E)=\inf\left\{ \sum_{j=1}^{\infty}\mu(E_{j}) : E\subset \bigcup_{j=1}^{\infty}E_{j}, \text{where } E_{j}\in\mathcal{A} \text{ for all }j\in\N \right\}$$
> Then $\mu_{*}$ is an [[Measurable Spaces and Functions#^bb3d18|exterior measure]] on $X$ satisfying $\mu_{*}(E)=\mu(E)$ for all $E\in\mathcal{A}$, and all sets in $\mathcal{A}$ are [[Measurable Spaces and Functions#^6580a8|Carathéodory measurable]].

> [!theorem] Carathéodory’s Extension Theorem 
> Suppose that $\mathcal{A}$ is a boolean algebra of sets in $X$, $\mu_{0}$ is a premeasure on $\mathcal{A}$, and $\mathcal{M}$ is the $\sigma$-algebra generated by $\mathcal{A}$ (i.e., the smallest $\sigma$-algebra containing $\mathcal{A}$). Then there exists a measure $\mu$ on $\mathcal{M}$ that extends $\mu_{0}$. Moreover, if $\mu$ is $\sigma$-finite, then it is unqiue.

*Proof*  This is a direct consequence of the above lemma. $\mu_{0}$ induces an exterior measure $\mu_{*}$, which is a measure on the $\sigma$-algebra of Carathéodory measurable sets. As all sets in $\mathcal{A}$ are Carathéodory measurable, and $\mathcal{M}$ is generated by $\mathcal{A}$, all sets in $\mathcal{M}$ are also Carathéodory measurable. Therefore $\mu_{*}$ is a measure on $\mathcal{M}$ as well, and we call it $\mu$.
To prove the uniqueness, we suppose $\nu$ is another measure defined on $\mathcal{M}$ that extends $\mu_{0}$. Let $E=\bigcup_{i=1}^{\infty}E_{i}$ containing where each $E_{i}\in\mathcal{A}$. Then there holds $$\nu(E)=\lim_{n\to \infty} \nu\left( \bigcup_{i=1}^{n}E_{i}\right)=\lim_{n\to \infty}\mu\left( \bigcup_{i=1}^{n}E_{i}\right)=\mu(E).$$

Pick a set $F\in\mathcal{M}$ with $\mu(F)<\infty$. If $F\subset\bigcup_{i}^{\infty} E_{i}$ for each $E_{i}\in\mathcal{A}$, then $$\nu(F)\leq \sum_{i=1}^{\infty}\nu(E_{i})=\sum_{i=1}^{\infty}\mu_{0}(E_{i}),$$so $\nu(F)\leq \mu(F)$ by taking the infimum over all such covers of $F$. To prove the reverse inequality, note that   $$\mu(F)=\sum_{j=1}^{\infty}\mu(F\cap G_{j})=\sum_{j=1}^{\infty}\nu(F\cap G_{j})=\nu(F).$$

Assume $\mu$ is $\sigma$-finite. We claim that $\mu(F)=\nu(F)$. Observe that since $\mu$ is $\sigma$-finite, we may write $X=\bigcup_{i}G_{i}$, where $G_{1},G_{2},\dots$ is a countable collection of disjoint sets in $\mathcal{A}$ with $\mu(E_{i})<\infty$. Then we have $$F\subset\bigcup_{i}^{\infty} (F\cap G_{i}).$$Let $E_F\cap G_{i}$





