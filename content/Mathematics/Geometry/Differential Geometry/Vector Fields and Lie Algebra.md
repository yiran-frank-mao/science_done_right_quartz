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

## Vector Fields on Lie Groups

> [!definition] Left-Invariant Vector Field  
> If $G$ is a Lie group and $v$ is a vector in $T_e G$, where $e$ is the identity element in $G$. Suppose $\ell_{g}\colon G\to G$ is the left multiplication map that sends $h$ to $gh$. Then we can use the maps $\D_{e}\ell_g$ to define a natural vector field on $G$, for each $g\in G$. We set  
> $$  V(g) := \d_{e}\ell_g (v).  $$  
> The resulting vector field $V$ is called a left-invariant vector field.

<u><b>e.g.</b></u>
- Let Lie group $G=\C\setminus\{0\}$, with the group operation of [[Complex Numbers#^a81924|complex number multiplication]]. Fix some $v\in T_{1}G=\R^{2}$, the left-invariant vector field $V$ is given by $$V(z) = \d_{1}\ell_{z} (v) = z v$$
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

## Lie Algebra of Lie Groups

Every Lie group $G$ has a canonical Lie algebra $\newcommand{\g}{\mathfrak{g}}\g$, which has two natural representations, either as the tangent space at the identity element $e$ of $G$, or as the space of left-invariant vector fields on $G$. We will see that the two representations are isomorphic.

> [!proposition]  
> Let $G$ be a Lie group, and suppose $X$ and $Y$ are smooth left-invariant vector fields on $G$. Then $[X,Y]$ is also left-invariant.

> [!proposition]
> The left-invariant vector fields on a Lie group form a Lie algebra.

*Proof*  It suffices to check $$\D\ell_g|_{e}$$

> [!theorem] 
> The set of all left-invariant vector fields on a Lie group $G$ is isomorphic to the tangent space at the identity element $e$ of $G$, via evaluation at $e$. In other words, every tangent vector $v\in T_{e}G$ extends uniquely to a left-invariant vector field.
> 

*Proof*  

> [!definition] Lie Algebra of a Lie Group
> The Lie algebra of a Lie group $G$, often denoted $\newcommand{\g}{\mathfrak{g}}\g$, is up to isomorphic, the Lie algebra of left-invariant vector fields on $G$, or the tangent space at the identity element $e$ of $G$. ^7b21eb

> [!remark]+
> Elements of the Lie algebra represent "infinitesimal transformations" or "directions of motion" within the group starting from the identity.
> 

> [!definition] Exponential Map
> For any Lie group $G$ with Lie algebra $\g$, the exponential map $\exp\colon \g \to G$ is defined by $$\exp(X)=\gamma(1),$$where $\gamma$ is the unique [[Integral Curves and Flows#^8974d8|integral curve]] of the left-invariant vector field $X$ such that $\gamma(0)=e$, or equivalently, $\gamma$ is the one-parameter subgroup generated by $X$.

<u><b>e.g.</b></u>  The Lie algebra of $S^{1}$, denoted $\newcommand{\s}{\mathfrak{s}}\s$, is isomorphic to $\R$. The exponential map of $S^{1}$ satisfies $$\exp(t x)=e^{itx}, \quad\text{for all } x\in\s\cong\R, t\in\R.$$ ^2ad381

> [!proposition]
> Let $G$ be a Lie group with associated Lie algebra $\g$. For any $X\in\g$, $s\mapsto\exp (sX)$ is the one-parameter subgroup of $G$ generated by $X$. That is, $\exp(tX)=\gamma(t)$ for all $t\in \R$.
> 

*Proof*  

> [!definition] Fundamental Vector Field
> Suppose $G$ is a Lie group with Lie algebra $\g$, acting on a smooth manifold $M$ with the action $*\colon G\times M\to M$ that $(g,p)\mapsto g* p$. The fundamental vector field on $M$ generated by the infinitesimal action of $\xi\in\g$, denoted by $\xi_{M}$ (or $X^{\xi}$), is defined at each point $p\in M$ as $$\newcommand{\dd}{\:\mathrm{d}}\newcommand{\d}{\mathrm{d}}\newcommand{\ddf}[2]{\frac{\d#1}{\d#2}}\newcommand{\pddf}[2]{\frac{\partial#1}{\partial#2}}\newcommand{\ddt}{\ddf{}{t}}\newcommand{\ddtz}{\ddt\bigg|_{t=0}} \xi_{M} \bigg|_{p}:=\ddtz \left(\exp(t\xi)*p\right).$$ ^5f72f5

<u><b>e.g.</b></u>  Since the $n$-torus $T^{n}=\left(S^{1}\right)^{n}$, its Lie algebra $\newcommand{\t}{\mathfrak{t}}\t$ is isomorphic to $\R^{n}$. From [[Vector Fields and Lie Algebra#^2ad381|the previous example]] of $S^{1}$, we can deduce that the exponential map of an $n$-torus takes the form $$\exp(tX)=\left(e^{itx_{1}},e^{itx_{2}},\dots,e^{itx_{n}}\right),\quad \text{for all } X=(x_{1},\dots,x_{n})\in \t\cong\R^{n}. $$Consider a torus $T^{n}$ acting on $\C^{n}$ by $$(e^{i\theta_{1}},\dots,e^{i\theta_{n}})*(z_{1},\dots,z_{n}):=(e^{ik_{1}\theta_{1}}z_{1},\dots,e^{ik_{n}\theta_{n}}z_{n}),$$for nonzero constants $k_{1},\dots,k_{n}\in \Z$. . Then for any $\xi=(\xi_{1},\dots,\xi_{n})\in\t$ and $z=(z_{1},\dots ,z_{n})\in \C^{n}$, there holds $$\xi_{M} \bigg|_{z}:=\ddtz \left(\exp(t\xi)*z\right)=(ik_{1}\xi_{1}z_{1},\dots,ik_{n}\xi_{n}z_{n}).$$ ^4fdba1