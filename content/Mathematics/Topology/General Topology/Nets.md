In the topology scenario, a net is a generalization of a sequence:

> [!definition] Net
> Suppose $X$ is a [[Topological Spaces#^65c94a|topological space]], then a *net* in $X$ is a map $x\colon I\to X$, where $(I,\lesssim)$ is a [[Preorder, Partial Order and Posets#^fa7f24|directed set]]. We often write it as $\{x_{i}\}_{i\in I}$. ^ed5107

> [!definition] Convergence of Nets
> Let $X$ be a topological space and $\{x_{i}\}_{i\in I}$ be a net in $X$. Then we say that *$\{x_{i}\}_{i\in I}$ converges to $x\in X$* if for every [[Closure, Interior and Boundary#^eda962|neighbourhood]] $U$ of $x$, there exists $i_{0}\in I$ such that $x_{i}\in U$ for all $i\gtrsim i_{0}$. We write $\lim_{i\in I}x_{i}=x$ or simply $x_{i}\to x$.
> 

> [!definition] Subnet
> Let $\{x_{i}\}_{i\in I}$ be a [[Nets#^ed5107|net]] in $X$. A *subnet* of $\{x_{i}\}_{i\in I}$ is a net $\{y_{j}\}_{j\in J}$ in $X$ such that there exists a map $f\colon J\to I$ satisfying $y=x\circ f$ and for all $i_{0}\in I$, there exists $j_{0}\in J$ such that $f(j)\gtrsim i_{0}$ for all $j\gtrsim j_{0}$.
> 

We now show that the similar results for sequences also hold for nets.

> [!proposition]
> Let $X$ be a topological space, and $Y\subset X$. Then $x\in \overline{Y}$ if and only if there exists a net $\{y_{i}\}_{i\in I}$ in $Y$ such that $y_{i}\to x$.

 *Proof*  Suppose $x\in \overline{Y}$. Then for every neighbourhood $U$ of $x$, we have $U\cap Y\neq \emptyset$. Let $I=\{U\subset X: U \text{ is a neighbourhood of } x\}$, and define a preorder on $I$ by $U\lesssim V$ if and only if $V\subset U$. Then $(I,\lesssim)$ is a directed set. For each $U\in I$, choose $y_{U}\in U\cap Y$. Then $\{y_{U}\}_{U\in I}$ is a net in $Y$ that converges to $x$. The converse is clear. $\square$
