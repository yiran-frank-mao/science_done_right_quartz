> [!definition] $L^{p}$ Norm of an Integrable Function
> For any integrable function $f\colon \R^d \to \R$, we define the $L^{p}$ norm of $f$ as $$\|f\|_{p} = \left( \int_{\R^{d}} |f|^p \right)^{1/p}.$$In particular, the $L^{1}$ norm is the integral of the absolute value of $f$.

> [!definition] $L^{1}$ Space
> We denote by $L^{1}(E)$ the [[Normed Spaces#^345fd3|normed vector space]] of all integrable functions on $E\subset\R^d$, modulo the [[Relations and Functions#^14741d|equivalence relation]] of being equal almost everywhere, with the norm defined by the $L^{1}$ norm.

> [!proposition]
> The $L^{1}$ norm is a norm on $L^{1}(E)$:
> 1. For all $a \in \C$,  $\|a f\|_{1} = |a| \|f\|_{1}$.
> 2. $\|f + g\|_{1} \leq \|f\|_{1} + \|g\|_{1}$.
> 3. $\|f\|_{1} = 0$ if and only if $f = 0$ a.e.
> $\quad$

> [!theorem] Riesz-Fischer Theorem
> The space $L^{1}(E)$ is [[Complete Metric Space#^67b510|complete]] with respect to the $L^{1}$ norm.

> [!corollary] 
> If $\{f_n\}_{n=1}^{\infty}$ converges to $f$ in $L^1$, then there exists a subsequence $\{f_{n_k}\}_{k=1}^{\infty}$ such that  
> $$f_{n_k}(x) \to f(x) \quad \text{a.e. } x.$$

*Proof*  [[Complete Metric Space#^ad57d2|Any convergent sequence (in a metric space) is Cauchy]], and hence has a Cauchy subsequence. By the completeness of $L^1$, this subsequence converges to some $f$. $\square$

> [!definition] Dense
> We say that a family $\mathcal{G}$ of integrable functions is dense in $L^{1}$ if for every $f\in L^{1}$ and every $\varepsilon>0$, there exists $g\in\mathcal{G}$ such that $\|f-g\|_{1}<\varepsilon$.

<u><b>e.g.</b></u>  The following families are dense in $L^{1}$:
- The [[Lebesgue Measurable Functions#^ad60a2|simple functions]].
- The [[Lebesgue Measurable Functions#^ad60a2|step functions]].
- The continuous functions with compact support.
$\quad$

## Invariance Properties


## Convolution

> [!definition] Convolution
> The convolution of two functions $f,g\in L^{1}(\R^{d})$ is defined by $$(f*g)(x):=\int_{\R^{d}}f(y)g(x-y)\dd y.$$ ^472754

> [!proposition] 
> Convolution is commutative, associative, and distributive over addition. ^f5d23e

## Fubini's Theorem

> [!theorem] Fubini's Theorem
> Suppose $f$ is integrable on $\R^{d_1} \times \R^{d_2}$. Then for almost every $y \in \R^{d_2}$, the slice $f^y(x):=f(x,y)$ is integrable on $\R^{d_1}$, the function defined by $\int_{\R^{d_{1}}} f^{y}(x) \dd x$ is integrable on $\R^{d_2}$. Moreover:
>$$\int_{\R^{d_2}} \left( \int_{\R^{d_1}} f(x,y) \dd x \right)\dd y = \int_{\R^d} f.$$

> [!theorem] Tonelli's Theorem
> Suppose $f$ is non-negative and [[Lebesgue Measurable Functions#^d36994|measurable]] on $\R^{d_1} \times \R^{d_2}$. Then for almost every $y\in\R^{d_{2}}$, the slice $f^y(x):=f(x,y)$ is measurable on $\R^{d_1}$, and the function defined by $\int_{\R^{d_{1}}} f^{y}(x) \dd x$ is measurable on $\R^{d_2}$. Moreover: $$\int_{\R^{d_2}} \left( \int_{\R^{d_1}} f(x,y) \dd x \right)\dd y = \int_{\R^d} f,$$ in the extended sense.