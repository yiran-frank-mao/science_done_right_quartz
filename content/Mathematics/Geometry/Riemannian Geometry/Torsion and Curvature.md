---
created: 2024-08-06
updated: 2024-10-29
---
## Torsion

>[!definition] Torsion
>Let $M$ be a manifold with an [[Connections#^f86a0b|affine connection]] $\nabla$ on the [[Tangent Vectors and Spaces#^e3492e|tangent bundle]]. The torsion tensor of $\nabla$ is the vector valued $2$-form defined on vector fields $X$ and $Y$ by $$T(X,Y)=\nabla_XY-\nabla_YX-[X,Y]$$where $[X,Y]$ is the [[Vector Fields and Lie Algebra#^beba98|Lie bracket]] of $X$ and $Y$.We say an affine connection is torsion free if its torsion tensor vanishes identically. ^bec0c5

> [!proposition]
> The torsion $T$ is tensorial.

*Proof*  Let $X,Y$ be vector fields and $f$ a smooth function. Then we have $$\begin{aligned}T(fX,Y)&=\nabla_{fX}Y-\nabla_Y(fX)-[fX,Y]\\&=f\nabla_XY- Y(f)X-f\nabla_YX+Y(f)X-f[X,Y]\\&=f(\nabla_XY-\nabla_YX-[X,Y])\\&=fT(X,Y)\end{aligned}$$$\square$

>[!proposition]
> In a local coordinate system, the torsion tensor is given by $$T_{ij}^k=\Gamma_{ij}^k-\Gamma_{ji}^k$$

*Proof* $$\begin{aligned}T(\partial_{i}, \partial_{j})=\nabla_{i} \partial_{j} -\nabla_{j} \partial_{i} - [\partial_{i}, \partial_{j}]=(\Gamma_{ij}^{k}-\Gamma_{ji}^{k})\partial_{k}\end{aligned}$$It follows that $T_{ij}^{k}=\Gamma_{ij}^{k}-\Gamma_{ji}^{k}$. $\square$

> [!corollary]
> An affine connection is torsion free if and only if the first two components of the [[Connections#^2f05b3|Christoffel symbols]] are symmetric. i.e. $\Gamma_{ij}^k=\Gamma_{ji}^k$. ^50eeae

*Proof*  It is straightforward in coordinate form. $\square$


## Curvature

> [!definition] Riemann Curvature
> Let $M$ be a manifold with an [[Connections#^f86a0b|affine connection]] $\nabla$ on the [[Tangent Vectors and Spaces#^e3492e|tangent bundle]]. The (Riemann) curvature tensor of $\nabla$ is the vector valued $2$-form defined on vector fields $X$ and $Y$ by $$R(X,Y):=\nabla_X\nabla_Y-\nabla_Y\nabla_X-\nabla_{[X,Y]}.$$
> Alternatively, the Riemann tensor can be defined as a $(1,3)$-tensor that acts on $X,Y,Z\in\mathfrak{X}(M)$ and $\omega\in\Lambda^{1}(M)$ by
> $$R(X,Y,Z,\omega):=\omega\left(\nabla_{X}\nabla_{Y} Z-\nabla_{}Y\nabla_{X} Z-\nabla_{[X,Y]} Z\right).$$ ^4605ee

In fact, we can also introduce the curvature tensor to any vector bundle:

> [!definition] Curvature Tensor
> Suppose $\nabla$ is a connection on a vector bundle $E$ over $M$, then the curvature tensor $R$ of $\nabla$ is the section of $T^{*}M\otimes T^{*}M\otimes E^{*}\otimes E$ defined by $$R(X,Y,\xi):=\nabla_{Y}(\nabla_{X}\xi)-\nabla_{X}(\nabla_{Y}\xi)-\nabla_{[Y,X]}\xi.$$

> [!remark]+ Geometric Meaning of Curvature
> The Riemann curvature tensor gives a measure of the non-commutativity of covariant derivatives acting on tensor fields on $M$.
> 

> [!proposition]
> An [[Connections#^f86a0b|affine connection]] is flat if and only if there exist a local coordinate system in which [[Connections#^2f05b3|Christoffel symbols]] vanish.

*Proof*

> [!theorem]
> An affine connection is flat if and only if the parallel transport is path independent.

> [!proposition]
> The components of the Riemann curvature tensor are given by $$R_{ijk}^{l}=\partial_{j}\Gamma_{ki}^{l}-\partial_{k}\Gamma_{ji}^{l}+\Gamma_{ki}^{m}\Gamma_{jm}^{l}-\Gamma_{ji}^{m}\Gamma_{km}^{l}.$$

> [!definition] Ricci Tensor
> Ricci tensor is the contraction of the Riemann curvature tensor over the first and third indices (equivalently, the second and fourth indices). Explicitly, it is a $(0,2)$-tensor such that$$R_{ij}:=R_{ikj}^{k}.$$ ^deb9d2

> [!proposition]
> The Ricci tensor is symmetric.
> 

*Proof*  $$R_{ij}=R^{k}_{ikj}=$$

We can further contract the Ricci tensor to obtain the Ricci scalar. But since the Ricci Tensor is already purely covariant, one cannot contract it further without introducing a metric. So we have the following definition:

> [!definition] Ricci Scaler
> Ricci scaler is a $(0,0)$-tensor, i.e. a smooth function, defined on a [[Riemannian Metrics#^c3ac13|semi Riemannian manifold]] by $$R=g^{ij}R_{ij}.$$
