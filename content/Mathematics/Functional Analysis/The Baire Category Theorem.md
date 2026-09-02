---
tags:
  - closed-graph-theorem
  - open-mapping-theorem
---
> [!definition] Baire
> A *Baire Space* is a [[Topological Spaces#^65c94a|topological space]] $X$ in which every countable intersection of open dense subsets remains dense.
> 

> [!theorem] Baire Category Theorem
> Every completely metrizable space is Baire. Every locally compact Hausdorff space is Baire. ^b97e4d





## Open Mapping Theorem

> [!theorem] Open Mapping Theorem
> Let $X$ and $Y$ be Banach spaces and $T$ a surjective bounded linear map of $X\to Y$. Then $T$ is an [[Continuous Maps on Topological Spaces#^cd295d|open map]].
> 



## Closed Graph Theorem

> [!theorem] Closed Graph Theorem
> Let $X$ and $Y$ be Banach spaces and $T$ a linear map of $X\to Y$. Then $T$ is bounded if and only if the graph of $T$ is closed in $X\times Y$.

> [!corollary] Helinger-Toeplitz Theorem
> Let $A$ be an everywhere defined linear operator on a Hilbert space $\newcommand{\H}{\mathcal{H}}\H$ such that $\langle x, Ay\rangle=\langle Ax,y\rangle$ holds for all $x,y\in\H$. Then $A$ is bounded. ^1d50d9

*Proof*  By the closed graph theorem, it suffices to show $\Gamma(A)$ is closed in $\H\times\H$. Suppose $\{(x_{n},Ax_{n})\}_{n=1}^{\infty}$ is a sequence in $\Gamma(A)$ that converges to $(x, y)$. Then $x_{n}\to x$ and $Ax_{n}\to y$. By the continuity of the inner product, we have $$\langle A(x_{n}-x),A(x_{n}-x)\rangle = \langle A^{2}(x_{n}-x),x_{n}-x\rangle\to 0.$$Therefore by triangle inequality, we have $$\|y-Ax\|\leq\|y-Ax_{n}\|+\|Ax_{n}-Ax\|\to 0.$$This shows that $y=Ax$, hence $(x,y)\in \Gamma(A)$, which implies that $\Gamma(A)$ is closed. $\square$

## Uniform Boundedness Principle

> [!theorem] Uniform Boundedness Principle
> Let $X$ be a Banach space and $Y$ a normed vector space. Let $\{T_{\alpha}\}_{\alpha\in A}$ be a family of bounded linear operators from $X$ to $Y$. If for every $x\in X$, the set $\{\|T_{\alpha}x\|\colon \alpha\in A\}$ is bounded, then the set $\{\|T_{\alpha}\|_{\text{op}}\colon \alpha\in A\}$ is bounded.
> 

*Proof*  Define sets $X_{n}:=\{x\in X : \sup_{\alpha\in A} \|T_{\alpha}x\|\leq n\}$. Each $X_{n}$ is closed because if a sequence $(x_{k})\subset X_{n}$ converges to $x\in X$, then $T_{\alpha}x_{k} \to T_{\alpha}x$ by continuity, so $\|T_{\alpha}x\| \leq \|T_{\alpha}x-T_{\alpha}x_{k}\|+\|T_{\alpha}x_{k}\|\leq \|T_{\alpha}x-T_{\alpha}x_{k}\|+n$ for all $k$, thus $\|T_{\alpha}x\|\leq n$ for all $\alpha$, therefore, $x\in X_{n}$. Note that from our assumption, we have $\cup_{n\in\N} X_{n} = X$. By the [[The Baire Category Theorem#^b97e4d|Baire category theorem]], there exists some $m\in\N$ such that $X_{m}$ has nonempty interior. So there exists $x_{0}\in X_{m}$ and $\varepsilon>0$ such that the closure of $B_{\varepsilon}(x_{0})$ is contained in $X_{m}$. For any arbitrary $u\in X$ with $\|u\|\leq 1$, we have $$\begin{aligned} \|T_{\alpha}u\| &= \varepsilon^{-1}\|T_{\alpha}x_{0}+\varepsilon T_{\alpha}u - T_{\alpha}x_{0} \| \\ &\leq \varepsilon^{-1}\|T_{\alpha}(x_{0}+\varepsilon u)\| + \varepsilon^{-1}\|T_{\alpha}x_{0}\| \\ &\leq 2\varepsilon^{-1}m,\end{aligned}$$which proves the desired statement. $\square$ 