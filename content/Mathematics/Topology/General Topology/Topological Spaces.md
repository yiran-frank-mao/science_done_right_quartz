---
created: 2023-12-11
updated: 2024-09-26
---
## Topology

>[!definition] Topological Space
> A *topology* $\mathcal{T}$ on a set $X$ is a collection of subsets of $X$, which we agree to call the “open sets”, such that 
>1. $T$ and $\emptyset$ are open；
>2. the [[Construction of Sets#^408460|intersection]] of finitely many open sets is open；
>3. arbitrary [[Construction of Sets#^678b42|unions]] of open sets are open.
>
> The pair $(X , \mathcal{T})$ is called a *topological space*. ^65c94a

<b><u>e.g.</u></b>  
- The topology induced by a [[Metric Spaces#^0eacc7|metric]]: in any metric space $(X,d)$ the collection of all open sets forms a topology.
- A topology is said to be *discrete* if all subsets are open. It is *indiscrete* or *trivial* if the only open sets are $T$ and $\emptyset$.
- Zariski Topology on $\R^{n}$: A set is open if it is $\R^n$, $\emptyset$, or its complement is the set of zeros of a polynomial with real coefficients.
$\quad$

> [!definition] Closedness
> In a topological space $(X, \mathcal{T})$, a set $C$ is called *closed* if $X\setminus C$ is open. i.e. $T\setminus C\in \mathcal{T}$. ^0849a0

>[!definition] Cofinite Topology & Cocountable Topology
> A topology is cofinite if all open subsets are $T$, $\emptyset$, or the set whose complement is finite.
> A topology is cocountable if all open subsets are $T$, $\emptyset$, or the set whose complement is countable.

>[!definition] Metrizable
>Topologies need not come from metrics, but if there is, we say that $(T , \mathcal{T})$ is *metrizable*.

>[!lemma] 
> Suppose that $X$ consists of more than one point. Then the indiscrete topology on $X$ is not metrizable.

*Proof*  Assume the indiscrete topology on $T$ is induced by a metric $d$ on $T$. Let $x,y\in T$ with $x\neq y$. Then $d(x,y)=\epsilon>0$. The set $B\left(x,\frac{\epsilon}{2}\right)$ is an open subset of $(T,d)$. Since $x\in B\left(x, \frac{\epsilon}{2}\right)$, this set is not empty. And since $y\notin B\left(x, \frac{\epsilon}{2}\right)$ this set is not all of $T$. But $\emptyset$ and $T$ are the only open sets, yielding a contradiction. $\square$

>[!definition] Coarser and Finer
>If $\mathcal{T}_1$ and $\mathcal{T}_2$ are two topologies on $T$ then we say that $\mathcal{T}_1$ is coarser than $\mathcal{T}_2$ if $\mathcal{T}_1\subset\mathcal{T}_2$, that is $\mathcal{T}_1$ contains fewer open sets than $\mathcal{T}_2$. In this situation, we also say that $\mathcal{T}_2$ is finer than $\mathcal{T}_1$. ^149286

<u><b>e.g.</b></u>  Given a set $X$, the trivial topology is the coarsest/weakest topology on $X$ and the discrete topology is the finest/strongest topology on $X$.

## Bases and Sub-bases

>[!definition] Base for a Topology
>A *basis* for a topology $\mathcal{T}$ on $T$ is a collection $\mathcal{B}\subset\mathcal{T}$ such that every set in $\mathcal{T}$ is the union of some sets from $\mathcal{B}$. ^2fc468

<u><b>e.g.</b></u>  Let $(X,d)$ be a [[Metric Spaces#^0eacc7|metric space]]. Then $$\mathcal{B}=\{B_r(x):x\in X\mathrm{~and~}r>0\}$$ is a basis for the metric topology on $X$.

> [!theorem]
> Let $(X,\mathcal{T})$ be a topological space. Then $\mathcal{B}\subset \mathcal{T}$ is a basis for $\mathcal{T}$ iff for any $x\in X$ and any $U ∈ \mathcal{T}$ with $x ∈ U$ there is $B ∈ \mathcal{B}$ such that $x \in B ⊂ U$.

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
> A topological space $(X,\mathcal{T})$ is *second-countable* if there is a [[Equinumerous and Countability#^79eb6c|countable]] basis for $\mathcal{T}$. ^a8abf4