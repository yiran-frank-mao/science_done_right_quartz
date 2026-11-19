## Equality Constrained Minimization

**Def**  <i><u>Equality Constrained Minimization</u></i>
The equality constrained minimization problem is simply
$$ \begin{aligned}

\text{minimize} \quad & f(x)\\ \text{subject to} \quad & Ax=b

\end{aligned} $$
where $f$ is convex and twice continuously differentiable. $A\in \R^{p\times n}$ with $\mathop{\text{rank}} A=p$. 
**Prop** The optimality condition is that $x^\star$ is optimal iff there exists $\nu^\star$ such that
$$ \nabla f(x^\star)+A^{\mathrm{T}}\nu^\star=0,\quad Ax^\star=b $$

**Def**  <i><u>Equality Constrained Quadratic Minimization</u></i>
The equality constrained quadratic minimization problem is$$ \begin{aligned}
\text{minimize} \quad & \frac{1}{2}x^{\mathrm{T}}Px+q^{\mathrm{T}}x+r\\ \text{subject to} \quad & Ax=b\end{aligned} $$**Prop** The optimality condition is given by: $$ \begin{bmatrix} P & A^{\mathrm{T}} \\ A & 0 \end{bmatrix} \begin{bmatrix} x^{\star} \\ \nu^\star \end{bmatrix} = \begin{bmatrix} -q \\ b \end{bmatrix} $$where the coefficient matrix is called KKT matrix.

**Prop** The KKT matrix is nonsingular if and only if
$$ Ax=0,\quad x\neq 0 \implies x^{\mathrm{T}}Px>0 $$
which is equivalent to $P + A^{\mathrm{T}} A \succ 0$.

## Eliminating Equality Constraints

**Thrm** For any equality constrained optimization problem, we can eliminate the equality constraint by representing $\{x \mid Ax = b\}$ as $\{Fz + \hat{x} \mid z \in \R^{n−p}\}$ where $\hat{x}$ is some particular solution and $\mathop{\mathrm{range}} F \in \R^{n\times(n-p)}=\ker A$ with $\mathop{\mathrm{rank}} F = n-p$ and $AF=0$. And thus the optimization problem becomes:
$$ \begin{aligned} \text{minimize} \quad & f(Fz+\hat{x}) \end{aligned} $$
which is an unconstrained problem with variable $z\in \R^{n-p}$. From solution $z^\star$, obtain $x^\star$ and $ν^\star$ as
$$ x^\star = Fz^\star+\hat{x}, \quad \nu^\star = -(AA^{\mathrm{T}})^{-1} A \nabla f(x^\star) $$

## Newton's Method

**Prop** The Newton step of $f$ at feasible $x$ for an equality constrained optimization problem is given by solution $v$ of
$$ \begin{bmatrix} \nabla^2f(x) & A^{\mathrm{T}} \\ A & 0 \end{bmatrix} \begin{bmatrix} v \\ w \end{bmatrix}
\begin{bmatrix} -\nabla f(x) \\ 0 \end{bmatrix} $$

**Prop** The Newton decrement is given by
$$ \lambda(x) = \sqrt{\Delta x_{\text{nt}}^{\mathrm{T}}\nabla^2f(x)^{−1}\Delta x_{\text{nt}}} = \sqrt{-\nabla f(x)^{\mathrm{T}}\Delta x_{\text{nt}}} $$
It satisfies that

$$ \frac{\mathrm{d}}{\mathrm{d}t}f(x+t\Delta x_{\text{nt}}) \Bigg|_{t=0}=-\lambda(x)^2 $$
Thus it gives an estimate of $f(x)-p^\star$ by $\frac{1}{2}\lambda(x)^2$.

**Algorithm**  <i><u>Newton’s Method with Equality Constraints</u></i>
Given a starting point $x \in \text{dom}{f}$ with $Ax=b$, tolerance $\varepsilon > 0$.
Repeat the following:
1. Compute the Newton step $\Delta x_{\text{nt}}$ and decrement $\lambda$.
2. Stopping criterion. quit if $\frac{1}{2}λ^2 ≤ ε$.
3. Line search: Choose step size $t$ by [backtracking line search](Descent%20Methods%20in%20Unconstrained%20Optimization.md#^bls)
4. Update: $x:=x+t \Delta x_{\text{nt}}$.

**Def**  <i><u>Dual Newton Step</u></i>
For a equality constrained optimization problem, we define the dual Newton step $\Delta\nu_{\text{nt}}$ as the solution of the following equation:
$$ \begin{bmatrix}\nabla^2f(x) & A^{\mathrm{T}} \\A & 0\end{bmatrix} \begin{bmatrix} \Delta\nu_{\text{nt}} \\ w \end{bmatrix} =- \begin{bmatrix}\nabla f(x) \\ Ax-b \end{bmatrix} $$
with optimality condition as $r(x,\nu)=(\nabla f(x)+A^{\mathrm{T}}\nu, Ax-b)=\mathbf{0}$.

**Algorithm**  <i><u>Infeasible Start Newton Method</u></i>
Given a starting point $x \in \text{dom}{f}$ with $Ax=b$, tolerance $\varepsilon > 0$, $\alpha\in(0,\frac{1} {2})$, $\beta\in(0,1)$.
Repeat the following:
1. Compute the Newton step $\Delta x_{\text{nt}}$ and dual Newton step $\Delta \nu_{\text{nt}}$.
2. Line search: Choose step size $t$ by [backtracking line search](Descent%20Methods%20in%20Unconstrained%20Optimization.md#^bls) on $\| r\|_2$:
    1. $t :=1$
    2. while $∥r(x + t∆x_{\text{nt}}, ν + t∆ν_{\text{nt}})∥_2 > (1 − αt)∥r(x, ν)∥_2$:
        1. $t:=\beta t$
3. Update: $x:=x+t \Delta x_{\text{nt}}$, $\nu:=\nu+t \Delta \nu_{\text{nt}}$
4. Stopping criterion: Until $Ax=b$ and $\| r(x,\nu)\|_2\leq \varepsilon$

## KKT Systems

**Thrm** The KKT system of a equality constrained optimization problem is
$$ \begin{bmatrix} H & A^{\mathrm{T}} \\ A &0 \end{bmatrix} \begin{bmatrix} v \\ w \end{bmatrix}= -\begin{bmatrix} g \\ h \end{bmatrix} $$
where $H=\nabla^2 f(x)$ is the Hessian is positive semidefinite for any convex problem.