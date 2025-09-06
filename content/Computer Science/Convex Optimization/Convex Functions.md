---
created: 2023-11-10
updated: 2024-09-17
---
## Convex Functions

**Def**  <i><u>Convex Function</u></i>
A function $\require{mhchem}\newcommand{\R}{\mathbb{R}} f\colon A \to \R$ is convex if $A$ is a convex set and $$ f(\theta x + (1-\theta)y)\leq \theta f(x) + (1-\theta)f(y) $$for all $x,y \in \textbf{dom}f,0\leq \theta \leq 1$ ^c53709

**Def**  <i><u>Strictly Convex</u></i>
A function $f\colon A \to \R$ is strictly convex if $A$ is a convex set and $$ f(\theta x + (1-\theta)y) < \theta f(x) + (1-\theta)f(y) $$for all $x,y \in \textbf{dom}f, x \neq y, 0\ < \theta < 1$ ^0aeb33

**Def**  <i><u>Strongly Convex</u></i>
A convex function $f$ is strongly convex if it has minimum positive curvature everywhere. That is $f$ is strongly convex on $S$ if there exists an $m > 0$ such that $$ \nabla^2f(x) \succeq mI\quad \text{for all $x\in S$} $$

**Def**  <i><u>Concave Function</u></i>
A function $f:\R^n \to \R$ is concave if $−f$ is convex.

**Prop** Affine functions are convex and concave; All norms are convex.

**Thrm** A function $f : \R^n \to \R$ is convex if and only if the function $g : \R \to \R$ that
$$ g(t) = f(x+tv), \quad \textbf{dom}g=\{ t \mid x+tv \in \textbf{dom} f \} $$
is convex for any $x\in \textbf{dom}f, v \in \R^n$

**Def**  <i><u>Extended-Value Extension</u></i>
The extended-value extension $\tilde{f}$ of $f$ is
$$ \tilde{f}(x)= \begin{cases} f(x) , & x\in \textbf{dom}f \\ \infty, & x\notin \textbf{dom}f \end{cases} $$

## Convex Conditions

**Thrm** $f:\R^n \to \R$ is differentiable if $\textbf{dom}f$ is open and the gradient $\nabla f(x)$ exists at each $x \in \textbf{dom}f$.

**Thrm** <i><u>First-Order Condition</u></i>
A differentiable $f$ with convex domain is convex iff:
$$ f(y) \geq f(x) + \nabla f(x)^{\top}(y-x) \text{ for all } x,y \in \textbf{dom} f $$

**Thrm** $f$ is twice differentiable if $\textbf{dom}f$ is open and the Hessian $\nabla^2f(x) \in\mathbb{S}^n$ exists at each $x \in \textbf{dom}f$

**Thrm** <i><u>Second-Order Condition</u></i>
For twice differentiable $f$ with convex domain, $f$ is convex if and only if $\nabla^2f(x) \succeq 0$ for all $x \in \textbf{dom}f$.

## Operations that Preserve Convexity

>[!comment]
>Practical methods for establishing convexity of a function
>1. Verify definition (often simplified by restricting to a line).
>2. For twice differentiable functions, show $\nabla^2f(x) \succeq 0$.
>3. Show that $f$ is obtained from simple convex functions by operations that preserve convexity.
>$\quad$

**Def**  <i><u>Perspective</u></i>
The perspective of a function $f : \R^n \to \R$ is the function $g : \R^n × \R \to \R$ such that $$ g(x,t)=tf(\frac{x}{t}), \quad \textbf{dom}g=\{(x,t)\mid x/t \in \textbf{dom}f, t>0 \} $$

>[!definition] Legendre Transformation
>The conjugate or Legendre transformation of a convex function $f$ is $$ f^{*}(y)=\sup_{x\in \textbf{dom}f}(y^{\top}x-f(x))$$ ![conjugate|300](https://i.imgur.com/Z3XYeyE.png) ^745078

> [!proposition]
> The Legendre transformation is involutive: $f^{**}=f$ for convex $f$.

*Proof*  

> [!proposition] Young's Inequality
> Suppose $f$ is convex, then $$yx\leq f(x)+f^{*}(y)$$

> [!lemma]
> The values of a quadratic form $f$ and of its Legendre transformation $f^{*}$ coincide at corresponding points: $f(\mathbf{x})=f^{*}(\nabla f(\mathbf{x}))$ ^30a07a

*Proof*



**Prop**  <i><u>Operations that Preserve Convexity</u></i>
- **Nonnegative Multiple**: $\alpha f$ is convex if $f$ is convex and $\alpha \geq 0$
- **Sum**: $f_1 + f_2$ is convex if $f_1, f_2$ convex (extends to infinite sums, integrals)
- **Composition with Affine Function**: $f(Ax+b)$ is convex if $f$ is convex.
- **Pointwise Maximum**: if $f_1,f_2,\dots,f_n$ are convex, then $f(x)=\max\{ f_1(x), f_2(x), \dots, f_n(x) \}$ is convex.
- **Pointwise Supremum**: if $f(x,y)$ is convex in $X$ for each $y\in \mathcal{A}$, then $g(x)=\sup_{y \in \mathcal{A}} f(x,y)$ is convex.
- **Composition with Scalar Map**: Suppose $g: \R^{n}\to \R$ and $h: \R \to \R$ and $f = h \circ g$, then $f$ is convex if either
    - $g$ convex, $h$ convex, $\tilde{h}$ nondecreasing
    - $g$ concave, $h$ convex, $\tilde{h}$ nonincreasing
- **Composition with Vector Map**: Suppose $g: \R^{n}\to \R^{k}$ and $h: \R \to \R$ and $f = h \circ g$, then $f$ is convex if either
    - $g$ convex, $h$ convex, $\tilde{h}$ nondecreasing
    - $g$ concave, $h$ convex, $\tilde{h}$ nonincreasing
- **Perspective Transformation**: The perspective of $f : \R^n \to \R$ is convex if $f$ is convex.
- **Conjugate**: The [conjugate](Convex%20Functions.md#^745078) of a function is always convex.





## Epigraph and Sublevel Set

**Def** <i><u>Sublevel Set</u></i>
The $\alpha$-sublevel set of $f : \R^n \to \R$ is
$$ C_\alpha = \{ x\in \textbf{dom}f \mid f(x) \leq \alpha\} $$

**Prop** Sublevel sets of convex functions are convex.

> [!definition] Epigraph
> The epigraph of $f:\R^2 \to \R$ is $$\textbf{epi}f = \{ (x,t)\in \R^{n+1} \mid x\in \textbf{dom}f, f(x) \leq t\}$$![epigraph.png|300](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/epigraph.png)

**Prop** $f$ is convex if and only if $\textbf{epi} f$ is a convex set
![|500](https://i.imgur.com/2NzUAuH.png)

## Quasiconvex

> [!definition] Quasiconvex
> $f:\R^n \to \R$ is quasiconvex if $\textbf{dom} f$ is convex and the sublevel sets $S_\alpha=\{ x \in \textbf{dom} f \mid f(x) \leq \alpha \}$ are convex for all $\alpha$. Equivalently, $f$ is quasiconvex if for all $x,y\in \textbf{dom} f$ and $\theta\in[0,1]$ we have $$ f(\theta x+(1-\theta)y)\leq\max\left\{f(x),f(y)\right\} $$We say $f$ is strictly quasiconvex if $$ f(\theta x+(1-\theta)y)<\max\left\{f(x),f(y)\right\} $$![quasiconvex|300](https://i.imgur.com/9XJoDqs.png
)

**Def**  <i><u>Quasiconcave</u></i>
$f$ is quasiconcave if $−f$ is quasiconvex.

**Prop** All convex functions are quasiconvex.

**Def**  <i><u>Quasilinear</u></i>
$f$ is quasilinear if it is quasiconvex and quasiconcave.

**Thrm**  <i><u>Modified Jensen Inequality</u></i>
Function $f$ is quasiconvex if and only if: $$ 0 \leq \theta \leq 1 \implies f(\theta x+(1-\theta)y)\leq \max\{f(x),f(y)\} $$

**Thrm** <i><u>First-order Condition</u></i>
Differentiable $f$ with convex domain is quasiconvex if and only if: $$ f(y)\leq f(x)\implies\nabla f(x)^{\mathrm{T}}(y-x)\leq0 $$
![firstorder|300](https://i.imgur.com/pTxptkW.png)

**Prop** Sums of quasiconvex functions are not necessarily quasiconvex

## Generalized Convexity

**Def** $f : \R^n \to \R^m$ is $K$-convex if $\textbf{dom}f$ is convex and $$ f(\theta x+(1-\theta)y) \preceq_K \theta f(x)+(1-\theta)f(y) $$for all $x,y \in \textbf{dom}f, 0 ≤ θ ≤ 1$.
<b><u>e.g.</u></b> $f : \mathbb{S}^m \to \mathbb{S}^m$, $f(X) = X^2$ is $\mathbb{S}^m_{+}$-convex.