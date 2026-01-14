## The Full Crossed Product Algebra

> [!definition] The Algebra of Test Functions
> Let $\newcommand{\A}{\mathcal{A}}\newcommand{\C}{\mathbb{C}}\newcommand{\Z}{\mathbb{Z}}\newcommand{\T}{S^{1}}(\A, G, \alpha)$ be a [[C*-Dynamical Systems#^c9bf4c|C*-dynamical system]]. We define the [[Vector Spaces#^f4b63e|vector space]] of $\A$-valued functions on $G$ with finite support as: $$C_c(G,\A) := \{h: G \to \A \mid h \text{ has finite support}\}$$
> We equip $C_c(G,\A)$ with a convolution product and an involution, making it a $\ast$-algebra.
> - **Convolution:** For $h, k \in C_c(G, \A)$, the product $h*k$ is defined as: $$(h*k)(t) = \sum_{s \in G} h(s) \alpha_s(k(s^{-1}t)) \quad \text{for } t \in G$$
> - **Involution:** The involution $h^*$ is defined as: $$h^*(t) = \alpha_t(h(t^{-1})^*)$$
>
> An element $h \in C_c(G,\A)$ can be formally written as a sum $h = \sum_{t \in G} h(t)\delta_t$, where $\delta_t$ is the function that is $1_\A$ at $t$ and $0$ elsewhere.

> [!definition] Integrated Form of a Covariant Representation
> Given a [[C*-Dynamical Systems#^ff0e48|covariant representation]] $(\pi, U)$ of $(\A, G, \alpha)$ on a [[Hilbert Spaces#^ae0212|Hilbert space]] $\mathcal{H}$, we can define a map $\pi \times U\colon  C_c(G,\A) \to B(\mathcal{H})$ by: $$(\pi \times U)(h) = \sum_{t \in G} \pi(h(t))U_t \in B(\mathcal{H})$$

> [!proposition]
> The map $\pi \times U$ is a $*$-representation of the algebra $C_c(G,\A)$.

> [!definition] The Full Crossed Product
> We define the universal norm on $C_c(G,\A)$ as: $$||h||_u = \sup_{(\pi, U)} ||(\pi \times U)(h)||$$where the supremum is taken over all covariant representations $(\pi, U)$ of $(\A,G,\alpha)$.  This norm is bounded by the $L^1$-norm:$$||h||_u \le \sum_{t \in G} ||\pi(h(t))U_t|| \le \sum_{t \in G} ||h(t)||_\A = ||h||_{L^1(G,\A)}$$
>
> The *(full) crossed product C\*-algebra*, denoted $\A \rtimes_{\alpha} G$, is the completion of $C_c(G,\A)$ with respect to the universal norm $|| \cdot ||_u$.

## Universal Property

> [!proposition] Canonical Maps
> There exist canonical maps from $\A$ and $G$ into the (multiplier algebra of) $\A \rtimes_\alpha G$.
> 1. The map $i_\A: \A \to \A \rtimes_\alpha G$ defined by $i_\A(a) = a\delta_e$ is an isometric *-homomorphism.
> 2. The map $i_G: G \to \A \rtimes_\alpha G$ defined by $i_G(s) = 1_\A\delta_s$ is an injective group homomorphism into the group of unitaries.

*Proof Sketch*  For the isometry of $i_\A$, we first note that for any covariant representation $(\pi, U)$: $$(\pi \times U)(i_\A(a)) = (\pi \times U)(a\delta_e) = \pi(a)U_e = \pi(a)$$This implies $||i_\A(a)||_u = \sup ||(\pi \times U)(i_\A(a))|| = \sup ||\pi(a)|| \le ||a||$.
To show the reverse inequality, one can construct a specific covariant representation using the universal representation $\pi_0$ of $\A$ and the left regular representation of $G$ on $\ell^2(G, \mathcal{H})$.  For this representation, one finds that $||(\pi_0 \times U)(i_\A(a))|| = ||a||$.  Therefore, $||i_\A(a)||_u = ||a||$.
For the map $i_G$:
- It is a homomorphism since $i_G(st) = 1_\A\delta_{st}$ and $(i_G(s))(i_G(t)) = (1_\A\delta_s)*(1_\A\delta_t) = 1_\A\delta_{st}$.
- To show injectivity, we can use the same covariant representation $(\pi_0, U)$ on $\ell^2(G, \mathcal{H})$. We have $(\pi_0 \times U)(i_G(s)) = \pi_0(1_\A)U_s = U_s$.  Since the left regular representation $s \mapsto U_s$ is injective, $i_G$ must also be injective.
$\square$

> [!theorem] Universal Property of the Crossed Product
> For every covariant representation $(\pi, U)$ of $(\A,G,\alpha)$ on $B(\mathcal{H})$, there exists a unique $*$-representation of the crossed product, which we also denote by $\pi \times U$, from $\A \rtimes_\alpha G$ to $B(\mathcal{H})$ such that:
> - $(\pi \times U)(i_\A(a)) = \pi(a)$ for all $a \in \A$.
> - $(\pi \times U)(i_G(s)) = U_s$ for all $s \in G$.
>
> Conversely, every non-degenerate representation of $\A \rtimes_\alpha G$ arises in this way from a covariant representation of $(\A,G,\alpha)$.

## The Reduced Crossed Product

> [!warning] Reduced vs. Full
> We can also define a **reduced norm** by taking the supremum only over *regular* covariant representations: $$||h||_r = \sup_{(\pi, U) \text{ regular}} ||(\pi \times U)(h)||$$
> The completion of $C_c(G,\A)$ with respect to this norm is the **reduced crossed product**, denoted $\A \rtimes_{\alpha, r} G$.
>
> In general, there is a surjective *-homomorphism $\A \rtimes_\alpha G \to \A \rtimes_{\alpha,r} G$.  However, this map may not be injective.

## Examples

### Trivial Group Action
If the group is trivial, $G=\{e\}$, and the action is the identity, then $\A \rtimes_{id} \{e\} \cong \A$.

### Group C*-Algebras
Let the C*-algebra be the complex numbers, $\A = \C$, and the action be the trivial action, $\alpha = id$.  The crossed product $\C \rtimes_{id} G$ is called the **group C*-algebra** of G, denoted $C^*(G)$.
- In this case, $C_c(G, \C)$ is just the space of complex-valued functions with finite support, $C_c(G)$.
- The convolution product becomes $(h*k)(t) = \sum_{s \in G} h(s)k(s^{-1}t)$.
- The involution is $h^*(t) = \overline{h(t^{-1})}$.
- $C^*(G)$ is the universal C*-algebra generated by a set of unitaries $\{u_s\}_{s \in G}$ satisfying the group relations $u_s u_t = u_{st}$.

### Abelian Groups
Consider the group C*-algebra $C^*(G)$ where $G$ is an **abelian** group.
- The algebra $C_c(G)$ is abelian.
- Since $C^*(G)$ is an abelian, unital C*-algebra, the Gelfand-Naimark theorem states that there exists a compact Hausdorff space $X$ such that $C^*(G) \cong C(X)$.

This space $X$ can be identified with the **Pontryagin dual** of G, denoted $\hat{G}$.

> [!definition] Character Group (Pontryagin Dual)
> A **character** of an abelian group $G$ is a group homomorphism $\psi: G \to \T$.  The set of all characters is denoted by $\hat{G}$.  When endowed with the topology of pointwise convergence, $\hat{G}$ becomes a compact Hausdorff space.

> [!proposition]
> For an abelian group $G$, we have the isomorphism $C^*(G) \cong C(\hat{G})$.

*Proof Sketch*
The proof involves showing a correspondence between the character space (maximal ideal space) of the C*-algebra $C^*(G)$ and the character group $\hat{G}$.
- Any character $\psi \in \hat{G}$ gives rise to a multiplicative linear functional $\varphi_\psi$ on $C_c(G)$ by setting $\varphi_\psi(u_s) = \psi(s)$.  This extends to a character on the full C*-algebra $C^*(G)$.
- Conversely, any character $\varphi$ on $C^*(G)$ gives a group character $\psi$ on G via $\psi(s) = \varphi(u_s)$.
- The topology of pointwise convergence on $\hat{G}$ corresponds to the weak-* topology on the character space of $C^*(G)$.
$\square$

**Examples of Dual Groups:**
- If $G = \Z_n$, its characters are of the form $\chi_k(j) = e^{2\pi i kj/n}$ for $k=0, \dots, n-1$.  Thus, $\hat{\Z}_n \cong \Z_n$.  (In general, for any finite abelian group, $G \cong \hat{G}$).
- If $G = \Z$, any character $\chi$ is determined by $\chi(1) \in \T$.  Thus, $\hat{\Z} \cong \T$.

### Free Groups
Consider the free group on two generators, $G = F_2$.
- The group C*-algebra $C^*(F_2)$ is the universal C*-algebra generated by two unitaries $U, V$.
- This contrasts with $C^*(\Z^2)$, which is the universal C*-algebra generated by two *commuting* unitaries $u,v$ (since $\Z^2$ is abelian).

> [!proposition]
> The C*-algebra $C^*(F_n)$ has a family of finite-dimensional representations $\{\pi_n\}$ such that their direct sum $\bigoplus_{n \in \mathbb{N}} \pi_n$ is an isometric representation.

*Proof Sketch*
The proof relies on approximating the universal representation.
1. By the Gelfand-Naimark theorem, $C^*(F_2)$ has a faithful (isometric) universal representation $\pi: C^*(F_2) \to B(\mathcal{H})$ on a separable Hilbert space $\mathcal{H}$.  Let $U = \pi(\delta_u)$ and $V = \pi(\delta_v)$ be the unitaries corresponding to the generators.
2. Let $\{e_k\}$ be an orthonormal basis for $\mathcal{H}$ and let $P_n$ be the projection onto the span of $\{e_1, \dots, e_n\}$.
3. Define compressed operators $A_n = P_n U|_{P_n(\mathcal{H})}$ and $B_n = P_n V|_{P_n(\mathcal{H})}$.  These are not necessarily unitary.
4. "Purify" these contractions to unitaries on a larger space. Define unitaries $U_n$ and $V_n$ on the space $P_n(\mathcal{H}) \oplus P_n(\mathcal{H})$ using $A_n$ and $B_n$.  For example: $$V_n = \begin{pmatrix} B_n & (I_n - B_n^* B_n)^{1/2} \\ (I_n - B_n B_n^*)^{1/2} & -B_n^* \end{pmatrix}$$
5. This defines a sequence of finite-dimensional representations $\pi_n: C^*(F_2) \to B(P_n(\mathcal{H}) \oplus P_n(\mathcal{H}))$ by setting $\pi_n(\delta_u) = U_n$ and $\pi_n(\delta_v) = V_n$.
6. One can then show that for any element $f \in C_c(F_2)$, the norm $||\pi_n(f)||$ converges to $||\pi(f)||$.  This implies that the direct sum representation is isometric: $$||\bigoplus_{n \ge 1} \pi_n(f)|| = \sup_{n \ge 1} ||\pi_n(f)|| = ||\pi(f)|| = ||f||_u$$  This isometry extends from $C_c(F_2)$ to all of $C^*(F_2)$.
$\square$
