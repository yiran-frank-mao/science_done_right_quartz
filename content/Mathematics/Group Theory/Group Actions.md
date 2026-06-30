---
created: 2023-11-22
updated: 2024-10-28
---
> [!definition] Group Action
> Let $G$ be a [[Groups, Order and Subgroups#^6e0960|group]] and $X$ a set. An *action* of $G$ on $X$ is a function
> $$ G \times X \to X, \quad (g,x) \mapsto g\cdot x $$
> satisfying
> - $1 \cdot x = x$ for all $x \in X$, and
> - $(gh) \cdot x = g \cdot (h \cdot x)$ for all $x \in X$ and $g,h \in G$
>
> A set $X$ equipped with an action of $G$ is called a *$G$-set*. ^4047e8

<b><u>e.g.</u></b>
- $G$ (the group) acts on $G$ (the set) by left multiplication.
- Let $H\leq G$. Then $G$ acts on the [[Cosets and Lagrange’s Theorem#^b825de|left coset space]] $G /H = \{g H \mid g \in G \}$ by left multiplication.
- $G$ acts on itself by conjunction.
$\quad$

> [!proposition]
> A group action of $G$ on a set $X$ is the same as a [[Homomorphisms, Normal Subgroup & Conjugation#^homo|homomorphism]] $G \to \operatorname{Sym}(X)$.

*Proof*  Given an action $G\times X \to X$ defined, for every $g \in G$, a map $\rho_g : X \to X$ by $\rho_g(x) = g \cdot x$. Then $\rho_g$ is a bijection because $\rho_{g^{-1}}$ is its inverse. Therefore, we get a map $$ \rho : G \to \operatorname{Sym}(X), \quad g\mapsto \rho_g $$Now check that $\rho$ is a homomorphism. Indeed, $$ \rho(g)\rho(h) = \rho_g \circ \rho_h = \rho_{gh} = \rho(gh) $$Conversely, given such $\rho$, define $G\times X \to X$ by $(g,x) \mapsto \rho_g(x)$. This is a group action and the two constructions we defined are inverses to each other. $\square$

> [!definition] Orbit and Stabiliser
> Let $G$ be a group acting on a set $X$ and let $x \in X$. Then, the *orbit* of $x$ is the subset $\mathcal{O}(x) = \{ g \cdot x \mid g \in G \} \subset X$. 
> The *stabilizer* of $x$ in $G$ is the subgroup $G_x = \operatorname{Stab}_G(x) = \{ g \mid g\cdot x =x \} \leq G$. ^705c54

<u><b>e.g.</b></u>  When $G$ acts on itself by conjugation, the orbits are called *conjugacy classes*.

> [!proposition]
> An action of a group $G$ on a set $X$ defines an [[Relations and Functions#^14741d|equivalence relation]] on $X$: $$ x ∼ y \iff \exists g \in G , y = g\cdot x. $$

*Proof*  Reflexivity follows from the fact that $1\cdot x = x$. Symmetry follows from the fact that if $y = g\cdot x$ then $x=g^{-1}\cdot y$. Transitivity follows from the fact that if $y = g\cdot x$ and $z = h\cdot y$ then $z = hg\cdot x$.  $\square$

## Classification of Actions

> [!definition] Transitive Action
> A group action is transitive if it has only one orbit. Equivalently, this means for any two elements $x,y\in X$, there exists an element $g\in G$ such that $g\cdot x=y$. ^065d30

> [!definition] Free Action
> A group action of $G$ on $X$ is said to be free if $g \cdot x = x$ implies $g = 1$ for all $x\in X$. ^fddea8

> [!definition] Faithful (Effective) Action
> An action of $G$ on $X$ is said to be faithful if the only element of $G$ that acts as the identity on $X$ is the identity element of $G$. ^f7c6a0

## The Orbit-Stabilizer Theorem

> [!definition] Centraliser
> The *centraliser* of an element $x$ in a group $G$, is the set $C_G(x)$ of elements that commute with $x$. 
> Or equivalently, the stabilizer of $x \in G$ under conjugation is the centralizer $C_G (x)$ of $x$.

> [!theorem] Orbit-Stabilizer Theorem
> Let $G$ be a group acting on a set $X$ . Let $x ∈ X$ and let $G_x$ be the stabilizer of $x$ in $G$ and let $\mathcal{O}(x$) be the orbit. Then the the map $$ \varphi\colon G/G_{x}\to \mathcal{O}(x),\quad gG_{x} \mapsto g\cdot x $$is a [[Relations and Functions#^042daf|bijection]]. In particular, if $G$ is finite then $|G|=|G_x||\mathcal{O}(x)|$. So the size of every orbit divides the order of the group. ^dac142

*Proof*  The map is surjective: an inverse image of $gx \in \mathcal{O}(x)$ is $gH$. The map is injective since: $$ gx = hx \iff h^{-1}gx=x \iff h^{-1}g\in G_x \iff gG_{x}=hG_{x}. $$$\square$

> [!corollary] Conjugacy Class Equation
> Let $G$ be a finite group, acting on itself by conjugation. Then $$ |G|=\sum_{i}|\mathcal{O}(x_{i})|=\sum_{i}[G:C_G(x_i)]. $$ ^becec5

*Proof*  We claim that $G$ is a disjoint union of conjugacy classes. That is, $\mathcal{O}(x)$ and $\mathcal{O}(y)$ are either the same or disjoint. Suppose $\mathcal{O}(x)\cap \mathcal{O}(y)$ is nonempty and we pick some $h\in \mathcal{O}(x)\cap \mathcal{O}(y)$, then $h=g_1xg_1^{-1}=g_2yg_2^{-1}$ for some $g_1,g_2\in G$. It follows that $y=g_2^{-1}g_1xg_1^{-1}g_2\in \mathcal{O}(x)$, so $\mathcal{O}(y)\subseteq \mathcal{O}(x)$. Similarly, $\mathcal{O}(x)\subseteq \mathcal{O}(y)$. Hence $\mathcal{O}(x)=\mathcal{O}(y)$. For every class $\mathcal{O}(x)$ we have $|\mathcal{O}(x)| = [G : C_G (x)]$ by [Orbit-Stabilizer Theorem](Group%20Actions.md#^dac142).  $\square$

## $p$-groups

> [!definition] $p$-group
> A finite group is called a *$p$-group* if its order is a $p$-power for some prime $p$. ^f455f4

> [!corollary]
> Every [[Group Actions#^f455f4|$p$-group]] has a non-trivial centre.

*Proof*  Let $𝐺$ be a finite $𝑝$−group and make it act on itself by conjugation. Observe that:$$ \begin{aligned} |\mathcal{O}(x)|=1 \iff x\in Z(G)\\ \end{aligned} $$By [[Group Actions#^becec5|class equation]], we know that $|G|=\sum_{i}|\mathcal{O}(x_{i})|=\sum_{i}[G:C_G(x_i)]$. Note that each $[G:C_G(x_i)]$ is a $p$-power, if $Z(G)$ were trivial, then there is only one term $|\mathcal{O}(e)|=1$, and all other terms are at least $p$, so $|G|=1+p^{k_{1}}+\cdots+p^{k_{m}}$ for some $k_{1},\dots, k_{m}\geq 1$, which is not divisible by $p$, a contradiction. Therefore, $Z(G)$ is non-trivial. $\square$

> [!theorem] Cauchy’s Theorem
> If $p$ is a [[Division and Prime#^47f235|prime]] dividing the order of a finite group $G$ then $G$ contains an element of order $p$.

*Proof*  Let $X=\{(x_{1}, \cdots, x_{p})\in G^{p} \mid x_{1}\cdots x_{p}=e\}$. The group $\Z/p\Z$ acts on $X$ by $$[n]\cdot (x_{1},\cdots, x_{p})=(x_{1+n},x_{2+n},\cdots, x_{p}, x_{1}, \cdots, x_{n}).  $$This is a well-defined group action because the multiplication of the RHS is $$ x_{1+n}\cdots x_{p}x_{1}\cdots x_{n}=(x_{1}\cdots x_{n})^{-1}(x_{1}\cdots x_{n})x_{1+n}\cdots x_{p}x_{1}\cdots x_{n}=e.$$Observe that $x\in X$ is a fixed point (i.e., $\mathcal{O}(x)=\{x\}$) if and only if $x=(a, a, \cdots, a)$ and $a^{p}=e$. If there were no elements of order $p$, then only $|\mathcal{O}((e,\cdots, e))|=1$, and all other $x$ will have $|\mathcal{O}(x)|=p$. It follows that $$|X|=|G|^{p-1}=1+kp$$for some $k\in\mathbb{N}$. This yields a contradiction because $p$ must divides $|G|^{p-1}$. $\square$

## Semidirect Products

> [!definition] Semidirect Product
> Given groups $G$ and $H$, and an $H$-action on $G$ by automorphisms, say $\varphi\colon H\to \mathrm{Aut}(G)$, the semidirect product $G \rtimes_{\varphi} H$ is the set $G\times H$, with multiplication defined by: $$(g_1,h_1)(g_2,h_2) = (g_1 \varphi_{h_1}(g_2), h_1 h_2). $$

<u><b>e.g.</b></u> If $\varphi$ is the trivial action then this construction reduces to the usual direct product $G\times H$.