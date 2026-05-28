## Unconstrained Minimization

**Def**  <i><u>Unconstrained Minimization</u></i>
Suppose $f$ is convex and twice continuously differentiable (hence $\text{dom} f$ is open), the unconstrained minimization is as follows:
$$ \begin{aligned} \text{minimize } & f(x)\\ \end{aligned} $$

## Decent Methods

**Def**  <i><u>Decent Method</u></i>
We define the descent methods as an iterative algorithm such that
$$ x^{(k+1)} = x^{(k)} + t(k)∆x^{(k)} \text{ \ with \ } f(x^{(k+1)}) < f(x^{(k)}) $$
where $∆x$ is the step or decent direction, $t$ is the step size or step length.

**Def**  <i><u>Line Search</u></i>
The line search approach(algorithm) output a step size that determines how far $x$ should move along the given descent direction.

**Algorithm** <i><u> Exact Line Search</u></i>
The exact line search algorithm find will output step size such that
$$ t=\argmin_{t>0} f(x+t \Delta x) $$

**Algorithm**  <i><u>Backtracking Line Search</u></i>
With parameters $α ∈ (0,\frac{1}{2}), β ∈ (0, 1)$, starting at $t=1$, repeat $t :=\beta t$ until $f(x+t\Delta x) < f(x) + \alpha t \nabla f(x)^{\mathrm{T}} \Delta x$.
![backtracking-image.png|330](https://i.imgur.com/dZy5iAn.png)
![Backtracking line search vs Exact line search|500](https://i.imgur.com/6QDPY44.png)^bls

**Algorithm**  <i><u>Gradient Descent Method</u></i>
The gradient decent method is a family of decent method with $\Delta x = -\nabla f(x)$. And stopping criterion usually of the form $\|∇f(x)\|_2 \leq ε$.

**Def**  <i><u>Normalized Steepest Descent Direction</u></i>
The normalized steepest descent direction at $x$ given $f$ is
$$ ∆x_{\text{nsd}} = \argmin_{v} \{\nabla f(x)^{\mathrm{T}} v \mid \|v\| = 1\} $$

**Def**  <i><u>Unnormalized Steepest Descent Direction</u></i>
The unnormalized steepest descent direction at $x$ given $f$ is
$$ ∆x_{\text{sd}} = \| \nabla f(x) \|_{*} \cdot \Delta x_{\text{nsd}} $$
where $\| \nabla f(x) \|_{*}^2= - \nabla f(x)^{\mathrm{T}} \cdot \Delta x_{\text{sd}}$

**Algorithm**  <i><u>Steepest Descent Method</u></i>
The steepest decent method is a family of decent method that find the steepest descent direction at point $x$ with $\Delta x = \Delta x_{\text{sd}}$

### Newton’s Method
**Def**  <i><u>Newton Step</u></i>
The newton step is defined as:
$$ \Delta x_{\text{nt}} = −\nabla^2f(x)^{−1}\nabla f(x) $$
$x + \Delta x_{\text{nt}}$ actually minimizes the second-order approximation of $f$ at $x$: $\hat{f}(x+v)=f(x)+\nabla f(x)^{\mathrm{T}}v+ \frac{1}{2} v^{\mathrm{T}} \nabla^2 f(x)v$
**Prop** $\Delta x_{\text{nt}}$ is the steepest descent direction at $x$ in local Hessian norm $\|u\|_{\nabla^2 f(x)} = (u^{\mathrm{T}}\nabla^2f(x)u)^{\frac{1}{2}}$

**Def**  <i><u>Newton Decrement</u></i>
Define the Newton decrement as follows as a measure of the proximity of $x$ to $x^*$:
$$ \lambda(x) = \sqrt{

\nabla f(x)^{\mathrm{T}}\nabla^2f(x)^{-1}\nabla f(x)

} $$

**Algorithm**  <i><u>Newton’s Method</u></i>
Given a starting point $x \in \text{dom}{f}$, tolerance $\varepsilon > 0$.
Repeat the following:
1. Compute the Newton step $\Delta x_{\text{nt}}$ and decrement $\lambda$.
2. Stopping criterion. quit if $\frac{1}{2}λ^2 ≤ ε$.
3. Line search: Choose step size $t$ by [backtracking line search](Descent%20Methods%20in%20Unconstrained%20Optimization.md#^bls)
4. Update: $x:=x+t \Delta x_{\text{nt}}$

**Fact** Cholesky factorization is often used to solve $H=\nabla^2 f(x)$. Let $g=-\nabla f(x)$, we have:
$$ H=LL^{\mathrm{T}}, \quad \Delta x_{\text{nt}}=L^{-\mathrm{T}}L^{-1}g, \quad \lambda = \| L^{-1}g \|_2 $$

**Prop** The Newton’s method is affine invariant, independent of linear changes of coordinates

**Prop** The number of iterations until $f(x) − p^\star ≤ ε$ is bounded above by
$$ \frac{f(x^{(0)})-p^\star}{\gamma}+\log_2 \log_2(\frac{\varepsilon_0}{\varepsilon}) $$
where $γ, ε_0$ are constants that depend on $m, L, x^{(0)}$. The second term is small and almost constant for practical purposes.