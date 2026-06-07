## Holonomic Constraints

> [!definition] Holonomic Constraint
> A holonomic constraint of an $n$ particle system $\{(m_{i},r_{i})\}_{i=1}^{n}$ is a constraint equation of the form: $$ f_j(r_1,r_2,\dots,r_n,t)=0.$$And so can be written as an equation between coordinates. 

> [!remark]
> The cool thing about holonomic constraints is that they reduce the degrees of freedom of the system.

<u><b>e.g.</b></u>
![holonomic_constraints|400](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/holonomic_constraints.jpg)

> [!definition] System with Holonomic Constraints
> Let $M$ be an $m$-dimensional surface in the $dn$-dimensional configuration space of the points $r_{1},r_{2},\dots,r_{n}$ with masses $m_{1},m_{2},\dots,m_{n}$. Let $q=(q_{1},q_{2},\dots,q_{m})$ be some [[Principle of Least Action#^663042|generalized coordinates]], the system described by $$\newcommand{\dd}{\:\mathrm{d}}\newcommand{\ddf}[2]{\frac{\dd #1}{\dd #2}}\newcommand{\pddf}[2]{\frac{\partial#1}{\partial#2}} \ddf{}{t}\pddf{L}{\dot{q}}-\pddf{L}{q}=0, \quad L=\frac{1}{2}\sum_{i=1}^{n} m_{i} \dot{r}_{i}^{2} + U(q)$$ is called a system of $n$ points with $dn-m$ ideal holonomic constraints.
> Or explicitly, using the Lagrange multipliers and the original generalized coordinate  $\lambda_{1},\lambda_{2},\dots,\lambda_{dn-m}$ and holonomic constraints $f_{1},f_{2},\dots,f_{dn-m}$, the equations of motion are: $$\ddf{}{t}\pddf{L}{\dot{q}}-\pddf{L}{q}=\sum_{i=1}^{dn-m}\lambda_{i}\pddf{f_{i}}{q}.$$ 

> [!remark]
> The meaning of these constraints in mechanics lies in the experimentally determined fact that many mechanical systems belong to this class more or less exactly.
> 

> [!definition] Degrees of Freedom
> The dimension of the configuration space is called the number of degrees of freedom.

## Lagrangian Dynamical System

> [!definition] Lagrangian Dynamical System
> A Lagrangian dynamical system is a pair $(M,L)$, where $M$ is a [[Manifolds, Atlases and Smooth Structures#^6ef2ef|smooth manifold]], $\newcommand{\R}{\mathbb{R}}L\colon TM\to \R$ is a smooth function on its [[Tangent Vectors and Spaces#^e3492e|tangent bundle]]. A curve $\gamma\colon \R\to M$ is called a motion in the Lagrangian dynamical system $(M,L)$ if $\gamma$ is an [[Variational Calculus#^aa327b|extremal]] of the functional $$S(f)=\int_{t_{1}}^{t_{2}}L(f(t),\dot{f}(t),t)\dd t.$$

<u><b>e.g.</b></u>  The configuration space of a planar double pendulum is the 2-torus $T^{2}$.

> [!definition] Natural Lagrangian System
> A Lagrangian dynamical system $(M,L)$ is called natural if $M$ is a [[Riemannian Metrics#^07b56e|Riemannian manifold]] with metric $g$, and $L$ is the difference between the kinetic energy and the potential energy: $$L(x,v)=T(x,v) - U(x)=\frac{1}{2}\langle v, v \rangle_{g_{x}}  - U(x),$$where $U\colon M\to \R$ is smooth. ^466228



