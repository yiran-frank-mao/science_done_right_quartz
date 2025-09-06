---
updated: 2025-08-20
completed: true
---
## The Lifting Criterion

A central question in the theory of covering spaces is determining when a map $f\colon Y \to X$ can be "lifted" to a map $\tilde{f}: Y \to \widetilde{X}$ such that $p \circ \tilde{f} = f$. The answer is purely algebraic.

> [!theorem] Lifting Criterion
> Let $p\colon (\widetilde{X}, \tilde{x}_0) \to (X, x_0)$ be a covering space. If $Y$ is a [[Connectedness and Paths#^630354|path-connected]] and [[Connectedness and Paths#^ba4f32|locally path-connected]] space, a continuous map $f\colon (Y, y_0) \to (X, x_0)$ can be lifted to a map $\tilde{f}\colon (Y, y_0) \to (\widetilde{X}, \tilde{x}_0)$ if and only if the image of its induced [[Homomorphisms, Normal Subgroup & Conjugation#^homo|homomorphism]] is a [[Groups, Order and Subgroups#^1ccb07|subgroup]] of the image of $p_*$:
> $$f_*(\pi_1(Y, y_0)) \leq p_*(\pi_1(\widetilde{X}, \tilde{x}_0)).$$ ^35ad1a

*Proof Sketch*  **Necessity ($\Rightarrow$)**: If a lift $\tilde{f}$ exists, then $f = p \circ \tilde{f}$. Applying the fundamental group functor gives $f_* = p_* \circ \tilde{f}_*$, which directly implies that $\newcommand{\im}{\mathrm{im}}\im(f_*) \leq \im(p_*)$.
**Sufficiency ($\Leftarrow$)**: Assuming the subgroup condition holds, we construct $\tilde{f}$. For any point $y \in Y$, we choose a path $\gamma$ from $y_0$ to $y$. The path $f \circ \gamma$ in $X$ is lifted to a unique path in $\widetilde{X}$ starting at $\tilde{x}_0$. We define $\tilde{f}(y)$ as the endpoint of this lift.
-  **Well-definedness**: If we choose a different path $\mu$ from $y_0$ to $y$, the loop $\gamma \cdot \mu^{-1}$ is mapped by $f_*$ into $p_*(\pi_1(\widetilde{X}, \tilde{x}_0))$. This condition guarantees that the lifts of $f \circ \gamma$ and $f \circ \mu$ have the same endpoint.
- **Continuity**: The local path-connectedness of $Y$ is essential to prove that the constructed map $\tilde{f}$ is continuous.

$\square$

> [!proposition]
> Suppose $Y$ is a [[Connectedness and Paths#^946cc4|connected space]] and we have two lifts $\tilde{f}_1, \tilde{f}_2\colon Y \to \widetilde{X}$ of a map $f\colon Y \to X$. If there is a point $y \in Y$ such that $\tilde{f}_1(y) = \tilde{f}_2(y)$, then the lifts are identical, i.e., $\tilde{f}_1 = \tilde{f}_2$. ^6ba239

*Proof*  Let $U = \{y \in Y : \tilde{f}_1(y) = \tilde{f}_2(y)\}$ and $V = \{y \in Y : \tilde{f}_1(y) \neq \tilde{f}_2(y)\}$. The sets $U$ and $V$ are disjoint, their union is $Y$, and they can be shown to be open. By assumption, $U$ is non-empty. Since $Y$ is a connected space, it cannot be the union of two disjoint non-empty open sets. Therefore, we must have $U=Y$, which implies $\tilde{f}_1 = \tilde{f}_2$ for all $y \in Y$. $\square$

> [!corollary] Universal Property of Universal Cover
> If a universal cover $(\widetilde{X}_{\text{univ}}, \tilde{x}_0)$ of $X$ exists and $X$ is [[Connectedness and Paths#^ba4f32|locally path-connected]], then for any other connected covering space $(\widetilde{X}, \tilde{x}_1)$ of $X$, there exists a unique lift (covering map) $\tilde{f}\colon (\widetilde{X}_{\text{univ}}, \tilde{x}_0) \to (\widetilde{X}, \tilde{x}_1)$.
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/universal_property_universal_cover.svg" alt="universal_property_universal_cover" style="width:35%;"/> ^c6cbd5

*Proof*  Note that a universal cover is automatically [[Connectedness and Paths#^630354|path-connected]] and [[Connectedness and Paths#^ba4f32|locally path-connected]]. So that we can apply the lifting criterion. And by the above proposition, this lifting is unique. $\square$

> [!definition] Morphisms of Covering Spaces
> A *morphism of covering spaces* (*covering space map*) from $p_1\colon \widetilde{X}_1 \to X$ to $p_2\colon \widetilde{X}_2 \to X$ is a continuous map $f\colon \widetilde{X}_1 \to \widetilde{X}_2$ such that $p_2 \circ f = p_1$.
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/map_of_covering_spaces.svg" alt="map_of_covering_spaces" style="width:25%;"/>
> An *isomorphism* of covering spaces is a covering space map $f$ for which there exists an inverse map $g$ such that $\newcommand{\id}{\mathrm{id}}g \circ f = \id_{\widetilde{X}_1}$ and $f \circ g = \id_{\widetilde{X}_2}$. ^4783f4

> [!corollary] Uniqueness of the Universal Cover
> If a [[Connectedness and Paths#^ba4f32|locally path-connected]] space $X$ has two universal covers, they are isomorphic.

*Proof*  The following diagram tells the story:
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/universal_cover_uniqueness.svg" alt="universal_cover_uniqueness" style="width:35%;"/>$\square$

## Existence of the Universal Cover

> [!definition] Semi-Locally Simply-Connected
> A space $X$ is *semi-locally simply-connected* if for any point $x \in X$ and any open neighborhood $U$ of $x$, there exists a smaller open neighborhood $V$ with $x \in V \subset U$ such that the map $\pi_1(V, x) \to \pi_1(X, x)$ induced by the inclusion is trivial. ^a1129b

> [!theorem] Fundamental Theorem of Covering Spaces
> If a space $X$ is [[Connectedness and Paths#^630354|path-connected]], [[Connectedness and Paths#^ba4f32|locally path-connected]], and [[Fundamental Theorem of Covering Spaces#^a1129b|semi-locally simply-connected]], then a universal cover of $X$ exists. ^88ac54

*Proof Sketch*  We can construct $\widetilde{X}_{\text{univ}}$ as the set of homotopy classes of paths in $X$ starting at a fixed basepoint $x_0 \in X$. An element in $\widetilde{X}_{\text{univ}}$ is denoted as $[\gamma]$, where $\gamma\colon [0,1] \to X$ with $\gamma(0) = x_0$.
The basepoint of $\widetilde{X}_{\text{univ}}$ is $\tilde{x}_0 = [c_{x_0}]$, the homotopy class of the constant path at $x_0$.
The projection map $p\colon \widetilde{X}_{\text{univ}} \to X$ is defined by mapping a path class to its endpoint: $p([\gamma]) = \gamma(1)$.
The topology on $\widetilde{X}_{\text{univ}}$ is defined using a basis of open sets. For any point $x \in X$ and any open neighborhood $V$ of $x$ that satisfies the SLSC condition (i.e., $\pi_1(V, x) \to \pi_1(X, x)$ is trivial), and for any point $[\gamma] \in p^{-1}(x)$, we define a basis open set:   $$\tilde{V}_{[\gamma]} = \{[\gamma \cdot \eta] : \eta \text{ is a path in } V \text{ starting at } x\}$$These sets form a basis for the topology on $\widetilde{X}_{\text{univ}}$. With this topology, the projection $p$ restricted to $\tilde{V}_{[\gamma]}$ is a homeomorphism onto $V$, and the full map $p\colon \widetilde{X}_{\text{univ}} \to X$ is the desired universal covering map. (The detailed point-set topology proof is omitted.) $\square$ ^353690

## Categorical Perspective

We can see immediately from the above that, the covering spaces of a given [[Topological Spaces#^65c94a|topological space]] $X$ form a [[Structure of Categories#^2f5c3a|category]] $\mathbf{Cov}(X)$. It is a subcategory of the [[Constructions on Categories#^8b8420|slice category]] $\mathbf{Top}/X$. Then the fundamental theorem of covering spaces can be interpreted as follows:
If a space $X$ is path-connected, locally path-connected, and semi-locally simply-connected, then the category $\mathbf{Cov}(X)$ is equivalent to the category of $\pi_{1}(X)-\mathbf{Set}$ (or functors from the fundamental groupoid to $\mathbf{Set}$).

Also, the [[Fundamental Theorem of Covering Spaces#^c6cbd5|universal property of the universal cover]] can be interpreted as the universal cover is the [[Objects and Elements#^a7dd74|initial object]] of the category of [[Connectedness and Paths#^946cc4|connected]] covering spaces of a "nice" space $X$.