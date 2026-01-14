> [!definition] Vector Fields on Manifolds
> Given a differentiable manifold $M$, a vector field $X$ on $M$ is a [[Vector Bundles#^947478|section]] of the [[Tangent Vectors and Spaces#^e3492e|tangent bundle]]. Explicitly, $X\colon M \to T(M)$ is an assignment that sends each point $p\in M$ to a tangent vector $X(p)\in T_{p}(M)$. The space of all vector fields is denoted by $\mathfrak{X}(M)$. or $\mathcal{X}(M)$. ^a87ff1

<u><b>e.g.</b></u>  $\Gamma(M\times \R^{k}) \cong C^{\infty}(M)^{\oplus k}$.

> [!remark]+ Vector Fields are Derivations
> One can see from the [[Tangent Vectors and Spaces#^f956d2|derivation definition of tangent vectors]] that a vector field $V$ can be identified as a derivation $C^{\infty}(M)\to C^{\infty}(M)$ that satisfies the equation: $$  (V(f))(x) := (V(x)) (f).$$ ^1804fc

The space of vector fields has a rich structure:

> [!proposition]
> The space of vector fields $\mathfrak{X}(M)$ is a $\R$-[[Vector Spaces#^f4b63e|vector space]].

*Proof*  It suffices to check that the scaler multiplication is valid. Indeed, $$(cX)(p):=c\cdot X(p), \quad \text{for all } c\in\R,p\in M,$$where the dot denotes the scalar multiplication in $T_{p}(M)$. It is clear that this satisfies distributivity and the associativity. $\square$

> [!proposition]
> The space of vector fields $\mathfrak{X}(M)$ is a [[Modules#^697aa9|module]] over the [[Ring, Field and Integral Domain#^178485|ring]] $C^{\infty}(M)$.

*Proof*  We can define the the scaler multiplication of a vector field $X$ by a smooth function $f\in C^{\infty}(M)$ as follows: $$(fX)(p) := f(p)\cdot X(p),\quad \text{for all } p\in M,$$where the dot denotes the scalar multiplication in $T_{p}(M)$. Clearly this gives a smooth vector field, and thus makes $\mathfrak{X}(M)$ a module over $C^{\infty}(M)$. $\square$

## Pullback Vector Fields

> [!definition] Pullback Vector Field
> Suppose $f\colon M\to N$ is a [[Smooth Functions and Maps#^39ce42|local diffeomorphism]]. The pullback of a vector field $X\in \mathfrak{X}(N)$ by $f$ is the [[Vector Bundles#^3c3b98|pullback section]] of the [[Tangent Vectors and Spaces#^e3492e|tangent bundle]]. That is $$(f^{*}X)(p):=(\d_{p}f)^{-1}(X(f(p)))$$

*Proof*  

$\quad$

## Lie Bracket of Vector Fields

> [!definition] Lie Bracket of Vector Fields
> Let $X, Y \in \mathfrak{X}(M)$. Then the Lie bracket $[X,Y]$ of $X$ and $Y$ is the vector field defined (as a derivation) by  
> $$   [X,Y] f := X(Y f) - Y(X f). $$
> The Lie bracket is thus the commutator of $X$ and $Y$ as operators on smooth functions. ^beba98

> [!proposition] Properties of Lie Bracket  
> The following hold for the Lie bracket of vector fields:
> 1. Bilinearity: $[X, aY + bZ] = a[X,Y] + b[X,Z]$.
> 2. Skew-symmetry: $[X,Y] = -[Y,X]$.
> 3. Jacobi Identity: $[X,[Y,Z]] + [Y,[Z,X]] + [Z,[X,Y]] = 0$.
>
>That is, $\mathfrak{X}(M)$ forms a [[Number Systems#^5fea5c|real]] [[Lie Algebra#^5007ba|Lie algebra]].

*Proof*  Bilinearity and skew-symmetry follow from the definition directly. We now check Jacobi identity. For all $f\in C^{\infty}(M)$, there holds $$\begin{aligned}&\,[X,[Y,Z]] + [Y,[Z,X]] + [Z,[X,Y]]  \\ =&\, X(Y(Zf)) -X(Z(Yf)) - Y(Z(Xf)) + Z(Y(Xf))  \\ &\, + Y(Z(Xf)) - Y(X(Z f)) - Z(X(Yf)) + X(Z(Yf)) \\ &\,+ Z(X(Yf)) - Z(Y(Xf)) - X(Y(Zf)) + Y(X(Zf)) \\ =&\,0 \end{aligned}$$ $\square$

> [!corollary] 
> Let $M$ be a smooth manifold and let $S$ be an immersed submanifold with or without boundary in $M$. If $X$ and $Y$ are smooth vector fields on $M$ that are tangent to $S$, then $[X, Y]$ is also tangent to $S$.

