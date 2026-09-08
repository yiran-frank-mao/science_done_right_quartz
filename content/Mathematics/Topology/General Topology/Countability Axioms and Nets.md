## Countability Axioms

> [!definition] Local Basis
> For each $x\in X$, a collection of [[Mathematics/Topology/General Topology/Closure, Interior and Boundary#^eda962|open neighbourhoods]] $\{N_{i}\}_{i\in I}$ is called a *local basis at $x$* if for any open neighbourhood $N$ of $x$ there is some $i$ so that $N_{i}\subset N$.
> 

> [!definition] First Countable
> A [[Mathematics/Topology/General Topology/Topological Spaces#^concept-39ce12df888c|topological space]] $(X,\mathcal{T})$ is *first-countable* if there is a [[Equinumerous and Countability#^79eb6c|countable]] local basis at each point $x\in X$. ^concept-b7c77a3b39fa

<u><b>e.g.</b></u>  
- Any metric space is first countable. To see this, note that the set of open balls centered at $x$ with radius $2^{-n}$ for all natural numbers $n$ form a countable local basis at $x$;
- Cofinite topology on uncountable sets is not first countable;
$\quad$

> [!proposition]
> If a topological space $X$ is first countable, then it has a countable nested local basis $$N_{1}\supset N_{2} \supset N_{3} \supset\cdots $$
> for all $x\in X$.

*Proof*  This is because for any countable local basis $N_{1}, N_{2}\cdots$, we can define a new countable local basis by setting $M_{n}:=\cap_{i=1}^{n} N_{i}$. $\square$

> [!definition] Second Countable
> A topological space $(X,\mathcal{T})$ is *second-countable* if there is a [[Equinumerous and Countability#^79eb6c|countable]] basis for $\mathcal{T}$. ^concept-5144b7350d14
> 

<u><b>e.g.</b></u>  $\R^{n}$ with the usual topology is second-countable, since the collection of all open balls with rational radius and rational center forms a countable basis.

> [!proposition]
> If $X$ is [[Mathematics/Topology/General Topology/Countability Axioms and Nets#^concept-5144b7350d14|second countable]], then
> 1. $X$ is [[Mathematics/Topology/General Topology/Countability Axioms and Nets#^concept-b7c77a3b39fa|first countable]];
> 2. $X$ is [[Mathematics/Topology/General Topology/Closure, Interior and Boundary#^acb78f|separable]];
> 3. $X$ is [[Mathematics/Topology/General Topology/Compactness of Topological Space#^concept-871f5f6137af|Lindelöf]].
> $\quad$
> 

*Proof*  Suppose $X$ is second countable with basis $\mathcal{B}=\{B_{1},B_{2},\cdots\}$ and $x\in X$. Pick all sets in $\mathcal{B}$ containing $x$, then this is a local basis at $x$, and is countable; To show separability, we define a countable subset by choosing a point from each basis set, say $Y:=\{x_{i} \mid x_{i}\in B_{i}\}$. Then $\overline{Y}=X$ because for any $x\notin Y$, a neighbourhood $U$ of $x$ contains some $B_{i}$, thus contains some $x_{i}\in Y$, so $x\in Y'$; The proof of Lindelöf is provided [[Compactness of Topological Space#^40d004|here]].  $\square$

>[!definition] Convergent Sequence
>Let $(X,τ)$ be a topological space. A sequence $(x_{n})$ in $X$ is called convergent to $x ∈ X$ if for any [[Closure, Interior and Boundary#^eda962|neighborhood]] $U$ of $x$ there exists an integer $N$ such that $x_{n} ∈ U$ for all $n≥N$. We write $\lim_{n→∞}x_{n} =x$ or simply $x_{n} →x$. ^72dffe

## Nets

In the topology scenario, a net is a generalization of a sequence:

> [!definition] Net
> Suppose $X$ is a [[Topological Spaces#^concept-39ce12df888c|topological space]], then a *net* in $X$ is a map $x\colon I\to X$, where $(I,\lesssim)$ is a [[Preorder, Partial Order and Posets#^fa7f24|directed set]]. We often write it as $\{x_{i}\}_{i\in I}$. ^ed5107

> [!definition] Convergence of Nets
> Let $X$ be a topological space and $\{x_{i}\}_{i\in I}$ be a net in $X$. Then we say that *$\{x_{i}\}_{i\in I}$ converges to $x\in X$* if for every [[Closure, Interior and Boundary#^eda962|neighbourhood]] $U$ of $x$, there exists $i_{0}\in I$ such that $x_{i}\in U$ for all $i\gtrsim i_{0}$. We write $\lim_{i\in I}x_{i}=x$ or simply $x_{i}\to x$.
> 

> [!definition] Subnet
> Let $\{x_{i}\}_{i\in I}$ be a [[Countability Axioms and Nets#^ed5107|net]] in $X$. A *subnet* of $\{x_{i}\}_{i\in I}$ is a net $\{y_{j}\}_{j\in J}$ in $X$ such that there exists a map $f\colon J\to I$ satisfying $y=x\circ f$ and for all $i_{0}\in I$, there exists $j_{0}\in J$ such that $f(j)\gtrsim i_{0}$ for all $j\gtrsim j_{0}$.
> 

We now show that the similar results for sequences also hold for nets. The crucial point is that the local 

> [!lemma]
> Suppose $X$ is a [[Mathematics/Topology/General Topology/Topological Spaces#^concept-39ce12df888c|topological space]], and $x\in X$. Then the collection of all open neighbourhoods of $x$, denoted $\mathcal{O}(x)$, is a [[Mathematics/Set Theory/Preorder, Partial Order and Posets#^fa7f24|directed set]] with inclusion being the [[Mathematics/Set Theory/Preorder, Partial Order and Posets#^fa7f22|preorder]]. 
> 

*Proof*  It is clear that $\subseteq$ is a preorder on $\mathcal{O}(x)$, and for every $U,V\in\mathcal{O}(x)$, $U\cup V$ contains both $U$ and $V$. $\square$

> [!proposition]
> Let $X$ be a topological space, and $Y\subset X$. Then $x\in \overline{Y}$ if and only if there exists a net $\{y_{i}\}_{i\in I}$ in $Y$ such that $y_{i}\to x$.

 *Proof*  Suppose $x\in \overline{Y}$. Then for every neighbourhood $U$ of $x$, we have $U\cap Y\neq \emptyset$. Let $I=\{U\subset X: U \text{ is a neighbourhood of } x\}$, and define a preorder on $I$ by $U\lesssim V$ if and only if $V\subset U$. Then $(I,\lesssim)$ is a directed set. For each $U\in I$, choose $y_{U}\in U\cap Y$. Then $\{y_{U}\}_{U\in I}$ is a net in $Y$ that converges to $x$. The converse is clear. $\square$


