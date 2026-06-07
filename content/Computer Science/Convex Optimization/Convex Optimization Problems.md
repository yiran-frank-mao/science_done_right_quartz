## Optimization Problem

>[!definition] 
>**Def**  <i><u>(General) Optimization Problem</u></i> $$
>\begin{aligned}
>\text{minimize } & f_0(x)\\
>\text{subject to }& f_i(x)\leq0 \quad i=1,\dots,m \\
>& h_i(x)=0 \quad i=1,\dots,p
>\end{aligned}$$ ^9790f7

**Def**  <i><u>Feasible Point</u></i>
A point $x$ is feasible if $x ∈ \textbf{dom} (f_0)$ and it satisfies the constraints.

**Def**  <i><u>Solution</u></i>
A solution, or optimal point, $x^⋆$ has the smallest value of $f_{0}$ among all feasible $x$.

**Def**  <i><u>Optimal Value</u></i>
The optimal value of an optimization problem is $$p^\star=\inf_{x\in\mathcal{D}}\left\{f_0(x) \left| \begin{array}{ll}f_i(x)\leq0,&i=1,\ldots,m\\h_i(x)=0,&i=1,\ldots,p\end{array}\right. \right\}$$$p^\star = ∞$ if the problem is infeasible.

**Def**  <i><u>Locally Optimal</u></i>
A point $x$ is locally optimal if there is an $R > 0$ such that $z = x$ is optimal for$$\begin{aligned}\text{minimize } & f_0(x)\\\text{subject to }& f_i(x)\leq0 \quad i=1,\dots,m \\& h_i(x)=0 \quad i=1,\dots,p \\&\|z-x \|_2 \leq R\end{aligned} $$

**Def**  <i><u>Equivalent Optimization Problems</u></i>
Two problems are equivalent if the solution of one is readily obtained from the solution of the other, and vice-versa.

## Convex Optimization Problem

**Def**  <i><u>Convex Optimization Problem</u></i>
A optimization problem is convex if $f_0,f_1,\dots,f_p$ are convex and $h_i(x)=a^{\mathrm{T}}_i x−b_i$ are affine, often written as $Ax=b$. A optimization problem is quasiconvex if $f_0$ is quasiconvex, $f_1,\dots,f_p$ are convex and $h_i(x)=a^{\mathrm{T}}_i x−b_i$ are affine, often written as $Ax=b$. $$
\begin{aligned}
\text{minimize } & f_0(x)\\
\text{subject to }& f_i(x)\leq0 \quad i=1,\dots,m \\
& Ax=b
\end{aligned} $$

**Prop**  An optimization problem is convex iff the objective function is convex and the feasible set is also convex.

**Prop**  Any local minimum of a convex problem is (globally) optimal.
**Proof**

**Thrm**  <i><u>Optimality Criterion for Differentiable Objective</u></i>
For an optimization problem with differentiable objective, $x$ is optimal if and only if it is feasible and $∇f_0(x)^{\mathrm{T}} (y − x) ≥ 0$ for all feasible $y$.

**Corollary**  For a unconstrained problem, $x$ is optimal if and only if $$
x ∈ \operatorname{\textbf{dom}} f_0, \quad ∇f_0(x) = 0$$

**Corollary**  For an equality constrained problem, $x$ is optimal if and only if there exists a $\nu$ such that $$
x ∈ \operatorname{\textbf{dom}} f_0, \quad Ax=b,\quad \nabla f_0(x)+A^{\mathrm{T}}\nu=0 $$Equivalently, $∇f_0(x)$ is orthogonal to the null space of $A$.

## Linear Program (LP)

**Def**  <i><u>Linear Program</u></i>
Linear program is a convex problem with affine objective and constraint functions: $$
\begin{aligned}
\text{minimize } \quad & c^{\mathrm{T}}x\\
\text{subject to }\quad & Gx\preceq h \\
& Ax=b
\end{aligned}$$![|330](https://i.imgur.com/8eRbraq.png)

**Def**  <i><u>Chebyshev Center</u></i>
Chebyshev centre of a polyhedron $\mathcal{P}=\{x\mid a_i^\mathrm{T}x\leq b_i,\mathrm{~}i=1,\ldots,m\}$ is the center of the largest inscribed ball$\mathcal{B}=\{x_c+u\mid\|u\|_2\leq r\}$
![|330](https://i.imgur.com/xGzByhb.png)

**Def**  <i><u>Linear-Fractional Program</u></i>
The linear-fractional program is of the form:$$
\begin{aligned}
\text{minimize } \quad & \frac{c^\mathrm{T}x+d}{e^\mathrm{T}x+f}\\
\text{subject to }\quad & Gx\preceq h \\
& Ax=b
\end{aligned}$$where $\textbf{dom}f_0(x)=\{x\mid e^\mathrm{T}x+f>0\}$.

**Prop**  Linear-fractional program is quasiconvex.

**Prop**  The linear-fractional program is equivalent to the following linear program: $$
\begin{aligned}
\text{minimize } \quad & c^{\mathrm{T}}y+dz\\
\text{subject to }\quad & Gy\preceq hz \\
& Ay=bz \\
& e^\mathrm{T}y+fz=1 \\
& z\geq 0
\end{aligned}$$

**Def**  <i><u>Generalised Linear-Fractional Program</u></i>
The generalised linear-fractional program is a a quasiconvex optimization problem to minimize the objective: $$
f_0(x)=\max_{i=1,...,r}\frac{c_i^Tx+d_i}{e_i^Tx+f_i}, \quad 
\operatorname{\textbf{dom}}f_0(x)=\{x\mid e_i^Tx+f_i>0,\mathrm{~}i=1,\ldots,r\}$$

## Quadratic Program (QP)

**Def**  <i><u>Quadratic Program</u></i>$$
\begin{aligned}
\text{minimize } \quad & \frac12x^\mathrm{T}Px+q^\mathrm{T}x+r\\
\text{subject to }\quad & Gx\preceq h \\
& Ax=b
\end{aligned}$$
where $P ∈ \mathbb{S}^n_+$, so objective is a convex quadratic.

**Def**  <i><u>Quadratically Constrained Quadratic Program (QCQP)</u></i> $$
\begin{aligned}
\text{minimize } \quad & \frac12x^\mathrm{T}P_0x+q_0^\mathrm{T}x+r_0\\
\text{subject to }\quad & \frac12x^\mathrm{T}P_ix+q_i^\mathrm{T}x+r_i\leq 0, \quad i=1,\dots,m \\
& Ax=b
\end{aligned}$$where $P_i ∈ \mathbb{S}^n_+$, objective and constraints are convex quadratic. If $P_1, \dots , P_m ∈ \mathbb{S}^n_{++}$ then the feasible region is the intersection of m ellipsoids and an affine set.

**Def**  <i><u>Second-order Cone Program (SOCP)</u></i> $$
\begin{aligned}
\text{minimize } \quad & f^\mathrm{T}x\\
\text{subject to }\quad & 
\|A_ix+b_i\|_2\leq c_i^\mathrm{T}x+d_i, \quad i=1,\dots,m \\
& Fx=g
\end{aligned}$$where $A_i\in\mathbb{R}^{n_i\times n},F\in\mathbb{R}^{p\times n}$.

**Prop**  For all LP and QCQP, exists some SOCP such that they are equivalent. i.e. SOCP is more general than QCQP and LP.

**Def**  <i><u>Robust Linear Programming</u></i>
The parameters in optimization problems are often uncertain, hence we introduce probability here:$$
\begin{aligned}
\text{minimize } \quad & c^{\mathrm{T}}x\\
\text{subject to }\quad
& \operatorname{\textbf{prob}} (Ax-b\preceq 0)\geq \eta
\end{aligned}$$

## Geometric Program (GP)

**Def**  <i><u>Monomial Function</u></i>
A monomial function is defined with the following form: $$
f(x) = cx_1^{a_1}x_2^{a_2}\dots x_n^{a_n},
\quad
\textbf{dom}f=\R^{n}_{++}$$

**Def**  <i><u>Posynomial Function</u></i>
A posynomial function is defined as sum of monomials: $$
f(x)=\sum_{k=1}^Kc_kx_1^{a_{1k}}x_2^{a_{2k}}\cdots x_n^{a_{nk}},\quad\operatorname{\textbf{dom}}f=\mathbb{R}_{++}^n$$

**Def**  <i><u>Geometric Programming</u></i> $$
\begin{aligned}
\text{minimize } & f_0(x)\\
\text{subject to }& f_i(x)\leq0 \quad i=1,\dots,m \\
& h_i(x)=1 \quad i=1,\dots,p
\end{aligned} $$with $f_i$ posynomial, $h_i$ monomial.

**Thrm**  Geometric programming problem is equivalent to the following convex problem: $$
\begin{aligned}
\text{minimize } & \log\left(\sum_{k=1}^K\exp\left(a_{0k}^\mathrm{T}y+b_{0k}\right)\right)\\
\text{subject to }& 
\log\left(\sum_{k=1}^K\exp\left(a_{ik}^\mathrm{T}y+b_{ik}\right)\right)\leq0\quad i=1,\dots,m \\
& Gy+d=0
\end{aligned} $$

**Def**  <i><u>Spectral Radius</u></i>
Suppose $A$ is a matrix and $λ_1,..., λ_n$ are its eigenvalues, the spectral radius $ρ(A)$ is defined as: $$
ρ(A) = \max \{|λ1|, |λ2|, ..., |λn|\} $$

## Generalized Inequality Constraints

**Def**  <i><u>Generalized Convex Optimization Problem</u></i>
Convex problem with generalized inequality constraints: $$
\begin{aligned}
\text{minimize } \quad& f_0(x)\\
\text{subject to }\quad& f_i(x)\leq_{K_i}0 \quad i=1,\dots,m \\
& Ax=b
\end{aligned} $$where $f_0:\mathbb{R}^n\to\mathbb{R}$ is convex, $f_i:\mathbb{R}^n\to\mathbb{R}^{k_i}$ is $K_i$-convex with respect to proper cone $K_i$.

## Semidefinite Program (SDP)

**Def**  <i><u>Semidefinite Program</u></i> $$
\begin{aligned}
\text{minimize } \quad & c^\mathrm{T}x\\
\text{subject to }\quad & x_1F_1+x_2F_2+\cdots+x_nF_n+G\preceq0 \\
& Ax=b
\end{aligned} $$with $F_i,G\in\mathbb{S}^k$.

## Optimal and Pareto Optimal Points

**Def**  <i><u>Pareto Optimal</u></i>
For some generalised optimization problem, suppose $\mathcal{O} = \{f_0(x) \mid x\text{ feasible}\}$. Feasible $x$ is optimal if $f_0(x)$ is the minimum value of $\mathcal{O}$. Feasible $x$ is Pareto optimal if $f_0(x)$ is a minimal value of $\mathcal{O}$.