---
created: 2024-01-08
updated: 2026-11-25
tags:
  - differential-geometry
  - differential-topology
---
A *manifold* itself is a purely topological object, but it is the most basic object in differential geometry. To do calculus on a manifold, we need to equip it with a *smooth structure,* which is given by an atlas of compatible charts. So the data of a *smooth manifold* is a manifold **together with** a smooth structure. We will discuss these concepts in detail in the following sections.

## Topological Manifolds

> [!definition] Locally Euclidean Space
> A [[Mathematics/Topology/General Topology/Topological Spaces#^concept-39ce12df888c|topological space]] $X$ is said to be *locally Euclidean of dimension $n$* if each point $x\in X$ has an open neighbourhood that is homeomorphic to an open subset of $\newcommand{\R}{\mathbb{R}}\R^{n}$. ^concept-ce681672e441

> [!remark]
> In the definition, we can replace "homeomorphic to an open subset of $\R^{n}$" by either "homeomorphic to $\R^{n}$" or "homeomorphic to an open ball in $\R^{n}$" without changing the definition.
> 

<u><b>e.g.</b></u>  A [[Mathematics/Topology/General Topology/Topological Spaces#^concept-39ce12df888c|topological space]] is locally Euclidean of dimension $0$ iff it is discrete.

>[!definition] Manifold & Manifold with Boundary
> An *$n$-dimensional topological manifold*, or *$n$-manifold* (without boundary) for short, is a [[Separation and Hausdorff Spaces#^f7bcc8|Hausdorff]] and [[Mathematics/Topology/General Topology/Countability Axioms and Nets#^concept-5144b7350d14|second-countable]] [[Mathematics/Geometry/Differential Geometry/Manifolds, Atlases and Smooth Structures#^concept-ce681672e441|locally Euclidean space]] of dimension $n$.
> A *manifold with boundary* is a Hausdorff and second-countable topological space $M$ such that each point has a neighbourhood homeomorphic to an open subset of the closed half-space $H^{n}=\{(x_{1},\dots,x_{n})\in \R^{n}: x_{n}\geq 0\}$. The *interior* of $M$, denoted $\operatorname{int}(M)$, is defined as
> $$ \operatorname{int}(M) := \{p \in M : p \text{ has an open neighbourhood homeomorphic to an open set in } \R^{n}\}. $$
> The *boundary* of $M$, denoted $\partial M$, is $\partial M=M\setminus \operatorname{int}(M)$.
> A *closed manifold* is a [[Compactness of Topological Space#^da2511|compact]] manifold without boundary. ^3407e4

> [!remark]
> Note that this notion of "interior" and "boundary" is totally different from the notion of [[Closure, Interior and Boundary#^871863|"interior"]] and [[Closure, Interior and Boundary#^d3c02b|"boundary"]] in general topology. In fact, as manifolds are topological spaces themselves, their boundaries are always empty in the sense of general topology.

> [!lemma]
> If $p\in H^{n}$, then no open neighbourhood of  $p$ is homeomorphic to an open set in $\R^{n}$.
> 

This lemma seems obvious, but it turns out to be nontrivial. We will need homotopy or homology to prove it. The following proposition is a direct consequence of this lemma:

> [!proposition]
> Let $M$ be an $n$-manifold with boundary. Then
> - $\partial M\subset M$ is closed;
> - $\partial M$ is an $(n-1)$-manifold without boundary;
> - $\operatorname{int}(M)$ is an $n$-manifold without boundary;
> - $M$ is a manifold without boundary if and only if $\partial M=\emptyset$.

> [!proposition]
> Every manifold, with or without boundary, is [[Mathematics/Topology/General Topology/Compactness of Topological Space#^concept-0adb622702af|locally compact]], [[Mathematics/Topology/General Topology/Compactness of Topological Space#^concept-0e2c3a1243de|paracompact]], and [[Mathematics/Topology/General Topology/Connectedness and Paths#^ba4f32|locally path-connected]].
> 

*Proof*  It is locally path-connected because it is locally Euclidean. It is locally compact because it is second-countable and locally Euclidean, thus has a countable basis of precompact sets (ref. [[Compactness of Topological Space#^99bdc9|proposition]]). [[Compactness of Topological Space#^60e960|It is paracompact because it is locally compact, Hausdorff, and second-countable]]. $\square$

Now we see some examples of manifolds and constructions of new manifolds from old ones:

<u><b>e.g.</b></u>  
- The closed unit ball in $\R^{2}$ is a 2-manifold with boundary $S^{1}$;
- Recall that if $f \colon X \to Y$ is a continuous map of topological spaces, then $x \mapsto (x, f(x))$ defines a topological embedding $\phi \colon X \to X \times Y$, giving a homeomorphism from $X$ onto the graph of $f$. Let $U ⊂\R^{n}$ be open and $f \colon U \to \R^{k}$ continuous. Then the graph $\Gamma( f ) ⊂\R^{n+k}$ is always a manifold homeomorphic to $U$; More generally, for any continuous map $f \colon M \to N$ of manifolds, we will see that $Γ( f ) ⊂M ×N$ is a (sub)manifold homeomorphic to $M$;
- If $M_{1}, \cdots , M_{k}$ are manifolds of dimensions $n_{1},\cdots, n_{k}$, then [[Constructions on Topological Spaces#^fbf303|the product]] $M_{1} \times \cdots \times M_{k}$ is a manifold of dimension $n_{1} +\cdots + n_{k}$. This is because the product of homeomorphisms is a homeomorphism. A concrete example is the torus $T^{2}=S^{1}\times S^{1}$, which is a 2-manifold;
- Similar to [[Constructions on Topological Spaces#^b43761|attaching topological spaces]], we can glue two manifolds with boundary along homeomorphic boundary components to get a new manifold without boundary. Concretely, given a homeomorphism $f\colon \partial N \to \partial M$, since $\partial N$ is closed in $N$, we can form the attaching space $M\cup_{f}N$. With this setup, $M\cup_{f}N$ is a manifold (without boundary). Moreover, there are topological embeddings $\varphi \colon M \hookrightarrow M\cup_{f} N$ and $\eta \colon N \hookrightarrow M \cup_{f} N$ whose images are closed and satisfy: $\varphi(M) \cup \eta(N) = M\cup_{f} N$ and $\varphi(M) ∩\eta(N) = \varphi(\partial M) = \eta(\partial N)$.
  <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/gluing_manifolds_along_boundary.svg" style="width:55%;"/>
- A special case of gluing two manifolds along the boundary is the *double* of a manifold with boundary $M$, which is the manifold $D(M) = M \cup_{\text{id}} M$ obtained by gluing two copies of $M$ along the identity map on $\partial M$. For example, the double of the closed unit disk in $\R^{n}$ is homeomorphic to $S^{n}$.

## Differentiable Manifolds

Note that [[Manifolds, Atlases and Smooth Structures#^concept-ce681672e441|local Euclideanness]] only requires existence of neighbourhoods that look like $\R^{n}$, and on a manifold, there might be different collections of homeomorphisms that makes it locally Euclidean. So we introduce:

>[!definition] Chart and Atlas
> A *chart* or *coordinate* for a manifold $M$ at some point $p\in M$ is a [[Isometries and Homeomorphisms#^85034b|homeomorphism]] $\varphi\colon U \to V$ where $U$ is an open neighbourhood of $p$ and $V$ is open in $\R^{n}$. We usually write it as a tuple $(U,\varphi)$.
> A collection of charts $\mathcal{A}=\{\varphi_{\alpha}\colon U_{\alpha}\to V_{\alpha}|\alpha\in I\}$ is called an *atlas* for $M$ if $\cup_{\alpha\in I}U_{\alpha}=M$. ^441ce2

<b><u>e.g.</u></b>
- The interval $[a,b]$ is a manifold with boundary. The inclusion $x\colon [a,b] \to \R$ serves as a chart, and $\{x\}$ is an atlas.
- The sphere $S^{n}=\{ x\in \R^{n+1}:\|x \| =1\}$ is a closed subset of Euclidean space, thus the topological requirements are satisfied. For $1\leq i\leq n+1$, define charts $(U_{i}^{\pm}, \varphi_{i}^{\pm})$, where $U_{i}^{\pm} = \{x \in S^{n} \mid \pm x_i > 0\}$ and $\varphi_i^\pm(x_0, \ldots, x_n) = (x_0, \ldots, \widehat{x}_i, \ldots, x_n)$.
- Define the following two maps: $$\varphi_{+}\colon S^{n}\setminus \{ N \}\to\R^{n}, \quad \varphi_{-}\colon S^{n}\setminus \{ S \} \to \R^{n}$$as follows: We write $x\in \R^{n+1}$ as $(y,z)$ where $y\in \R^{n}$ and $z\in \R$, we take $\varphi_{+}(y,z)=\frac{y}{1-z}$ and $\varphi_{-}(y,z)=\frac{y}{1+z}$. Then we have 


> [!warning] 
> Again, an atlas is an extra structure on a (topological) manifold! 
> 

A manifold can have many different atlases, this is against our spirit of geometry. One of the main goals of differential geometry is to study the geometrical properties that are independent of the choice of atlas^[a side note: this is also a spirit of physics. We won't like physics laws to be dependent on the coordinates we choose.]. So we need a definition that is independent of the coordinates used!

> [!definition] Compatible Charts & Smooth Atlas
> Two charts $(\varphi, U)$ and $(\eta, V)$ are *compatible* if the *transition map* $\varphi\circ \eta^{-1} \colon U \cap V \to U\cap V$ is smooth.
> Let $M$ be an $n$-dimensional manifold. An atlas $\mathcal{A}=\{\varphi_{\alpha}\colon U_{\alpha}\to V_{\alpha}|\alpha\in I\}$ for $M$ is *smooth* if for every charts in $\mathcal{A}$ are compatible with each other.
> 

> [!definition] Compatible Atlases & Maximal Atlas
> Two differentiable atlases $\mathcal{A}$ and $\mathcal{B}$ are *compatible* if their union is also a differentiable atlas.
> A smooth atlas is called *maximal* if it is not contained in any other atlas. In other words, a maximal atlas $\mathcal{A}_{\text{max}}$ is the one that contains all charts of $M$ that are compatible with $\mathcal{A}_{\text{max}}$.

> [!proposition]
> Two differentiable atlases $\mathcal{A}$ and $\mathcal{B}$ are compatible if and only if for every chart $\phi$ in $\mathcal{A}$ and $\eta$ in $\mathcal{B}$, both $\phi \circ \eta^{-1}$ and $\eta \circ \phi^{-1}$ are smooth.

> [!definition] Smooth Manifold
> A *$C^{k}$-structure* on a manifold $M$ is an [[Relations and Functions#^973688|equivalence class]] of differentiable atlases, where two atlases are deemed equivalent if they are *$C^{k}$-compatible*.
> A *smooth manifold* is a manifold $M$ together with a smooth ($C^{\infty}$) structure on $M$. ^6ef2ef

> [!remark]
> Note that equivalence classes of smooth atlases are in one-to-one correspondence with maximal smooth atlases by picking the maximal atlas in each equivalence class. So we can also define a smooth structure by a maximal smooth atlas on $M$.
> 

<u><b>e.g.</b></u>  
- We have seen that a $0$-manifold $M$ is just a countable discrete space. Each point $p \in M$ has a unique chart $\varphi_{p} \colon \{p\}\to \R^{0}=\{*\}$. The collection of such charts is smooth and maximal, so each $0$-manifold has a unique smooth structure;
- On $\R^{n}$, the atlas $\newcommand{\id}{\operatorname{id}}\mathcal{A}=\{(\id_{\R^{n}},\R^{n})\}$ is a smooth (non-maximal) atlas making $\R^{n}$ a smooth manifold;
- Consider the set $M=\R$ with the usual topology. $\mathcal{A}=\{ x\mapsto x\colon\R\to \R\}$ and $\mathcal{B}=\{ x \mapsto x^{3} \colon \R \to \R \}$ are both differentiable atlases. They are not compatible because $x\mapsto \sqrt[3]{x}$ is not smooth (its derivative is $1/3 x^{-2/3}$, which blows up at $0$).
- Let $M$ be a smooth $n$–manifold with a maximal atlas $\mathcal{A}$. For any open subset $U\subset M$, we can define an atlas on $U$ by $\mathcal{A}_{U} := \{(\varphi, V) \in \mathcal{A} \mid V \subset U\}$. It’s easy to see this gives a maximal smooth atlas on $U$. Thus every open subset of $M$ naturally inherits a smooth structure, making it a open submanfold of $M$. ^2794bb
- The 4-manifold [$E_{8}$](https://en.wikipedia.org/wiki/E8_manifold) is a topological manifold, but not smooth (i.e., there is no smooth structure).
- On $S^{n}\subset \R^{n+1}$, we can define an atlas of charts $(U_{i}^{\pm}, \varphi_{i}^{\pm})$, where $U_{i}^{\pm} = \{x \in S^{n} \mid \pm x_i > 0\}$ and $\varphi_i^\pm(x_0, \ldots, x_n) = (x_0, \ldots, \widehat{x}_i, \ldots, x_n)$. This atlas is in fact smooth, which we can verify by computing the transition maps: $$\varphi_i^\pm \circ (\varphi_j^\pm)^{-1}(y_1, \ldots, y_n) = \left(y_1, \ldots, \widehat{y}_i, \ldots, \pm\sqrt{1 - |y|^2}, \ldots, y_n\right)$$ Since these transitions are smooth, the atlas determines a smooth structure. This is the *standard smooth structure* on $S^{n}$.
  <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/smooth_structure_of_S^2.svg" style="width:60%;"/>
- The real projective space $\newcommand{\RP}{\mathbb{R}\text{P}}\RP^{n}$ is a smooth $n$-manifold with the smooth structure determined by the atlas $\{(U_{i}, \varphi_{i})\}_{i=0}^{n}$ where $$ U_{i}=\{[x] \in \RP^{n} \mid x\in\R^{n}, x_{i}\neq 0\},\qquad \varphi_{i}([x])=\left( \frac{x_{0}}{x_{i}}, \cdots, \widehat{\frac{x_{i}}{x_{i}}},\cdots, \frac{x_{n}}{x_{i}} \right). $$We can verify by computing the transition maps that this atlas is smooth: for $j\leq i$, $$\varphi
  _{j}\circ \varphi_{i}^{-1} ([y]) = \left(\frac{y_{1}}{y_{j}}, \cdots, \widehat{\frac{y_{j}}{y_{j}}},\cdots, \frac{y_{i-1}}{y_j},\frac{1}{y_{j},}\frac{y_{i+1}}{y_j},\cdots, \frac{y_n}{y_j} \right). $$
- If $M_{1}, \cdots, M_{k}$ are smooth manifolds, then their product $M_{1} \times \cdots \times M_{k}$ is a smooth manifold with the product smooth structure. This is because transition maps of the product of charts are the product of the transition maps of the charts, and the product of smooth maps is smooth. Thus the torus $T^{2}=S^{1}\times S^{1}$ is a smooth 2-manifold.

Dimension 4 is particularly special and exotic in the theory of smooth manifolds, there are smooth 4-manifolds which are [[Isometries and Homeomorphisms#^85034b|homeomorphic]] but not diffeomorphic. We have the following theorem:

> [!theorem]
> $\R^{n}$ for all $n\neq 4$ has a unique smooth structure up to diffeomorphism. $\R^{4}$ has uncountably many smooth structures.

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
> Suppose $M$ is a smooth manifold with or without boundary. An *embedded (or regular) submanifold* of $M$ is a subset $S \subset M$ that is a manifold (without boundary) in the subspace topology, endowed with a smooth structure with respect to which the inclusion map $S\hookrightarrow M$ is a [[Smooth Maps#^9d6e60|smooth embedding]]. ^632f7d

> [!lemma] Open Submanifold Lemma
> An open subset of a manifold is a manifold of the same dimension.

*Proof*  Let $M$ be an $n$-dimensional smooth manifold. Suppose $U\subset M$ is open, and $\mathcal{A}=\{(V_{\alpha}, \varphi_{\alpha})\}$ is an atlas of $M$. Consider the restricted atlas $\mathcal{A}|_{U}=\{(V_{\alpha}\cap U, \varphi_{\alpha}|_{V_{\alpha}\cap U})\}$ which covers $U$. Since each $V_{\alpha}$​ is open in $M$, and $U$ is open in $M$, so $V_{\alpha}\cap U$ is open in $M$ and hence open in the subspace topology on $U$. Moreover, on overlaps, the transition maps are also smooth, and $U$ remains Hausdorff and second countable.