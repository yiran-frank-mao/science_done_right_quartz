---
tags:
  - algebra
---

> [!definition] Frobenius Algebra
> A *Frobenius algebra* is a finite-dimensional $\newcommand{\K}{\mathbb{K}}\K$-algebra $A$ equipped with a linear functional $\varepsilon\colon A \to \K$ whose nullspace contains no nontrivial left ideals. This linear functional $\varepsilon$ is called the *Frobenius form*.
> Alternatively, it is a finite-dimensional $\newcommand{\K}{\mathbb{K}}\K$-algebra equipped with an associative nondegenerate pairing $\beta\colon A \otimes A \to \K$, we call this pairing the *Frobenius pairing*.
> Moreover, it can be defined as a finite-dimensional $\newcommand{\K}{\mathbb{K}}\K$-algebra $A$ equipped with left (or right) $A$-isomorphism to its dual $A^{*}$.

> [!remark]
> The Frobenius form/pairing is part of the structure. i.e., an algebra can carry various Frobenius structures. A concrete example will be illustrated [[Frobenius Algebra#^46636d|later]].

> [!definition] Symmetric Frobenius Algebra
> A Frobenius algebra $A$ is *symmetric* if one and hence all of the following equivalent conditions hold:
> 1. The Frobenius form $\varepsilon\colon A \to \K$ is central. i.e., $\varepsilon(ab)=\varepsilon(ba)$;
> 2. The Frobenius pairing $\beta$ is symmetric;
> 3. The left $A$-isomorphism is also right $A$-linear;
> 4. The right $A$-isomorphism is also left $A$-linear.
> $\quad$

<u><b>e.g.</b></u>  
- The trivial Frobenius algebra $\K$ with Frobenius form being the identity map. Clearly, there is no nontrivial ideals in the kernel.
- The matrix algebra $\newcommand{\Mat}{\mathrm{Mat}}\Mat_{n}(\K)$ of all $n\times n$ matrices over $\K$ is a symmetric Frobenius algebra with the usual trace map. Moreover, if we precompose the trace with a noncentral invertible matrix, we can obtain another Frobenius structure on $\Mat_{n}(\K)$. For example, in the case of $\Mat_{n}(\R)$, precomposing the trace by $\begin{pmatrix}0&1\\ 1&0\end{pmatrix}$ gives another valid Frobenius form on $\Mat_{n}(\R)$. ^46636d
- Consider the group algebra $\K G$ over some finite group $G=\{g_{i}\}_{0\leq i\leq n}$. The Frobenius form can be defined as follows: $$\varepsilon\colon \K G \to \K, \quad g_{0}\mapsto 1, \quad g_{j}\mapsto 0 \text{ for }j \neq 0.$$
- Let $X$ be a compact oriented manifold. The cohomology ring $H^{*}(X;\K)$ with the cup product is a Frobenius algebra with the Frobenius form given by integration over the fundamental class of $X$: $$\varepsilon\colon H^{*}(X;\K) \to \K, \quad \alpha \mapsto \int_{[X]} \alpha.$$
