> [!definition] Lie Group
> A Lie group $G$ is a group that is also a [[Manifolds and Atlases#^6ef2ef|smooth manifold]], such that the group operations of multiplication and inversion are both smooth maps. That is $$(x,y)\mapsto x^{-1}y$$is a smooth mapping of the product manifold into $G$. ^0e5dd8

<u><b>e.g.</b></u>  The [[Linear Groups#^2ce0d2|group of rotations]] in $\mathbb{R}^{2}$, $\newcommand{\SO}{\mathrm{SO}}\SO(2)$, is a Lie group. Each element of $\mathrm{SO}(2)$ can be represented by some rotation angle $\theta\in S^{1}$, this gives a chart so that $\SO_{2}$ is a smooth manifold. And the multiplication operation corresponds to the addition of angles, which is smooth. In general, $$\SO(n)\subset \mathrm{O}(n)\subset \mathrm{SL}(n,\R) \subset \mathrm{GL}(n,\R)$$are all Lie groups.

> [!proposition]
> Let $G$ be a Lie group. Then the left multiplication by $g\in G$, $\ell_{g}\colon G\to G$, is a diffeomorphism of $G$ onto itself.
> 

> [!proposition]
> For any Lie group $G$ of dimension $k$, we have $$TG\cong G\times \R^{k}$$ with respect to a basis $\{\partial_{1}, \dots \partial_{k}\}$ for $T_{e}G$.

*Proof*  Define a map $\phi\colon TG \to G\times T_{e}G$ by $[g,v] \mapsto \left(g, \D_{g}\ell_{g^{-1}}(v)\right)$, which is linear along each [[Vector Bundles#^9cb683|fiber]] ([[Tangent Vectors and Spaces#^76649d|tangent space]]) of $TG$. $\square$

> [!definition] Adjoint Representation (Action)
> 
> 
