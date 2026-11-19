## Inequality Constrained Minimization

**Def**  <i><u>Inequality Constrained Minimization</u></i>
The inequality constrained minimization problem is defined as follows: $$ \begin{aligned} \text{minimize } \quad & f_0(x)\\ \text{subject to }\quad & f_i(x)\leq0 \quad i=1,\dots,m \\ & Ax=b \end{aligned} $$where $f_i$ are [[Convex Functions#^c53709|convex]], twice continuously differentiable. $A\in\R^{p\times n}$ with rank $p$. And the problem is strictly feasible, that is exists $\tilde{x} \in \textbf{dom}f_0$ such that
$$ f_i({\tilde x}) < 0 \text{ for all $i=1,\dots,m$}, \quad A\tilde x=b $$

**Prop** Strong duality holds and dual optimum is attained for the above problem.

## Log Barrier Method

**Thrm** We can reformulate the inequality constraints via indicator functions:
$$ \begin{aligned} \text{minimize } \quad & f_0(x)+\sum_{i=1}^m I_\R\_(f_i(x))\\ \text{subject to }\quad & Ax=b \end{aligned} $$
where
$$ I_\R\_(u)=\begin{cases} 0 \quad &\text{if $u\leq0$} \\ \infty \quad &\text{otherwise} \end{cases} $$

**Def**  <i><u>Log Barrier</u></i>
We define the log barrier function to smoothly approximate sum of indicator functions $I_\R\_(u)$:
$$ I_\R\_(u)\approx -\frac{1}{t} \log(-u) $$
The approximation improves as $t → ∞$.
Thus the original inequality constrained problem can be expressed as:
$$ \begin{aligned} \text{minimize } \quad & f_0(x)-\frac{1}{t}\sum_{i=1}^m \log(-f_i(x)) \\

\text{subject to } \quad & Ax=b \end{aligned} $$

**Def** <i><u> Logarithmic Barrier Function</u></i>
For a series of inequality constraints $f_i(x)\leq0$ that are strictly feasible, we define the logarithmic barrier function as:
$$ \phi(x)=-\sum_{i=1}^m \log(-f_i(x)), \quad \textbf{dom}f=\{ x\mid f_i(x)<0 \text{ for all } i \} $$

**Prop** Logarithmic barrier function is convex and twice continuously differentiable.

**Def**  <i><u>Central Path</u></i>
For $t > 0$, define $x^\star(t)$ as the solution of
$$ \begin{aligned}\text{minimize } \quad & tf_0(x)+\phi(x) \\ \text{subject to } \quad & Ax=b\end{aligned} $$
Assume that $x^\star(t)$ exists and is unique for each $t > 0$, then the central path is $\{ x^{\star}(t) \mid t>0 \}$.

**Prop** $x = x^\star(t)$ if there exists a $w$ such that
$$ t\nabla f_0(x)+\sum_{i=1}^m \frac{1}{-f_i(x)}\nabla f_i(x)+A^{\mathrm{T}}w=0,\quad Ax=b $$

**Prop** The solution of the central path problem guarantees that $f_0(x^\star(t)) − p^\star ≤ \frac{m}{t}$. ^dgap

**Thrm**  <i><u>Interpretation via KKT Conditions</u></i>
$x = x^\star(t), λ = λ^\star(t), ν = ν^\star(t)$ satisfy
1. Primal constraints: $f_i(x) ≤ 0, i = 1,...,m, Ax = b$
2. Dual constraints: $λ \succeq 0$
3. Approximate complementary slackness: $−λ_if_i(x) = \frac{1}{t} , i = 1, \dots , m$
4. Gradient of Lagrangian with respect to $x$ vanishes:$$ \nabla f_0(x)+\sum_{i=1}^m \lambda_i \nabla f_i(x)+A^T \nu=0 $$
>[!remark]
>Difference with KKT is that condition 3 replaces $λ_if_i(x) = 0$

**Thrm**  <i><u>Force Field Interpretation</u></i>
Consider a centering problem:
$$ \begin{aligned}\text{minimize } \quad & tf_0(x)-\sum_{i=1}^m \log(-f_i(x)) \end{aligned} $$
- $tf_0(x)$ is the potential of force field $F_0(x) = −t∇f_0(x)$
- $− \log(−f_i(x))$ is the potential of force field $F_i(x) = \frac{1}{f_i(x)}∇f_i(x)$
The forces balance at $x^\star(t)$:
$$ F_0\left(x^{\star}(t)\right)+\sum_{i=1}^m F_i\left(x^{\star}(t)\right)=0 $$

**Algorithm**  <i><u>Barrier Method</u></i>
Given strictly feasible $x$, $t := t^{(0)} > 0$, $μ > 1$, tolerance $ε > 0$.
Repeat:
1. Centering step: Compute $x^\star(t)$ by minimizing $tf_0 + \phi$, subject to $Ax = b$.
2. Update: $x:=x^\star(t)$.
3. Stopping criterion: quit if $\frac{m}{t} \leq \varepsilon$. (It follows from [proposition](Interior%20Point%20Methods%20in%20Inequality%20Constrained%20Minimization.md#^dgap))
4. Increase: $t := μt$.

**Fact**
- Centering usually done using Newton’s method, starting at current $x$.
- Choice of $μ$ involves a trade-off: large $μ$ means fewer outer iterations, more inner (Newton) iterations; typical values of $μ$ is in $[10, 20]$.
## Generalized Inequality Problems

**Def**  <i><u>Generalized Inequality Problem</u></i>
The generalized inequality problem is defined as
$$ \begin{aligned}\text{minimize } \quad & f_0(x)\\\text{subject to }\quad & f_i(x)\leq_{K_i} 0 \quad i=1,\dots,m \\& Ax=b \end{aligned} $$
with $f_0$ convex, $f_i:\R^{n} \to \R^{k_i}$ convex with respect to [proper cones]() $K_i \subseteq \R^{k_i}$ and twice continuously differentiable. $A∈\R^{p×n}$with $\mathop{\text{rank}}A=p$.

**Def**  <i><u>Generalized Logarithm</u></i>
A function $\psi : \R^q → \R$ is a generalized logarithm for proper cone $K \subseteq \R^q$ if
- $\text{dom}\psi = \text{int} K$ and $\nabla^2 \psi(y) \prec0$ for $y\succ_K 0$
- $ψ(sy)=ψ(y)+θ\log s$ for $y\succ_K0$, $s>0$(here $θ$ is called the degree of $ψ$)
<b><u>e.g.</u></b>
- Nonnegative orthant $K = \R^q_+$and $ψ(y) =\sum_{i=1}^n \log y_i$, with degree $θ = n$.
- Positive semidefinite cone $K = \mathbb{S}_n^+$ and $\psi(Y)=\log \det Y$, with degree $\theta=n$.

**Prop** For any $y\succ_K 0$, we have
$$ \nabla \psi(y) \succeq_{K^{\star}} 0, \quad y^{\mathrm{T}}\nabla\psi(y)=\theta $$

**Def**  <i><u>Generalized Logarithmic Barrier</u></i>
For $f_1(x) \preceq_{K_1} 0, \dots , f_m(x) \preceq_{K_m} 0$, we define the generalized logarithmic barrier as:
$$ \phi_{\text{general}}(x)=-\sum_{i=1}^m \psi_i(-f_i(x))\\ \text{dom}\phi=\{x \mid f_i(x)\prec_{K_i}0 \text{ for all } i\} $$
where $\psi_i$ is a generalized logarithmic function for $K_i$ with degree $\theta_i$. **Def** _Generalized Central Path_
The generalized central path is $\{ x^\star(t) \mid t>0 \}$ where $x^\star(t)$ solves
$$ \begin{aligned}\text{minimize } \quad & tf_0(x)+\phi_{\text{general}}(x) \\\text{subject to } \quad & Ax=b\end{aligned} $$

**Thrm** $x = x^\star(t)$ if there exists a $w ∈\R^p$ such that
$$ t \nabla f_0(x)+\sum_{i=1}^m (\mathrm{D} f_i(x))^{\mathrm{T}} \nabla \psi_i\left(-f_i(x)\right)+A^T w=0 $$
where $\mathrm{D}f_i(x) \in \R^{k_i \times n}$ is the derivative matrix of $f_i$. Therefore, $x^\star(t)$ minimizes Lagrangian $L(x, λ^\star(t), ν^\star(t))$ by rewriting the equation above, where
$$ \lambda_i^{\star}(t)=\frac{1}{t} \nabla \psi_i\left(-f_i\left(x^{\star}\right)\right), \quad \nu^{\star}(t)=\frac{w}{t} $$
with duality gap$$ f_0\left(x^{\star}(t)\right)-g\left(\lambda^{\star}(t), \nu^{\star}(t)\right)=\frac{1}{t} \sum_{i=1}^m \theta_i $$^gdgap

**Algorithm**  <i><u>Generalized Barrier Method</u></i>
Given strictly feasible $x$, $t := t^{(0)} > 0$, $\mu>1$, tolerance $ε > 0$.
Repeat:
1. Centering step: Compute $x^\star(t)$ by minimizing $tf_0 + \phi$, subject to $Ax = b$.
2. Update: $x:=x^\star(t)$.
3. Stopping criterion: quit if $\frac{\sum_i\theta_i}{t} \leq \varepsilon$. (It follows from [proposition](Interior%20Point%20Methods%20in%20Inequality%20Constrained%20Minimization.md#^gdgap))
4. Increase: $t := μt$.