---
created: 2025-08-06
updated: 2025-08-11
tags:
  - algebraic-topology
  - cw-complex
  - fundamental-group
  - euler-characteristic
completed: true
---
## Procedure to Construct CW Complexes

> [!definition] CW Complex
> A *CW complex* is a [[Topological Spaces#^65c94a|topological space]] $X$ constructed inductively from disks of increasing dimension. The construction proceeds as follows:
> - Step $0$ ($0$-skeleton): Start with a discrete set of points, $X^0$, called the *0-cells*.
> - Step $n$ ($n$-skeleton): Assuming the $(n-1)$-skeleton $X^{n-1}$ has been constructed, the *n-skeleton* $X^n$ is formed by attaching $n$-dimensional disks $D^n_\alpha$ to $X^{n-1}$ via *attaching maps* $\varphi_\alpha\colon S^{n-1} \to X^{n-1}$, where $S^{n-1}$ is the boundary of $D^n_\alpha$. The space $X^{n}$ is the quotient space:
>    $$X^n = X^{n-1} \coprod_{\alpha} D^n_\alpha \bigg/ (x \sim \varphi_\alpha(x) \text{ for } x \in \partial D^n_\alpha).$$
> - Step $∞$ (The full space): The CW complex $X$ is the union of all its skeletons, $X = \bigcup_{n=0}^{\infty} X^n$, endowed with the weak topology: a set $A \subset X$ is open (or closed) if and only if its intersection $A \cap X^n$ with every skeleton is open (or closed) in $X^n$.
> 
> An *n-cell* refers to one of the disks $D^n$ attached at step $n$. Specifically, $D^{n}_{\alpha}$ is a *closed n-cell*, and its [[Closure, Interior and Boundary#^871863|interior]], $\text{int}(D^n_\alpha)$, is an *open n-cell*. For each cell $D^{n}_{\alpha}$, the composition of the quotient map with the inclusion of the disk $D^n_\alpha$ gives a *characteristic map* $\Phi_\alpha\colon D^n_\alpha \to X$. ^e68c52

> [!remark]+ Why "CW"?
> The C in CW stands for "closure-finite", and the W for "weak" topology.
> 

<u><b>e.g.</b></u>
- The sphere $S^2$ can be given a CW structure with:
	- **Two 0-cells**: $v$ and $w$. So the 0-skeleton is $(S^2)^0 = \{v, w\}$.
	- **Two 1-cells**: $a$ and $b$. The attaching map for $a$ sends the endpoints of $D^1$ to $v$ and $w$, and the map for $b$ sends the endpoints to $w$ and $v$. The 1-skeleton is two arcs joining $v$ and $w$, forming a circle.
	- **Two 2-cells**: $E$ and $F$. These correspond to the two hemispheres. Their boundaries ($S^1$) are attached to the 1-skeleton. The attaching map for $E$ is $\varphi_E = a \cdot b$, which traces the circular 1-skeleton. Similarly, the attaching map for $F$ is $\varphi_F = b \cdot a$, which traces the same circle.
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/CW_complex_sphere.svg" alt="CW_complex_sphere" style="width:20%;"/>
- The closed orientable surface of genus $g$, $M_g$, has a very economical CW structure:
	- **One 0-cell**: $v$.
	- **$2g$ 1-cells**: $a_1, b_1, \dots, a_g, b_g$. The 1-skeleton $(M_g)^1$ is a wedge of $2g$ circles.
	- **One 2-cell**: $E$. This single 2-cell is attached to the 1-skeleton. Its boundary is identified with the path given by the product of commutators: $$\varphi(\partial E) = [a_1, b_1] [a_2, b_2] \cdots [a_g, b_g] = a_1 b_1 a_1^{-1} b_1^{-1} \cdots a_g b_g a_g^{-1} b_g^{-1}.$$


## Euler Characteristic

> [!definition] Euler Characteristic
> For a finite CW complex $X$ (one with a finite number of cells), the *Euler characteristic* $\chi(X)$ is defined as the alternating sum of the number of cells in each dimension:
> $$\chi(X) = \sum_{n \ge 0} (-1)^n (\text{number of $n$-cells in } X)$$
> This generalizes the familiar formula $V-E+F$ for polyhedra. ^ddd7c6

<u><b>e.g.</b></u>
- For the 2-sphere $S^2$, using the structure with 2 0-cells, 2 1-cells, and 2 2-cells: $\chi(S^2) = 2 - 2 + 2 = 2$.
- For the genus $g$ surface $M_g$, using the structure with 1 0-cell, $2g$ 1-cells, and 1 2-cell: $\chi(M_g) = 1 - 2g + 1 = 2 - 2g$.
$\quad$

## The Fundamental Group of a CW Complex

The CW structure is particularly useful for computing the fundamental group.

> [!proposition]
> Attaching cells of dimension $n \ge 3$ does not change the fundamental group.

*Proof Sketch*: Let $Y = X \cup_\varphi D^n$ with $n \ge 3$. We apply the van Kampen's theorem. The space can be divided into two open sets: $A = Y \setminus \{\text{center of } D^n\}$ and $B = \text{int}(D^n)$. The intersection $A \cap B$ deformation retracts to $S^{n-1}$. For $n \ge 3$, the sphere $S^{n-1}$ is simply connected, so its fundamental group is trivial. The Seifert-van Kampen theorem then implies that $\pi_1(Y) \cong \pi_1(A) * \pi_1(B) \cong \pi_1(X) * \{e\} \cong \pi_1(X)$. $\square$

This means that $\pi_1(X)$ depends only on its 2-skeleton, $X^2$. The effect of attaching 2-cells is described by the following theorem.

> [!theorem]
> Let $Y$ be the space obtained from a [[Connectedness and Paths#^630354|path-connected]] space $X$ by attaching a 2-cell $D^2$ via an attaching map $\varphi\colon S^1 \to X$. Let $x_0$ be a basepoint in $X$. The inclusion map $i: X \hookrightarrow Y$ induces a [[Relations and Functions#^042daf|surjective]] [[Homomorphisms, Normal Subgroup & Conjugation#^homo|homomorphism]] $i_*\colon \pi_1(X, x_0) \to \pi_1(Y, x_0)$.
> The kernel of $i_*$ is the normal subgroup $N$ generated by the element $[h \cdot \varphi \cdot h^{-1}]$, where $h$ is any path from $x_0$ to the loop $\varphi(S^1)$. Therefore,
> $$\pi_1(Y, x_0) \cong \pi_1(X, x_0) / N.$$

*Proof*  Let $Y = X \cup_\varphi D^2$. We choose two open sets for the theorem:
1.  $A = Y \setminus \{p\}$, where $p$ is the center point of the attached disk $D^2$. This set is path-connected and deformation retracts onto $X$, so $\pi_1(A, x_0) \cong \pi_1(X, x_0)$.
2.  $B = \text{int}(D^2)$. This set is an open disk, which is contractible. Therefore, $\pi_1(B, x_1)$ is the trivial group for any basepoint $x_1 \in B$.

The intersection $A \cap B$ is an open annulus, which deformation retracts to a circle $S^1$. Its fundamental group is infinite cyclic, $\pi_1(A \cap B, x_1) \cong \mathbb{Z}$, generated by a loop $[\psi]$ that goes around the puncture $p$.
By the [[van Kampen's Theorem#^9e0d9b|van Kampen's theorem]], $\pi_1(Y, x_0)$ is the amalgamated product of $\pi_1(A,x_0)$ and $\pi_1(B,x_0)$ over $\pi_1(A \cap B, x_1)$. The generator $[\psi]$ is trivial in $\pi_1(B)$ and corresponds to the attaching loop $[\varphi]$ in $\pi_1(A)$.
The theorem states that $\pi_1(Y, x_0)$ is the quotient of $\pi_1(A, x_0)$ by the normal subgroup generated by the image of the loop from the intersection. To express the loop $[\varphi]$ relative to the basepoint $x_0$, we conjugate it by a path $h$ connecting $x_0$ to the loop. The corresponding element in $\pi_1(X, x_0)$ is $[h \cdot \varphi \cdot h^{-1}]$.
Setting this element to the identity (since it's trivial in the other part of the amalgam) gives the result: $$\pi_1(Y, x_0) \cong \pi_1(A, x_0) / \langle \langle [h \cdot \varphi \cdot h^{-1}] \rangle \rangle \cong \pi_1(X, x_0) / \langle \langle [h \cdot \varphi \cdot h^{-1}] \rangle \rangle$$where $\langle \langle \cdot \rangle \rangle$ denotes the normal closure of the subgroup. $\square$

## Real Projective Space as a CW Complex

The real projective space $\newcommand{\RP}{\mathbb{R}\mathrm{P}}\RP^n$ can be defined in several equivalent ways:
1.  As the space of all lines passing through the origin in $\mathbb{R}^{n+1}$.
2.  As the quotient space $(\mathbb{R}^{n+1} \setminus \{0\}) / \sim$, where $x \sim \lambda x$ for any non-zero [[Number Systems#^5fea5c|real number]] $\lambda$.
3.  As the quotient of the $n$-sphere $S^n$ by identifying antipodal points: $x \sim -x$.
4.  As the quotient of the $n$-disk $D^n$ by identifying antipodal points on its boundary: $x \sim -x$ for $x \in \partial D^n$.
$\quad$

> [!proposition]
> $\RP^n$ is a CW complex with exactly one $k$-cell for each dimension $k$ from $0$ to $n$.

*Proof*  We can show this by induction. We construct $\RP^n$ from $\RP^{n-1}$ by attaching a single n-cell.
* The attaching map for the $n$-cell ($D^n$) is the quotient map $p\colon \partial D^{n} = S^{n-1} \to \RP^{n-1}$.
* The resulting space is $\RP^{n-1} \cup_p D^n$. This space is homeomorphic to taking the n-disk $D^n$ and identifying antipodal points $x$ and $-x$ on its boundary $\partial D^n$.
* This construction, $D^n / (x \sim -x \text{ for } x \in \partial D^n)$, is precisely the definition of $\RP^n$.
* Since $\RP^0$ is a single point (a 0-cell), we can inductively build $\RP^n = e^0 \cup e^1 \cup \dots \cup e^n$.

$\square$

