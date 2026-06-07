---
updated: 2025-02-24
cssclasses:
  - img-grid
  - img-zoom
---
Recall the definition of a winding number in the complex plane$\newcommand{\C}{\mathbb{C}}\newcommand{\dd}{\,\mathrm{d}}$:

![[The Argument Principle#^03d006|winding number]]

> [!definition] Kontsevich Integral
> The unnormalised Kontsevich integral $Z\colon \C\mathcal{K}\to \mathcal{C}$ of a knot is defined as: $$\begin{aligned}Z\left(K\right)&=\sum_{m=0}^\infty\frac1{\left(2\pi i\right)^m}\int\limits_{\substack{t_{\min}<t_1<\ldots<t_m<t_{\max}\\ t_j\text{ are noncritical}}}\sum_{P=\left\{\left(z_j,z_j^{\prime}\right)\right\}}\left(-1\right)^{\#P_{\downarrow}} D_{P}\bigwedge_{j=1}^{m}\frac{\dd z_{j}-\dd z_{j}^{\prime}}{z_{j}-z_{j}^{\prime}}\end{aligned}$$where
> - the integration domain is an $m$-dimensional simplex divided by the critical values into a certain number of connected components,
> - $P=\{(z_{i},z'_{i})\}_{i=1}^{m}$ is the set of unordered pairs of strands,
> - $\#P_{\downarrow}$ is the number of decreasing strands in $P$,
> - $D_{P}$ is the chord diagram associated to $P$ by joining each $z_{i}$ and $z_{i}^{\prime}$ with a chord.
> 
> The integral makes sense as "a big combo of simultaneous winding numbers" by picking the point $z_{i}$ or $z_{i}'$ along the chosen strand that you chose for $P$, and project this point to the complex plane.

<u><b>e.g.</b></u>  Let's consider the hump:

![kontsevich_integral_eg.svg|500](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/kontsevich_integral_eg.svg)

> [!proposition]
> The Kontsevich integral is well defined, the coefficients of the series are finite.

*Proof (Sketch)*  The coefficient of each $D_{P}$ is $$\pm \int \bigwedge_{j=1}^{m}\frac{\dd z_{j}-\dd z_{j}^{\prime}}{z_{j}-z_{j}^{\prime}},$$so the only thing that we need to care about is whether the denominators are bounded below.
Possible issues are:
1. Two strands can be arbitrarily close.
2. Next to a critical point.
3. Next to a critical point but don't form an isolated chord.

(1) is resolved by restricting on tame knots, (2) and (3) are resolved by applying the 1T relation.

> [!lemma]
> The Kontsevich integral is invariant under horizontal isotopy with fixed critical points.

> [!lemma]
> The Kontsevich integral is invariant under moving critical points by finger moves.

However, it is not invariant in general if one changes the number of critical points. This is why we need to normalise the Kontsevich integral:

> [!definition] Normalised Kontsevich Integral
> The normalised Kontsevich integral is defined as $$\bar{Z}(K):=\frac{Z(K)}{Z(H)^{c/2}}$$where $H$ is the hump, $c$ is the number of critical points of $K$.

> [!proposition]
> The normalised Kontsevich integral is a knot invariant.

> [!theorem]
> The rubber band map compose the normalised Kontsevich integral $\pi\circ \bar{Z}$ is a universal quantum invariant.



## References
- [Wolfram Mathworld, Kontsevich Integral](https://mathworld.wolfram.com/KontsevichIntegral.html)