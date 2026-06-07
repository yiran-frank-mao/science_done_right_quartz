---
created: 2023-11-22
updated: 2024-10-28
---
> [!definition] Group Action
> Let $G$ be a group and $X$ a set. An *action* of $G$ on $X$ is a function
> $$ G \times X \to X, \quad (g,x) \mapsto g\cdot x $$
> satisfying
> - $1 \cdot x = x$ for all $x \in X$, and
> - $(gh) \cdot x = g \cdot (h \cdot x)$ for all $x \in X$ and $g,h \in G$
>
> A set $X$ equipped with an action of $G$ is called a *$G$-set*. ^4047e8

<b><u>e.g.</u></b>
- $G$ (the group) acts on $G$ (the set) by left multiplication.
- Let $H\leq G$. Then $G$ acts on $X = G /H = \{g H \mid g \in G \}$ by left multiplication.
- $G$ acts on itself by conjunction.
$\quad$

> [!proposition]
> A group action of $G$ on a set $X$ is the same as homomorphism $G \to \operatorname{Sym}(X)$.

*Proof*  Given an action $G\times X \to X$ defineed, for every $g \in G$, a map $\rho_g : X \to X$ by $\rho_g(x) = g \cdot x$. Then $\rho_g$ is a bijection because $\rho_{g^{-1}}$ is its inverse. Therefore, we get a map $$ \rho : G \to \operatorname{Sym}(X), \quad g\mapsto \rho_g $$Now check that $\rho$ is a homomorphism. Indeed, $$ \rho(g)\rho(h) = \rho_g \circ \rho_h = \rho_{gh} = \rho(gh) $$Conversely, given such $\rho$, define $G\times X \to X$ by $(g,x) \mapsto \rho_g(x)$. This is a group action and the two constructions we defined are inverses to each other. $\square$

> [!definition] Orbit and Stabiliser
> Let $G$ be a group acting on a set $X$ and let $x \in X$. Then, the orbit of $x$ is the subset $\mathcal{O}(x) = \{ g \cdot x \mid g \in G \} \subset X$. The stabilizer of $x$ in $G$ is the subgroup $G_x = \operatorname{Stab}_G(x) = \{ g \mid g\cdot x =x \} \leq G$. ^705c54

## Classification of Actions

> [!definition] Transitive Action
> A group action is transitive if it has only one orbit. Equivalently, this means for any two elements $x,y\in X$, there exists an element $g\in G$ such that $g\cdot x=y$. ^065d30

> [!definition] Free Action
> A group action of $G$ on $X$ is said to be free if $g \cdot x = x$ implies $g = 1$ for all $x\in X$. ^fddea8

> [!definition] Faithful (Effective) Action
> An action of $G$ on $X$ is said to be faithful if the only element of $G$ that acts as the identity on $X$ is the identity element of $G$. ^f7c6a0

> [!proposition]
> An action of a group $G$ on a set $X$ defines an [[Relations and Functions#^14741d|equivalence relation]] on $X$: $$ x ∼ y \iff \exists g \in G , y = g\cdot x $$

## The Orbit-Stabilizer Theorem

> [!definition] Conjugacy Classes
> When $G$ acts on itself by conjugation, the orbits are called conjugacy classes.

> [!definition] Centraliser
> The centralizer of an element $x$ in a group $G$, is the set $C_G(x)$ of elements that commute with $x$. Or equivalently, the stabilizer of $x \in G$ under conjugation is the centralizer $C_G (x)$ of $x$.

> [!theorem] Orbit-Stabilizer Theorem
> Let $G$ be a group acting on a set $X$ . Let $x ∈ X$ and let $H = G_x$ be the stabilizer of $x$ in $G$ and let $\mathcal{O}(x$) be the orbit. Then the the map $$ \varphi\colon G/H \to \mathcal{O}(x),gH \mapsto gx $$is a bijection. In particular, if $G$ is finite then $|G|=|G_x||\mathcal{O}(x)|$. So the size of every orbit divides the order of the group. ^dac142

*Proof*  The map is surjective: an inverse image of $gx \in \mathcal{O}(x)$ is $gH$. The map is injective since: $$ gx = hx \iff h^{-1}gx=x \iff h^{-1}g\in G_x=H \iff gH=hH $$

> [!theorem] The Class Equation
> Let $G$ be a finite group. Then $$ |G|=\sum_i[G:C_G(x_i)]. $$

*Proof*  $G$ acts on itself by conjugation. It follows that $G$ is a disjoint union of conjugacy classes. For every class $\mathcal{O}(x)$ we have $|\mathcal{O}(x)| = [G : C_G (x)]$ as by [Orbit-Stabilizer Theorem](Group%20Actions.md#^dac142) we have $\mathcal{O}(x)\cong G/C_G(x)$.

> [!definition] $p$-group
> A finite group is called a $p$-group if its order is a $p$-power.

> [!corollary]
> Every $p$-group has a non-trivial centre.

*Proof*  Let $𝐺$ be a finite $𝑝$−group and make it act on itself by conjugation. Observe that:$$ \begin{aligned} |\mathcal{O}(x)|=1 \iff x\in Z(G)\\ \end{aligned} $$By class equation, we know that $|\mathcal{O}(x)| = [G : C_G (x)]$.

> [!lemma]
> For any group $𝐺$, $𝐺/𝑍(𝐺)$ is cyclic iff $𝐺$ is abelian.

> [!theorem] Cauchy’s Theorem
> If $p$ is a prime dividing the order of a finite group $G$ then $G$ contains an element of order $p$.

*Proof*


## Semidirect Products

> [!definition] Semidirect Product
> Given groups $G$ and $H$, and an $H$-action on $G$ by automorphisms, say $\varphi\colon H\to \mathrm{Aut}(G)$, the semidirect product $G \rtimes_{\varphi} H$ is the set $G\times H$, with multiplication defined by: $$(g_1,h_1)(g_2,h_2) = (g_1 \varphi_{h_1}(g_2), h_1 h_2). $$

<u><b>e.g.</b></u> If $\varphi$ is the trivial action then this construction reduces to the usual direct product $G\times H$.