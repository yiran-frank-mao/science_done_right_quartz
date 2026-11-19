---
updated: 2025-02-14
cssclasses:
  - img-grid
  - img-zoom
---
## Singular Knots

> [!definition] Singular Knot
> A singular knot is a smooth map $S^{1}\to S^{3}$ which fails to be an embedding, where the only failures allowed are simple double points. That is, places where the curve intersects itself transversally, and at the intersection only two threads intersect.

> [!attention] 
> We will restrict our attention to oriented singular knots, which are equipped with a direction.

> [!definition] Singular Knot Diagram
> A singular knot diagram is a planar projection of a singular knot, which has two types of crossings: regular crossings with over/under strand information, and double points.

Each singularity of a singular knot can be resolved two ways: by replacing the double point with an over-crossing, or with an under-crossing. So we can define a resolution map as follows:

> [!definition] Resolution Map
> Let $\mathcal{K}_{n}$  denote the set of $n$-singular knots. The resolution map $\newcommand{\C}{\mathbb{C}}\rho\colon \mathcal{K}_{n}\to \C \mathcal{K}$ is defined by replacing each singularity of a given $n$-singular knot by the difference of its two resolutions.
> 
> ![resolution_map.svg|350](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/resolution_map.svg)

## The Vassiliev Filtration

> [!theorem] Vassiliev Filtration
> Suppose $\mathcal{K}$ is the set of all oriented knots $S^{1}\hookrightarrow S^{3}$, consider the algebra $\C\mathcal{K}$ of formal linear combinations. The Vassiliev-Goussarour filtration is a filtration of $\C\mathcal{K}$ by the number of double points in a singular knot diagram resulting from the inverse resolution map:$$ \C\mathcal{K}=\mathcal{F}_{0}\supseteq \mathcal{F}_{1} \supseteq \mathcal{F}_{2} \supseteq \cdots $$where $\mathcal{F}_{n}$ is the ideal spanned by knots with at least $n$ double points.

<u><b>e.g.</b></u>  We can compute the trefoil minus unknot as follows: 

![vassiliev_filtration.svg|50%](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/Vassiliev_filtration.svg)

> [!remark]
> $\C\mathcal{K}$ is an algebra by linearly extending the commutative monoid structure. i.e. make [[Knots and Links#^433222|connected sum]] distributive.




