---
created: 2023-12-11
updated: 2024-09-26
---
## Topology

>[!definition] Topological Space
>A *topology* $\mathcal{T}$ on a set $T$ is a collection of subsets of $T$ , which we agree to call the “open sets”, such that 
>1. $T$ and $\emptyset$ are open
>2. the intersection of finitely many open sets is open
>3. arbitrary unions of open sets are open.
>
>The pair $(T , \mathcal{T})$ is called a *topological space*. ^65c94a

<b><u>e.g.</u></b>  The topology induced by a metric: in any metric space $(X,d)$ the collection of all open sets forms a topology.

> [!definition] Closed Sets
> In a topological space $(T , \mathcal{T})$, a set $C$ is called closed if $T\setminus C$ is open. i.e. $T\setminus C\in \mathcal{T}$. ^0849a0

>[!definition] Discrete Topology & Trivial Topology
>A topology is said to be discrete if all subsets are open. It is indiscrete or trivial if the only open sets are $T$ and $\emptyset$.

>[!definition] Cofinite Topology & Cocountable Topology
> A topology is cofinite if all open subsets are $T$, $\emptyset$, or the set whose complement is finite.
> A topology is cocountable if all open subsets are $T$, $\emptyset$, or the set whose complement is countable.

>[!definition] Zariski Topology on $\R^n$
> A set is open if it is $\R^n$, $\emptyset$, or its complement is the set of zeros of a polynomial with real coefficients.

>[!definition] Metrizable
>Topologies need not come from metrics, but if there is, we say that $(T , \mathcal{T})$ is metrizable.

>[!lemma] 
> Suppose that $T$ consists of more than one point. Then the indiscrete topology on $T$ is not metrizable.

*Proof*  Assume the indiscrete topology on $T$ is induced by a metric $d$ on $T$. Let $x,y\in T$ with $x\neq y$. Then $d(x,y)=\epsilon>0$. The set $B\left(x,\frac{\epsilon}{2}\right)$ is an open subset of $(T,d)$. Since $x\in B\left(x, \frac{\epsilon}{2}\right)$, this set is not empty. And since $y\notin B\left(x, \frac{\epsilon}{2}\right)$ this set is not all of $T$. But $\emptyset$ and $T$ are the only open sets, yielding a contradiction. $\square$

>[!definition] Coarser and Finer
>If $\mathcal{T}_1$ and $\mathcal{T}_2$ are two topologies on $T$ then we say that $\mathcal{T}_1$ is coarser than $\mathcal{T}_2$ if $\mathcal{T}_1\subset\mathcal{T}_2$, that is $\mathcal{T}_1$ contains fewer open sets than $\mathcal{T}_2$. In this situation, we also say that $\mathcal{T}_2$ is finer than $\mathcal{T}_1$. ^149286

<u><b>e.g.</b></u>  Given a set $X$, the trivial topology is the coarsest/weakest topology on $X$ and the discrete topology is the finest/strongest topology on $X$.

## Bases and Sub-bases

>[!definition] Base for a Topology
>A basis for a topology $\mathcal{T}$ on $T$ is a collection $\mathcal{B}\subset\mathcal{T}$ such that every set in $\mathcal{T}$ is the union of some sets from $\mathcal{B}$. ^2fc468

<u><b>e.g.</b></u>  Let $(X,d)$ be a metric space. Then $$\mathcal{B}=\{B_r(x):x\in X\mathrm{~and~}r>0\}$$ is a basis for the metric topology on $X$.

> [!theorem]
> Let $(X,\mathcal{T})$ be a topological space. Then $\mathcal{B}⊂\mathcal{T}$ is a base for $\mathcal{T}$ iff for any $x\in X$ and any $U ∈ \mathcal{T}$ with $x ∈ U$ there is $B ∈ \mathcal{B}$ such that $x \in B ⊂ U$.

> [!proposition]
> A collection of sets cannot be basis for two distinct topologies.

*Proof*  Suppose that $\mathcal{B}$ is a basis for both $\mathcal{T}$ and $\mathcal{T}^\prime$. Then every set in $\mathcal{T}^\prime$ is a union of sets in $\mathcal{B}$. Since $\mathcal{B}\subset \mathcal{T}$, every set in $\mathcal{T}^\prime$ is open in $(T, \mathcal{T})$, this implies that $\mathcal{T}^{\prime}\subset \mathcal{T}$. Similarly, we have $\mathcal{T}\subset\mathcal{T}^\prime$.

**Lemma**  If $\mathcal{B}$ is a basis for $\mathcal{T}$ then
- $T$ is the union of some sets from $\mathcal{B}$ ^e1f920
- If $B_{1},B_{2}\in \mathcal{B}$ then $B_{1}\cap B_{2}$ is the union of some sets from $\mathcal{B}$. ^c6f5f0


**Thrm**  Let $T$ be a set and let $\mathcal{B}$ be a collection of subsets of $T$ that satisfy [[Topological Spaces#^e1f920|property(B1)]]  and [[Topological Spaces#^c6f5f0|property(B2)]]. Then there is a unique topology $\mathcal{T}$ on $T$ whose basis is $\mathcal{B}$. Its open sets are precisely the unions of sets from $\mathcal{B}$: $$\mathcal{T}=\left\{\bigcup_{\alpha\in A}B_{\alpha}\mid B_{\alpha}\in \mathcal{B}\right\}$$
*Proof*  

>[!theorem] 
> Let $X$ be a set. Let $\tau$ and $\tau^{\prime}$ be two topologies on $X$ with bases $\mathcal{B}$ and $\mathcal{B}^{\prime}$ respectively. The following are equivalent:
>- $\tau \subset \tau^{\prime}$.
>- For each $B\in \mathcal{B}$ and each $x\in B$ there is $B^{\prime}\in \mathcal{B}^{\prime}$ such that $x\in B^{\prime} \subset B$.
>$\quad$
>

*Proof*  

>[!definition] Sub-basis
>A sub-basis for a topology $\mathcal{T}$ on $T$ is a collection $\mathcal{B}\subset \mathcal{T}$ such that every set in $\mathcal{T}$ is a union of finite intersections of sets from $\mathcal{B}$. ^02668a

> [!definition] Second-Countable
> A topological space $(T,\mathcal{T})$ is second-countable if there is a countable base for $\mathcal{T}$. ^a8abf4

## Subspaces and Finite Product Spaces

>[!definition] Subspace Topology
>If $(T,\mathcal{T})$ is a topological space and $S\subset T$ , then the subspace topology on $S$ is $$\mathcal{T}_{S}=\{U\cap S \mid U \in \mathcal{T} \}$$ We call $(S,\mathcal{T}_{S})$ a topological subspace of $T$. ^a942da

<b><u>e.g.</u></b>  If we consider $[0,1]$ as a subspace of $\R$ then the open sets in $[0,1]$ consist of all sets $U\cap [0,1]$ where $U$ is an open subset of $\R$. In particular, $[0, a)$ is open for every $a\in(0, 1)$. 

> [!lemma]
> Suppose that $(X, d)$ is a metric space with corresponding topology $\mathcal{T}$. If $S\subset X$ then subspace topology $\mathcal{T}_{S}$ on $S$ corresponds to the topology on $S$ that arises from the metric space $(S,d\big|_{S})$.

*Proof*  

>[!proposition] 
> Closed subset in closed subspace is closed in the original topological space.

*Proof*  Let $S$ be a closed subspace of $X$, and $C\subset S$ is closed in $S$. Then $$S\setminus C = W \cap S$$for some open set $W$ in $X$. It follows that $C = S\setminus(W\cap S)=S\setminus W$. Thus, $$X\setminus C = X \setminus (S\setminus W)=(X\setminus S) \cup W$$Since $S$ is closed in $X$, $X\setminus S$ is open. Therefore $X\setminus C$ is open, and $C$ is closed in $X$. $\square$

>[!definition] Product Topology
>Suppose that $(T_{1},\mathcal{T}_{1})$ and $(T_{2}, \mathcal{T}_{2})$ are two topological spaces. Then the product topology on $T_{1}\times T_{2}$ is the topology $\mathcal{T}$ with basis $$\mathcal{B}=\{U_{1}\times U_{2} \mid U_{1}\in \mathcal{T}_{1},U_{2}\in\mathcal{T}_{2}\}$$ We call $(T_{1}\times T_{2}, \mathcal{T})$ the topological product of $T_{1}$ and $T_{2}$. ^fbf303

**Thrm**  Let $(X,τ_{X})$ and $(Y,τ_{Y})$ be topological spaces with respective bases $\mathcal{B}_{X}$ and $\mathcal{B}_{Y}$. Then 