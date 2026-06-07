In this section, we develop bump functions and partitions of unity, which are tools for patching together local smooth objects into global ones.

> [!definition] Partition of Unity
> Let $M$ be a manifold, and $\mathcal{A} = \{U_{\alpha}\}_{\alpha \in A}$ an open cover of $M$. A _(smooth) partition of unity_ subordinate to the cover $\mathcal{A}$ is a collection of functions $\{\rho_{\alpha}\}_{\alpha \in A} \subset C^{\infty}(M)$ satisfying:
> 
> 1. For every $x \in M$ and every $\alpha \in A$, $0 \leq \rho_{\alpha}(x) \leq 1$.
> 2. The support $\operatorname{supp}(\rho_{\alpha}) = \{x \in M : \rho_{\alpha}(x) \neq 0\}$ is contained in $U_{\alpha}$ for each $\alpha \in A$.
> 3. The set of supports $\{\operatorname{supp}(\rho_{\alpha}) : \alpha \in A\}$ is locally finite. That is, for every point $x \in M$, there exists an open neighborhood $U$ of $x$ in $M$ such that $\{\alpha : \operatorname{supp}(\rho_{\alpha}) \cap U \neq \emptyset\}$ is finite.
> 4. For each $x \in M$, $\sum_{\alpha \in A} \rho_{\alpha}(x) = 1$.
>$\quad$

> [!theorem]  
> Let $M$ be a manifold and $\mathcal{A}$ an open cover. Then there exists a smooth partition of unity subordinate to $\mathcal{A}$.

First, we will develop the basic building blocks for the construction, which are smooth compactly supported functions on Euclidean space: 

> [!lemma]  
> If $0 < r_1 < r_2$, then there exists $H_{r_1, r_2} \in C^{\infty}(\mathbb{R}^n)$ such that  
> - $H(x) = 1$ for $x \in \overline{B_{r_1}(0)}$,  
> - $0 < H(x) < 1$ for $x \in B_{r_2}(0) \setminus B_{r_1}(0)$, and  
> - $H(x) = 0$ for $x \notin B_{r_2}(0)$.
> $\quad$

*Proof*  Let $f\colon \R\to \R$ satisfy $$f(t)=\begin{cases}e^{-1/t}, \quad & t>0, \\ 0, \quad & t\leq 0.\end{cases}$$Then the function $H\colon \R^{n} \to \R$ such that $$H(x):=\frac{f(r_{2}-|x|)}{f(r_{2}-|x|)+f(|x|-r_{1})}$$will do the job. $\square$

## Applications of Partitions of Unity

> [!corollary] Existence of Bump Functions
> Let $M$ be a smooth manifold. For any closed subset $A\subseteq M$ and any open subset $U$ containing $A$, there exists a smooth bump function for $A$ supported in $U$. That is, a smooth function $\rho\colon M\to \R$ such that $\rho(x)=1$ for $x\in A$ and $\supp \rho \subset U$.

*Proof*  Let $U_{0}=U$, $U_{1}=M\setminus A$, and $\mathcal{A}=\{U_{0},U_{1}\}$. Then we can find a partition of unity $\{\rho_{0},\rho_{1}\}$ subordinate to $\mathcal{A}$. Since $\rho_{1}(x)=0$ for $x\in A$, we have that $\rho_{0}(x)=1$ for $x\in A$. Moreover, the support of $\rho_{0}$ is contained in $U_{0}=U$. $\square$

> [!proposition]
> Smooth functions on a closed submanifold are restrictions. That is, if $N$ is a closed $k$-dimensional submanifold of $M$, then for any smooth function $f\in C^{\infty}(N)$, there exists $g\in C^{\infty}(M)$ such that $g\Big|_{N}=f$.
> 

It is an important question whether an abstract manifold can always be realized as a submanifold of some Euclidean space. A simple case is when the manifold is compact. In this case, we can use the following theorem:

> [!theorem] Embedding Compact Manifolds in High Dimension
> Let $M$ be a compact manifold. Then for sufficiently large $N$ there exists a smooth embedding $F \colon M →\R^{N}$.

