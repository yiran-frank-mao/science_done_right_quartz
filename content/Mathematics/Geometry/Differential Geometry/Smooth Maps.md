## Smoothness

>[!definition] Smooth Map
>Let $M$ be a smooth $n$-manifold with dimension $n$, an atlas $\mathcal{A}$ representing the differentiable structure on $M$. Let $N$ be another smooth $k$-manifold, and differentiable atlas $\mathcal{B}$. Let $f$ be a map from $M$ to $N$. Then $f$ is *smooth* if it is continuous, and for all $x\in M$, and every chart $\varphi\colon U\to V$ in $\mathcal{A}$ with $x\in U$ and $\eta\colon W\to Z$ in $\mathcal{B}$ with $f(x)\in W$, the map $\eta \circ f \circ \varphi^{-1}$ is smooth on $\newcommand{\R}{\mathbb{R}}Z \subset \R^{k}$.
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/smooth_maps_between_smooth_manifolds.svg" style="width:45%;"/>
> The collection of all such smooth maps are denoted as $C^{\infty}(M,N)$, and we usually write $C^{\infty}(M)$ for $C^{\infty}(M,\R)$. ^4fb5f6

> [!remark]
> Although the definition requires that the map $\eta \circ f \circ \varphi^{-1}$ is smooth for every chart $\varphi\colon U\to V$ in the atlas, it is enough to check the smoothness for a single chart around each point, because our atlases are smooth, so transition maps are all smooth!
> Moreover, to also check continuity in a streamlined way, we simply need to show that for each $x\in M$ there exists a chart $(U, \varphi)$ at $x$ and a chart $(V, ψ)$ at $f(x)$ such that $f (U) \subset V$ and $\psi \circ f \circ \varphi^{−1} \colon \varphi(U) \to \psi(V)$ is smooth.

<u><b>e.g.</b></u>  
- Every constant map is smooth;
- The identity map $\text{id}_{M}\colon M\to M$ is smooth;
- The inclusion map $i\colon U\hookrightarrow M$ is smooth for every open subset $U\subset M$;
- The composition of smooth maps is smooth;
- The inclusion map $S^{n}\hookrightarrow \R^{n+1}$ is smooth. We can take 
- The quotient map $\pi\colon \newcommand{\P}{\mathbb{P}}\R^{n+1}\setminus \{0\}\to\R\P^{n}$ is smooth. Note that $\R\P^{n}\cong S^{n}/(-x\sim x)$

> [!lemma] Gluing Lemma for Smooth Maps (Smoothness is Local)
> Let $f\colon M\to N$ be a function between smooth manifolds. Then $f$ is smooth iff each $p\in M$ has an open neighbourhood $U_{p}$ such that $f|_{U_{p}}$ is smooth^[Note that we have shown that [[Manifolds, Atlases and Smooth Structures#^2794bb|any open subset of a smoot manifold is a smooth submanifold]].].
> 

*Proof*  The "only if" part is clear. 

> [!proposition]
> A map $f\colon M\to \R^{n}$ is smooth if and only if each component function $f_{i}$ is smooth.

*Proof*  If $f$ is smooth, then $f_{i}\circ \varphi^{-1}$ is smooth for every chart $\varphi\colon U\to V$. Conversely, if each $f_{i}$ is smooth, then $f\circ \varphi^{-1}=(f_{1}\circ \varphi^{-1},f_{2}\circ \varphi^{-1},\dots, f_{n}\circ \varphi^{-1})$ is smooth. $\square$

> [!proposition]
> A map $g$ between smooth manifolds $M$ and $N$ is smooth if and only if $f \circ g$ is a smooth function on $M$ whenever $f$ is a smooth function on $N$.

*Proof*  Clearly if $\chi$ is smooth, then $f\circ \chi$ is smooth. Conversely, if $f\circ \chi$ is smooth on $M$, then for every chart $\varphi\colon U\to V$ in the atlas of $M$, the composition $f\circ \chi \circ \varphi^{-1}$ is smooth on $V$. Hence $\chi$ is smooth by definition. $\square$

> [!proposition]
> A map $F\colon M\to N$ between smooth manifolds is smooth if and only if for every smooth function $f\colon N\to \R$, the precomposition $f\circ F$ is a smooth function on $M$. Equivalently, the pullback satisfies $F^{*}(C^{\infty}(N)) \subset C^{\infty}(M)$.
> 

> [!definition] Diffeomorphism
> A map $F\colon M \to N$ between smooth manifolds is a *diffeomorphism* if it is smooth, and has a smooth inverse. 
> $F$ is a *local diffeomorphism* about $x\in M$ if there is an open neighborhood $U$ of $x$ such that $F|_{U}$ is a diffeomorphism to an open subset of $N$. ^39ce42
> 

## Further Classification of Smooth Maps

In calculus and real analysis, a large amount of information of a smooth function is included in its derivative. Similarly, we can classify smooth maps between smooth manifolds through their differentials.

> [!definition] Rank
> Suppose $F\colon M\to N$ is a smooth map between smooth manifolds, and $x\in M$. The *rank* of $F$ at $x$, denoted $\operatorname{rank}_{x}(F)$, is the rank of the differential $\newcommand{\d}{\mathrm{d}}\d_{x} F \colon T_{x}M \to T_{F(x)}N$. If $\operatorname{rank}_{x}(F)$ is constant for all $x\in M$, we say that $F$ has *constant rank*.

> [!definition] Immersion & Submersion
> A smooth map $F\colon M\to N$ is an *immersion* if $\d_{x} F$ is [[Mathematics/Set Theory/Relations and Functions#^042daf|injective]] for all $x\in M$, and a *submersion* if $\d_{x} F$ is [[Mathematics/Set Theory/Relations and Functions#^042daf|surjective]] for all $x\in M$. Equivalently, $F$ is an immersion if $\operatorname{rank}_{x}(F)=\dim M$ for all $x\in M$, and a submersion if $\operatorname{rank}_{x}(F)=\dim N$ for all $x\in M$. ^9d6e60

> [!proposition]
> If $F\colon M\to N$ has rank $k$ at $x\in M$, then there exist an open neighborhood $U$ of $x$ such  that $F|_{U}$ has rank at least $k$ for all $y\in U$.
> 

<u><b>e.g.</b></u>  
- Canonical projections $\pi\colon M\times N\to M$ are submersions;
- A smooth curve $\gamma\colon I\to M$ is an immersion if and only if it has no stationary points, i.e., $\gamma'(t)\neq 0$ for all $t\in I$;
- Projection map 
- Composition of immersions is an immersion, and composition of submersions is a submersion.
$\quad$

> [!definition] Smooth Embedding
> A smooth map $F\colon M \to N$ is an embedding if $F$ is a homeomorphism onto its image with the [[Mathematics/Topology/General Topology/Constructions on Topological Spaces#^a942da|subspace topology]], and for any charts $\varphi$ and $\eta$ for $M$ and $N$ respectively, $\eta\circ F\circ \varphi^{-1}$ has derivative of full rank. ^9d6e60

> [!remark]
> A smooth embedding is a topological embedding that is also an immersion.
> 

> [!theorem] Regular Value Theorem
> 

## 