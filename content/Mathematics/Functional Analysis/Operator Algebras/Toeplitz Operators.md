---
created: 2025-09-27
updated: 2025-09-27
tags:
  - toeplitz-operators
  - functional-analysis
  - c-star-algebra
completed: true
---
## Preliminaries and the Hardy Space

Let's establish the setting for our discussion.
- We use the *normalized arc length measure* $\newcommand{\d}{\mathrm{d}}\d\mu(\theta) = \frac{\d\theta}{2\pi}$ for $z = e^{i\theta}$.
- We denote the Lebesgue spaces as $L^p := L^p(S^{1}, \mu)$.
- The functions $e_n(z) = z^n$ for $\newcommand{\Z}{\mathbb{Z}}n \in \Z$ form an orthonormal basis for the [[Hilbert Spaces#^ae0212|Hilbert space]] $L^2(S^{1})$.
$\quad$

> [!definition] Hardy Space
> The *Hardy space* $H^2$ is the subspace of $L^2(S^{1},\mu)$ consisting of functions whose negative Fourier coefficients vanish:
> $$H^{2} = \left\{ f \in L^2(S^{1},\mu) : \hat{f}(n) = \langle f, e_n \rangle = 0 \text{ for all } n < 0 \right\}$$
> $H^{2}$ is a closed subspace of $L^2(S^{1})$ and thus is a [[Hilbert Spaces#^ae0212|Hilbert space]] in its own right. The set $\{e_n\}_{n \ge 0}$ forms an orthonormal basis for $H^2$.

## Multiplication and Toeplitz Operators

We can define operators on $L^2(S^{1},\mu)$ using functions from $L^\infty(S^{1},\mu)$.

> [!definition] Multiplication Operator
> For any $\varphi \in L^\infty(S^{1},\mu)$, the *multiplication operator* $M_{\varphi}\colon L^2(S^{1},\mu) \to L^2(S^{1},\mu)$ is defined by:
> $$M_{\varphi} f = \varphi f.$$
> 

> [!proposition]
> The multiplication operator is a [[Orthogonality and Bounded Linear Maps#^f95b62|bounded linear operator]] with the following properties:
> - $\|{M_{\varphi}}\| = \|{\varphi}\|_\infty$.
> - The map $\varphi \mapsto M_\varphi$ is a $*$-homomorphism onto its image. Specifically, $M_{\varphi}^{*} = M_{\overline{\varphi}}$, $M_{\varphi+\psi} = M_\varphi + M_\psi$, and $M_{\varphi\psi} = M_\varphi M_\psi$.
> - $M_\varphi$ is invertible if and only if $\varphi$ is invertible in $L^\infty(S^{1},\mu)$.
> $\quad$
> 

Using the multiplication operator and the projection onto the Hardy space, we can define the Toeplitz operator.

> [!definition] Toeplitz Operator
> Let $P\colon L^2(S^{1},\mu) \to H^2$ be the orthogonal projection. For any $\varphi \in L^\infty(S^{1})$, the *Toeplitz operator* $T_\varphi\colon H^2 \to H^2$ is defined by:
> $$T_\varphi f = P(M_\varphi f) = P(\varphi f) \quad \text{for } f \in H^2.$$ ^04cb08

> [!proposition] 
> We have the following properties of Toeplitz operators:
> - **Boundedness**: $T_\varphi$ is a bounded operator on $H^{2}$ with $\|{T_\varphi}\| \le \|{\varphi}\|_{\infty}$.
> - **Linearity**: The map $\varphi \mapsto T_\varphi$ is linear.
> - **Adjoint**: $(T_\varphi)^* = T_{\overline{\varphi}}$.
> - **Non-multiplicativity**: In general, $T_\varphi T_\psi \neq T_{\varphi\psi}$.
> - If $T_{\varphi}$ is invertible, then $\varphi$ is invertible, but $T_{\varphi}^{-1}\neq T_{\varphi^{-1}}$ in general.
> - The spectrum satisfies $\sigma(\varphi) \subseteq \sigma(T_{\varphi})$.
> $\quad$

The structure of Toeplitz operators becomes clear when we examine their matrix representation with respect to the orthonormal basis $\{e_n\}_{n \ge 0}$ of $H^2$.

> [!definition] Toeplitz Matrix
> For $m,n \ge 0$, the $(m,n)$-th matrix entry of $[T_\varphi]$ is:
> $$\newcommand{\dd}{\,\mathrm{d}} \langle T_\varphi e_n, e_m \rangle = \langle P(\varphi e_n), e_m \rangle = \langle \varphi e_n, e_m \rangle = \int_{S^{1}} \varphi(z) z^n \overline{z^m} \dd\lambda(z) = \hat{\varphi}(m-n). $$
> This means the matrix of $T_\varphi$ has constant entries along its diagonals. Such a matrix is called a *Toeplitz matrix*:
> $$ [T_\varphi] =\begin{pmatrix}\hat{\varphi}(0) & \hat{\varphi}(-1) & \hat{\varphi}(-2) & \cdots \\\hat{\varphi}(1) & \hat{\varphi}(0) & \hat{\varphi}(-1) & \cdots \\\hat{\varphi}(2) & \hat{\varphi}(1) & \hat{\varphi}(0) & \cdots \\ \vdots & \vdots & \vdots & \ddots \end{pmatrix}.$$

<u><b>e.g.</b></u>  Let $\varphi(z) = z$. Then $\hat{\varphi}(1) = 1$ and all other Fourier coefficients are zero. The operator $T_z = T_{e_1}$ is the unilateral shift operator $S$, which acts as $S(e_n) = e_{n+1}$. Its adjoint, $T_{\bar{z}} = T_{e_{-1}} = S^*$, is the backward shift.

The algebraic structure of Toeplitz operators is rich and subtle.

> [!theorem] Compactness Condition
> A Toeplitz operator $T_\varphi$ is [[Compact Operators#^67af67|compact]] if and only if its symbol $\varphi$ is identically zero.

> [!theorem] Commutator Property
> For continuous symbols $\varphi, \psi \in C(S^{1})$, the commutator is compact:
> $$ T_\varphi T_\psi - T_{\varphi\psi} \in K(H^2). $$
> This means that Toeplitz operators with continuous symbols commute modulo the compacts.

*Proof*  We can prove this by induction on the Fourier modes of the symbols.
1. **Base Case**: For $n=1$, we show that $T_\psi T_{e_{-1}} - T_{\psi e_{-1}}$ is a rank-one operator. For $f \in H^2$: $$ P(e_{-1}f) = e_{-1} f - \langle f, e_0 \rangle e_{-1} $$So, $T_{e_{-1}}f = e_{-1} f - \langle f, e_0 \rangle e_0$. Then $T_\psi T_{e_{-1}} f = T_\psi (e_{-1}f - \langle f, e_0 \rangle e_0) = T_{\psi e_{-1}}f - \langle f, e_0 \rangle T_\psi e_0$. The difference is the rank-one operator $f \mapsto -\langle f, e_0 \rangle (T_\psi e_0)$, which is compact.
2. **Inductive Step**: Assume $T_\psi T_{e_{-k}} - T_{\psi e_{-k}}$ is compact. Then we can write: $$ T_\psi T_{e_{-(k+1)}} - T_{\psi e_{-(k+1)}} = \underbrace{(T_\psi T_{e_{-k}} - T_{\psi e_{-k}})}_{\text{compact by induction}} T_{e_{-1}} + \underbrace{(T_{\psi e_{-k}} T_{e_{-1}} - T_{\psi e_{-(k+1)}})}_{\text{compact by base case}} $$    Since the compact operators form an ideal, the sum is compact. By linearity and density of trigonometric polynomials in $C(S^{1})$, the result holds for all $\varphi, \psi \in C(S^{1})$.

$\square$

## The Toeplitz Algebra

> [!definition] Toeplitz Algebra
> The *Toeplitz algebra*, denoted $\newcommand{\A}{\mathscr{T}(S^{1})}\A$, is the unital [[C*-Algebras#^e4fdc6|C\*-algebra]] generated by all Toeplitz operators with continuous symbols:
> $$ \mathscr{T}(S^{1}) := C^*\left(\{ T_\varphi : \varphi \in C(S^{1}) \}\right),$$with unit $T_{e_{0}}$.

A remarkable result is that this algebra contains all compact operators and is generated by a single element.

> [!proposition]
> The Toeplitz algebra contains the ideal of compact operators, $K(H^2) \subseteq \A$. Furthermore, the algebra is generated by the unilateral shift: $\A = C^*(S)$.

*Proof*  The operator $I - SS^* = T_1 - T_z T_{\bar{z}}$ is the projection onto the span of $e_0$. This is a rank-one operator in $\A$. From this, we can construct matrix units $E_{m,n} = S^m(I-SS^*)(S^*)^n$, which are also in $\A$. The linear span of these matrix units is the set of finite-rank operators. Since $\A$ is closed, it contains the closure of the finite-rank operators, which is precisely $K(H^2)$. $\square$

The structure of the Toeplitz algebra is completely characterized by the following fundamental theorem.

> [!theorem] Structure of the Toeplitz Algebra
> The C\*-algebra of compact operators $K(H^2)$ is a closed ideal in the Toeplitz algebra $\A$. The quotient algebra is $*$-isomorphic to the algebra of continuous functions on the circle, $C(S^{1})$. This relationship is summarized by the [[Abelian Categories#^0c5eb9|short exact sequence]]:
> $$ 0 \to K(H^2) \xrightarrow{i} \A \xrightarrow{\pi} C(S^{1}) \to 0. $$
> The symbol map $\pi\colon \A \to C(S^{1})$ is a $*$-homomorphism defined by $\pi(T_\varphi) = \varphi$, with $\ker(\pi) = K(H^2)$.

*Proof*  It suffices to prove that $\Phi\colon C(S^{1})\to \A/K(H^{2})$, $\varphi \mapsto T_{\varphi}+K(H^{2})$ is a $*$-isomorphism. $\Phi$ is linear and preserves adjoints. Since $T_{\varphi}T_{\psi}-T_{\varphi\psi}\in K(H^{2})$, we have that $\Phi$ is multiplicative, so $\Phi$ is a $*$-homomorphism. Since $\A=C^{*}(\{T_{\varphi}:\varphi\in C(S^{1})\})$, $\Phi$ is surjective. If $\Phi(T_{\varphi})=0$, then $T_{\varphi}$ is compact, so $\varphi=0$, hence $\Phi$ is injective. $\square$
