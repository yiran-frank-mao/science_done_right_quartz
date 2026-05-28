---
tags:
  - covering-spaces
  - algebraic-topology
updated: 2025-08-21
completed: true
---
## Covering Spaces

> [!definition] Covering Space
> A covering space is a continuous map $p\colon \widetilde{X}\to X$ such that each point $x\in X$ has an open neighborhood $U$ such that
> - $p^{-1}(U)$ is a disjoint union of open sets in $\widetilde{X}$: $p^{-1}(U)=\bigsqcup_{\alpha\in A} V_{\alpha}$,
> - for each $\alpha\in A$, the restriction $p|_{V_{\alpha}}\colon V_{\alpha}\to U$ is a homeomorphism.
>
> Such a neighborhood $U$ is called *evenly covered* by $p$, and the set of all such open neighbourhoods is called a *good cover* of $X$. ^b33205

<u><b>e.g.</b></u>
- Let's consider the space $X = S^1 \lor S^1$ covered by $\widetilde{X}=S^{1}\vee S^{1} \vee S^1$.
  <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/covering_space_ex_S1_wedge_S1.svg" alt="covering_space_ex_S1_wedge_S1" style="width:50%;"/>
  A good cover for $X$ can be $\{U_1, U_2, U_3\}$, where: $U_1$ is a neighborhood of the 'a' loop. $U_3$ is a neighborhood of the 'b' loop. $U_2$ is a small neighborhood of the wedge point.
  <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/good_cover_S1_wedge_S1.svg" alt="good_cover_S1_wedge_S1" style="width:60%;"/>
  The image above shows a portion of a covering space $\widetilde{X}$ of $X$. The preimages of the open sets, for example $p^{-1}(U_1)$, consist of disjoint copies of open sets where each copy is homeomorphic to $U_1$.
- **The Empty Set**: For any space $X$, the map $p\colon \emptyset \to X$ is a covering space. Any open cover of $X$ is a good cover since the preimage of any set is the empty set.
- **The Identity Map**: $\newcommand{\id}{\mathrm{id}}\id\colon X \to X$ is a trivial covering space. Any open cover is a good cover.
- **The Real Line over the Circle**: The exponential map $\newcommand{\R}{\mathbb{R}}p\colon \R\to S^{1}$ defined by $p(t)=e^{2\pi it}$ is a covering map, wrapping the real line around the circle infinitely many times. Locally, it looks like $\R\to S^{1}$ is a bunch of evenly spaced intervals mapping homeomorphically onto an arc of the circle. A concrete application of this can be seen in [[The Fundamental Group#^6ff1bb|the proof]] of the fundamental group of $S^1$.
- **The Complex Plane without the Origin**: The map $p\colon (0, \infty) \times \mathbb{R} \to \mathbb{C} \setminus \{0\}$ given by $(r, x) \mapsto re^{2\pi i x}$ is a covering map. This is essentially the exponential map viewed through polar coordinates.
- **The n-fold Cover of the Circle**: For a fixed integer $n \ge 1$, the map $p_{n}\colon S^{1} \to S^{1}$ defined by $z \mapsto z^n$ is a covering space. This map wraps the circle around itself $n$ times. In general, one can think of this as "the sphere over real projective space", that is, $\newcommand{\RP}{\mathbb{R}\mathrm{P}}p\colon S^{n} \to \RP^{n}$ which identifies antipodal points is a covering space.
$\quad$

> [!definition] Universal Cover
> A *universal cover* of a topological space $X$ is a covering space $\widetilde{X}$ with a covering map $p\colon \widetilde{X}\to X$ such that $\widetilde{X}$ is [[The Fundamental Group#^3b18ee|simply connected]]. ^06336e

<u><b>e.g.</b></u>
* The map $p\colon \mathbb{R} \to S^1$ is a universal cover, since $\mathbb{R}$ is simply-connected.
* The universal cover of a torus $T$ is $\R^{2}$.
* For $n \ge 2$, the map $p\colon S^n \to \RP^n$ is a universal cover because $S^n$ is simply-connected.
* The universal cover of $X = S^1 \lor S^1$ is an infinite 4-valent tree, which is the Cayley graph of the free group on two generators.
$\quad$

## The Homotopy Lifting Property

> [!proposition] Homotopy Lifting Property
> Let $p\colon \widetilde{X} \to X$ be a covering space. Let $F\colon Y \times I \to X$ be a [[Homotopy Types#^2c10b4|homotopy]], and let $\tilde{f}_0\colon Y \to \widetilde{X}$ be a lift of the initial map $f_0 = F(\cdot, 0)$ (meaning $p \circ \tilde{f}_0 = f_0$). Then, there exists a unique lift of the entire homotopy, $\tilde{F}\colon Y \times I \to \widetilde{X}$, such that $p \circ \tilde{F} = F$ and $\tilde{F}(\cdot, 0) = \tilde{f}_0$.
> The property is summarized by the following commutative diagram:
> $$\begin{CD}Y \times \{0\} @>{\tilde{f}_0}>> \widetilde{X} \\@V{i}VV @VV{p}V \\Y \times I @>>{F}> X\end{CD}$$ ^4faa27

*Proof Sketch*  The goal is to find a unique map $\tilde{F}\colon Y \times I \to \tilde{X}$ that makes the full diagram commute. For each point $y \in Y$, we can lift the path $t \mapsto F(y, t)$ to a path in $\tilde{X}$ starting at $\tilde{f}_0(y)$. We can then find a neighborhood $N_y$ of $y$ and lift the homotopy on the "tube" $N_y \times I$ to a map $\tilde{F}\colon N_y \times I \to \tilde{X}$. Because these local lifts are unique, they must agree on the overlaps of neighborhoods, such as on $(N_{y_0} \cap N_{y_1}) \times I$. This allows us to "glue" these local lifts together to construct the desired global lift $\tilde{F}$. $\square$

A key result connecting the topology of a covering space to its base space involves their [[The Fundamental Group#^74adbc|fundamental groups]]. The homotopy lifting property leads to this fundamental proposition.

> [!proposition]
> For any [[Covering Spaces#^b33205|covering space]] $p\colon (\widetilde{X}, \tilde{x}_0) \to (X, x_0)$, the homomorphism induced on the [[The Fundamental Group#^74adbc|fundamental groups]], $p_*\colon \pi_1(\widetilde{X}, \tilde{x}_0) \to \pi_1(X, x_0)$, is [[Relations and Functions#^042daf|injective]].

*Proof Sketch*  If a loop class $[\tilde{f}]$ in $\pi_1(\widetilde{X}, \tilde{x}_0)$ maps to the identity in $\pi_1(X, x_0)$, it means its projection $f = p \circ \tilde{f}$ is null-homotopic in $X$. By the [[Covering Spaces#^4faa27|homotopy lifting property]], this null-homotopy can be lifted to a homotopy in $\tilde{X}$ that starts at $\tilde{f}$ and ends at a lift of the constant path at $x_0$. Since lifts are unique, the endpoint of this homotopy must be the constant path at $\tilde{x}_0$, proving that $\tilde{f}$ is null-homotopic. Thus, the kernel of $p_*$ is trivial. $\square$

> [!remark]
> This injectivity allows us to view $\pi_1(\widetilde{X}, \tilde{x}_0)$ as a subgroup of $\pi_1(X, x_0)$. The image, $p_*(\pi_1(\widetilde{X}, \tilde{x}_0))$, consists of all loop classes in $X$ whose representative loops lift to loops in $\widetilde{X}$ based at $\tilde{x}_0$. ^92b0f0

## Sheets, Fibers, and Group Index

The geometric picture of a covering space having multiple "sheets" over the base space can be made precise and connected to the algebraic structure of the fundamental groups. In fact, a covering space is also an example of a fiber bundle where the fibers are discrete sets.

> [!lemma]
> For a covering space $p\colon \widetilde{X} \to X$, if the base space $X$ is [[Connectedness and Paths#^946cc4|connected]], then the cardinality of the fiber, $|p^{-1}(x)|$, is constant for all $x \in X$. This constant value is called the *number of sheets* of the cover.

*Proof*  The function mapping a point $x$ to the number of points in its fiber, $|p^{-1}(x)|$, is locally constant due to the nature of evenly covered neighborhoods. Since $X$ is connected, any locally constant function on it must be globally constant. $\square$

<u><b>e.g.</b></u> 
- The map $p(z) = z^n$ from $S^1$ to $S^1$ is an $n$-sheeted cover.
- The standard covering map $p\colon S^n \to \RP^{n}$ is a 2-sheeted cover.
$\quad$

The main theorem of this section provides a beautiful correspondence between the geometry of the sheets and the algebra of group theory.

> [!proposition]
> If $\widetilde{X}$ and $X$ are [[Connectedness and Paths#^630354|path-connected]], the number of sheets of the covering $p\colon \widetilde{X} \to X$ is equal to the [[Cosets and Lagrange’s Theorem#^6fa811|index]] of the subgroup $H = p_*(\pi_1(\widetilde{X}, \tilde{x}_0))$ within the group $G = \pi_1(X, x_0)$.
> $$\text{Number of Sheets} = [G : H].$$

*Proof Sketch*  We construct a bijection $\Psi$ from the set of left cosets $G/H$ to the fiber $p^{-1}(x_0)$.
1.  First, define a map $\Phi: G \to p^{-1}(x_0)$ that takes a loop class $[f]$ and maps it to the endpoint of its lift $\tilde{f}$ which starts at $\tilde{x}_0$.
2.  This map is constant on the left cosets of $H$. For any $[h] \in H$, the lift of $h \cdot f$ terminates at the same point as the lift of $f$, so $\Phi([h][f]) = \Phi([f])$. Therefore, $\Phi$ induces a map $\Psi: G/H \to p^{-1}(x_0)$.
3.  **Surjectivity**: Any point $\tilde{x}$ in the fiber can be reached by a path from $\tilde{x}_0$ (since $\tilde{X}$ is path-connected). The projection of this path gives a loop class in $G$ that maps to $\tilde{x}$.
4.  **Injectivity**: If two cosets map to the same point in the fiber, it means the lifts of their representative loops end at the same point. This implies that the loop $f_1 \cdot f_2^{-1}$ lifts to a loop in $\tilde{X}$, meaning $[f_1][f_2]^{-1} \in H$. Thus, the cosets must have been the same.

$\square$

<u><b>e.g.</b></u>  Let's analyze the 3-sheeted cover $\widetilde{X}$ of $X = S^1 \lor S^1$.
* The fundamental group of the base space is the free group on two generators, $G = \pi_1(X, x_0) = \langle a, b \rangle \cong F_2$.
* The covering space $\tilde{X}$ is a graph with fundamental group $H' = \pi_1(\widetilde{X}, \tilde{x}_0) \cong F_3$, with generators we can call $x, y, z$.
* The induced map $p_*$ sends these generators to loops in $X$. For instance, they might correspond to $p_*(x) = a$, $p_*(y) = b^2$, and $p_*(z) = bab^{-1}$.
* The image subgroup is $H = p_*(H') = \langle a, b^2, bab^{-1} \rangle \subseteq \langle a, b \rangle$.
* A group-theoretic calculation shows that the index of this subgroup, $[F_2 : \langle a, b^2, bab^{-1} \rangle]$, is 3. This matches the number of sheets of the cover, confirming the theorem.

