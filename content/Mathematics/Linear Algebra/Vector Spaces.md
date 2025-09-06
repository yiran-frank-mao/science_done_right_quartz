>[!definition] Vector Space
>Let $F$ be a [[Ring, Field and Integral Domain#^575174|field]]. A $F$-vector space is a set $V$ with two operations:
>- Addition: $+\colon V\times V\to V, (v_{1},v_{2})\mapsto v_1+v_2$
>- Scalar multiplication: $\cdot\colon F\times V\to V, (c,v)\mapsto c\cdot v$
>
> which satisfy the following properties: 
>- Associativity: $\forall v_{1},v_{2},v_{3} \in V, a,b\in F,(v_{1}+v_{2})+v_{3}=v_{1}+(v_{2}+v_{3}), (a\cdot b)\cdot v_{1}= a\cdot (b\cdot v_{1})$
>- Commutativity: $\forall v_{1},v_{2} \in V, v_{1}+v_{2}=v_{2}+v_{1}$
>- Additive Identity: $\exists 0\in V, \forall v\in V, 0+v=v$
>- Additive Inverse: $\forall v\in V, \exists w\in V, v+w=0$
>- Multiplicative Identity: $\exists 1\in F, \forall v\in V,1\cdot v=v$
>- Distributivity: $\forall a,b\in F, v_{1},v_{2}\in V, a\cdot(v_{1}+v_{2})=a\cdot v_{1}+a\cdot v_{2}, (a+b)\cdot v_{1}=a\cdot v_{1}+b\cdot v_{2}$
>$\quad$^f4b63e

<u><b>e.g.</b></u>  The set $\newcommand{\R}{\mathbb{R}}F[a,b]=\{f\colon[a,b]\to\R\}$ is a vector space on $\R$ under the addition and scalar multiplication defined by $$(f+g)(x)=f(x)+g(x),\quad (\alpha f)(x) = \alpha f(x)$$$C[a,b]=\{f\colon[a,b]\to\R\mid f \text{ is continuous}\}$ is a subspace under the same addition and scalar multiplication.

>[!proposition] 
>Let $V$ be an $F$-vector space, $v\in V, c\in F$, then
>- $0_{F}\cdot v=0_{V}$
>- $c\cdot 0_{V} = 0_{V}$
>- $(-1)\cdot v=-v$
>- $c\cdot v=0 \implies c=0_{F} \text{ or } v=0_{V}$
>$\quad$

*Proof*  $0_{F}\cdot v=(0_{F}+0_{F})\cdot v=0_{F}\cdot v+0_{F}\cdot v$. It follows that $$0=0_{F}\cdot v+ (-0_{F}\cdot v)=0_{F}\cdot v$$$\square$

>[!definition] Subspace
>A subspace $W$ of a vector space $V$ is a subset $W\subseteq V$ which is also a vector space inherit the same operations as in $V$.

>[!proposition] 
>A subset $W\subseteq V$ is a subspace of a $F$-vector space $V$ if and only if 
>- $0\in W$
>- $w_{1},w_{2}\in W \implies w_{1}+w_{2}\in W$
>- $c\in F, w\in W \implies cw \in W$
>$\quad$

## Span and Linear Combinations

>[!definition] Span
>The span of a set of vectors $S\subseteq V$ is the set of all finite linear combinations of vectors in $S$: $$\mathrm{span}(S)=\left\{\sum_{i=1}^{n} c_{i}v_{i} \mid n\in\N, v_{i}\in S, c_{i}\in F\right\}.$$^ce69a9

>[!proposition] 
> The span of any nonempty set of vectors is a subspace.