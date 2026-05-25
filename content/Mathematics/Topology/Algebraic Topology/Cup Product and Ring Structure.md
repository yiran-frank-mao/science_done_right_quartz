## The Cup Product

> [!definition] Cup Product
> Let $R$ be a [[Ring, Field and Integral Domain#^178485|ring]]. The *cup product* is a map
> $$\smallsmile \colon C^k(X;R) \times C^l(X;R) \to C^{k+l}(X;R)$$
> given by the following formula. For $\varphi \in C^k(X;R)$, $\psi \in C^l(X;R)$, and a singular $(k+l)$-simplex $\sigma\colon \Delta^{k+l} \to X$, we define:
> $$(\varphi \smallsmile \psi)(\sigma) = \varphi(\sigma|_{[v_0, \dots, v_k]}) \cdot \psi(\sigma|_{[v_k, \dots, v_{k+l}]})$$
> Here, $\sigma|_{[v_0, \dots, v_k]}$ is the restriction of $\sigma$ to the "front face" (a $k$-simplex), $\sigma|_{[v_k, \dots, v_{k+l}]}$ is the restriction to the "back face" (an $l$-simplex), and the product is taken in the ring $R$.

The cup product interacts with the coboundary operator via the following rule.

> [!lemma] Coboundary Formula for Cup Product
> For $\varphi \in C^k(X;R)$ and $\psi \in C^l(X;R)$, the following Leibniz-type rule holds:
> $$d^{k+l+1}(\varphi \smallsmile \psi) = (d^{k+1}\varphi) \smallsmile \psi + (-1)^k \varphi \smallsmile (d^{l+1}\psi).$$

An important consequence of this formula is that the cup product of two cocycles ($d^{k}\varphi=0$, $d^{l}\psi=0$) is again a cocycle. Furthermore, the product of a cocycle and a coboundary is a coboundary. This implies that the cup product descends to a well-defined product on cohomology: $$\smallsmile : H^k(X;R) \times H^l(X;R) \to H^{k+l}(X;R).$$

## The Cohomology Ring

The above properties mean that $H^*(X;R)$ equipped with the cup product forms a ring:

> [!theorem]
> $H^*(X;R) = \bigoplus_k H^k(X;R)$ is a unital, associative, [[Ring, Field and Integral Domain#^178485|ring]] under the cup product. The unit $1 \in H^0(X;R)$ is represented by the cocycle $\varphi \in C^0(X;R)$ which maps every 0-simplex (a point in $X$) to the multiplicative identity $1_R \in R$.
> This is called the *cohomology ring* of $X$ with coefficients in $R$.

*Proof of Unital Property*  Let $\mathbf{1} \in H^0(X;R)$ be the unit element, represented by the cocycle $\varphi$ where $\varphi(x) = 1_R$ for any point $x \in X$. Let $[\psi] \in H^n(X;R)$ be represented by the cocycle $\psi \in C^n(X;R)$. For any $n$-simplex $\sigma: \Delta^n \to X$ with vertices $[v_0, \dots, v_n]$, we have: $$(\varphi \smallsmile \psi)(\sigma) = \varphi(\sigma|_{[v_0]}) \cdot \psi(\sigma|_{[v_0, \dots, v_n]})$$Since $\sigma|_{[v_0]}$ is a 0-simplex, $\varphi(\sigma|_{[v_0]}) = 1_R$. Therefore, $$(\varphi \smallsmile \psi)(\sigma) = 1_R \cdot \psi(\sigma|_{[v_0, \dots, v_n]}) = \psi(\sigma)$$This shows that $\varphi \smallsmile \psi = \psi$, so $[\mathbf{1}] \smallsmile [\psi] = [\psi]$. A similar calculation shows $[\psi] \smallsmile [\mathbf{1}] = [\psi]$, so it is a two-sided unit. $\square$

> [!proposition] Induced Homomorphisms
> Let $f\colon X \to Y$ be a [[Continuous Functions on Topological Spaces#^33ee5a|continuous map]]. The induced map on cohomology $f^{*}\colon H^{*}(Y;R) \to H^{*}(X;R)$ is a homomorphism of graded rings. That is, it preserves the ring structure:
> $$f^{*}(1) = 1,\quad f^{*}(x \smallsmile y) = f^{*}(x) \smallsmile f^{*}(y).$$

<u><b>e.g.</b></u>  The cohomology ring of the torus $T^2 = S^1 \times S^1$ with integer coefficients is isomorphic to the exterior algebra on two generators of degree 1. Recall our $\Delta$-complex structure for the torus:
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/torus_delta_complexes.svg" alt="torus_delta_complexes" style="width:23%;"/>
The chain complex is $$ 0 \to \Z\{U,L\} \xrightarrow{d_{2}} \Z\{a,b,c\} \xrightarrow{d_{1}} \Z\{v\} \to 0 ,$$where $d_{2}(U) = a - c + b$, $d_{2}(L) = b - c + a$, and $d_{1}(a) = d_{1}(b) = d_{1}(c) = 0$. So we have the homology groups: $$H_{0}=\Z\{v\},\quad H_{1}=\Z\{\bar{a},\bar{b}\}, \quad H_{2}=\Z\{U-L\}. $$Dualize to get the cochain complex: $$0\leftarrow \Z\{U^{*}, L^{*}\}\xleftarrow{d^{2}}\Z\{a^{*}, b^{*}, c^{*}\} \xleftarrow{d^{1}} \Z\{v^{*}\} \leftarrow 0, $$where $d^{2}$ maps $$a^{*}\mapsto U^{*}+L^{*},\quad b^{*}\mapsto U^{*}+L^{*},\quad c^{*}\mapsto -U^{*}-L^{*}, $$and $d^{1}$ is the zero map (we can think of $d^{1}$ and $d^{2}$ as the transpose of $d_{1}$ and $d_{2}$). Thus, the cohomology groups are: $$H^{0}=\Z\{v^{*}\},\quad H^{1}=\Z\{a^{*}+c^{*}, b^{*}+c^{*}\}, \quad H^{2}=\Z\{\bar{U}^{*}\}.$$


If $\alpha, \beta$ are generators for $H^1(T^2; \Z)$, then:
$$H^*(T^2; \Z) \cong \Lambda_\Z(\alpha, \beta)$$

## Graded Commutativity

The cohomology ring is not strictly commutative in general, but it satisfies a property called s*uper-commutativity* or *graded commutativity*.

> [!theorem] Graded Commutativity of the Cup Product
> If $R$ is a [[Ring, Field and Integral Domain#^178485|commutative ring]], then for any cohomology classes $x \in H^k(X;R)$ and $y \in H^l(X;R)$, the following relation holds:
> $$x \smallsmile y = (-1)^{kl} (y \smallsmile x)$$

> [!remark]+
> An interesting consequence of graded commutativity is that for any element $x$ of odd degree $k=2m+1$ in a graded commutative ring $A$, we have
> $$x \smallsmile x = (-1)^{k \cdot k} (x \smallsmile x) = (-1)^{(2m+1)^2} (x \smallsmile x) = - (x \smallsmile x)$$
> This implies $2(x \cup x) = 0$. If the ring $A$ has no 2-torsion (e.g., if the coefficient ring is $\Z$ or $\mathbb{Q}$), this means $x^2 = 0$.

<u><b>e.g.</b></u>  The cohomology rings of real and complex projective spaces are fundamental examples.
- The infinite complex projective space $\newcommand{\CP}{\mathbb{C}\mathrm{P}}\CP^\infty$ has a cohomology ring that is a polynomial ring on a single generator $x \in H^2(\CP^\infty; \Z)$: $$ H^*(\CP^\infty; \Z) \cong \Z[x].$$
- For the finite-dimensional complex projective space $\CP^{n}$, the ring is a truncated polynomial ring: $$H^*(\CP^{n};  \Z) \cong \Z[x] / (x^{n+1})$$with $x$ in degree $2$, i.e., $x$ is the generator of $H^{2}(\CP^{n}; \Z)$.
- The infinite real projective space $\newcommand{\RP}{\mathbb{R}\mathrm{P}}\RP^\infty$ with $\Z/2\Z$ coefficients also has a polynomial ring structure on a generator $x \in H^1(\RP^\infty; \Z/2\Z)$: $$ H^{*}(\RP^{\infty};  \Z/2) \cong  \Z/2[x]$$
- For the finite-dimensional real projective space $\RP^n$, the ring is aoh truncated polynomial ring: $$H^*(\RP^{n};  \Z/2) \cong \Z/2[x] / (x^{n+1})$$with $x$ in degree $1$.
- Moreover, the [[de Rham Cohomology#^b54c25|de Rham cohomology]] of a [[Manifolds and Atlases#^6ef2ef|smooth manifold]] with real coefficients is a canonical example of a cohomology ring (see [[Differential Forms#^143f20|here]]).

## Examples of Cohomology Rings

> [!definition] Exterior Algebra
> The *exterior algebra* on generators $x_1, \dots, x_n$ over a ring $R$, denoted $\Lambda_R(x_1, \dots, x_n)$, is an algebra where the generators anti-commute ($x_i x_j = -x_j x_i$) and each generator squares to zero ($x_i^2 = 0$). For example:
> - $\Lambda_R(x)$ is additively $R\{1, x\}$ with $x^2 = 0$.
> - $\Lambda_R(x, y)$ is additively $R\{1, x, y, xy\}$ with $x^2=0$, $y^2=0$, and $yx=-xy$.


$\quad$