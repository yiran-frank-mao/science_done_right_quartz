---
created: 2025-08-21
updated: 2025-08-21
cssclasses:
  - img-grid
  - img-zoom
completed: true
tags:
  - covering-spaces
---
## Covering Space Actions

Recall the definition of a group action:

![[Group Actions#^4047e8]]

We can treat it as a group homomorphism $\rho\colon G \to \mathrm{Homeo}(X)$. We usually assume the action is [[Group Actions#^f7c6a0|faithful]] (i.e., $\rho$ is injective). If not, we can replace $G$ with the quotient group $G/\ker(\rho)$.

> [!definition] Covering Space Action
> A $G$-action on a [[Topological Spaces#^65c94a|space]] $Y$ is called a *covering space action* if for any point $y \in Y$, there exists an open neighborhood $U$ of $y$ such that for any two distinct elements $g_1, g_2 \in G$, the sets $g_1U$ and $g_2U$ are disjoint.
> $$g_1 \neq g_2 \implies g_1U \cap g_2U = \emptyset$$
> When a group $G$ acts on a space $Y$, we can form the (quotient) [[Group Actions#^705c54|orbit space]] $X = Y/G$. The points of $X$ are the orbits of points in $Y$ under the action of $G$.

## Properties of Covering Space Actions

> [!theorem]
> If a group $G$ acts on a [[Topological Spaces#^65c94a|space]] $Y$ via a covering space action, and $X = Y/G$ with projection $p\colon Y \to X$, then:
> 1. $p\colon Y \to X$ is a [[Deck Transformations and Normal Covers#^aaf7ba|normal covering space]].
> 2. If $Y$ is also [[Connectedness and Paths#^946cc4|connected]], then the group of [[Deck Transformations and Normal Covers#^988018|deck transformations]] is isomorphic to the group $G$, i.e., $\text{Aut}_X(Y) \cong G$.
> 3. If $Y$ is also [[Connectedness and Paths#^630354|path-connected]] and [[Connectedness and Paths#^ba4f32|locally path-connected]], then the group of deck transformations is isomorphic to the quotient of the fundamental groups: $G \cong \pi_1(X, [y_0]) / p_*(\pi_1(Y, y_0))$.
> $\quad$

*Proof*  **(1)** First, we show $p: Y \to X$ is a covering space. Let $U$ be a neighborhood of a point $y \in Y$ as in the definition of a covering space action. Then $p(U)$ is an open set in $X$. Its preimage is $p^{-1}(p(U)) = \bigsqcup_{g \in G} gU$. The restriction of $p$ to each disjoint open set $gU$ is a homeomorphism onto $p(U)$. These sets $p(U)$ form a basis of evenly covered neighborhoods for the topology on $X$, so $p$ is a covering map.
To show the covering is normal, we must show that for any $y_1, y_2 \in Y$ such that $p(y_1) = p(y_2)$, there exists a deck transformation $f \in \text{Aut}_X(Y)$ with $f(y_1) = y_2$. By definition of the quotient space, $p(y_1) = p(y_2)$ means that $y_1$ and $y_2$ are in the same orbit, so there exists some $g \in G$ such that $y_2 = gy_1$[cite: 29]. The action of this $g$ (i.e., the map $f = \rho(g): Y \to Y$) is a deck transformation, and since $f(y_1) = gy_1 = y_2$, the condition is satisfied and the covering is normal.
**(2)** If $Y$ is connected, any deck transformation $f \in \text{Aut}_X(Y)$ is uniquely determined by its action on a single point, say $y_1$. Since $f$ is a deck transformation, we must have $p(f(y_1)) = p(y_1)$. This implies that $f(y_1)$ and $y_1$ are in the same fiber, so there must be some $g \in G$ such that $f(y_1) = gy_1$. Since the action of $g$ is also a deck transformation that sends $y_1$ to $gy_1$, and since deck transformations are uniquely determined by their action on one point, we must have $f = \rho(g)$. Thus, every deck transformation corresponds to an element of $G$.
**(3)** This is a standard result from covering space theory which states that for a normal covering space with a path-connected base space, the group of deck transformations is isomorphic to $\pi_1(X) / p_*(\pi_1(Y))$. $\square$

<u><b>e.g.</b></u>
- The group of integers $\mathbb{Z}$ acts on the real line $\mathbb{R}$ by addition: $(n, x) \mapsto n+x$. The quotient space is the circle, $\mathbb{R}/\mathbb{Z} \cong S^1$. This shows $\pi_{1}(S^{1})\cong \Z$.
- The group $\mathbb{Z}/2\mathbb{Z}$ acts on the $n$-sphere $S^n$ via the antipodal map ($x \mapsto -x$). The quotient space is the $n$-dimensional real projective space, $S^n / (\mathbb{Z}/2\mathbb{Z}) \cong \mathbb{R}\mathrm{P}^n$. So, $\pi_{1}(\mathbb{R}\mathrm{P}^n) \cong \mathbb{Z}/2\mathbb{Z}$ for $n \geq 2$.
- The cyclic group $\mathbb{Z}/p\mathbb{Z}$ acts on the $(2n-1)$-sphere $S^{2n-1}$, viewed as the unit sphere in $\mathbb{C}^n$. A generator of the group acts by multiplication by a $p$-th root of unity, $e^{2\pi i / p}$. The quotient space $S^{2n-1} / (\mathbb{Z}/p\mathbb{Z})$ is called a **lens space**, denoted $L_p^n$.
- Consider genus-$g$ surface $M_{g}$ for $g=mn+1$. The group $G=\Z/n\Z$ acting on $M_{g}$ by rotating each component of genus $m$. The quotient space is a surface with genus $h=m+1$.
  <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/covering_space_action_ex.svg" alt="covering_space_action_ex" style="width:20%;"/>
$\quad$
