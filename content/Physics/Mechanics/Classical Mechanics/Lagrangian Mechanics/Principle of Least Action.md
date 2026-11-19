---
updated: 2025-03-05
---
## Generalized Coordinates

> [!definition] Generalized Coordinates
> Given a mechanical system of $n$ points, the generalized coordinates are any coordinates in the configuration space. We usually denote it as $q=(q_{1},q_{2},\dots,q_{k})\colon \E \to \E^{3n}$. ^663042

> [!principle] D'Alembert's Principle
> The sum of the differences between the forces acting on a system of massive particles and the time derivatives of the momenta of the system itself projected onto any virtual displacement consistent with the constraints of the system is zero. Thus, in mathematical notation, D'Alembert's principle is written as follows, $$ \sum_{i}(\mathbf{F}_{i}-m_{i}\mathbf{\dot{v}}_{i}-{\dot{m}}_{i}\mathbf{v}_{i})\cdot{\delta\mathbf{r}_{i}}=0 $$

## Principle of Least Action

> [!definition] Lagrangian
> The Lagrangian of a mechanical system is defined as $L = T - U$, which is the difference between kinetic energy and potential energy.

> [!definition] Action
> The action of  a mechanical system is a functional: $$ S[q] = \int_{t_1}^{t_2} L(q,\dot q,t) \mathrm{d}t. $$

> [!theorem] Hamilton’s Principle
> The motion of a mechanical system (from Newton's equation) $q(t)$ described by $k$ generalized coordinates $q = (q_1, q_2, ..., q_k)$ between two specified states $q_1 = q(t_1)$ and $q_2 = q(t_2)$ at two specified times $t_1$ and $t_2$ is an [[Variational Calculus#^aa327b|extremal]] of the action functional. That is, $$\frac{\dd }{\dd t} \left( \frac{\partial L}{\partial \dot{\gamma}(t)} \right) - \frac{\partial L}{\partial \gamma(t)}=0.$$
> It is also called the principle of least action.  ^9d2a0d

*Proof*  Since $U=U(q)$, and $T=\sum_{i} m_{i}\dot{r}_{i}^{2}/2$, we have $$\pddf{L}{\dot{q}_{i}}=\pddf{T}{\dot{q}_{i}}=m_{i}\dot{q_{i}}$$and $\pddf{L}{q_{i}}=-\pddf{U}{q_{i}}$. $\square$

> [!definition] Canonical Momentum and Force
> The canonical (generalized) momentum is defined as $$ p_{i} = \frac{\partial L}{\partial\dot q_{i}} $$where $L$ is the Lagrangian and $q$ is some general coordinate. Correspondingly, the generalized force is defined as $$ Q_{i} = \frac{\partial L}{\partial q_{i}}.$$ ^5e80a1

## Generalization of Conservation of Angular Momentum

> [!definition] Cyclic Coordinates
> A coordinate $q_{i}$ is called cyclic if $\pddf{L}{q_{i}}=0$. ^2c3e64

> [!proposition]
> The generalized momentum $p_{i}$ of a cyclic coordinate $q_{i}$ is conserved.

*Proof*  By Lagrange's equation, we know that $\frac{\dd}{\dd t}\left(\pddf{L}{\dot{q}_{i}}\right)=\pddf{L}{q_{i}}=0$. $\square$

**Thrm** The total kinetic energy of a rigid body is given by
$$ T = \frac{1}{2}M \dot{\mathbf{r_c}}^2 + \frac{1}{2}I_c\omega_c^2 $$
**Proof** By definition we know that $\mathbf{r_c} = \frac{\int \mathbf{r} \mathrm{d}m}{M}$.