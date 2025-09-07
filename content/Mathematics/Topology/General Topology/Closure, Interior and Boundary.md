## Closure and Interior

>[!definition] Closedness
>Let $(X,τ)$ be a [[Topological Spaces#^65c94a|topological space]]. A subset $A ⊂ X$ is called closed if $A^{c} \in \tau$.

>[!definition] Closure
>The closure $\bar{A}$ of a set $A\subset T$ is the [[Construction of Sets#^408460|intersection]] of all closed sets that contain $A$. We can say that the closure of $A$ is therefore the smallest closed set that contains $A$. ^cf4e59

>[!proposition] 
> If $A$ is non-empty then $\bar{A}$ is non-empty.

>[!proposition] 
> $\bar{A}$ is always closed.

>[!definition] Interior
>The interior of $A$, written as $A^\circ$ or $\interior A$, is the union of all open subsets of $A$. It is the largest open subset of $A$. ^871863

>[!proposition] 
> $\bar{A} = (\interior(A^{c}))^{c}$.

## Neighbourhood, Boundary and Limit Points

>[!definition] Neighbourhood
>Let $(T,\mathcal{T})$ to be a topological space. A neighbourhood of $x ∈ T$ is a set $H \subset T$ such that $x ∈ U ⊂ H$ for some $U \in \mathcal{T}$ . An open neighbourhood of $x ∈ T$ is an open set $U\in\mathcal{T}$ that contains $x$. ^eda962

>[!definition] Boundary
>The boundary $\partial H$ of a set $H$ is the set of all points $x$ with the property that every neighbourhood of $x$ meets both $H$ and its complement: $$ \partial H=\left\{x\in T\mid \text{ $U$ is open and $x\in U$ $\implies$  $U\cap H\neq \emptyset$ and $U\cap(T\setminus H)\neq\emptyset$}\right\}$$

>[!theorem] 
> Let $(X,τ)$ be a topological space and $A ⊂ X$. Then $\partial A =\bar{A} ∩\overline{A^{c}}$ and $\bar{A}=A\cup \partial A$.

>[!theorem] 
> Let $(X,τ)$ be a topological space and $A ⊂ X$. Then
>- A is open iff $A \cap \partial A = \emptyset$.
>- A is closed iff $\partial A \subset A$.
>
>$\quad$

*Proof*  If $A$ is open, then every $x ∈ A$ has the neighborhood $A$ that does not intersect $A^{c}$ and thus $x \notin ∂A$. Thus $A∩∂A = \emptyset$. Conversely, if $A∩∂A=\emptyset$, then for any $x ∈A$ we have $x\notin ∂A$. Thus there is an open neighborhood $U_{x}$ of $x$ not intersecting both $A$ and $A^{c}$. Since $x ∈ U_{x} ∩ A$, we have $U_{x} ∩A^{c} =\emptyset$. Thus $U_{x} ⊂A$ and hence $A=\bigcup_{x\in A} U_{x}$ is open. $\square$

>[!definition] Limit Point and Isolated Point
>Let $S ⊂ T$. A point $x ∈ T$ is a limit point of $S$ if every neighbourhood of $x$ intersects $S \setminus \{x\}$. (Note that a limit point of $S$ does not need to belong to $S$). A point in $S$ that is not a limit point of $S$ is called an isolated point.

>[!theorem] 
>Let $X$ be a topological space and $A ⊂ X$ . Then $$\bar{A} = A \cup \{\text{limit points of } A\}$$

>[!definition] Dense, Nowhere Dense and Meagre
>A subset $A$ of $T$ is dense in $T$ if $\bar{A}=T$, is nowhere dense in $T$ if ${(\bar{A})}^\circ = \emptyset$, is meagre in $T$ if it is a union of a countable number of nowhere dense sets. ^b560bf

<u><b>e.g.</b></u>  $\Q$ is dense in $\R$ (as is $\R \setminus\Q$). In $\R$, one-point sets are nowhere dense; so $\Q$ is meagre in $\R$.

>[!lemma] 
> A subset $A$ of $T$ is nowhere dense if and only if $T \setminus \bar{A}$ is dense in $T$.

<b><u>e.g.</u></b>  $\mathbb{Q}$ is dense in $\R$ (as is $\R \setminus\mathbb{Q}$). In $\R$, one-point sets are nowhere dense; so $\mathbb{Q}$ is meagre in $\R$. However, $\R \setminus\mathbb{\bar{Q}} = \emptyset$, so Q isn’t nowhere dense.

## Convergent Sequences

>[!definition] Convergent Sequence
>Let $(X,τ)$ be a topological space. A sequence $(x_{n})$ in $X$ is called convergent to $x ∈ X$ if for any [[Closure, Interior and Boundary#^eda962|neighborhood]] $U$ of $x$ there exists an integer $N$ such that $x_{n} ∈ U$ for all $n≥N$. We write $\lim_{n→∞}x_{n} =x$ or simply $x_{n} →x$. ^72dffe
