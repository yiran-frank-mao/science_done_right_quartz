## Signed Measures and Total Variation

> [!definition] Signed Measure
> A signed measure on a measurable space $(X,\mathcal{S})$ is a function $\mu\colon \mathcal{S}\to (-\infty,\infty]$ such that $\mu(\emptyset)=0$ and $$\mu\left(\bigcup_{k=1}^\infty E_k\right)=\sum_{k=1}^\infty\mu(E_k)$$for any countable collection $\{E_k\}_{k=1}^\infty$ of disjoint sets in $\mathcal{S}$.
> 

<u><b>e.g.</b></u>  Suppose $(X,\mathcal{S},\lambda)$ is a [[Measurable Spaces and Functions#^c2e020|measure space]], and $f\colon X\to\R$ is a measurable function. Then we can define a signed measure $\mu$ on $(X,\mathcal{S})$ by $$\mu(E):=\int_{E} f\dd\lambda.$$

> [!definition] Total Variation
> Let $μ$ be a signed measure on a measurable space $(X,\mathcal{S})$. The total variation of $μ$, denoted by $|\mu|$, is defined for any measurable set $A\in\mathcal{S}$ as: $$|\mu|(A) = \sup_{ A = \bigsqcup_{i=1}^n A_i } \left\{ \sum_{i=1}^\infty |\mu(A_i)| \right\}.$$

> [!theorem] Jordan decomposition 
> Let $\nu$ be a signed measure on a measurable space $(X, \mathcal{F})$. Then there exist two mutually singular finite non-negative measures $\nu^+$ and $\nu^-$, called the *positive variation* and *negative variation* of $\nu$, such that: 
> $$\nu = \nu^+ - \nu^-, \nu^+(E) = \sup_{A \subset E} \nu(A), \nu^-(E) = \sup_{B \subset E} -\nu(B), \nu^+ = \frac{1}{2}(|\nu|+\nu),\nu^- = \frac{1}{2}(|\nu|-\nu)$$
> This decomposition is unique and is known as the *Jordan decomposition* of $\mu$.


## Absolute Continuity and Mutual Singularity
 
> [!definition] Support of a Measure
> Given a measure space $(X, \mathcal{S}, \mu)$, a signed measure $\mu$ is said to be supported on a set $A\subset X$, if for every $E\in \mathcal{S}$, $\mu(E)=\mu(E\cap A)$.
> 

> [!definition] Mutually Singular Measures
> Two signed measures $\mu$ and $\nu$ on a measurable space $(X, \mathcal{S})$ are said to be mutually singular, denoted $\mu\perp\nu$, if there exists disjoint measurable sets $A,B\in\mathcal{S}$ such that $\nu$ is supported on $A$ and $\mu$ is supported on $B$.

> [!definition] Absolute Continuity
> Suppose $\mu$ is a measure and $\nu$ is a signed measure on a measurable space $(X, \mathcal{S})$. We say that $\nu$ is absolutely continuous with respect to $\mu$, denoted $\nu\ll\mu$, if for every measurable set $E\in\mathcal{S}$, if $\mu(E)=0$, then $\nu(E)=0$.
> 

<u><b>e.g.</b></u>  Suppose $(X,\mathcal{S}, \mu)$ is a measure space, and $f\colon X\to [0,\infty]$ is a [[Measurable Spaces and Functions#^11c83a|measurable function]]. Then we can define another measure $\nu$ on $(X,\mathcal{S})$ by $$\nu(E):=\int_{E} f\dd\mu.$$Then clearly that whenever $\mu(E)=0$, the integral $\int_{E} f\dd\mu=0$, so $\nu\ll\mu$. Moreover, if $\mu$ is $\sigma$-finite and and $\mu(f^{-1}(\infty))=0$ then $\nu$ is also $\sigma$-finite.

> [!proposition]
> Suppose $\mu$ and $\nu$ are two measures on a measurable space $(X, \mathcal{S})$. If $\nu(X)<\infty$ and $\nu\ll\mu$, then for all $\varepsilon>0$, there exits some $\delta>0$ such that $\mu(E)\leq \delta$ implies $\nu(E)\leq \varepsilon$ for all measurable sets $E$.
> 

> [!theorem] Radon-Nikodym Theorem
> Suppose $\mu$ is a $\sigma$-finite measure and $\nu$ is a $\sigma$-finite signed measure on the same measurable space $(X,\mathcal{S})$. There exits unique measures $\nu_{a}$ and $\nu_{s}$, such that
> - $\nu=\nu_{a}+\nu_{s}$,
> - $\nu_{s}\perp \mu$,
> - $\nu_{a}\ll\mu$.
> 
> Moreover, there exits a unique integrable function $f\in L^{1}(X,\mu)$ such that $$\nu_{a}(E)=\int_{E} f\dd\mu$$ for all measurable sets $E\in \mathcal{S}$.

> [!remark]
> In the case that $\nu\ll \mu$, $\nu_{s}=0$, and $\nu=\nu_{a}$.
> 
