---
completed: true
updated: 2025-10-19
tags:
  - lie-groups
  - differential-geometry
  - linear-algebra
  - groups
---
## Lie Groups of Finite Dimension

> [!definition] Lie Group
> A *Lie group* $G$ is a [[Groups, Order and Subgroups#^6e0960|group]] that is also a [[Manifolds and Atlases#^6ef2ef|smooth manifold]], such that the group operations of multiplication and inversion are both smooth maps. That is $$(x,y)\mapsto x^{-1}y$$is a smooth mapping of the product manifold into $G$. ^0e5dd8

<u><b>e.g.</b></u>  The [[Linear Groups#^2ce0d2|group of rotations]] in $\newcommand{\R}{\mathbb{R}}\R^{2}$, $\newcommand{\SO}{\mathrm{SO}}\SO(2)$, is a Lie group. Each element of $\mathrm{SO}(2)$ can be represented by some rotation angle $\theta\in S^{1}$, this gives a chart so that $\SO_{2}$ is a smooth manifold. And the multiplication operation corresponds to the addition of angles, which is smooth. In general, $$\SO(n)\subset \mathrm{O}(n)\subset \mathrm{SL}(n,\R) \subset \mathrm{GL}(n,\R)$$are all Lie groups.

> [!proposition]
> Let $G$ be a Lie group. Then the left multiplication by $g\in G$, $\ell_{g}\colon G\to G$, is a [[Smooth Functions and Maps#^39ce42|diffeomorphism]] of $G$ onto itself.
> 

> [!proposition]
> For any Lie group $G$ of dimension $k$, we have $$TG\cong G\times \R^{k}$$ with respect to a basis $\{\partial_{1}, \dots \partial_{k}\}$ for $T_{e}G$.

*Proof*  Define a map $\phi\colon TG \to G\times T_{e}G$ by $\newcommand{\d}{\mathrm{d}}[g,v] \mapsto \left(g, \d_{g}\ell_{g^{-1}}(v)\right)$, which is linear along each fiber ([[Tangent Vectors and Spaces#^76649d|tangent space]]) of $TG$. $\square$

## Matrix Lie Groups

> [!definition] Matrix Lie Group
> A *matrix Lie group* is a closed [[Groups, Order and Subgroups#^1ccb07|subgroup]] of $\newcommand{\C}{\mathbb{C}}\newcommand{\GL}{\mathrm{GL}}\GL_{n}(\C)$, using the standard topology from $\C^{n^{2}}$.

> [!attention] 
> We have not yet established that a matrix Lie group is indeed a Lie group. This will be proved later, after introducing the exponential map for complex matrices.

<u><b>e.g.</b></u>  In fact, most of common Lie groups, and Lie groups that are used in physics are matrix Lie groups:
- Orthogonal Group: $\newcommand{\O}{\mathrm{O}}\O_{n}:=\{A\in\GL_{n}(\R)\mid A^{\top}A=I_{n}\}$, $\newcommand{\SO}{\mathrm{SO}}\SO_{n}=\mathrm{SL}_{n}(\R)\cap\O_{n}$.
- [[Unitary Groups#^f61f3c|Unitary groups]]: $\newcommand{\U}{\mathrm{U}}\U_{n}:=\{A\in\GL_{n}(\C)\mid A^{*}A=I_{n}\}$, $\newcommand{\SL}{\mathrm{SL}}\newcommand{\SU}{\mathrm{SU}}\SU_{n}=\SL_{n}(\C)\cap\U_{n}$.
- [[Symplectic Group#^fae051|Symplectic group]]: $\newcommand{\SP}{\mathrm{Sp}}\SP_{2n}(F):=\{A\in \GL_{2n}(F)\mid A^{\top} J A = J \}$.

But clearly not every Lie group is a matrix Lie group. Here are two examples of non-matrix Lie groups:
- Elliptic curves over  $\C$.
- The [[Covering Spaces#^06336e|universal cover]] of $\SL_{n}(\R)$.
$\quad$
### Compactness

One benefit of matrix Lie groups is that it is easy to check [[Compactness of Topological Space#^da2511|compactness]] by [[Continuous Functions on Topological Spaces#^6e5465|Heine-Borel theorem]]. For example, $\U_{n}$ and $\O_{n}$ are compact since every orthogonal/unitary matrix has Frobenius norm $\sqrt{n}$, and so is bounded. On the other hand, $\SL_{2}(\R)$ is not compact since the [[Groups, Order and Subgroups#^1ccb07|subgroup]] $\left\{\begin{pmatrix}t & 0 \\ 0 & 1/t\end{pmatrix}\mid t\neq0\right\}$ is not bounded.

### Connectedness

Checking [[Connectedness and Paths#^946cc4|connectedness]] is not hard as well. $\GL_{n}(\C)$, $\SL_{n}(\C)$, $\SO_{n}$, $\U_{n}$, $\SU_{n}$ are all connected matrix Lie groups. Besides, we have the following result:

> [!proposition]
> Let $G$ be a matrix Lie group, and let $H$ be the path connected component of the identity $I \in G$ . Then $H$ is a [[Homomorphisms, Normal Subgroup & Conjugation#^normal|normal subgroup]] of $G$.
> 

*Proof*  We first show that $H\leq G$ is a subgroup. For $A,B\in H$, there is a path $\gamma_{B}$ joining $I$ and $B$. Suppose $\ell_{A}\colon G\to G$ is the left multiplication by $A$, and $i\colon G\to G$ is the inversion map. Then $\ell_{A}\circ i\circ \gamma_{B}$ is a path joining $A$ and $AB^{-1}$, hence $AB^{-1}\in H$, so $H$ is a subgroup. For any $C\in G$, consider the conjugation map $f\colon G\to G$ defined by $f(X)=CXC^{-1}$. Since $f$ is continuous and $f(I)=I$, $f\circ \gamma_{B}$ joins $I$ and $CBC^{-1}$, hence $CBC^{-1}\in H$. Therefore, $H$ is a normal subgroup of $G$. $\square$