---
created: 2024-08-17
updated: 2024-10-07
tags: []
---
## $\sigma$-Algebra and Measurable Spaces

>[!definition] $\sigma$-Algebra
>Suppose $X$ is a set and $\mathcal{S}$ is a set of subsets of $X$. Then $\mathcal{S}$ is called a $\sigma$-algebra on $X$ if it is closed under countable unions, countable intersections, and complements:
>- $\emptyset \in \mathcal{S}$;
>- if $Y\in \mathcal{S}$, then $X\setminus Y\in \mathcal{S}$;
>- if $Y_{1}, Y_{2}, \dots \in \mathcal{S}$, then $\bigcup_{i=1}^{\infty} Y_{i}\in\mathcal{S}$.
>
> Note that the closedness on countable intersections comes freely from (2) and (3).  ^60a516

>[!definition] Measurable Space
>A measurable space is an ordered pair of a set and an associated $\sigma$-algebra $(X, \mathcal{S})$. An element of $\mathcal{S}$ is called an $\mathcal{S}$-measurable set, or just a measurable set. ^0bddf6

> [!proposition]
> Suppose $X$ is a set and $\mathcal{A}$ is a set of subsets of $X$. Then the intersection of all $σ$-algebras on $X$ that contain $\mathcal{A}$ is a $σ$-algebra on $X$.

*Proof*  

## Measurable Functions

> [!definition] Measurable Function
> Suppose $(X, \mathcal{S})$ and $(Y,\mathcal{T})$ are measurable spaces. A function $f \colon X → Y$ is an measurable function if $$f^{-1}(E) \in \mathcal{S}\quad \text{for all } E\in \mathcal{T}.$$ ^11c83a

> [!definition] Essential Range
> The essential range of a measurable function $f\colon (X,\mathcal{S})\to (Y,\mathcal{T})$ is the set $$\mathrm{ess\,range}(f):=\{y\in Y\mid \forall U\in \mathcal{T} \text{ with }y\in U, \mu(f^{-1}(U))>0\},$$where $\mu$ is a measure on $(X,\mathcal{S})$.

## Measure Spaces

> [!definition] Measure
> Suppose $(X, \mathcal{S})$ is a measurable space. A measure $\mu$ on $(X, \mathcal{S})$ is a function $\mu \colon \mathcal{S} → [0,\infty]$ such that: $\mu(\emptyset)=0$ and $$\mu\left(\bigcup_{k=1}^\infty E_k\right)=\sum_{k=1}^\infty\mu(E_k)$$for any countable collection $\{E_k\}_{k=1}^\infty$ of disjoint sets in $\mathcal{S}$.
> In this case, we call $(X, \mathcal{S}, \mu)$ a measure space. ^c2e020

> [!proposition]
> For a measure $\mu$ defined on a measurable space $(X,\mathcal{S})$, the following properties hold:
> - Monotonicity: $\mu(E)\leq \mu(F)$ for $E\subset F$,
> - Subadditivity: $\mu\left(\bigcup_{i=1}^{\infty} E_{i}\right)\leq \sum^{\infty}_{i}\mu(E_{i})$.
> $\quad$

*Proof*  Observe that for any $E\subset F$, $E$ and $F\setminus E$ are disjoint, and $F=E\cup (F\setminus E)$, thus $$\mu(F)=\mu(E)+\mu(F\setminus E)\geq \mu(E).$$For subadditivity, we can divide the union into disjoint sets. Suppose $G_{n}=\bigcup_{i=1}^{n} E_{i}$, let $F_{1}:=E_{1}$, and $F_{i}:=E_{i}\setminus G_{i-1}$ for $i\geq 2$. Then each $F_{i}$ is disjoint, and we have $$\mu\left(\bigcup_{i=1}^{\infty} E_{i}\right)=\mu\left(\bigcup_{i=1}^{\infty} F_{i}\right)= \sum_{i=1}^{\infty} \mu(F_{i})\leq \sum_{i=1}^{\infty}\mu(E_{i}),$$where the last inequality follows from monotonicity. $\square$

> [!definition] $\sigma$-Finite Measure
> A measure space $(X, \mathcal{S},\mu)$ is $\sigma$-finite if there exists a countable collection $\{A_{i}\}_{i=1}^{\infty}$ of measurable sets such that $$X=\bigcup_{i=1}^{\infty} A_{i},$$ and $\mu(A_{i})<\infty$ for all $i$. ^0bddf6

<u><b>e.g.</b></u>  
- The Lebesgue measure on $\R$ is $\sigma$-finite because $\R=\bigcup_{i=1}^{\infty} [-i,i]$.
- The counting measure on $\R$ is not $\sigma$-finite, because one cannot decompose $\R$ into a countable union of sets with finite [[Cardinality#^1fd903|cardinality]].
$\quad$

> [!definition] Complete Measure
> A measure $\mu$ defined on a measurable space $(X,\mathcal{S})$ is complete if for all $F\in\mathcal{S}$ that $\mu(F)=0$ and $E\subset F$ implies $E\in \mathcal{S}$. 
> 

## Exterior Measure and Carathéodory Theorem

> [!definition] Exterior (Outer) Measure
> Let $X$ be a set. The exterior measure $\mu_{*}$ on $X$ is defined on all subsets of $X$ to $[0,\infty]$ such that 
> - $\mu_{*}(\emptyset)=0$;
> - $\mu_{*}(A) \leq \mu_{*}(B)$ if $A\subseteq B$;
> - $\mu_{*}(\bigcup_{i=1}^{\infty} A_{i}) \leq \sum_{i=1}^{\infty} \mu_{*}(A_{i})$.
>$\quad$ ^bb3d18

> [!definition] Carathéodory Measurable
> Suppose $\mu_{*}$ is an exterior measure. A set $E$ in $X$ is Carathéodory measurable or simply measurable if one has $$\mu_*(A)=\mu_*(E\cap A)+\mu_*(E^c\cap A)\quad\text{ for every }A\subset X.$$ ^6580a8

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
> Let $X$ be a set. A boolean algebra $\mathcal{A}$ on $X$ is a nonempty collection of subsets satisfies
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





