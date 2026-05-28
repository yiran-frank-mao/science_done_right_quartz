---
tags:
  - conformal-field-theory
  - virasoro-algebra
---
## Construction of the Verma Module

Recall that the [[Witt Algebra and Virasoro Algebra#^61c2ec|Virasoro algebra]] can be decomposed as $$\newcommand{\vir}{\mathfrak{vir}}\newcommand{\h}{\mathfrak{h}} \newcommand{\n}{\mathfrak{n}}\vir = \n^{+} \oplus \h \oplus \n^{-}.$$We can define a "universal" highest weight representation on it, called the *Verma module*.

> [!definition] Verma Module
> Let $\newcommand{\vir}{\mathfrak{vir}}\newcommand{\b}{\hat{\mathfrak{b}}}\b := \mathfrak{h} \oplus \mathfrak{n}^+$, and fix [[Complex Numbers#^a81924|complex numbers]] $c$ (the *central charge*) and $h$ (the *highest weight*).  
> Define a [$\b$-module](Universal%20Enveloping%20Algebra#^217488) $\mathbb{C}_{h,c}$, whose underlying vector space is $\mathbb{C}$, with action $$\kappa \cdot 1_{U(\b)} = c, \quad d_{0} \cdot 1_{U(\b)} = h, \quad x \cdot 1_{U(\b)} = 0 \quad \text{for all } x \in \mathfrak{n}^+.$$
> The *Verma module*, denoted $\newcommand{\ver}{\mathcal{V}_{h,c}}\ver$ or $M(h,c)$, is then the $\vir$-module defined by the [[Tensor Products of Modules#^431038|tensor product]]$$\ver := U(\vir) \otimes_{U(\b)} \mathbb{C}_{h,c},$$equipped with the left action $$y \cdot (u \otimes z) \;=\; (yu) \otimes z, \quad \text{for all } y \in U(\vir), u \in U(\vir), z \in \mathbb{C}_{h,c}.$$
> In other words, the Verma module is the [[Objects and Elements#^a7dd74|initial object]] in the [[Structure of Categories#^2f5c3a|category]] $\newcommand{\HW}{\mathsf{HW}_{h,c}^{\bullet}}\HW$ of pointed highest weight representations (i.e., objects are tuples $(V,v_{0})$ where $v_{0}\in V$ is a highest weight vector) of weight $(h,c)$.
> 

Suppose $V$ is a complex vector space. We call $(\pi, V)$ a *highest (lowest) weight representation* for $\vir$ of weight $(h,c)$ for complex numbers $h,c$ if the following conditions are satisfied:
- $\pi(L_{0})$ diagonalizes on $V$ with eigenvalues contained in $h+\Z_{\geq 0}$;
- Eigenspaces of $\pi(L_{0})$ are finite-dimensional, in particular, the $h$-eigenspace is one-dimensional;
$\quad$

> [!lemma]
> For any representation $V$ of a complex [[Lie Algebra#^5007ba|Lie algebra]] $\newcommand{\g}{\mathfrak{g}}\g$, with elements $\{d_{i}\}_{i\in\Z}$ satisfying $[d_{0},d_{n}]=\lambda(n)d_{n}$.  Let $V_{k}:=\ker(d_{0}-k)$. Then  $d_{n} V_{k} \subseteq V_{k+\lambda(n)}$ for all $n,k\in \C$.

*Proof*  For any $v\in V_{k}$, we have $$d_{0}(d_{n}v) = d_{n}d_{0}v + [d_{0},d_{n}]v = d_{n}(kv) + \lambda(n)d_{n}v = (k+\lambda(n))d_{n}v,$$so $d_{n}v \in V_{k+\lambda(n)}$. $\square$

> [!proposition]
> The Verma module is a highest weight representation for $\vir$ of weight $(h,c)$. It has a unique nonzero proper irreducible quotient $L(h,c)$.
> 

*Proof*  By the [[Universal Enveloping Algebra#^28e157|Poincaré–Birkhoff–Witt theorem]], $U(\vir)$ is spanned by ordered monomials. So we can express any $u\in U(\vir)$ as $u=u^{-}u^{0}u^{+}$ where $u^{-}$, $u^{0}$ and $u^{+}$ are basis of $U(\n^{-})$, $U(\h)$ and $U(\n^{+})$ respectively. If $u^{+}$ is nonempty (in terms of words), then $$u\otimes z=(u^{-}u^{0}u^{+})\otimes z=(u^{-}u^{0})\otimes (u^{+}z)=0.$$Therefore, it suffices to consider only the case when $u^{+}$ is empty, i.e., $u=u^{-}u^{0}$. 
By our construction of the Verma module, $v_{0}=1_{U(\vir)}\otimes 1_{\C}$ is an eigenvector of $L_{0}$ generating the $h$-eigenspace. Let us denote $V_{k}:=\ker(L_{0}-k)$. Note that $[L_{0},L_{n}]=-n L_{n}$, so by the above lemma, $$L_{n}V_{h} \subseteq V_{h-n}, \quad \text{for all } n\leq0.$$It follows that any $u^{-}u^{0} \otimes 1_{\C}$ is an eigenvector of $L_{0}$ with eigenvalue $h-m$ for some $m\leq0$. Hence, $L_{0}$ diagonalizes on $\ver$. Moreover, there are only finite ways to decompose $m$, so the dimension of each eigenspace is finite.
We now show that it has a unique nonzero proper irreducible quotient $L(h,c)$. In $\ver$, the eigenspace $V_{h}$ is one-dimensional. Hence every proper submodule cannot intersect with $V_{h}$. Note that the sum of any proper submodule is still proper, so it is possible to pick a unique maximal module $N$ by taking the sum of all proper submodules. Then $L(h,c):=\ver / N$ is the unique nonzero proper irreducible quotient.  $\square$

## The Shapovalov Form

> [!lemma]
> Let $\xi_{h,c}\colon U(\b)\to \C$ be the weight of $\C_{h,c}$ such that $$d_{0}\mapsto h, \quad, \kappa\mapsto c,\quad 1_{U(\vir)}\mapsto 1_{\C}.$$
> Then $\ver\cong U(\vir) / J$, where $J$ is the left ideal $U(\vir)\langle x-\xi_{h,c}(x) 1_{U(\vir)}\mid x\in U(\vir) \rangle$. ^8abb86

*Proof*  Define $\phi\colon U(\vir)\to \ver$ by $x\mapsto x \otimes 1_{\C}$, which is clearly [[Relations and Functions#^042daf|surjective]]. For any $b\in U(\b)$, $$\phi(ub)=ub\otimes 1_{\C} = u\otimes \xi_{h,c}(b)=\xi_{h,c}(b)(u\otimes 1_{\C})=\phi(\xi_{h,c}(b)u),$$therefore $ub-\xi_{h,c}(b)u\in \ker \phi$, so $J\subseteq \ker \phi$. Conversely, $J$ describes the only relation we imposed when constructing $\ver$ (this is the universal property of $\ver$), concluding that $\ker \phi = J$, so by the first isomorphism theorem, $\ver\cong U(\vir)/J$. $\square$

> [!proposition]
> The unique quotient $L(h,c)$ of $\ver$ admits a unique nonzero contravariant form up to scalar multiplication.
> 

*Proof*  Let us first construct a contravariant form on $U(\vir)$. By the [[Universal Enveloping Algebra#^28e157|Poincaré–Birkhoff–Witt theorem]], any element of $U(\vir)$ has either no factor from $\n^{-}$, or at least one factor from $\n^{-}$ appearing on the left, so we can write $U(\vir)=U(\b) \oplus \n^{-} U(\b)$. Denote $p\colon U(\vir)\to U(\b)$ and $q\colon U(\vir)\to \n^{-} U(\b)$ as the projections. We extend the anti-involution to $U(\vir)$ by $1_{U(\vir)}^{*}=1_{U(\vir)}$, and $(xy)^{*}=y^{*}x^{*}$.
We claim that $p$ is $\ast$-equivariant and multiplicative. The anti-involution fixes $\h$, and swaps $\n^{+}$ and $\n^{-}$, so $p(x^{*})=p(x)^{*}$ for all $x\in U(\vir)$. Using the triangular decomposition of $\vir$, we can write any $u\in U(\vir)$ as $u=u^{-}u^0u^{+}$. Then $$p(uv)=p(u^{-}u^{0}u^{+}v)=(p(u^{0}) + p(u^+))p(v)=p(u)p(v),$$so $p$ is multiplicative.
Now we can define $\langle \cdot,\cdot \rangle_{h,c}$ on $U(\vir)$ as $$\langle x,y \rangle_{h,c}:=\xi_{h,c}(p(y^{*}x)). $$It is anti-linear: $\langle x,\lambda y \rangle_{h,c}=\xi_{h,c}(p(\overline{\lambda}y^{*}x))=\overline{\lambda}\xi_{h,c}(p(y^{*}x))$. Moreover, $\langle y,x \rangle_{h,c} = \xi_{h,c}(p(x^{*}y)) = \overline{\xi_{h,c}(p(y^{*}x))} = \overline{\langle x,y \rangle_{h,c}}$, and it is contravariant by construction, so it is indeed a contravariant Hermitian form on $U(\vir)$.
The [[The Verma Module#^8abb86|above lemma]] shows that $\langle \cdot, \cdot \rangle_{h,c}$ can be pushed down to $\ver$ if it kills $J$. That is, for all $x,y\in U(\vir)$ and $z\in U(\b)$, we want to show that $$\langle x(z-\xi_{h,c}(z)), y \rangle_{h,c} = 0 = \langle x, y(z-\xi_{h,c}(z)) \rangle_{h,c}.$$Observe that $$\langle xz,y \rangle_{h,c}=\xi_{h,c}(p(y^{*}xz)) = \xi_{h,c}(p(y^{*}x)p(z))=\xi_{h,c}(p(y^*x))\xi_{h,c}(z)=\langle x,y \rangle_{h,c}\xi_{h,c}(z) , $$proving the first equality. The second equality holds similarly. Hence we can define a contravariant form on $\ver$ by $$\langle u\otimes 1_{\C}, v \otimes 1_{\C} \rangle_{\ver}:=\langle u,v \rangle_{h,c} . $$Now we show that $\langle \cdot,\cdot \rangle_{\ver}$ is unique up to a scalar. Let $v_{0}$ be a highest weight vector. Then for any $x,y\in U(\n^{-})$, a contravariant form $\langle \cdot,\cdot \rangle$ must satisfy $$\langle x\cdot v_{0},y\cdot v_{0} \rangle=\langle v_{0}, x^{*}y \cdot v_{0} \rangle = \langle v_{0}, p(x^{*}y)\cdot v_{0} \rangle + \langle v_{0}, q(x^{*}y)\cdot v_{0} \rangle = \langle v_{0}, \xi_{h,c}(p(x^{*}y)) v_{0} \rangle, $$which is completely determined by $\langle v_{0}, v_{0} \rangle$. $\square$

Hence, we are able to define a distinguished contravariant form on $\ver$:

> [!definition] Shapovalov Form
> The *Shapovalov form* on the Verma module $\ver$ is the unique contravariant Hermitian form $\langle \cdot, \cdot \rangle$ such that $\langle v_{0}, v_{0} \rangle = 1$ for $v_{0}=1_{U(\vir)}\otimes 1_{\C}$.
> 

## References

[Goodman and Wallach, Projective unitary positive-energy representations of $\mathrm{Diff}(S^1)$](https://linkinghub.elsevier.com/retrieve/pii/0022123685900904)