## Bi-level Optimization

**Def**  <i><u>Bi-level Optimization Problem</u></i>
Bi-level optimization problems refer to two related optimization tasks, each one is assigned to a decision level (i.e., upper and lower levels). The evaluation of an upper level solution requires the evaluation of the lower level.
$$ \begin{aligned} \text{minimize } \quad & J(x,y)\\ \text{subject to }\quad & y\in \argmin_{u} f(x,u) \end{aligned} $$

**Def**  <i><u>Parameterized Optimization Problem</u></i>
Parameterized optimization problem considers optimization problems depending on a parameter and describes how the feasible set, the value function, and the local or global minimizers of the program depend on changes in the parameter. That is we define a solution mapping $x \mapsto y$ as $y(x)=u^\star$:
$$ y(x) \in \left [ \begin{array}{ll}{\operatorname{argmin}_u} & f(x, u) \\ \text{subject to}_u& h_i(x, u)=0, \quad i=1, \ldots, p \\& g_i(x, u) \leq 0, \quad i=1, \ldots, q .\end{array} \right] $$

## Differentiable Optimization

**Thrm**  <i><u>Dini’s Implicit Function Theorem</u></i>
Let $f : \R^n × \R^m → \R^m$ be differentiable in a neighbourhood of $(x, u)$ and such that $f (x, u) = 0$, and let $\frac{\partial f (x, u)}{\partial u}$ be nonsingular. Then the solution mapping $Y$ has a single-valued localization $y$ around $x$ for $u$ which is differentiable in a neighbourhood $X$ of $x$ with Jacobian satisfying
$$ \frac{dy(x)}{dx}=-\left(\frac{\partial f(x,y(x))}{\partial y}\right)^{-1}\frac{\partial f(x,y(x))}{\partial x} $$

<b><u>e.g.</u></b> Circle example: Consider $f (x, y) = x^2 + y^2 − 1$, we have
$$ \frac{\mathrm{d}y}{\mathrm{d}x}=-\left(\frac{\partial f}{\partial y}\right)^{-1}\left(\frac{\partial f}{\partial x}\right)=-\left(\frac1{2y}\right)(2x)=-\frac{x}{y} $$

**Thrm**  <i><u>Differentiating Unconstrained Optimization Problems</u></i>
Let $f : \R × \R → \R$ be twice differentiable and let $y(x)\in\operatorname{argmin}_uf(x,u)$. Then for non-zero Hessian
$$ \frac{\mathrm{d}y(x)}{\mathrm{d}x}=-\left(\frac{\partial^2f}{\partial y^2}\right)^{-1}\frac{\partial^2f}{\partial x\partial y} $$

**Thrm**  <i><u>Differentiating Equality Constrained Optimization Problems</u></i>
Consider functions $f : \R^n × \R^m → \R$ and $h : \R^n × \R^m → \R^q$. Let
$$ y(x)\in\left.\begin{array}{ll}\arg\min_{u\in\mathbb{R}^m}&f(x,u)\\\text{subject to}&h(x,u)=0\end{array}\right. $$
Assume that $y(x)$ exists, that $f$ and $h$ are twice differentiable in the neighbourhood of $(x,y(x))$, and that $\operatorname{rank}(\frac{\partial h(x,y)}{\partial y}) = q$. Then for $H$ non-singular:$$\frac{\mathrm{d}y(x)}{\mathrm{d}x}=H^{-1}A^T(AH^{-1}A^T)^{-1}(AH^{-1}B-C)-H^{-1}B$$where
$$ \begin{array}{ll}A=\frac{\partial h(x,y)}{\partial y}\in\R^{q\times m}

&&B=\frac{\partial^2f(x,y)}{\partial x\partial y}-\sum_{i=1}^q\nu_i\frac{\partial^2h_i(x,y)}{\partial x\partial y}\in\R^{m\times n}\\

C=\frac{\partial h(x,y)}{\partial x}\in\R^{q\times n}&&

H=\frac{\partial^2f(x,y)}{\partial y^2}-\sum_{i=1}^q\nu_i\frac{\partial^2h_i(x,y)}{\partial y^2}\in\R^{m\times m}\end{array} $$
and $\nu \in \R^q$ satisfies $\nu^{\mathrm{T}}A = \frac{\partial f(x,y)}{\partial y}$

**Fact**  <i><u>Dealing with Inequality Constraints</u></i>
Replace inequality constraints with log-barrier approximation, treat as equality constraints if active and ignore otherwise.

**Fact**  At one extreme we can try back propagate through the optimization algorithm, while at the other extreme we can use the implicit differentiation result to hand-craft efficient backward pass code. However, there are also options in between, for example:
- use automatic differentiation to obtain quantities $A$, $B$, $C$ and $H$ from software implementations of the objective and (active) constraint functions.
- implement the optimality condition $∇\mathcal{L} = 0$ in software and automatically differentiate that.