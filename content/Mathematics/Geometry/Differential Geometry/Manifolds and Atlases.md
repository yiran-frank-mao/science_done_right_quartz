---
created: 2024-01-08
updated: 2024-10-20
tags:
  - differential-geometry
---
>[!definition] Manifold & Manifold with Boundary
> An *$n$-dimensional manifold*, or *$n$-manifold* (without boundary) for short, is a [[Separation and Hausdorff Spaces#^f7bcc8|Hausdorff]] and [[Topological Spaces#^a8abf4|second-countable]] [[Topological Spaces#^65c94a|topological space]] $M$ with the property that each point has a neighbourhood that is [[Isometries and Homeomorphisms#^85034b|homeomorphic]] to an open subset of $n$-dimensional Euclidean space $\R^{n}$. 
> A *manifold with boundary* is a Hausdorff and second-countable topological space $M$ such that each point has a neighbourhood homeomorphic to an open subset of the closed half-space $H^{n}=\{(x_{1},\dots,x_{n})\in \R^{n}: x_{n}\geq 0\}$. The *boundary* of $M$ is the set of points that correspond to points in $H^{n}$ with $x_{n}=0$.
> A *closed manifold* is a [[Compactness of Topological Space#^da2511|compact]] manifold with no boundary. ^3407e4

Clearly, on a manifold, there might be different collections of homeomorphisms that makes it locally Euclidean. So we introduce:

>[!definition] Chart and Atlas
>A *chart* for a manifold $M$ is a [[Isometries and Homeomorphisms#^85034b|homeomorphism]] $φ\colon U \to V$ where $U$ is open in $M$ and $V$ is open in $\R^n$. A collection of charts $\mathcal{A}=\{\varphi_{\alpha}\colon U_{\alpha}\to V_{\alpha}|\alpha\in I\}$ is called an *atlas* for $M$ if $\cup_{\alpha\in I}U_{\alpha}=M$.
>A manifold equipped with an atlas is called a *topological manifold*. ^441ce2

<b><u>e.g.</u></b>
- Consider the set $M=\R$ with the usual topology. $\mathcal{A}=\{ x\mapsto x\colon\R\to \R\}$ and $\mathcal{B}=\{ x \mapsto x^{3} \colon \R \to \R \}$ are both differentiable atlases. They are not compatible since the union $\{ x\mapsto x, x\mapsto x^{3} \}$ is not differentiable.
- The sphere $S^{n}=\{ x\in \R^{n+1}:\|x \| =1\}$ is a closed subset of Euclidean space, thus the topological requirements are satisfied. Define the following two maps: $$\varphi_{+}\colon S^{n}\setminus \{ N \}\to\R^{n}, \quad \varphi_{-}\colon S^{n}\setminus \{ S \} \to \R^{n}$$as follows: We write $x\in \R^{n+1}$ as $(y,z)$ where $y\in \R^{n}$ and $z\in \R$, we take $\varphi_{+}(y,z)=\frac{y}{1-z}$ and $\varphi_{-}(y,z)=\frac{y}{1+z}$. Then we have 
$\quad$

> [!definition] Compatible Charts & Smooth Atlas
> Two charts $\varphi$ and $\eta$ are *compatible* if $\varphi\circ \eta^{-1}$ is a diffeomorphism.
> Let $M$ be an $n$-dimensional manifold. An atlas $\mathcal{A}=\{\varphi_{\alpha}\colon U_{\alpha}\to V_{\alpha}|\alpha\in I\}$ for $M$ is *differentiable* or *smooth* if for every $\alpha$ and $\beta$ in $I$, the map $\varphi_{\beta}$ and $\varphi_{\alpha}$ are compatible.
> 

> [!definition] Compatible Atlases & Maximal Atlas
> Two differentiable atlases $\mathcal{A}$ and $\mathcal{B}$ are *compatible* if their union is also a differentiable atlas.
> A smooth atlas is called *maximal* if it is not contained in any other atlas. In other words, a maximal atlas $\mathcal{A}_{\text{max}}$ is the one that contains all charts of $M$ that are compatible with $\mathcal{A}_{\text{max}}$.

> [!proposition]
> Two differentiable atlases $\mathcal{A}$ and $\mathcal{B}$ are compatible if and only if for every chart $\phi$ in $\mathcal{A}$ and $\eta$ in $\mathcal{B}$, both $\phi \circ \eta^{-1}$ and $\eta \circ \phi^{-1}$ are smooth.

> [!definition] Smooth Manifold
> A *$C^{k}$-structure* on a manifold $M$ is an [[Relations and Functions#^973688|equivalence class]] of differentiable atlases, where two atlases are deemed equivalent if they are *$C^{k}$-compatible.
> A *smooth manifold* is a manifold $M$ together with a smooth ($C^{\infty}$) structure on $M$. ^6ef2ef

<u><b>e.g.</b></u>  
- A given manifold can carry many different atlases: For example, if $M=\R$ we can take two charts $\phi_{1}(x) = x$ and $\phi_{2}(x) = x^{3}$. Then both $\{\phi_{1}\}$ and $\{\phi_{2}\}$ are smooth atlases for $M$, they define different smooth atlases, while they are compatible.
- The 4-manifold [$E_{8}$](https://en.wikipedia.org/wiki/E8_manifold) is a topological manifold, but not smooth.
$\quad$

In fact, dimension 4 is particularly special and exotic in the theory of smooth manifolds, there are smooth 4-manifolds which are [[Isometries and Homeomorphisms#^85034b|homeomorphic]] but not diffeomorphic. We have the following theorem:

> [!theorem]
> $\R^{n}$ for all $n\neq 4$ has a unique smooth structure. $\R^{4}$ has uncountably many smooth structures.

## Submanifolds

> [!definition] Submanifold of $\R^{n}$
> A subset $S\subseteq \R^{n}$ is a $k$-dimensional submanifold of $\R^{n}$, if for every $x\in S$ there exists an open set $U\subseteq \R^{n}$ containing $x$ and a diffeomorphism $\varphi\colon U\to \R^{n}$ such that $\varphi(U\cap S)=\varphi(U)\cap (\R^{k}\times \{0\})$, with $0\in\R^{n-k}$. We call such a map $\varphi$ a submanifold chart for $S$ at $x$.

<u><b>e.g.</b></u>  

> [!proposition]
> Any $k$-dimensional submanifold $S$ of $\R^{n}$ is a smooth manifold.

There are several equivalent ways to define submanifolds:

> [!proposition]
> Let $\Sigma$ be a subset of $\mathbb{R}^n$. The following are equivalent:
> 1. $\Sigma$ is a $k$-dimensional submanifold of $\mathbb{R}^n$;
> 2. $\Sigma$ is locally the graph of a smooth function. That is, for every $x \in \Sigma$, there is a neighbourhood $U$ of $x$ in $\mathbb{R}^n$, a linear injection $\iota: \mathbb{R}^k \to \mathbb{R}^n$ and a complementary linear injection $\iota^{\perp}\colon \mathbb{R}^{n-k} \to \mathbb{R}^n$,  
>    an open subset $A \subset \mathbb{R}^k$, and a smooth map $u: A \to \mathbb{R}^{n-k}$ such that  
>    $$\Sigma \cap U = \{\iota(z) + \iota^{\perp}(u(z)) : z \in A\}.$$
> 3. $\Sigma$ is locally the level set of a submersion. That is, for every $x \in \Sigma$, there is a neighbourhood $U$ of $x$ in $\mathbb{R}^n$ and a submersion $G: U \to \mathbb{R}^{n-k}$ such that  
>    $$\Sigma \cap U = G^{-1}(0) = \{y \in U : G(y) = 0\}.$$
> 4. $\Sigma$ is locally the image of an embedding. That is, for every $x \in \Sigma$, there exists a neighbourhood $U$ of $x$ in $\mathbb{R}^n$, an open set $A \subset \mathbb{R}^k$, and a smooth embedding $F\colon A \to U$ such that $\Sigma \cap U = F(A)$.
> $\quad$

> [!definition] Embedded Submanifold
> Suppose $M$ is a smooth manifold with or without boundary. An embedded (or regular) submanifold of $M$ is a subset $S \subset M$ that is a manifold (without boundary) in the subspace topology, endowed with a smooth structure with respect to which the inclusion map $S\hookrightarrow M$ is a [[Smooth Functions and Maps#^9d6e60|smooth embedding]]. ^632f7d

> [!lemma] Open Submanifold Lemma
> An open subset of a manifold is a manifold of the same dimension.

*Proof*  Let $M$ be an $n$-dimensional smooth manifold. Suppose $U\subset M$ is open, and $\mathcal{A}=\{(V_{\alpha}, \varphi_{\alpha})\}$ is an atlas of $M$. Consider the restricted atlas $\mathcal{A}|_{U}=\{(V_{\alpha}\cap U, \varphi_{\alpha}|_{V_{\alpha}\cap U})\}$ which covers $U$. Since each $V_{\alpha}$​ is open in $M$, and $U$ is open in $M$, so $V_{\alpha}\cap U$ is open in $M$ and hence open in the subspace topology on $U$. Moreover, on overlaps, the transition maps are also smooth, and $U$ remains Hausdorff and second countable.