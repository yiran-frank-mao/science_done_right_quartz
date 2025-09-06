## The Dual Problem

>[!definition] Lagrangian and Lagrange Dual Function
For an optimization problem: $$ \begin{aligned} \text{minimize } & f_0(x)\\ \text{subject to }& f_i(x)\leq0 \quad i=1,\dots,m \\ & h_i(x)=0 \quad i=1,\dots,p \end{aligned} $$Define the Lagrangian $L: \R^n \times \R^m \times \R^p \to \R$ as: $$ \begin{aligned}L(x,\lambda,\nu) &= f_0(x) + \lambda^{\top} f(x) + \nu^{\top}h(x) \\ &= f_0(x) + \sum_{i=1}^m\lambda_if_i(x) + \sum_{i=1}^p \nu_i h_i(x)\end{aligned} $$Define the Lagrange dual function $g:\R^m \times \R^p \to \R$ as: $$ g(\lambda, \nu) = \inf_{x \in \textbf{dom} f_0} L(x,\lambda,\nu) $$ ^07ae38

> [!theorem]
> For any optimization problem, the Lagrange dual function is concave.

> [!theorem] Lower Bound Property
> If $λ \succeq 0$, then the Lagrange dual function is a lower bound for the original objective function: $g(λ, ν) \leq f_0(x^{*})$.

>[!definition] Lagrange Dual Problem
> For any optimization problem, the dual problem is to maximize the dual function: $$ \begin{aligned} \text{maximize } \quad & g(\lambda, \nu)\\ \text{subject to }\quad & \lambda \succeq 0 \end{aligned} $$ ^f694a1

>[!proposition]
> The dual problem is always a convex optimization problem.

>[!definition] Weak and Strong Duality
We call an optimization problem with strong duality if the dual optimal equals to the primal optimal. Conversely, we call it weak duality.
<b><u>e.g.</u></b> A nonconvex problem with strong duality, suppose $A\nsucceq 0$:
$$ \begin{aligned} \text{minimize } \quad & x^\mathrm{T}Ax+2b^{\mathrm{T}}x\\ \text{subject to }\quad & x^\mathrm{T}x\leq 1 \end{aligned} $$ ^bf5e08

>[!theorem] Slater’s Condition
Strong duality holds for a convex problem$$ \begin{aligned}
\text{minimize} \quad &f_0(x) \\ \text{subject to} \quad&f_i(x)\leq0,i=1,\dots,m \\ &Ax=b\end{aligned} $$if it is strictly feasible:$$ \exists x \in \mathbf{int}\mathcal{D}: f_i(x)<0, i=1,\dots,m $$

>[!theorem]
>**Thrm**  <i><u>Complementary Slackness</u></i>
Assume strong duality holds, $x^{\star}$ is primal optimal, $(λ^{\star},ν^\star)$ is dual optimal, then $$ \lambda_i^\star f_i(x^\star)=0 \text{ for } i=1,\dots,m $$

## KKT Conditions

> [!theorem] Theorem: Karush-Kuhn-Tucker (KKT) Conditions
> The following conditions hold for a problem with differentiable $f_i$ and $h_i$ such that strong duality holds and $x, λ, ν$ are optimal:
> 1. Primal feasible: $f_i(x) \leq 0, i = 1,\dots,m,\quad h_i(x) = 0, i = 1,\dots,p$
> 2. Dual feasible: $\lambda \succeq 0$
> 3. Complementary slackness: $λ_if_i(x) = 0, i = 1, \dots, m$
> 4. Gradient of Lagrangian with respect to $x$ vanishes:$$ \nabla f_0(x) + \sum_{i=1}^m\lambda_i \nabla f_i(x) + \sum_{i=1}^p\nu_i\nabla h_i(x)=0 $$

> [!theorem]
> If $x, \lambda, \nu$ satisfy the KKT conditions for a convex problem, then they are optimal.

> [!proposition]
> If Slater’s condition is satisfied, then $x$ is optimal if and only if there exists $λ, ν$ that satisfy the KKT conditions.
