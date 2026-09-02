>[!definition] Metric, Metric Space
> A *metric* $d$ on a set $X$ is a map $\newcommand{\R}{\mathbb{R}}d\colon X\times X\to\R$ such that 
> 1. Positivity: $d(x,y)\geq 0$ with equality if and only if $x=y$;
>2. Symmetry: $d(x,y)=d(y,x)$ for every $x,y\in X$;
>3. Triangle inequality: $d(x,z)\leq d(x,y)+d(y,z)$ for every $x,y,z\in X$.
> 
> We call $(X,d)$ a *metric space*.  ^0eacc7

<u><b>e.g.</b></u>  
- The *discrete metric* on any non-empty set $X$ is defined by setting $d(x,x) = 0$ and $d(x,y) = 1$ if $x \neq y$;
- Any [[Normed Spaces#^345fd3|norm]] $\|\cdot\|$ on a [[Vector Spaces#^f4b63e|vector space]] $X$ gives rise to a metric on $X$ by setting $d (x , y ) = \|x-y\|$. For example, on $\R^{n}$, we have $L^{p}$ metrics for $1 \leq p \leq \infty$ given by $$d_{p}(x,y)=\left(\sum_{i=1}^{n}|x_{i}-y_{i}|^{p}\right)^{1/p},$$which are induced from [[Normed Spaces#^af1cb7|$L^{p}$ norms]].
- Let $\R^{J} = \prod_{j\in J}\R$. Then the *uniform metric* on $\R^{J}$ is given by $$d_{u}(x,y)=\sup\left\{\min\{|x_{j}-y_{j}|, 1\}:j\in J\right\}.$$More generally, over a set $\mathscr{F}$ of functions $X\to\R$, the *uniform metric* is defined as$$d_{u}(f,g)=\sup_{x\in X} \| f(x)-g(x)\|.$$
- Consider the set $\Z$ of integers. Let $p$ be a prime. For any $x,y ∈ \Z$ with $x \neq y$, there is a unique $k ∈ \N$ such that $x −y = p^{k}n$, where $n ∈ \Z$ is not divisible by $p$. The following is called the *$p$-adic metric*: $$d(x,y)=\begin{cases}\frac{1}{k+1} \quad &\text{if } x\neq y \\0 \quad &\text{otherwise}\end{cases}$$
- Let $(X_1, d_1)$ and $(X_2, d_2)$ be two metric spaces. Then for any $1\leq p\leq\infty$, we have $$
\varrho_p((x_1,x_2),(y_1,y_2))=\begin{cases}(d_1(x_1,y_1)^p+d_2(x_2,y_2)^p)^{1/p}&1\leq p<\infty\\\max(d_1(x_1,y_1),d_2(x_2,y_2))&p=\infty,\end{cases}
$$ defines a metric on $X_{1} \times X_2$.
- Let $X$ be the set of all words (finite sequences of 26 symbols). Then the *Levenshtein (spelling) distance* between word $x$ and $y$ is the minimum number of ‘edits’ required to change from $x$ to $y$, where an ‘edit’ is any one of (i) insertion of a symbol (ii) deletion of a symbol (iii) change of a letter.
- Let $G$ be a [[Basics of Graphs#^9c650d|graph]]. The *combinatorial metric* defined on the vertices of $G$ is the minimal number of edges required to join the two vertices. (For this definition, we need to assume that each pair of vertices can be joined by a path in the graph).
$\quad$

## Metric Subspace

> [!definition] Metric Subspace
> Let $(X,d)$ be a metric space and $S$ be a subset of $X$. Define $$d_{S}(x,y):=d(x,y)\quad \forall x,y\in S$$Then $d_S$ is a metric on $S$ which is called the *induced metric on $S$* and $(S,d_{S})$ is called a *metric subspace* of $(X,d)$.

> [!proposition]
> Suppose $(S,d_{S})$ is a nonempty metric subspace of $(X,d)$. Given $x\in S$. Let $B_r^S(x)$ denote the open ball in $S$ of radius $r$ with center $x$. Then $$B_{r}^{S}(x)=S\cap B_r(x).$$
> 

*Proof*  For any $y\in B_{r}^{S}(x)$, $y\in S$ and $y\in B_{r}(x)$, so $y\in S\cap B_{r}(x)$. Conversely, for any $y\in S\cap B_{r}(x)$, $y\in S$ and $y\in B_{r}(x)$, so $d_{S}(x,y)=d(x,y)<r$, hence $y\in B_{r}^{S}(x)$. $\square$

> [!proposition]
> Let $(X,d)$ be a metric space and $(S,d)$ a subspace. Let $A ⊂ S$, then
> - $A$ is open in $S$ iff  $A=S∩O$ with $O$ open in $X$.
> - $A$ is closed in $S$ iff $A=S∩C$ with $C$ closed in $X$.


<u><b>e.g.</b></u> Consider $S = (0, 2]$ in $\R$. $(0,1)$ and $(1,2]$ are open in $S$, but $(1,2]$ is not open in $\R$. $(0,1]$ and $[1,2]$ are closed in $S$, but $(0,1]$ is not closed in $\R$.