To state the main theorem, we first need the (complex version) Stone-Weierstrass theorem:
## The Stone-Weierstrass Theorem

> [!theorem] Stone-Weierstrass Theorem (Real Version)
> Let $X$ be a locally compact Hausdorff space. Let $C_0(X, \mathbb{R})$ be the algebra of all continuous real-valued functions on $X$ vanishing at infinity, equipped with the sup-norm.
> Assume that $\mathcal{B}$ is a real subalgebra of $C_0(X, \mathbb{R})$ such that:
> 1.  $\mathcal{B}$ **separates the points** of $X$ (i.e., for any $x, y \in X$ with $x \neq y$, there exists an $f \in \mathcal{B}$ such that $f(x) \neq f(y)$).
> 2.  $\mathcal{B}$ is **non-vanishing** (i.e., for any $x \in X$, there exists an $f \in \mathcal{B}$ such that $f(x) \neq 0$).
>
> Then, $\mathcal{B}$ is [[Closure, Interior and Boundary#^b560bf|dense]] in $C_0(X, \mathbb{R})$.

*Proof*  The core of the proof is to show that the closure of $\mathcal{B}$, denoted $\overline{\mathcal{B}}$, is a sublattice. That is, if $f, g \in \overline{\mathcal{B}}$, then $\max\{f, g\}$ and $\min\{f, g\}$ are also in $\overline{\mathcal{B}}$.
**Step 1: For any distinct $x, y \in X$, there exists $f \in \mathcal{B}$ such that $f(x) \neq 0$ and $f(y) \neq 0$.**
This extends the initial conditions. By the separation and non-vanishing properties, we can construct a function $f_t \in \mathcal{B}$ that is non-zero at both $x$ and $y$.
**Step 2: For any distinct $x, y \in X$ and any $a, b \in \mathbb{R}$, there exists an $f \in \mathcal{B}$ such that $f(x) = a$ and $f(y) = b$.**
Using Step 1, we can find functions $f_1 \in \mathcal{B}$ that separate $x$ and $y$. We can then solve a system of linear equations to find coefficients $\alpha, \beta$ such that $f = \alpha f_1 + \beta f_1^2$ satisfies the conditions. Since $\mathcal{B}$ is an algebra, $f \in \mathcal{B}$.
$$
\begin{pmatrix} f_1(x) & f_1(x)^2 \\ f_1(y) & f_1(y)^2 \end{pmatrix} \begin{pmatrix} \alpha \\ \beta \end{pmatrix} = \begin{pmatrix} a \\ b \end{pmatrix}
$$
The determinant is $f_1(x)f_1(y)(f_1(y)-f_1(x))$, which is non-zero, guaranteeing a unique solution.
**Step 3: If $f \in \overline{\mathcal{B}}$, then $|f| \in \overline{\mathcal{B}}$.**
The function $|t|$ can be uniformly approximated by a sequence of polynomials $\{p_n(t)\}$ on any closed interval $[-M, M]$. We can ensure $p_n(0)=0$. Since $f$ is bounded on the compact space $X$, its range is contained in some $[-M, M]$. The function $p_n \circ f$ is in $\mathcal{B}$ for any polynomial $p_n$ (since $\mathcal{B}$ is an algebra). As $p_n \to |t|$ uniformly on $[-M, M]$, the sequence of functions $p_n \circ f$ converges uniformly to $|f|$. Since $\overline{\mathcal{B}}$ is closed, the limit $|f|$ must be in $\overline{\mathcal{B}}$. From this, it follows that $\overline{\mathcal{B}}$ is a sublattice, because: $$\begin{aligned}\max\{f, g\} = \frac{f+g+|f-g|}{2} \in \overline{\mathcal{B}},\\ \min\{f, g\} = \frac{f+g-|f-g|}{2} \in \overline{\mathcal{B}}.\end{aligned}$$
**Step 4: $\overline{\mathcal{B}} = C_0(X, \mathbb{R})$.**
Let $h \in C_0(X, \mathbb{R})$ and $\epsilon > 0$. We want to construct an $f \in \mathcal{B}$ such that $||f-h||_\infty < \epsilon$.
For any pair of points $x, y \in X$, by Step 2, we can find a function $f_{x,y} \in \mathcal{B}$ such that $f_{x,y}(x) = h(x)$ and $f_{x,y}(y) = h(y)$.
1.  Fix $y \in X$. For each $x \in X$, define the open set $U_x = \{z \in X \mid f_{x,y}(z) < h(z) + \epsilon\}$. Since $X$ is compact, the open cover $\{U_x\}_{x \in X}$ has a finite subcover $\{U_{x_1}, \dots, U_{x_n}\}$. Define $f_y = \max\{f_{x_1,y}, \dots, f_{x_n,y}\}$. By Step 3, $f_y \in \overline{\mathcal{B}}$. This function satisfies $f_y(z) < h(z) + \epsilon$ for all $z \in X$ and $f_y(y) = h(y)$.
2.  Now, for each $y \in X$, define the open set $V_y = \{z \in X \mid f_y(z) > h(z) - \epsilon\}$. Again, this forms an open cover of $X$, so we can find a finite subcover $\{V_{y_1}, \dots, V_{y_k}\}$. Define $f = \min\{f_{y_1}, \dots, f_{y_k}\}$. This $f$ is in $\overline{\mathcal{B}}$.

By construction, $f_y > h - \epsilon$ near $y$. The final function $f$ satisfies $f(z) > h(z) - \epsilon$ for all $z \in X$. Also, since each $f_{y_j}(z) < h(z) + \epsilon$, their minimum $f$ also satisfies $f(z) < h(z) + \epsilon$.
Therefore, we have $h(z) - \epsilon < f(z) < h(z) + \epsilon$ for all $z \in X$, which means $||f-h||_\infty < \epsilon$. $\square$

> [!theorem] Stone-Weierstrass Theorem (Complex Version)
> Let $X$ be a locally compact Hausdorff space, and let $C_0(X, \mathbb{C})$ be the algebra of complex-valued continuous functions on $X$ vanishing at infinity. Let $\mathcal{B}$ be a complex subalgebra of $C_0(X, \mathbb{C})$ satisfying:
> 1. $\mathcal{B}$ separates the points of $X$.
> 2. $\mathcal{B}$ is non-vanishing.
> 3. $\mathcal{B}$ is a $\ast$-subalgebra (i.e., if $f \in \mathcal{B}$, then its complex conjugate $\overline{f}$ is also in $\mathcal{B}$).
>
> Then, $\mathcal{B}$ is [[Closure, Interior and Boundary#^b560bf|dense]] in $C_0(X, \mathbb{C})$ with respect to the supremum norm. ^2419f7

*Proof*  Let $\mathcal{B}_{\mathbb{R}} = \{ f \in \mathcal{B} \mid f = \overline{f} \}$ be the set of real-valued functions in $\mathcal{B}$. $\mathcal{B}_{\mathbb{R}}$ is a real subalgebra of $C_0(X, \mathbb{R})$. For any $f \in \mathcal{B}$, we can write $\operatorname{Re}(f) = \frac{f+\overline{f}}{2}$ and $\operatorname{Im}(f) = \frac{f-\overline{f}}{2i}$. Since $\mathcal{B}$ is a $\ast$-subalgebra, both $\operatorname{Re}(f)$ and $\operatorname{Im}(f)$ are in $\mathcal{B}_{\mathbb{R}}$. $\mathcal{B}_{\mathbb{R}}$ separates points and is non-vanishing. Thus, by the real version of the Stone-Weierstrass theorem, $\overline{\mathcal{B}_{\mathbb{R}}} = C_0(X, \mathbb{R})$. Since any function $h \in C_0(X, \mathbb{C})$ can be written as $h = \operatorname{Re}(h) + i\operatorname{Im}(h)$, and both $\operatorname{Re}(h)$ and $\operatorname{Im}(h)$ can be approximated by functions in $\mathcal{B}_{\mathbb{R}}$, it follows that $\mathcal{B}$ is dense in $C_0(X, \mathbb{C})$. Specifically, $\overline{\mathcal{B}} = \overline{\mathcal{B}_{\mathbb{R}}} + i\overline{\mathcal{B}_{\mathbb{R}}} = C_0(X, \mathbb{R}) + iC_0(X, \mathbb{R}) = C_0(X, \mathbb{C})$. $\square$

> [!remark]
> The condition of being a $\ast$-subalgebra is essential. For example, consider the disk algebra $A(\mathbb{D})$, the set of functions holomorphic on the open unit disk $\mathbb{D}$ and continuous on its closure. Viewed as a subalgebra of $C(\partial \mathbb{D})$, it separates points and is non-vanishing, but it is not a $\ast$-subalgebra and is not dense in $C(\partial \mathbb{D})$.

## The Gelfand Theorem

This fundamental theorem provides a concrete representation for any abstract abelian C\*-algebra.

> [!proposition] Existence of Characters
> Any non-zero commutative C\*-algebra $\mathcal{A}$ has a character.

*Proof*  If $\mathcal{A}$ is unital, this is a standard result from Banach algebra theory. If $\mathcal{A}$ is non-unital, since $\mathcal{A} \neq \{0\}$, there exists $a \in \mathcal{A}$ with $a \neq 0$. For an abelian C\*-algebra, $\|a\| = r(a)$. The spectral radius is given by $r(a) = \sup\{|\tau(a)| : \tau \in \Omega(\tilde{\mathcal{A}})\}$, where $\Omega(\tilde{\mathcal{A}})$ is the character space of the unitization. Since $\|a\| \neq 0$, there must be a character $\tau$ on $\tilde{\mathcal{A}}$ such that $\tau(a) \neq 0$. The restriction of this character to $\mathcal{A}$ is the required non-zero character on $\mathcal{A}$. $\square$

> [!theorem] Gelfand Theorem for Commutative C*-Algebras
> If $\mathcal{A}$ is a commutative C\*-algebra, let $\Omega(\mathcal{A})$ be its [[Gelfand Representation#^6c5c63|character space]] equipped with the weak-$\ast$ topology. The [[Gelfand Representation#^c27815|Gelfand representation]]
> $$ \Gamma\colon \mathcal{A} \to C_0(\Omega(\mathcal{A})) $$
> defined by $\Gamma(a)(\tau) = \tau(a)$ is an isometric $\ast$-isomorphism. ^7594b2

*Proof*
-  **$\ast$-Homomorphism**: Since characters are \*-homomorphisms, for any $\tau \in \Omega(\mathcal{A})$, we have $\Gamma(a^*)(\tau) = \tau(a^*) = \overline{\tau(a)} = \overline{\Gamma(a)(\tau)}$. Thus $\Gamma(a^*) = \overline{\Gamma(a)}$, making $\Gamma$ a \*-homomorphism.
-  **Isometry**: For any $a \in \mathcal{A}$, the element $a^*a$ is self-adjoint. $$ \|\Gamma(a)\|^2 = \|\overline{\Gamma(a)}\Gamma(a)\| = \|\Gamma(a^*)\Gamma(a)\| = \|\Gamma(a^*a)\| = r(a^*a) = \|a^*a\| = \|a\|^2 $$So $\|\Gamma(a)\| = \|a\|$, which means $\Gamma$ is an isometry and thus injective.
-  **Surjectivity**: The image $\Gamma(\mathcal{A})$ is a $\ast$-subalgebra of $C_0(\Omega(\mathcal{A}))$. It can be shown to separate points and be non-vanishing. By the Stone-Weierstrass theorem, $\Gamma(\mathcal{A})$ is dense in $C_0(\Omega(\mathcal{A}))$. Since $\Gamma$ is an isometry and $\mathcal{A}$ is a Banach space (complete), its image $\Gamma(\mathcal{A})$ is also complete and therefore closed in $C_0(\Omega(\mathcal{A}))$. A dense and closed subspace must be the whole space, so $\Gamma(\mathcal{A}) = C_0(\Omega(\mathcal{A}))$. Thus $\Gamma$ is surjective. 

$\square$

## Continuous Functional Calculus in C\*-Algebras

The Gelfand theorem allows us to "do calculus" with elements of a C\*-algebra by applying continuous functions to them.

> [!lemma]
> Suppose $\mathcal{A}$ is a unital commutative C\*-algebra. Let $a\in\mathcal{A}$ be normal, $\Omega:=\Omega(C^{*}(1,a))$, and $\Gamma\colon C^{*}(1,a) \to C_{0}(\Omega)$ be its Gelfand representation. Then the map $\Omega\to \C$, $\tau\mapsto \tau(a)$ is a homeomorphism onto the spectrum $\sigma(a)$ of $a$.

*Proof*  Assume $\tau_{1}(a)=\tau_{2}(a)$. Because $C^{*}(1,a)$ is generated by $1$ and $a$, $\tau_{1}$ has to agree with $\tau_{2}$ on the whole $C^{*}(1,a)$, thus the mapping is [[Relations and Functions#^042daf|injective]]. It is continuous by the definition of the weak\* topology on $\Omega$. Moreover, $\Omega$ is [[Compactness of Topological Space#^da2511|compact]] [[Separation and Hausdorff Spaces#^f7bcc8|Hausdorff]] and $$\{\tau(a): \tau\in\Omega\}=\sigma_{C^{*}(1,a)}(a)=\sigma_{\mathcal{A}}(a),$$hence it is a [[Isometries and Homeomorphisms#^85034b|homeomorphism]]. $\square$

> [!lemma]
> Suppose $X$ and $Y$ are [[Compactness of Topological Space#^da2511|compact]] [[Separation and Hausdorff Spaces#^f7bcc8|Hausdorff]] spaces, and $\psi\colon X\to Y$ is a homeomorphism. Then the pullback $\psi^{*}\colon C(Y) \to C(X)$, $f\mapsto f\circ \psi$ is an isometric $\ast$-isomorphism.

> [!theorem] Continuous Functional Calculus
> Let $\mathcal{A}$ be a unital C\*-algebra and let $a \in \mathcal{A}$ be a [[C*-Algebras#^1e36a9|normal element]] . Let $\sigma(a)$ be the spectrum of $a$. There exists a unique unital $\ast$-homomorphism
> $$ \theta_a\colon C(\sigma(a)) \to \mathcal{A} $$
> such that $\theta_a(z) = a$, where $z$ is the identity function $z(\lambda) = \lambda$ on $\sigma(a)$.
> Moreover, $\theta_a$ is an isometry from $C(\sigma(a))$ onto the C\*-subalgebra generated by $1$ and $a$, denoted $C^*(1, a)$.
> Therefore, we are allowed to write $f(a):=\theta_{a}(f)$ for any continuous function $f \in C(\sigma(a))$. ^b9e7cb

*Proof*  We establish a chain of isomorphisms to show existence. Let $\Omega = \Omega(C^*(1,a))$ be the spectrum of the commutative C\*-algebra generated by $1$ and $a$. We have the following facts:
- The Gelfand representation $\Gamma\colon C^*(1,a) \to C(\Omega)$ is an isometric $*$-isomorphism.
* There is a homeomorphism $\psi\colon \Omega \to \sigma(a)$ given by $\psi(\tau) = \tau(a)$.
* This homeomorphism induces an isometric $*$-isomorphism $\psi^*: C(\sigma(a)) \to C(\Omega)$ where $\psi^*(f) = f \circ \psi$.

We define $\theta_a = \Gamma^{-1} \circ \psi^*$. This is an isometric $*$-isomorphism from $C(\sigma(a))$ onto $C^*(1,a)$, and one can check that $\theta_a(z) = a$.
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/cont_functional_calculus.svg" alt="cont_functional_calculus" style="width:40%;"/>
We now prove the uniqueness. Suppose $\theta_1$ and $\theta_2$ are two such unital $\ast$-homomorphisms. They both map the constant function $1$ to the identity element $1_{\A} \in \mathcal{A}$, and they both map the identity function $z$ to $a$. The set $\{1, z\}$ generates the algebra of all polynomials in $z$. By the [[The Gelfand Theorem for Commutative C*-Algebras#^2419f7|Stone-Weierstrass theorem]], the algebra of polynomials in $z$ and $\overline{z}$ is dense in $C(\sigma(a))$. Since $\theta_1$ and $\theta_2$ are continuous and agree on a dense subset, they must be equal on all of $C(\sigma(a))$. $\square$

<u><b>e.g.</b></u>  If $f$ is a polynomial, $f(a)$ is defined algebraically. For a general continuous function $f$, we can find a sequence of polynomials $\{p_n\}$ that converges uniformly to $f$ on $\sigma(a)$, and we define $f(a) := \lim_{n\to\infty} p_n(a)$.
1. If $A = C(X)$ for a compact Hausdorff space $X$, then for any $a \in A$ and $f \in C(\sigma(a))$, the element $f(a)$ is the composition of functions: $f(a)(x) = f(a(x))$.
2. If $A = M_n(\mathbb{C})$ and $a$ is a self-adjoint matrix, we can diagonalize it with a unitary matrix $U$ such that $a = UDU^*$, where $D$ is a diagonal matrix of eigenvalues. Then for any $f \in C(\sigma(a))$, $f(a) = Uf(D)U^*$, where $f(D)$ is the diagonal matrix obtained by applying $f$ to each diagonal entry of $D$.
$\quad$

> [!theorem] Spectral Mapping Theorem
> Let $a$ be a [[C*-Algebras#^1e36a9|normal element]] in a unital C\*-algebra $\mathcal{A}$. For any $f \in C(\sigma(a))$, we have:
> $$ \sigma(f(a)) = f(\sigma(a)) = \{f(\lambda) \mid \lambda \in \sigma(a)\}. $$
> Furthermore, $f(a)$ is normal, and for any $g \in C(\sigma(f(a)))$, we have that $g(f(a)) = (g \circ f)(a)$.

*Proof*  The spectrum of $f(a)$ within the full algebra $\mathcal{A}$ is the same as its spectrum within the subalgebra $C^*(1, a)$. Using the Gelfand representation for $C^*(1,a)$, the spectrum of an element is the range of its Gelfand transform: $$\sigma(f(a)) = \{ \tau(f(a)) \mid \tau \in \Omega(C^*(1, a)) \}.$$The $*$-homomorphism property means $\tau(f(a)) = f(\tau(a))$. So, $\sigma(f(a)) = \{ f(\tau(a)) \mid \tau \in \Omega(C^*(1, a)) \}$. Since the map $\tau \mapsto \tau(a)$ is a homeomorphism from $\Omega(C^*(1, a))$ onto $\sigma(a)$, the set of values $\{\tau(a)\}$ is precisely $\sigma(a)$. Therefore, $\sigma(f(a)) = \{ f(\lambda) \mid \lambda \in \sigma(a) \}$. $\square$