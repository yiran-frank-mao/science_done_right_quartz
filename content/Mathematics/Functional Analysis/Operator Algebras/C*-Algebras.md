---
updated: 2025-10-29
created: 2025-08-21
tags:
  - c-star-algebra
---
## C*-Algebras: Definitions and Examples

> [!definition] $\ast$-Algebra & $\ast$-Homomorphism
> A $\ast$-algebra $\newcommand{\A}{\mathcal{A}}\A$ is an [[Non-Commutative Rings#^2c3d07|algebra]] over $\newcommand{\C}{\mathbb{C}}\C$ equipped with an *involution* $\ast \colon \A \to \A$ such that $a^{**}=a$, $(ab)^{*}=b^{*}a^{*}$, $(a+b)^{*}=a^{*}+b^{*}$, $(\lambda a)^{*}=\bar{\lambda}a^{*}$ for all $a,b\in A$ and $\lambda\in \C$.
> A *$\ast$-homomorphism* between $\ast$-algebras is an algebra homomorphism also preserving the involution. A [[Relations and Functions#^042daf|bijective]] $*$-homomorphism is called a *$\ast$-isomorphism*. ^1a6445

> [!definition] Banach $\ast$-Algebra & C*-Algebra
> A *Banach $\ast$-algebra* is a [[Normed and Banach Algebras#^040470|Banach algebra]] $\mathcal{A}$ that is also a $*$-algebra, with the involution $*$ such that $\|a^*\| = \|a\|$ for all $a \in \mathcal{A}$. If $\mathcal{A}$ is unital, we also require $\|1_{\A}\| = 1$.
>A *C\*-algebra* is a Banach $*$-algebra $\mathcal{A}$ that satisfies the *C\*-identity*:
> $$ \|a^*a\| = \|a\|^2 \quad \text{for all } a \in \mathcal{A}.$$ ^e4fdc6

> [!remark]+
> If a C\*-algebra $\mathcal{A}$ has a unit $1$, then $\|1\| = 1$. This follows from the C\*-identity: $\|1^*1\| = \|1\|^2$. Since $1^*=1$, this gives $\|1\| = \|1\|^2$, and since $1 \neq 0$, we must have $\|1\|=1$.

<u><b>e.g.</b></u>
1. The [complex numbers $\mathbb{C}$](Complex%20Numbers#^a81924) with the involution being [[Complex Numbers#^50b19e|conjugation]] is a C\*-algebra.
2. For a locally compact Hausdorff space $X$, the algebra $C_0(X)$ of continuous complex-valued functions vanishing at infinity is a C\*-algebra with pointwise operations and the involution $f^*(x) = \overline{f(x)}$. The norm is the supremum norm.
3. For a Hilbert space $\H$, the algebra $B(\H)$ of bounded linear operators on $H$ is a unital C\*-algebra, where the involution is the [[Adjoints and Riesz Representation Theorem#^671f74|operator adjoint]].
$\quad$
 
> [!definition] $\ast$-Subalgebra & C*-Subalgebra
> Let $\mathcal{A}$ be a $\ast$-algebra. A $*$-subalgebra $\mathcal{B}$ of $\mathcal{A}$ is a *$\ast$-subalgebra* if it is closed under the involution, i.e., $b^* \in \mathcal{B}$ whenever $b \in \mathcal{B}$.
> Similarly, a *C\*-subalgebra* of a C\*-algebra $\mathcal{A}$ is a norm-closed $\ast$-subalgebra of $\mathcal{A}$.

> [!definition] Special Elements
> Let $\mathcal{A}$ be a $*$-algebra. An element $a \in \mathcal{A}$ is called:
> - *Self-adjoint* (or Hermitian) if $a = a^*$
> - *Normal* if $a^*a = aa^*$
> - A *projection* if $p = p^* = p^2$
>
> If $\mathcal{A}$ is unital, an element $u \in \mathcal{A}$ is called:
> - *Unitary* if $u^*u = uu^* = 1_{\A}$
> - An *isometry* if $u^*u = 1_{\A}$ 
>  $\quad$ ^1e36a9

## Fundamental Properties

> [!proposition] Properties of Unital C*-Algebras
> Let $\mathcal{A}$ be a unital C\*-algebra.
> 1. If $a \in \mathcal{A}$ is invertible, then $a^*$ is invertible and $(a^*)^{-1} = (a^{-1})^*$.
> 2. For any $a \in \mathcal{A}$, the spectrum of its adjoint is given by $\sigma(a^*) = \{\bar{\lambda} \mid \lambda \in \sigma(a)\}$.
> 3. Any $a \in \mathcal{A}$ can be uniquely written as $a = \text{Re}(a) + i\,\text{Im}(a)$, where $\text{Re}(a) = \frac{a+a^*}{2}$ and $\text{Im}(a) = \frac{a-a^*}{2i}$ are self-adjoint.
> 4. If $a$ is self-adjoint ($a=a^*$), then its spectrum $\sigma(a)$ is a subset of the real numbers $\mathbb{R}$, and $r(a) = \|a\|$.
> 5. If $u$ is unitary, then $\|u\|=1$ and its spectrum $\sigma(u)$ is a subset of the unit circle $\{z \in \mathbb{C} \mid |z|=1\}$.
> $\quad$

> [!corollary] Uniqueness of the C*-Norm
> There is at most one norm on a $\ast$-algebra that makes it a C\*-algebra.

*Proof*  Suppose $\|\cdot\|_1$ and $\|\cdot\|_2$ are two norms on a $\ast$-algebra $\mathcal{A}$ that both satisfy the C\*-identity. For any $a \in \mathcal{A}$, the element $a^*a$ is self-adjoint. For any self-adjoint element $h$, its norm is equal to its spectral radius, $\|h\| = r(h)$. Since the spectral radius depends only on the algebraic structure, it is independent of the norm. Thus, for any $a \in \mathcal{A}$: $$ \|a\|_1^2 = \|a^*a\|_1 = r(a^*a) = \|a^*a\|_2 = \|a\|_2^2 $$This implies $\|a\|_1 = \|a\|_2$. $\square$

## Unitarization

If a C\*-algebra $\mathcal{A}$ does not have a unit, it's possible to embed it into a larger, unital C\*-algebra.

> [!definition] Unitarization
> Let $\mathcal{A}$ be a non-unital Banach $*$-algebra. The *unitarization* of $\mathcal{A}$ is the algebra $\tilde{\mathcal{A}} = \mathcal{A} \times \mathbb{C}$, with operations:
> - **Addition**: $(a, \lambda) + (b, \mu) = (a+b, \lambda+\mu)$
> - **Multiplication**: $(a, \lambda)(b, \mu) = (ab + \mu a + \lambda b, \lambda\mu)$
> - **Involution**: $(a, \lambda)^* = (a^*, \bar{\lambda})$
>
> $\tilde{\mathcal{A}}$ is a unital \*-algebra with unit $(0, 1)$.

> [!theorem] The C*-Norm on the Unitization
> Let $\mathcal{A}$ be a non-unital C\*-algebra. The norm on its unitization $\tilde{\mathcal{A}}$ defined by
> $$ \|(a, \lambda)\|_{\tilde{\mathcal{A}}} = \sup\{\|ax + \lambda x\| : x \in \mathcal{A}, \|x\| \le 1\} $$
> makes $\tilde{\mathcal{A}}$ a C\*-algebra.
>

*Proof*  This norm is the operator norm of the left multiplication operator $L_a + \lambda I$ acting on $\mathcal{A}$. It can be shown that this norm is complete and satisfies the C\*-identity. The key step in proving the C\*-identity is showing $\|(a,\lambda)\|^2 \le \|(a,\lambda)^*(a,\lambda)\|$. $\square$

## Homomorphisms

> [!theorem] $\ast$-Homomorphisms are Contractive
> Any $*$-homomorphism $\varphi\colon \mathcal{A} \to \mathcal{B}$ between C\*-algebras is a contraction, i.e., $\|\varphi\| \le 1$.
>

*Proof*  For any self-adjoint element $a=a^* \in \mathcal{A}$, we have $\sigma(\varphi(a)) \subseteq \sigma(a)$. This implies $r(\varphi(a)) \le r(a)$. For a C\*-algebra, the norm of a self-adjoint element equals its spectral radius. So, $\|\varphi(a)\| \le \|a\|$. For a general element $a$, we have: $$ \|\varphi(a)\|^2 = \|\varphi(a)^*\varphi(a)\| = \|\varphi(a^*a)\| \le \|a^*a\| = \|a\|^2 $$Thus, $\|\varphi(a)\| \le \|a\|$. $\square$

> [!corollary] $*$-Isomorphisms are Isometries
> Any $*$-isomorphism between C\*-algebras is an isometry.

> [!proposition] Characters on Abelian C*-Algebras
> Any character (non-zero multiplicative linear functional) $\tau$ on an abelian C\*-algebra $\mathcal{A}$ is a $*$-homomorphism.

*Proof*  WLOG, assume $\mathcal{A}$ is unital. Let $h = h^*$ be a self-adjoint element. One can show that $\tau(h)$ must be a real number. For an arbitrary $a \in \mathcal{A}$, write it as $a = \text{Re}(a) + i\,\text{Im}(a)$. Then: $$ \tau(a^*) = \tau(\text{Re}(a) - i\,\text{Im}(a)) = \tau(\text{Re}(a)) - i\tau(\text{Im}(a)) $$Since $\tau(\text{Re}(a))$ and $\tau(\text{Im}(a))$ are real, this is equal to $\overline{\tau(\text{Re}(a)) + i\tau(\text{Im}(a))} = \overline{\tau(a)}$. $\square$

> [!theorem] Spectral Permanence
> Let $\mathcal{A}$ be a unital C\*-algebra and let $\mathcal{B}$ be a C\*-subalgebra of $\mathcal{A}$ containing the unit of $\mathcal{A}$. Then for any element $b \in \mathcal{B}$, its spectrum in $\mathcal{B}$ is the same as its spectrum in $\mathcal{A}$.
> $$ \sigma_{\mathcal{B}}(b) = \sigma_{\mathcal{A}}(b).$$
>

*Proof*  The inclusion $\sigma_{\mathcal{A}}(b) \subseteq \sigma_{\mathcal{B}}(b)$ is always true. To prove the other direction, one shows that if $b$ is invertible in $\mathcal{A}$, it must also be invertible in $\mathcal{B}$. This is first proven for self-adjoint elements, leveraging the fact that for such elements $h$, $\sigma_{\mathcal{B}}(h) \subseteq \mathbb{R}$, which implies that $\mathbb{C} \setminus \sigma_{\mathcal{B}}(h)$ is connected. Since the spectra must agree for self-adjoint elements, one can extend the argument to arbitrary elements $b \in \mathcal{B}$ by considering the self-adjoint element $b^*b$. $\square$