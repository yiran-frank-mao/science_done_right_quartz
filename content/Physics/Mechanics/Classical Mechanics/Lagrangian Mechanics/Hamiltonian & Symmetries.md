## Hamilton's Equations

> [!definition] Hamiltonian
> Recall that the [[Principle of Least Action#^5e80a1|canonical momentum]] is defined as $\newcommand{\dd}{\:\mathrm{d}}\newcommand{\ddf}[2]{\frac{\dd #1}{\dd #2}}\newcommand{\pddf}[2]{\frac{\partial#1}{\partial#2}}p_{j}=\pddf{L}{\dot{q_{j}}}$, we define the hamiltonian as the [[Convex Functions#^745078|Legendre transform]] of the Lagrangian, viewed as a function of $\mathbf{\dot{q}}$: $$ H (\mathbf{q},\mathbf{p},t)=\mathbf{\dot q}\cdot\mathbf{p}-L(\mathbf{q},\mathbf{\dot{q}},t)$$

> [!definition] Hamilton’s Equations
> We can easily derive the following Hamilton’s equations from the [[Principle of Least Action#^9d2a0d|Euler-Lagrange equation]]: $$\dot p_j = - \frac{\partial H}{\partial q_{j}},\quad \dot q_j = \frac{\partial H}{\partial p_{j}},\quad - \frac{\partial L}{\partial t}= \frac{\partial H}{\partial t}.$$ ^5ef3ed

> [!theorem] 
> The hamiltonian in a conservative potential is the total energy.

*Proof*  Under the assumption that $L=T-U$, and $T$ is a quadratic form with respect to $\mathbf{\dot{q}}$, in a conservative system, $U$ only depends on $\mathbf{q}$. We invoke the [[Convex Functions#^30a07a|lemma]], and obtain $H=2T-(T-U)=T+U$. $\square$

> [!corollary]
> $$\ddf{H}{t}=\pddf{H}{t}.$$In particular, for a system whose Hamiltonian does not dependent explicitly on time, the Hamiltonian is conserved.

*Proof*  We have the following equations hold: $$\begin{aligned} \ddf{H}{t}&=\pddf{H}{\mathbf{p}} \dot{\mathbf{p}} + \pddf{H}{\mathbf{q}}\dot{\mathbf{q}}+ \pddf{H}{t}\\ &= -\pddf{H}{\mathbf{p}}\pddf{H}{\mathbf{q}} + \pddf{H}{\mathbf{q}}\pddf{H}{\mathbf{p}}+ \pddf{H}{t}\\ &=\pddf{H}{t}.\end{aligned}$$ $\square$

## Symmetries

> [!proposition]
> One coordinate is [[Principle of Least Action#^2c3e64|cyclic]] if and only if $\frac{\partial H}{\partial q_i}=0$, which leads to a constant momentum.

> [!theorem] Noether's Theorem
> Every continuous symmetry of the action corresponds to a conserved quantity and vice versa.
> $$\ddf{L(S,Q,\dot{Q},t)}{S}=0 \implies \pddf{L}{\dot{Q}}\pddf{Q}{S}=0$$where $L(S,Q,\dot{Q},t)$ is the Lagrangian, $S$ is the action and $Q$ is some generalized coordinates. ^05c1b6

*Proof*  A proof of Noether's theorem using [[Symplectic Geometry|symplectic geometry]] is given [[Poisson Bracket#^1f3e3a|here]]. $\square$