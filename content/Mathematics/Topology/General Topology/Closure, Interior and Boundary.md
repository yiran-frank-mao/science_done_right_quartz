## Closure and Interior

>[!definition] Closure
> Suppose $X$ is a [[Topological Spaces#^65c94a|topological space]]. The *closure* $\bar{A}$ of a set $A\subset X$ is the [[Construction of Sets#^408460|intersection]] of all closed sets that contain $A$. We can say that the closure of $A$ is therefore the smallest closed set that contains $A$. ^cf4e59

>[!proposition] 
> If $A$ is non-empty then $\bar{A}$ is non-empty. Moreover, $\bar{A}$ is always [[Topological Spaces#^0849a0|closed]].

>[!definition] Interior
>The *interior* of $A$, written as $A^{\circ}$, is the union of all open subsets of $A$. It is the largest open subset of $A$. ^871863

>[!proposition] 
> $\bar{A} = ((A^{c})^{\circ})^{c}$.

*Proof*  Note that $(A^{c})^{\circ}$ is open, so $((A^{c})^{\circ})^{c}$ is closed. Therefore, to show the LHS is contained in RHS, it suffices to show $A\subset ((A^{c})^{\circ})^{c}$. Indeed, for any $x\in A$, we have $$x\in A = (A^{c})^{c}\subset ((A^{c})^{\circ} )^{c}.$$For the other direction, suppose $S$ is a closed set containing $A$, then $S^{c}\subset A^{c}$ is open, so $S^{c} \subset (A^{c})^{\circ}$. Therefore, $((A^{c})^{\circ})^{c}\subset S$. In particular, $((A^{c})^{\circ})^{c}\subset \bar{A}$.  $\square$

## Neighbourhood, Boundary and Limit Points

>[!definition] Neighbourhood
> Let $(X,\mathcal{T})$ to be a topological space. 
> An *open neighbourhood* of $x ∈ X$ is an open set $U\in\mathcal{T}$ that contains $x$. 
> A *neighbourhood* of $x\in X$ is a set containing an open neighborhood of $x$. ^eda962

>[!definition] Boundary
>The boundary $\partial H$ of a set $H\subset X$ is the set of all points $x$ with the property that every neighbourhood of $x$ meets both $H$ and its complement: $$ \partial H=\left\{x\in X\mid \text{ $U$ is open and $x\in U$ $\implies$  $U\cap H\neq \emptyset$ and $U\cap(T\setminus H)\neq\emptyset$}\right\}$$

>[!theorem] 
> Let $(X,τ)$ be a topological space and $A ⊂ X$. Then $\partial A =\bar{A} ∩\overline{A^{c}}$ and $\bar{A}=A\cup \partial A$.

>[!theorem] 
> Let $(X,τ)$ be a topological space and $A ⊂ X$. Then
>- A is open iff $A \cap \partial A = \emptyset$.
>- A is closed iff $\partial A \subset A$.
>$\quad$

*Proof*  If $A$ is open, then every $x ∈ A$ has the neighborhood $A$ that does not intersect $A^{c}$ and thus $x \notin ∂A$. Thus $A∩∂A = \emptyset$. Conversely, if $A∩∂A=\emptyset$, then for any $x ∈A$ we have $x\notin ∂A$. Thus there is an open neighborhood $U_{x}$ of $x$ not intersecting both $A$ and $A^{c}$. Since $x ∈ U_{x} ∩ A$, we have $U_{x} ∩A^{c} =\emptyset$. Thus $U_{x} ⊂A$ and hence $A=\bigcup_{x\in A} U_{x}$ is open. $\square$

>[!definition] Limit Point & Isolated Point
> Let $S \subset X$. A point $x ∈ X$ is a *limit point* of $S$ if every [[Closure, Interior and Boundary#^eda962|open neighbourhood]] of $x$ intersects $S \setminus \{x\}$. (Note that a limit point of $S$ does not need to belong to $S$). The set of all limit points is called the *derived set*, denoted $S'$
> A point in $S$ that is not a limit point of $S$ is called an *isolated point*. Equivalently, A point $x$ is an isolated point of $A$ if there is an open subset $U$ of $X$ such that $U\setminus A= \{x\}$. ^11cf9f

<u><b>e.g.</b></u>  Consider $A=(0,1)\subset \R$, then $A'=[0,1]$; For $\{1/n\}_{n=1}^{\infty}\subset \R$, the only limit point is $0$.

>[!theorem] 
> Let $X$ be a topological space and $A \subset X$ . Then $$\bar{A} = A \cup A'$$

>[!definition] Dense, Nowhere Dense and Meagre
>A subset $A$ of $T$ is *dense* in $T$ if $\bar{A}=T$, is *nowhere dense* in $T$ if ${(\bar{A})}^\circ = \emptyset$, is *meagre* if it is a union of a countable number of nowhere dense sets. ^b560bf

> [!definition] Separable Space
> A topological space is *separable* if it has a [[Equinumerous and Countability#^79eb6c|countable]] [[Closure, Interior and Boundary#^b560bf|dense]] subset. ^acb78f
> 

>[!lemma] 
> A subset $A$ of $T$ is nowhere dense if and only if $T \setminus \bar{A}$ is dense in $T$.

<b><u>e.g.</u></b>  $\mathbb{Q}$ is dense in $\R$ (as is $\R \setminus\mathbb{Q}$). In $\R$, one-point sets are nowhere dense; so $\mathbb{Q}$ is meagre in $\R$. However, $\R \setminus\mathbb{\bar{Q}} = \emptyset$, so $\Q$ isn’t nowhere dense.

## Convergent Sequences

>[!definition] Convergent Sequence
>Let $(X,τ)$ be a topological space. A sequence $(x_{n})$ in $X$ is called convergent to $x ∈ X$ if for any [[Closure, Interior and Boundary#^eda962|neighborhood]] $U$ of $x$ there exists an integer $N$ such that $x_{n} ∈ U$ for all $n≥N$. We write $\lim_{n→∞}x_{n} =x$ or simply $x_{n} →x$. ^72dffe
