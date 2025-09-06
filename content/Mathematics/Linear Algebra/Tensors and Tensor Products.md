---
created: 2024-05-18
updated: 2024-09-24
---
Tensors and tensor products are multilinear generalizations of vectors and matrices. They provide a flexible framework for representing and manipulating data in various fields. In fact, there are multiple ways to define tensors and tensor products. We will start with an abstract algebraic definition, and then provide constructive definitions in terms of multilinear maps. ^bd55c9

> [!definition] Multilinear Map
> Suppose $U_{i}$ and $W$ are [[Vector Spaces#^f4b63e|vector spaces]].  A function $f \colon \prod_{i=1}^{n} U_{i} \to W$ is called multilinear if it is linear in each variable. That is, when for all $k<n$, the function $u_{k} \mapsto f (u_{1},\dots,u_{n})$ is linear for each $u_{i} ∈ U_{i}$ with $i\neq k$. In particular, a bilinear function is a multilinear function of two variables. ^da894d

## Tensor Product of Vector Spaces

>[!definition] Tensor Product of Vector Spaces
>The tensor product of vector spaces $U$ and $V$ over the same field is a vector space $U \otimes V$ together with a bilinear function $f\colon U \times V\to U \otimes V$ such that for every vector space $W$ and bilinear function $g \colon U \times V \to W$ there exists a unique linear function $h \colon U \otimes V \to W$ such that $g = h \circ f$:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/tensor_product_universal_property.svg" alt="tensor_product_universal_property" style="width:27%;"/>
>The function $f$ usually stays anonymous and is written as $(a, b) \mapsto a \otimes b$. ^732917

> [!theorem] Construction of Tensor Product of Vector Spaces
> The tensor product of vector spaces $U$ and $V$ over the same field $F$ is a vector space $U \otimes V$ of the same field $F$ spanned by the set of all pure (elementary) tensors of the form $u \otimes v$ for $u\in U$ and $v\in V$ with the following properties hold:
> - $(v_{1}+v_{2})\otimes w = v_{1}\otimes w + v_{2}\otimes w$.
> - $v\otimes (w_{1}+w_{2}) = v\otimes w_{1} + v\otimes w_{2}$.
> - $(\lambda v)\otimes w = \lambda(v\otimes w) = v\otimes (\lambda w)$ for all $\lambda\in F$.
> $\quad$

>[!remark]+ Intuition of Tensor Products
>Tensor products of vector spaces are to Cartesian products of sets as direct sums of vectors spaces are to disjoint unions of sets.

> [!proposition] 
> A basis of $U\otimes V$ is given by the set of all pure tensor products of basis vectors of $U$ and $V$.

*Proof*  

> [!proposition]
> The tensor product is a [[Functoriality and Naturality#^653948|bifunctor]] from the [[Structure of Categories#^2f5c3a|category]] of vector spaces to itself.

## Tensors as Multilinear Maps

> [!theorem]
> Suppose $U$ and $V$ are finite dimensional vector spaces. The tensor product space $U^{*}\otimes V$ of  [[Mathematics/Linear Algebra/Duality#^6c7627|dual space]] of $U$ and $V$ can be naturally identified with the space of linear maps $U\to V$. That is $$\Hom(U,V) \cong U^{*} \otimes V.$$

*Proof*  For any $\alpha\otimes v\in U^{*} \otimes V$, we can identify it with the linear map $\phi_{\alpha\otimes v} \colon U \to V$ given by $$\phi_{\alpha\otimes v}(u) = \alpha(u)v.$$ This gives a linear map $\phi \colon U^{*} \otimes V \to \Hom(U,V)$, and we can easily see that $\phi$ is an isomorphism. $\square$

> [!remark]+ What does it mean by "naturally identified"?
> This is a subtle but interesting point. It means that this isomorphism is "special" and "nice", so that it does not depend on the choice of basis. In fact, this is what covectors are all about. Covectors are designed to eliminate the need to fix a basis when working with dual spaces. By contrast, if the isomorphism _did_ depend on the choice of basis, it would be considered _non-canonical_, and we would typically only assert the existence of an isomorphism, without identifying a specific one.

> [!definition] Tensor
> A tensor $\Phi$ of type $(r,s)$ over a [[Vector Spaces#^f4b63e|vector space]] $V$ on the [[Ring, Field and Integral Domain#^575174|field]] $F$ is a multilinear map: $$\Phi \colon \underbrace{V^{*}\times\dots\times V^{*}}_{r}\times\underbrace{V\times\dots\times V}_{s}\to F$$where $V^*$ denotes the [[Duality#^6c7627|dual space]] of $V$, $r$ is called contravariant order and $s$ is called covariant order. ^efc3f2

<u><b>e.g.</b></u>  A matrix $M\in\newcommand{\R}{\mathbb{R}}\R^{n\times n}$ naturally forms a $(1,1)$-tensor $(v,w^{\top})\mapsto w^{\top} M v$.

> [!proposition]
> Tensors of type $(r,s)$ over a [[Vector Spaces#^f4b63e|vector space]] $V$ are exactly elements of the tensor space $$V^{r,s}:=V^{\otimes r}\otimes (V^{*})^{\otimes s}$$
> 

> [!definition] Tensor Product of Tensors
> Let $T$ and $S$ be two tensors of types $(k,l)$ and $(p,q)$ respectively. Then the tensor product $T \otimes S$ is the tensor of type $(k+p,l+q)$ defined by $$(T \otimes S) (v_{1},\dots,v_{k+p},w_{1},\dots,w_{l+q}) = T(v_{1},\dots v_{k},w_{1},\dots,w_{l}) \cdot S(v_{k+1},\dots,v_{k+p}, w_{l+1},\dots,w_{l+q})$$for all vectors $v_{i}\in V$ and covectors $w_{i} \in V^{*}$.

## References and Useful Links
- [MATH 55a: Honors Abstract Algebra](https://people.math.harvard.edu/~elkies/M55a.10/tensor.pdf).
- [A Concrete Introduction to Tensor Products](https://www.youtube.com/watch?v=KnSZBjnd_74).
- [Complete Derivation: Universal Property of the Tensor Product](https://www.youtube.com/watch?v=vZzZhdLC_YQ).