Tensors are mathematical objects that generalize the familiar concepts of scalars, vectors, and exterior forms to higher dimensions. Their crucial feature lies in their ability to represent physical laws in a form that remains valid regardless of the coordinate system used by an observer.

## Covectors and The Cotangent Bundle

> [!definition] Covector & Cotangent Space
> A covector $\omega$ at $x\in M$ is an element in the [[Mathematics/Linear Algebra/Duality#^6c7627|dual]] of the [[Tangent Vectors and Spaces#^76649d|tangent space]], i.e. a linear map from $T_{x}(M)$ to $\R$. The dual of $T_{x}M$, which we denote $T_{x}^{*}(M)$, and is called the cotangent space at $x$. ^bd6c33

Similar to the tangent space, the set of all covectors on $M$ forms a [[Vector Bundles#^9cb683|vector bundle]] over $M$, denoted $T^{*}(M)$, called the cotangent bundle:

> [!definition] Cotangent Bundle
> A cotangent bundle is the [[Construction of Sets#^e08e6f|disjoint union]] of the cotangent spaces of a manifold $M$: $$T^{*}M= \bigsqcup_{p}T^{*}_{p}M=\{(p,v):p\in M, \omega\in T^{*}_{p}(M)\}.$$ ^f98eed

## Tensor and Tensor Fields

> [!definition] Tensor (Field) on Manifold
> A tensor of type $(r,s)$ at $x\in M$ is a $(r,s)$-[[Tensors and Tensor Products#^efc3f2|tensor]] over $T_{x}M$.
> A tensor field of type $(r,s)$ on $M$ is a smooth assignment of a tensor of type $(r,s)$ at each point $x\in M$.
> Inherited from the terminology of tensors,  tensor fields of type $(0,r)$ is said to be covariant, and tensor fields of type $(s,0)$ is said to be contravariant.
> The set of all tensors of type $(r,s)$ at $x$ forms a vector space, denoted $T_{x}^{r,s}(M)$, and the set of all tensors of type $(r,s)$ on $M$ forms a [[Vector Bundles#^9cb683|vector bundle]] over $M$, denoted $T^{r,s}(M)$. ^efc3f2

> [!remark]+
> One can naturally recognize every tensor field as a map $\mathfrak{X}(M)^{r}\times \mathfrak{X}^{*}(M)^{s} \to C^{\infty}(M)$.

<u><b>e.g.</b></u>  
- A covector is just a tensor of type $(0,1)$, and a vector is a tensor of type $(1,0)$.
- Real-valued functions are covariant, vector fields are contravariant.
- One-forms or covectors are also covariant. This is nice, because the prefix "co-" means not only duality, but also covariance.
$\quad$

## Tensors in Local Coordinates

> [!definition] Tensor Components
> Let $(x^{1},\dots,x^{n})$ be a coordinate on $U\subset M$. If $A\in T^{s}_{r}(M)$ is a tensor field, the components of $A$ relative to this coordinate are the real valued functions: $$A^{j_{1},\dots,j_{s}}_{i_{1},\dots,i_{r}}=A(\partial_{i_{1}},\dots,\partial_{i_{r}}\d x^{j_{1}},\dots,\d x^{j_{s}}),$$where all indices run from $1$ to $n$.

> [!theorem] Contraction Tensor
> Let $A$ be a tensor at $x\in M$ of type $(r,s)$. Then there is a tensor of type $(r-1,s-1)$, the contraction of $A$ with respect to the $i$-th covector and the $j$-th vector is a tensor at $x$ of type $(r-1,s-1)$ given by $$A_{i}^{j}:=\sum_{k=1}^{n} A^{j}_{i_{1},\dots,i_{r}}$$

<u><b>e.g.</b></u>  A special case is where $T$ is a tensor of type $(1,1)$. This takes a vector and gives another vector, and so is nothing other than a linear operator on $T_{x}M$. There is a unique contraction in this case, which is just the trace of the operator: $\newcommand{\tr}{\operatorname{tr}}\tr(T)=\sum_{i=1}^{n}T^{i}_{i}.$

## Raising and Lowering Indices

Lowering and raising indices is the procedure of converting between covariant (lower) and contravariant (upper) components of tensors by contracting with the [[Riemannian Metrics#^c3ac13|metric tensor]] $g$ or its inverse $g^{-1}$.


