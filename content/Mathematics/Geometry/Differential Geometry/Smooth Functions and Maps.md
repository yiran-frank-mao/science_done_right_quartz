## Smoothness

>[!definition] Smooth Map
>Let $M$ be a smooth $n$-manifold with dimension $n$, an atlas $\mathcal{A}$ representing the differentiable structure on $M$. Let $N$ be another smooth $k$-manifold, and differentiable atlas $\mathcal{B}$. Let $f$ be a map from $M$ to $N$. Then $f$ is *smooth* if it is continuous, and for all $x\in M$, and every chart $\varphi\colon U\to V$ in $\mathcal{A}$ with $x\in U$ and $\eta\colon W\to Z$ in $\mathcal{B}$ with $f(x)\in W$, the map $\eta \circ F \circ \varphi^{-1}$ is smooth on $Z \subset \R^{k}$.
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/smooth_maps_between_smooth_manifolds.svg" style="width:45%;"/>
> The collection of all such smooth maps are denoted as $C^{\infty}(M,N)$, and we usually write $C^{\infty}(M)$ for $C^{\infty}(M,\R)$. ^4fb5f6

> [!proposition]
> Although the definition requires that the map $f\circ \varphi^{-1}$ is smooth for every chart $\varphi\colon U\to V$ in the atlas, it is enough to check the smoothness for a single chart around each point. Similar argument applies to check that a map between manifolds is smooth.

*Proof*  If $\varphi\colon U\to V$ is a chart with $f\circ \varphi^{-1}$ smooth, and $\eta \colon W \to Z$ is another chart with $W$ overlapping $U$, then $f\circ \eta^{-1}=f\circ \varphi^{-1}\circ \varphi \circ \eta^{-1}$ is smooth at the overlapping region. $\square$

<u><b>e.g.</b></u>  
- Every constant map is smooth;
- The identity map $\text{id}_{M}\colon M\to M$ is smooth;
- The inclusion map $i\colon U\hookrightarrow M$ is smooth for every open subset $U\subset M$;
- The composition of smooth maps is smooth;
- The inclusion map $S^{n}\hookrightarrow \R^{n+1}$ is smooth. We can take 
- The quotient map $\pi\colon \newcommand{\P}{\mathbb{P}}\R^{n+1}\setminus \{0\}\to\R\P^{n}$ is smooth. Note that $\R\P^{n}\cong S^{n}/(-x\sim x)$
$\quad$

> [!proposition]
> A map $f\colon M\to \R^{n}$ is smooth if and only if each component function $f_{i}$ is smooth.

*Proof*  If $f$ is smooth, then $f_{i}\circ \varphi^{-1}$ is smooth for every chart $\varphi\colon U\to V$. Conversely, if each $f_{i}$ is smooth, then $f\circ \varphi^{-1}=(f_{1}\circ \varphi^{-1},f_{2}\circ \varphi^{-1},\dots, f_{n}\circ \varphi^{-1})$ is smooth. $\square$

> [!proposition]
> A map $g$ between differentiable manifolds $M$ and $N$ is smooth if and only if $f \circ g$ is a smooth function on $M$ whenever $f$ is a smooth function on $N$.

*Proof*  Clearly if $\chi$ is smooth, then $f\circ \chi$ is smooth. Conversely, if $f\circ \chi$ is smooth on $M$, then for every chart $\varphi\colon U\to V$ in the atlas of $M$, the composition $f\circ \chi \circ \varphi^{-1}$ is smooth on $V$. Hence $\chi$ is smooth by definition. $\square$

> [!proposition]
> 
> 


## Further Classification of Maps

> [!definition] Diffeomorphism
> A map $F\colon M \to N$ between smooth manifolds is a *diffeomorphism* if it is smooth, and has a smooth inverse. 
> $F$ is a *local diffeomorphism* about $x\in M$ if for every $x\in M$ there is an open neighborhood $U$ of $x$ such that $F|_{U}$ is a diffeomorphism to an open subset of $N$. ^39ce42
> 



> [!definition] Immersion
> $F\colon M\to N$ is an immersion if for every $x$ in $M$ there exist charts $\varphi\colon U\to V$ for $M$ and $\eta\colon W\to Z$ for $N$ with $x\in U$ and $F(x)\in Z$, such that the map $\eta \circ F \circ \varphi^{-1}$ has derivative which is injective at $\varphi(x)$.

> [!definition] Submersion
> $F$ is a submersion if for each $x ∈ M$ there are charts $φ$ and $η$ such that the derivative of $η \circ F \circ φ^{-1}$ at $φ(x)$ is surjective.

> [!definition] Smooth Embedding
> A smooth map $F\colon M \to N$ is an embedding if $F$ is a homeomorphism onto its image with the [[Mathematics/Topology/Algebraic Topology/Operations on Spaces#^a942da|subspace topology]], and for any charts $\varphi$ and $\eta$ for $M$ and $N$ respectively, $\eta\circ F\circ \varphi^{-1}$ has derivative of full rank. ^9d6e60

> [!remark]
> A smooth embedding is a topological embedding that is also an immersion.
> 

> [!theorem] Regular Value Theorem
> 
