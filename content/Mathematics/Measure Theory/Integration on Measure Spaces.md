## Real-valued Measurable Functions

To discuss integration, we have to focus on functions with values in the extended real numbers.

> [!proposition]
> A function $f$ on a [[Measurable Spaces and Functions#^c2e020|measure space]] $(X,\mathcal{S},\mu)$ with values in the extended real numbers $[-\infty,\infty]$ (with standard Borel sigma algebra) is measurable if and only if $f^{-1}([-\infty,a])\in \mathcal{S}$ for all $a\in \R$.
> 

> [!definition] Integrable Functions
> Suppose $(X,\mathcal{S},\mu)$ is a measure space. A measurable function $f\colon X\to \hat{\R}$ is integrable if $$\int_{X} |f(x)|\dd\mu(x)<\infty.$$ ^56d25a

## Properties of Integration

The elementary properties of integral continue to hold:

> [!proposition]
> The following properties hold for integrals on a measure space $(X,\mathcal{S},\mu)$:
> - **Linearity**: $\int (a f + b g) = a \int f + b \int g.$ 
> - **Additivity**: If $E$ and $F$ are disjoint subsets of $X$, then $\int_{E \cup F} f = \int_E f + \int_F f.$
> - **Monotonicity**: If $f \leq g$, then $\int f \leq \int g.$
> - **Triangle inequality**: $\left| \int f \right| \leq \int |f|.$
> $\quad$

The basic limit theorems also hold:

> [!lemma] Fatou's Lemma
> If $\{f_{n}\}_{n=1}^{\infty}$ is a sequence of non-negative measurable functions on $(X,\mathcal{S},\mu)$, then $$\int\liminf_{n\to \infty} f_{n}\dd\mu \leq \liminf_{n\to \infty} \int f_{n} \dd\mu.$$

> [!theorem] Monotone Convergence Theorem
> If $\{f_{n}\}_{n=1}^{\infty}$ is a sequence of non-negative measurable functions with $f_n\nearrow f$ on $(X,\mathcal{S},\mu)$, then $$\lim_{n\to \infty} \int f_{n} \dd\mu = \int f \dd\mu.$$

> [!theorem] Bounded Convergence Theorem
> If $\{f_{n}\}_{n=1}^{\infty}$ is a sequence of measurable functions on $(X,\mathcal{S},\mu)$ with $\mu(X)<\infty$ and $\|f_{n}\|_{\infty}\leq M$ for all $n$. If $f_{n}\to f$ a.e., then $$\lim_{n\to \infty} \int f_{n} \dd\mu = \int f \dd\mu.$$ ^f80aa2

> [!theorem] Dominated Convergence Theorem
> If $\{f_{n}\}_{n=1}^{\infty}$ is a sequence of measurable functions with $f_n\to f$ pointwise a.e. on $(X,\mathcal{S},\mu)$, and $|f_{n}|<g$ for some integrable $g$, then $$\lim_{n\to \infty} \int f_{n} \dd\mu = \int f \dd\mu.$$

## The Space of Integrable Functions

> [!definition] $L^1(X,\mu)$
> We denote by $L^{1}(X,\mu)$ the space of all integrable functions on $(X,\mathcal{S},\mu)$, modulo the equivalence relation of being equal almost everywhere, with the norm defined by the integral of the absolute value: $$\|f\|_{L^{1}}=\int_{X} |f(x)| \dd\mu.$$

> [!proposition]
> The space $L^{1}(X,\mu)$ is a [[Complete Metric Space#^67b510|complete]] [[Normed Spaces#^345fd3|normed vector space]].
> 

> [!definition] $L^2(X,\mu)$
> We define $L^{2}(X,\mu)$ to be the  equivalence classes of measurable functions for which $\int_{X}|f(x)|^{2}\dd\mu < \infty$. It posses an inner product: $$\langle f,g\rangle:=\int_{X} f\bar{g}\dd\mu,$$which induces a norm $$\|f\|_{L^{2}}=\left( \int_{X} |f(x)|^2 \dd\mu \right)^{1/2}.$$ ^e45bb9

> [!proposition]
> The space $L^{2}(X,\mu)$ is a (possibly non-separable) [[Hilbert Spaces#^ae0212|Hilbert space]].
> 

> [!proposition]
> Suppose $(X,\mathcal{S},\mu)$ is a measure space. Then any $f\in L^2(E)$ for $E\subset X$ is integrable if $\mu(E)<\infty$.

*Proof*  This follows from the Cauchy-Schwarz inequality: $$\int_{E}|f(x)|\dd\mu(x)\leq \left(\int_{E}|f(x)|^{2}\dd\mu(x)\right)^{1/2}\left(\mu(E)\right)^{1/2}<\infty.$$ $\square$

## Product Measures and Fubini's Theorem

> [!definition] Measurable Rectangle
> Let $(X_{1},\mathcal{S}_{1})$ and $(X_{2},\mathcal{S}_{2})$ be measurable spaces. A measurable rectangle is a set of the form $A \times B$, where $A \in \mathcal{S}_{1}$ and $B \in \mathcal{S}_{2}$.

> [!lemma] 
>  Let $(X_{1},\mathcal{S}_{1})$ and $(X_{2},\mathcal{S}_{2})$ be measurable spaces. Then $$ \mathcal{S}_{1} \otimes \mathcal{S}_{2}:=\left\{\bigcup_{i=1}^{n} A_i \times B_{i} : A_{i} \in \mathcal{S}_{1}, B_i \in \mathcal{S}_{2}\right\} $$is a $\sigma$-algebra on $X_{1} \times X_{2}$. It is the smallest $\sigma$-algebra containing all measurable rectangles.

> [!definition] Product Measure
> Suppose $(X_{1},\mathcal{S}_{1},\mu_{1})$ and $(X_{2},\mathcal{S}_{2},\mu_{2})$ are two measure spaces. A measure $\nu$ on $(X_{1} \times X_{2}, \mathcal{S}_{1}\otimes\mathcal{S}_{2})$ is called a product measure if for all measurable rectangles $A \times B$, we have $$\nu(A \times B) = \mu_{1}(A) \mu_{2}(B).$$

> [!theorem] Product Measure Theorem
> Suppose $(X_{1},\mathcal{S}_{1},\mu_{1})$ and $(X_{2},\mathcal{S}_{2},\mu_{2})$ are two measure spaces. Then there exists a measure $\nu$ on $(X_{1} \times X_{2}, \mathcal{S}_{1}\otimes\mathcal{S}_{2})$ such that $\nu(A \times B) = \mu_{1}(A) \mu_{2}(B)$ for all measurable rectangles $A \times B$. Moreover, if $\mu_{1}$ and $\mu_{2}$ are $\sigma$-finite, then $\nu$ is unique and $\sigma$-finite, and we denote it as $\mu_{1} \times \mu_{2}$.

*Proof*  

> [!theorem] Tonelli's Theorem
> Suppose $(X_{1},\mathcal{S}_{1},\mu_{1})$ and $(X_{2},\mathcal{S}_{2},\mu_{2})$ are two $\sigma$-finite measure spaces, and $f\colon X_{1}\times X_{2}\to [0,\infty]$ is $\mathcal{S}_{1}\otimes\mathcal{S}_{2}$-measurable. Then 
> - $x\mapsto \int_{X_{2}}f(x,y)\dd\mu_{2}(y)$ is an $\mathcal{S}_{1}$-measurable function on $X_{1}$,
> - $y\mapsto \int_{X_{1}}f(x,y)\dd\mu_{1}(x)$ is an $\mathcal{S}_{2}$-measurable function on $X_{2}$,
> 
> and $$\int_{X_{1}\times X_{2}} f\dd(\mu_{1}\times \mu_{2})=\int_{X_{1}}\int_{X_{2}} f\dd\mu_{2}\dd\mu_{1}=\int_{X_{2}}\int_{X_{1}}f\dd\mu_{1}\dd\mu_{2}.$$
> 

> [!theorem] Fubini's Theorem
> Suppose $(X_{1},\mathcal{S}_{1},\mu_{1})$ and $(X_{2},\mathcal{S}_{2},\mu_{2})$ are two $\sigma$-finite measure spaces, and $f\colon X_{1}\times X_{2}\to \hat{\R}$ is $\mu_{1}\times\mu_{2}$-integrable. Then $y\mapsto f(x,y)$ is $\mu_{2}$-integrable for a.e. $y\in X_{2}$, and $x\mapsto f(x,y)$ is $\mu_{1}$-integrable for a.e. $x\in X_{1}$. Moreover, we have 
> - $x\mapsto \int_{X_{2}}f(x,y)\dd\mu_{2}(y)$ is an $\mathcal{S}_{1}$-measurable function on $X_{1}$,
> - $y\mapsto \int_{X_{1}}f(x,y)\dd\mu_{1}(x)$ is an $\mathcal{S}_{2}$-measurable function on $X_{2}$,
> 
> and $$\int_{X_{1}\times X_{2}} f\dd(\mu_{1}\times \mu_{2})=\int_{X_{1}}\int_{X_{2}} f\dd\mu_{2}\dd\mu_{1}=\int_{X_{2}}\int_{X_{1}}f\dd\mu_{1}\dd\mu_{2}.$$