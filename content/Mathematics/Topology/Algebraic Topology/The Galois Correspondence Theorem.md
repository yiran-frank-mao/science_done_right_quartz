---
created: 2025-08-19
updated: 2025-08-25
tags:
  - algebraic-topology
  - covering-spaces
  - fundamental-group
completed: true
---
Last time, we constructed the universal covering space $\widetilde{X}_{\text{univ}}$. This construction is the key to classifying all possible covering spaces of a given space $X$.

> [!proposition] Covering Spaces from Subgroups
> Suppose $X$ is a "nice" space ([[Connectedness and Paths#^630354|path-connected]], [[Connectedness and Paths#^ba4f32|locally path-connected]], and [[Fundamental Theorem of Covering Spaces#^a1129b|semi-locally simply-connected]]). Let $G = \pi_1(X, x_0)$. For any subgroup $H < G$, there exists a path-connected covering space $p\colon \widetilde{X}_H \to X$ with a basepoint $\tilde{x}_0 \in p^{-1}(x_0)$ such that $$p_*(\pi_1(\widetilde{X}_H, \tilde{x}_0)) = H.$$

*Proof* Recall that the universal covering space is the set of (homotopy classes of) paths in $X$ starting at the basepoint $x_0$: $$\widetilde{X}_{\text{univ}} = \{[f] : f \text{ is a path in } X \text{ starting at } x_0\}$$Any path $f$ starting at $x_0$ lifts to a path $\tilde{f}$ in $\widetilde{X}_{\text{univ}}$ starting at $\tilde{x}_0 = [c_{x_0}]$ (the constant path), where the lifted path is defined by $\tilde{f}(t) = [f|_{[0,t]}]$. The endpoint of this path is simply the class $[f]$.
We can define an equivalence relation $\sim$ on the points of $\widetilde{X}_{\text{univ}}$: $$[f] \sim [g] \iff f(1) = g(1) \text{ and } [f \cdot g^{-1}] \in H$$Here, since $f$ and $g$ end at the same point, the concatenation $f \cdot g^{-1}$ is a well-defined loop based at $x_0$, so its homotopy class $[f \cdot g^{-1}]$ is an element of $\pi_1(X, x_0) = G$.
We define the covering space $\widetilde{X}_H$ as the quotient space $\widetilde{X}_{\text{univ}} / \sim$. The projection map $p\colon \widetilde{X}_{H} \to X$ sends an equivalence class containing $[f]$ to the endpoint $f(1)$.
A path $f$ in $X$ starting at $x_0$ lifts to a loop in $\widetilde{X}_H$ based at $\tilde{x}_0$ if and only if the endpoint of its lift, the equivalence class of $[f]$, is the same as the start point, the equivalence class of $[c_{x_0}]$. This occurs if and only if $[f] \sim [c_{x_0}]$, which by definition means $f(1) = c_{x_0}(1) = x_0$ and $[f \cdot c_{x_0}^{-1}] = [f] \in H$.
Therefore, the loops in $\widetilde{X}_H$ based at $\tilde{x}_0$ correspond precisely to the elements of the subgroup $H$.
$$p_*(\pi_1(\widetilde{X}_H, \tilde{x}_0)) = H$$
$\square$

This construction establishes a fundamental link between the topology of covering spaces and the algebraic structure of the fundamental group:

> [!theorem] The Galois Correspondence Theorem
> Let $X$ be a [[Connectedness and Paths#^630354|PC]], [[Connectedness and Paths#^ba4f32|LPC]], and [[Fundamental Theorem of Covering Spaces#^a1129b|SLSC]] space.
> 1. There is a one-to-one correspondence between the set of isomorphism classes of **based** path-connected covering spaces of $X$ and the set of [[Groups, Order and Subgroups#^1ccb07|subgroups]] of $\pi_1(X, x_0)$.
> 2. There is a one-to-one correspondence between the set of isomorphism classes of path-connected covering spaces of $X$ (unbased) and the set of conjugacy classes of subgroups of $\pi_1(X, x_0)$.
> $\quad$

*Proof*  (1) is clear from the above proposition. To prove (2), we need to show that changing the basepoint in the cover $\widetilde{X}$ corresponds to conjugating the subgroup $H = p_*(\pi_1(\widetilde{X}, \tilde{x}_0))$.
Let $\tilde{x}_1$ be another point in the fiber over $x_0$. Since $\widetilde{X}$ is path-connected, choose a path $\tilde{f}$ in $\widetilde{X}$ from $\tilde{x}_0$ to $\tilde{x}_1$. Its projection $f = p \circ \tilde{f}$ is a loop in $X$ based at $x_0$, so its class $[f]$ is in $\pi_1(X, x_0)$.
We want to compute the subgroup corresponding to the new basepoint, $p_*(\pi_1(\widetilde{X}, \tilde{x}_1))$. The path $\tilde{f}$ induces an isomorphism from $\pi_1(\widetilde{X}, \tilde{x}_1)$ to $\pi_1(\widetilde{X}, \tilde{x}_0)$ by conjugation: an element $[\tilde{g}] \in \pi_1(\widetilde{X}, \tilde{x}_1)$ is mapped to $[\tilde{f} \cdot \tilde{g} \cdot \tilde{f}^{-1}] \in \pi_1(\widetilde{X}, \tilde{x}_0)$.
Applying the homomorphism $p_*$ gives: $$\begin{aligned}p_*(\pi_1(\widetilde{X}, \tilde{x}_0)) = p_*([\tilde{f} \cdot \pi_1(\widetilde{X}, \tilde{x}_1) \cdot \tilde{f}^{-1}])\\ H = [p \circ \tilde{f}] \cdot p_*(\pi_1(\widetilde{X}, \tilde{x}_1)) \cdot [p \circ \tilde{f}]^{-1}\end{aligned}$$Letting $[f] = [p \circ \tilde{f}]$, we can rearrange to find the new subgroup:$$p_*(\pi_1(\widetilde{X}, \tilde{x}_1)) = [f]^{-1} H [f]$$Thus, changing the basepoint from $\tilde{x}_0$ to $\tilde{x}_1$ changes the corresponding subgroup $H$ to a conjugate subgroup. This shows that an unbased covering space corresponds to an entire conjugacy class of subgroups. $\square$

<u><b>e.g.</b></u> We now see an example that utilize the Galois correspondence and pure topology methods to solve a group theory problem, specifically, classify all conjugacy classes of subgroups of a group $G=\langle a, b \mid a^{2}, b^{2} \rangle$.
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/RP1_wedge_RP1.svg" alt="RP1_wedge_RP1" style="width:29%;"/>
Consider a space $\newcommand{\RP}{\mathbb{R}\mathrm{P}}X=\RP^{2}\vee\RP^{2}$ with fundamental group $\pi_1(X) \cong \mathbb{Z}/2 * \mathbb{Z}/2$. This group has the presentation $G = \langle a, b \mid a^{2}, b^{2} \rangle$. The PC covering spaces of $X$ correspond to the conjugacy classes of subgroups of $G$.
The universal cover $\widetilde{X}_{\text{univ}}$ corresponds to the trivial subgroup $\{e\}$:
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/universal_cover_RP1_wedge_RP1.svg" alt="universal_cover_RP1_wedge_RP1" style="width:38%;"/>
Other covering spaces correspond to larger subgroups. The following [[Covering Spaces#^b33205|covering space]] with two $\RP^{2}$ at the endpoints and any number of spheres in the middle corresponds to $\langle b, (ab)^{n}a\rangle$:
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/other_covering1_RP1_wedge_RP1.svg" alt="other_covering1_RP1_wedge_RP1" style="width:54%;"/>
A circle of spheres corresponds to $\langle (ab)^n \rangle$ for some $n \geq 0$:
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/other_covering2_RP1_wedge_RP1.svg.svg" alt="other_covering2_RP1_wedge_RP1.svg" style="width:30%;"/>
This fully describes the conjugacy classes of subgroups of $G$.