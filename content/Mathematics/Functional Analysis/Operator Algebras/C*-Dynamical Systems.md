---
created: 2025-10-15
updated: 2025-10-15
cssclasses:
  - img-grid
  - img-zoom
completed: true
tags:
  - quantum-mechanics
  - c-star-algebra
  - operator-theory
  - dynamical-systems
---
## Group Actions and C\*-Dynamical Systems

Throughout, we assume $G$ is a countable group equipped with the discrete topology.

Recall the definition of a group action:

![[Group Actions#^4047e8]]

If $X$ is a topological space, we say that $G$ acts *continuously* if the action map $G \times X \to X$ is *continuous*.

<u><b>e.g.</b></u>
- Let $G = (\mathbb{R}, +)$ and $X = \mathbb{R}^n$. Consider an [[Ordinary Differential Equations#^a24b52|initial value problem]] given by $\dot{x}(t) = F(x(t))$  for a sufficiently nice function $F: \mathbb{R}^n \to \mathbb{R}^n$. For any $z \in \mathbb{R}^n$, let $x_z(t)$ be the unique solution with initial condition $x_z(0) = z$. We can define an action of $\mathbb{R}$ on $\mathbb{R}^n$ by $t \cdot z := x_z(t)$.
	- $0 \cdot z = x_z(0) = z$.
	- $s \cdot (t \cdot z) = s \cdot x_z(t)$. The solution starting at $x_z(t)$ is just a time-shift of the original solution, i.e., $x_{x_z(t)}(s) = x_z(t+s)$. Thus, $s \cdot (t \cdot z) = x_z(t+s) = (t+s) \cdot z$.

- Let  be a locally compact topological space and let $h \in \text{Homeo}(X)$ be a homeomorphism. The group $G = \mathbb{Z}$ acts continuously on  via $n \cdot x := h^n(x)$ for $n \in \mathbb{Z}$ and $x \in X$.
$\quad$

A group action on a space $X$ induces a natural action on the C\*-algebra of continuous functions on $X$.

> [!proposition]
> Let $G$ be a group acting continuously on a locally compact space $X$. This induces a map $\alpha\colon G \to \text{Aut}(C_0(X))$  given by
> $$(\alpha_s(f))(x) = f(s^{-1} \cdot x), \quad s \in G, x \in X, f \in C_0(X)$$
> This map $\alpha$ is a group homomorphism.

> [!definition] C\*-Dynamical System
> A *C\*-dynamical system* is a triple $(\mathcal{A}, G, \alpha)$, where $\mathcal{A}$ is a [[C*-Algebras#^e4fdc6|C*-algebra]], $G$ is a [[Groups, Order and Subgroups#^6e0960|group]], and $\alpha\colon G \to \text{Aut}(\mathcal{A})$ is a [[Homomorphisms, Normal Subgroup & Conjugation#^homo|homomorphism]]. The homomorphism is often required to be continuous in an appropriate sense. ^c9bf4c

> [!proposition]
> If $(C_0(X), G, \alpha)$ is a C\*-dynamical system, then there exists a continuous action of $G$ on $X$ that induces $\alpha$.
>

 *Proof Sketch* For each $s \in G$, $\alpha_s$ is an automorphism of $C_0(X)$. By the Gelfand-Naimark theorem, there exists a unique homeomorphism $h_s: X \to X$ such that $\alpha_s(f) = f \circ h_s^{-1}$ for all $f \in C_0(X)$. The homomorphism property $\alpha_{st} = \alpha_s \circ \alpha_t$ implies $h_{st} = h_s \circ h_t$, defining a group action $s \cdot x := h_s(x)$.

## Covariant Representations

> [!definition] Covariant Representation
> Let $(\mathcal{A}, G, \alpha)$ be a C\*-dynamical system. A *covariant representation* of $(\mathcal{A}, G, \alpha)$ on a [[Hilbert Spaces#^ae0212|Hilbert space]] $\newcommand{\H}{\mathcal{H}}\H$ is a pair $(\pi, U)$ where:
> 1. $\pi\colon \mathcal{A} \to B(\H)$ is a $\ast$-representation of $\mathcal{A}$ on $\H$.
> 2. $U\colon G \to U(\H)$ is a unitary representation of $G$ on $\H$.
> 3. They satisfy the covariance condition: $\pi(\alpha_s(a)) = U_s \pi(a) U_s^*$ for all $a \in \mathcal{A}$ and $s \in G$.
> $\quad$ ^ff0e48

<u><b>e.g.</b></u>  Let $(C_0(G), G, L)$ be the dynamical system where $G$ acts on itself by left multiplication, and $L$ is the action on functions by left translation: $(L_s f)(t) = f(s^{-1}t)$. Define a representation $\pi$ of $C_0(G)$ on $\ell^2(G)$ by multiplication operators: $$(\pi(f)\xi)(s) = f(s)\xi(s) \quad \text{for } f \in C_0(G), \xi \in \ell^2(G)$$Let $\lambda$ be the *left regular representation* of $G$ on $\ell^2(G)$: $$(\lambda_{s}\xi)(t) = \xi(s^{-1}t)$$Then $(\pi, \lambda)$ is a covariant representation.

## The Regular Representation Construction

Given any C\*-dynamical system $(\mathcal{A}, G, \alpha)$ and a representation $\pi_{0}\colon \mathcal{A} \to B(\H)$, one can construct a covariant representation on the larger Hilbert space $\ell^2(G, \H)$. It consists of functions $\xi\colon G \to \H$ such that $\sum_{t \in G} \|\xi(t)\|_H^2 < \infty$. The inner product is $\langle \xi, \eta \rangle = \sum_{t \in G} \langle \xi(t), \eta(t) \rangle_H$.
1. **Unitary Representation $\lambda$**: Define $\lambda\colon G \to \mathcal{U}(\ell^2(G,H))$ by $$(\lambda_s \xi)(t) = \xi(s^{-1}t)$$This is a unitary representation of $G$.
2. **Algebra Representation $\Pi$**: Define $\Pi\colon \mathcal{A} \to B(\ell^2(G, H))$ by $$(\Pi(a)\xi)(t) = \pi_0(\alpha_{t^{-1}}(a))\xi(t)$$
$\quad$

> [!theorem]
> The pair $(\Pi, \lambda)$ constructed above is a covariant representation of $(\mathcal{A}, G, \alpha)$.
>

*Proof*  We must check that $\lambda_s \Pi(a) \lambda_s^* = \Pi(\alpha_s(a))$. For any $\xi \in \ell^2(G,H)$ and $t \in G$: $$\begin{aligned}(\lambda_s \Pi(a) \lambda_s^* \xi)(t) &= (\Pi(a) \lambda_s^* \xi)(s^{-1}t) \\&= \pi_0(\alpha_{(s^{-1}t)^{-1}}(a)) (\lambda_s^* \xi)(s^{-1}t) \\&= \pi_0(\alpha_{t^{-1}s}(a)) \xi(s(s^{-1}t)) \\&= \pi_0(\alpha_{t^{-1}s}(a)) \xi(t) \\&= \pi_0(\alpha_{t^{-1}}(\alpha_s(a))) \xi(t) \\&= (\Pi(\alpha_s(a))\xi)(t)\end{aligned}$$The calculation follows from the definitions of $\Pi$, $\lambda$, and the homomorphism property of $\alpha$. Thus, the covariance condition holds.  $\square$
