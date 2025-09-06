## Simple Functions and Measurable Functions

> [!definition] Characteristic Function
> A characteristic function of a set $E$ is a function defined by $$\chi_{E}(x)=\begin{cases}
1,\text{ if }x\in E \\ 0, \text{if }x\notin E\end{cases}$$

> [!definition] Simple Function, Step Function
> A simple function is a function that can be expressed as a finite linear combination of characteristic functions of measurable sets with finite measure: $$f=\sum_{k=1}^{N}a_{k}\chi_{E_{k}}$$where $a_{k}$ are constants. In particular, if each $E_{k}$ is a rectangle, then $f$ is called a step function. ^ad60a2

> [!definition] Lebesgue Measurable Function  
> A function $f\colon E\to [-\infty,\infty]$ defined on a measurable subset $E$ of $\R^d$ is Lebesgue measurable, if the set $f^{-1}(B)$  is Lebesgue measurable for all Borel set $B\subseteq\R$.
> To simplify our notation, we shall often denote the set $\{x \in E : f(x) < a\}$ simply by $\{f < a\}$ whenever no confusion is possible. ^d36994

> [!proposition]
> The followings are equivalent:
> 1. $f$ is Lebesgue measurable.
> 2. $\{f\leq a\}$ or $\{f\geq a\}$ or $\{f<a\}$ or $\{f>a\}$ is measurable for all $a\in \R$. 
> $\quad$

> [!proposition]
> The followings are equivalent for a finite-valued function $f$:
> 1. $f$ is measurable.
> 2. $\{a\leq f<b\}$ is measurable for all $a,b\in\R$.
> 3. $f^{-1}(O)$ is measurable for all open sets $O\subset \R$.
> 4. $f^{-1}(C)$ is measurable for all closed sets $C\subset \R$.
>
>$\quad$

> [!proposition]
> If $f$ is continuous on $\R^{d}$, then $f$ is measurable. If $f$ is measurable and finite-valued, and $\Phi$ is continuous, then $\Phi\circ f$ is measurable. 
> 

> [!proposition]
> Suppose $\{f_{n}\}_{n=1}^{\infty}$ is a sequence of measurable functions. Then $$x\mapsto\sup_{n}f_{n}(x), \quad x\mapsto\inf_{n} f_{n}(x),\quad \limsup_{n\to \infty} f_{n}(x),\quad \liminf_{n\to \infty}f_{n}(x)$$are measurable. In particular, if $\lim_{n\to \infty} f_{n}$ exists a.e., it is measurable.

*Proof*  Note that $\{\sup_{n} f_{n}>a\}=\bigcup_{n}\{f_{n}>a\}$, and $\{\limsup_{n} f_{n}>a\}=\bigcap_{N}\bigcup_{n\geq N}\{f_{n}>a\}$, and other cases are similar. $\square$

> [!proposition]
> If $f$ and $g$ are measurable, then  
> 1. The integer powers $f^k$, $k \geq 1$ are measurable.  
> 2. $f+g$ and $fg$ are measurable if both $f$ and $g$ are finite-valued.
>$\quad$

> [!definition] Almost Everywhere
> We say that a property holds almost everywhere (a.e.) if the set of points where the property fails is a null set.

<u><b>e.g.</b></u>  We say functions $f=g$ a.e. $x\in E$ if $\{x\in E: f(x)\neq g(x)\}$ has (outer) measure zero.

> [!proposition]
> Suppose $f$ is measurable, and $f(x)=g(x)$ a.e. $x\in E$. Then $g$ is measurable.

## Approximation by Simple Functions

> [!theorem]
> Suppose $f$ is a non-negative measurable function on $\R^d$. Then there exists an increasing sequence of non-negative simple functions $\{\varphi_k\}_{k=1}^{\infty}$ that converges pointwise to $f$, namely,  
> $$ \varphi_k(x) \leq \varphi_{k+1}(x) \quad \text{and} \quad \lim_{k \to \infty} \varphi_k(x) = f(x), \quad \text{for all } x. $$ ^ac3203

> [!corollary]
> Suppose $f$ is measurable on $\mathbb{R}^d$. Then there exists a sequence of simple functions $\{\varphi_k\}_{k=1}^{\infty}$ that satisfies  
>  $$|\varphi_k(x)| \leq |\varphi_{k+1}(x)| \quad \text{and} \quad \lim_{k \to \infty} \varphi_k(x) = f(x), \text{ for all } x.$$
> In particular, we have $|\varphi_k(x)| \leq |f(x)|$ for all $x$ and $k$.

We may now go one step further, and approximate by step functions. Here, in general, the convergence may hold only almost everywhere.

> [!theorem]
> Suppose $f$ is measurable on $\mathbb{R}^d$. Then there exists a sequence of step functions $\{\psi_k\}_{k=1}^{\infty}$ that converges pointwise to $f(x)$ for almost every $x$. ^d54652

