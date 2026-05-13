---
updated: 2025-02-06
completed: true
cssclasses:
  - img-zoom
---
## A Smooth Approach

> [!definition] Knot and Link
> A (smooth) *knot* is a smooth embedding $K \colon S ^{1} \hookrightarrow S^{3}$.
> More generally, a *link* $L$ with $n$ connected components is a smooth embedding of $\underbrace{S^1\sqcup\cdots\sqcup S^1}_{n\text{ copies}}$ into $S^{3}$.

> [!remark] When are two knots same?
>  Homotopy is a continuous deformation, which is not enough, because one path might cross itself under the deformation. We need to consider isotopy, which is a continuous deformation of embeddings. However, it turns out that isotopy is not enough either, because any tangle can be shrunk to a point.
>  ![knot_isotopy.gif|350](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/knot_isotopy.gif)
>  To solve this, we need to consider one of the following:
>  - Ambient isotopy: a continuous deformation of the space.
>  - Smooth isotopy: a differentiable deformation of knots.
>  - Thick tubes instead of circles.
> $\quad$

> [!definition] Knot Equivalence
> We will say that two knots (or links) $K_{1}$ and $K_{2}$ are *equivalent* if they are ambient isotopic, that is, if there is a continuous $h\colon S^{3} \times [0, 1] \to S^3$ such that $h(\cdot, t) = h_{t} : S^{3} \to S^{3}$ satisfy $\DeclareMathOperator{\id}{id} h_{0}=\id_{S^{3}}$ and $h_{1}\circ K_{1}=K_{2}$. Such a map $h$ is called an ambient isotopy.

> [!remark]+
>  According to the definition, a knot or a link is a map. However, we are allowed to think about a knot or a link as the image of such maps, because knots with the same image are equivalent to each other.

<u><b>e.g.</b></u> The simplest knot is the unknot.

## Knot Diagrams

> [!definition] Knot Diagram
> A knot diagram (or link diagram) is a 4-valent graph with over/under crossing information at each vertex. The diagram is embedded in a plane $S^2 ⊂ S^3$ called the projection plane.
> ![knot_table.svg|70%](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/knot_table.svg)

> [!theorem] Reidemeister Moves
> Two knot diagrams represent the same knot if and only if one can be obtained from the other by a finite sequence of Reidemeister moves. The below are three types of Reidemeister moves:
> ![Reidemeister_moves.svg|75%](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/Reidemeister_moves.svg)

> [!remark]
> However, if a knot diagram $D$ represents unknot, one may need a huge number of Reidemeister moves to show this. In fact, it is an open problem to determine the minimum number of Reidemeister moves required to show that a given knot diagram represents the unknot.

## Algebraic Structure for Knots

> [!definition] Connected Sum
> Connected sum is a binary operation on knots, denoted by $K_{1} \# K_{2}$, where $K_{1}$ and $K_{2}$ are two knots. The connected sum of two knots is obtained by removing a small open disk from each knot and gluing the two resulting boundaries together. ^433222

<u><b>e.g.</b></u> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/connected_sum.svg" alt="" style="width:40%;"/>

> [!remark] Why connected sum is well-defined?
> First, it does not matter where we attach, because, say we are connecting $K_{1}$ with $K_{2}$, we can always move $K_{2}$ around to grow it back.
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/connect_sum_attach.svg" alt="connect_sum_attach" style="width:65%;"/>
> Moreover, knots are naturally equipped with a counterclockwise orientation. The connected sum of two knots is well defined up to orientation. i.e. there is only one way to connect in an orientation-preserving way, and we can only pick one of the following:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/connect_sum_orientation.svg" alt="connect_sum_orientation" style="width:90%;"/>

> [!proposition]
> Connected sum is associative, unital and commutative. Thus the set of all knots with the connected sum operation forms a commutative [[Free Groups and Relations#^587eee|monoid]], denoted by $(\mathcal{K}, \#)$.

*Proof*  Clearly the unit is the unknot, commutativity and associativity are inherited from the underlying operation. $\square$

Since such monoid is just isomorphic to positive integers with multiplication $(\mathbb{Z}_{>0},\cdot)$, we can introduce the following concepts accordingly:

> [!definition] Prime Knot
> A knot is prime if it is not the connected sum of two non-trivial knots.

> [!theorem]
> Every knot has a unique prime decomposition. There are infinitely many prime knots.

*Proof*  By the isomorphism and the fact that [[Division and Prime#^1e1100|there are infinitely many prime numbers]]. $\square$
