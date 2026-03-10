---
updated: 2025-08-23
completed: true
tags:
  - homotopy
  - algebraic-topology
---
## Homotopy

> [!definition] Retraction
> Suppose $X$ is a [[Topological Spaces#^65c94a|topological space]], then a continuous map $r\colon X\to X$ such that $r^{2}=r$ is called a retraction. The image of $r$ is called the retract of $X$. 

> [!remark]+
> Retraction is the topological analogue of a projection in linear algebra. In general, they are the maps that "project" the space onto a subspace while preserving the structure of the space.

> [!definition] Homotopy
> A *homotopy* is a continuous deformation of one function into another. Formally, given two [[Continuous Functions on Topological Spaces#^33ee5a|continuous functions]] $f,g\colon X \to Y$, where $X,Y$ are [[Topological Spaces#^65c94a|topological spaces]], a homotopy between $f$ and $g$ is a continuous function $H\colon X \times [0,1] \to Y$ such that $H(-,0)=f$ and $H(-,1)=g$.
> One says that two maps $f$ and $g$ are *homotopic*, if there exists a homotopy $H$ from $f$ to $g$, and denoted $f\simeq g$.
> For [$C^{k}$-manifolds](Manifolds%20and%20Atlases.md#%5E6ef2ef), we can also define *$C^{k}$-homotopy* by requiring the homotopy $H$ to be $C^{k}$-smooth. ^2c10b4
> 

<u><b>e.g.</b></u>  A deformation retraction of $X$ onto a subspace $A$ is a homotopy from the identity map of $X$ to a retraction of $X$ onto $A$, that is, a map $r\colon X\to X$ such that $r(X)=A$ and $\newcommand{\id}{\mathrm{id}} r|_{A}=\id$. ^05414e

> [!definition] Relative Homotopy
> Let $A\subset X$ be a subspace. $f,g\colon X\to Y$ be continuous maps with $f|_{A}=g|_{A}$. Then we say $f\simeq g$ relative to $A$ if there exists a homotopy $H\colon X\times [0,1]\to Y$ such that $H(a,t)=f(a)=g(a)$ for all $a\in A$ and $t\in [0,1]$.

> [!definition] Homotopy Equivalence
> A map $f\colon X\to Y$ is called a homotopy equivalence if there is a map $g\colon Y\to X$ such that $f\circ g\simeq \id_{Y}$ and $g\circ f\simeq \id_{X}$. In this case, topological spaces $X$ and $Y$ are said to be homotopy equivalent, or to have the same homotopy type, and denoted $X\simeq Y$.
> 

> [!remark]+
> It is easy to see that homotopy equivalence is an equivalence relation. Furthermore, it is weaker than homeomorphism.

> [!lemma]
> Two topological spaces are homotopy equivalent if and only if there exists a third space $Z$ containing both $X$ and $Y$ as deformation retracts.

> [!definition] Contractible Space
> A topological space is contractible if it has the same homotopy type as a point.
> 

## Path Homotopy

An important concept in homotopy theory is the path homotopy, which deals with paths in [[Topological Spaces#^65c94a|topological spaces]]. We first recall the following definition of a path:

![[Connectedness and Paths#^1c51ed]]

So a path homotopy is a homotopy between paths relative to the boundary of the interval. Formally, given two paths $\gamma_{1},\gamma_{2}\colon [0,1]\to X$ in a topological space $X$ with same endpoints, a homotopy between them is a continuous function $H\colon [0,1]\times [0,1]\to X$ such that $H(0,s)=\gamma_{1}(s)$ and $H(1,s)=\gamma_{2}(s)$ for all $s\in [0,1]$. ^76ea93

> [!definition] Concatenation of Paths
> For two paths $\gamma_{1}\colon [0,1]\to X$ and $\gamma_{2}\colon [0,1]\to X$ such that the end point of $\gamma_{1}$ coincides with the start point of $\gamma_{2}$, we define their concatenation $\gamma_{1}\cdot\gamma_{2}\colon [0,1]\to X$ by $$(\gamma_{1}\cdot\gamma_{2})(s)=\begin{cases} \gamma_{1}(2s),\quad s\in[0,1/2],\\ \gamma_{2}(2s),\quad s\in[1/2,1]. \end{cases}$$

>[!definition] Reversed Path
> If $\gamma\colon [0,1] \to X$ is a path, then the reversed path $\gamma^{-}$ is given by $\gamma^{-}(t)=\gamma(1-t)$. ^2b9913

Now we have some operations on paths, so one might want to ask if there is any algebraic structure on the set of paths. The answer is yes, and it is called the [[The Fundamental Group#^74adbc|fundamental group]], which will be discussed in the next page.