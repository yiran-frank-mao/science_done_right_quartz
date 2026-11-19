## Simple Functions and Measurable Functions

As we defined the [[Measurable Spaces and Functions#^11c83a|measurable functions]], when the domain of a function is endowed with the Lebsgue $\sigma$-algebra, we call it *Lebesgue measurable*:

> [!definition] Lebesgue Measurable Function  
>  A function $f\colon \R^{d} \to \R$ is *Lebesgue measurable* if it is measurable when the domain $\R^{d}$ is endowed with the Lebesgue $\sigma$-algebra. ^d36994

> [!proposition]
> To simplify our notation, we shall often denote the set $\{x \in E : f(x) < a\}$ simply by $\{f < a\}$ whenever no confusion is possible. 
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
> If $f$ and $g$ are measurable, then  
> 5. The integer powers $f^k$, $k \geq 1$ are measurable.  
> 6. $f+g$ and $fg$ are measurable if both $f$ and $g$ are finite-valued.
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

