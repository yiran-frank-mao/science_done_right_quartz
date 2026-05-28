## Singular Cohomology

We can construct a specific cohomology theory, called singular cohomology, by dualizing the singular chain complex.

> [!definition] Cochains
> Let $X$ be a [[Topological Spaces#^65c94a|topological space]] and $G$ be an [[Groups, Order and Subgroups#^6d511a|abelian group]] (the *coefficient group*). The group of *$n$-cochains* with coefficients in $G$ is the group of all homomorphisms from the singular $n$-chain group $C_n(X)$ to $G$:
> $$C^n(X;G) := \operatorname{Hom}(C_n(X), G)$$
> An element $\varphi \in C^n(X;G)$ is a map $\varphi\colon C_n(X) \to G$, and it is completely determined by its values on the basis of singular $n$-simplices $\sigma\colon \Delta^n \to X$.

> [!definition] Coboundary Operator
> The *coboundary operator* $d^{n}\colon C^{n-1}(X;G) \to C^n(X;G)$ is defined as the dual of the boundary operator $d_{n}\colon C_n(X) \to C_{n-1}(X)$. For $\varphi \in C^{n-1}(X;G)$ and a singular $n$-simplex $\sigma$, it is defined by:
> $$(d^n\varphi)(\sigma) = \varphi(d_{n}\sigma) = \sum_{i=0}^n (-1)^i \varphi(\sigma|_{[v_0, \dots, \hat{v}_i, \dots, v_n]}).$$

> [!lemma] 
> $d^{n+1} \circ d^n = 0$. Therefore, $(C^*(X;G), d^*)$ is a cochain complex.

*Proof*  For any $\varphi \in C^{n-1}(X;G)$ and any $(n+1)$-simplex $\sigma$: $$(d^{n+1}(d^n\varphi))(\sigma) = (d^n\varphi)(d_{n+1}\sigma) = \varphi(d_n(d_{n+1}\sigma)) = \varphi(0) = 0$$since $\partial_n \circ \partial_{n+1} = 0$ in the singular chain complex. $\square$

> [!definition] Singular Cohomology Group
> The *$n$-th singular cohomology group* of $X$ with coefficients in $G$ is the $n$-th cohomology group of this cochain complex:
> $$H^n(X;G) = \frac{\ker(d^{n+1})}{\operatorname{im}(d^n)}.$$
> If the coefficient group $G = \mathbb{Z}$, is clear from the context, or is not important for the discussion, we often write $H^n(X)$ for $H^n(X;G)$.

A continuous map $f:X \to Y$ induces a chain map $f_\#: C_n(X) \to C_n(Y)$, which in turn induces a cochain map $f^\#: C^n(Y;G) \to C^n(X;G)$ by $\varphi \mapsto \varphi \circ f_\#$. This map on cochains induces a homomorphism on the cohomology groups, $f^{*}\colon H^n(Y;G) \to H^n(X;G)$.