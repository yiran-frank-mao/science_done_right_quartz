---
created: 2023-11-04
updated: 2026-10-28
completed: true
---
## Polynomials

> [!definition] Polynomial Ring
> Let $R$ be a ring. The polynomial ring in one variable over $R$ is the set of sequences:$$\{ (a_n)_{n=0}^\infty \mid a_n \in R, \exists n_0\in \mathbb{N}, a_n=0 \text{ for all } n\geq n_0  \}$$Equivalently,$$ R[x] = \left\{ \sum_{n=0}^\infty a_n x^n \mid a_n \in R, \exists n_0\in \mathbb{N}, a_n=0 \text{ for all } n\geq n_0  \right\}$$with addition $(a_n)+(b_n)=(a_n+b_n)$ and multiplication $(a_n)\cdot(b_n)=(\sum_{k=0}^n a_kb_{n-k})$.

> [!proposition]
> $R[x]$ is a ring. The identity $1$ is the polynomial $(1+0x+0x^2+\cdots)$.

*Proof*  This is straightforward. $\square$

> [!definition] Degree and Leading Term
> The *degree* of a polynomial $f = \sum_{n} a_{n} x^{n} \in R[x]$, denoted $\deg(f)$, is the largest $n$ with $a_n \neq 0$. The element zero does not have a degree.
> The term $a_{n} x^{n}$ for $n = \deg(f)$ is called the *leading term* of $f$. The polynomial $f$ is called *monic* if the coefficient of the leading term is a [[Ring, Field and Integral Domain#^c4d0ce|unit]].

> [!lemma]
> For all $f,g\in R[x]$, $\deg(f g) \leq \deg(f)+\deg(g)$. In particular, $\deg(f g) = \deg(f)+\deg(g)$ if one of $f,g$ is monic.
> Moreover, it is equality for all $f,g\in R[x]$ if and only if $R$ is an [[Ring, Field and Integral Domain#^domain|integral domain]]. ^296dad

*Proof*  Suppose $f = \sum_{n=0}^{m} a_n x^n$ and $g = \sum_{n=0}^{k} b_n x^n$ with $a_m, b_k \neq 0$. Then the leading coefficient of $fg$ is $a_m b_k$, which is non-zero for all $f$ and $g$ if and only if $R$ is an integral domain. $\square$

> [!proposition]
> If $R$ is an [[Mathematics/Ring Theory/Ring, Field and Integral Domain#^domain|integral domain]], then $R[x]^{\times} = \{r+ 0x+0x^2+\dots \mid r\in R^{\times} \} \cong R^{\times}$, so $R[x]$ is also an integral domain. ^fc05c5

*Proof*  Suppose $R$ is an integral domain. Then $\deg(fg)=\deg (f)+\deg(g)$ for all $f,g\in R[x]$. That is, the degree increases under multiplication, so the only way $fg=1$ or $fg=0$ is when both $f$ and $g$ are constants. So $R[x]^{\times} = \{r+ 0x+0x^2+\dots \mid r\in R^{\times} \} \cong R^{\times}$, and $R[x]$ is also an integral domain. $\square$

> [!remark]- Nonconstant polynomials can be units if $R$ is not an integral domain
> This not true if $R$ is not an integral domain. In $(\Z/4)[x]$, we have 
> $$ (1+2x)(1-2x)=1-4x^{2}=1.  $$
> 

> [!proposition] Universal Property of Polynomial Rings (Substitution Principle)
> Suppose $R,S$ are [[Mathematics/Ring Theory/Ring, Field and Integral Domain#^concept-b822d04b4a4b|commutative unital rings]], and fix some $\alpha\in S$. If $\varphi\colon R\to S$ is a ring homomorphism, then there is a unique ring homomorphism $\Phi\colon R[x]\to S$ that agrees with $\varphi$ on $R$ and that maps $x$ to $\alpha$.
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/polynomial_ring_induced_homomorphism.svg" style="width:20%;"/>
> More generally, given $α_1, \dots , α_n \in S$ there is a unique homomorphism $R[x_1,\dots,x_n]→S$ that agrees with $φ$ on constants and maps $x_k$ to $α_k$.

*Proof Idea*  It is easy to check that $\Phi$ is a homomorphism. In fact, after specifying that $\Phi(x)=\alpha$ and $\Phi(r)=\varphi(r)$ for all $r\in R$, $\Phi$ has been fully determined. $\square$

> [!corollary] Evaluation Homomorphism
> Suppose $R[x]$ is a polynomial ring. Then the evaluation map $\operatorname{ev}_{α} \colon R[x] \to R$ given by $f \mapsto f(α)$ for any $\alpha\in R$ is a ring homomorphism.
> 

*Proof*  This is immediate from the above proposition by considering the identity map $\operatorname{id}\colon R\to R$. $\square$

## Division with Remainder

> [!theorem] Division with Remainder for Polynomials
> Let $R$ be a commutative unital ring and $f,g \in R[x]$ with $f$ monic. Then there are uniquely determined polynomials $q,r \in R[x]$, such that $g = f \cdot q + r$ and such that $\deg(r) < \deg(f)$ or $r=0$. The polynomial $q$ is called the *quotient* and the polynomial $r$ is called the *remainder*. ^71da0e

*Proof by Example*  This process is usually called the *long division*. Consider $R=\Z/4$, $f(x)=3x^{2}+x+2$, $g(x)=2x^{3}+x^{2}+3x+1$. Then we have the following process: $$\begin{aligned} r_{1}(x):=&g(x)-2xf(x)=3x^{2}-x+1, \\ r_{2}(x):=&r_{1}(x)-f(x)=2x+3. \end{aligned}$$Therefore, $g(x)=(2x+1)f(x)+(2x+3)$. Note that requiring $f$ to be monic is crucial here because we need the leading coefficient to be invertible to find out the quotient (i.e., the $2x$ in the first line) at each step. This algorithm is guaranteed to terminate because the degree goes down by each step (ref. [[Polynomial Rings#^296dad|lemma]]). $\square$

> [!corollary]
> Let $g \in R[x]$ and $\alpha \in R$. The remainder of division of $g$ by $x − \alpha$ is $g(\alpha)$. It follows that $x − \alpha$ divides $g(x)$ if and only if $g(\alpha) = 0$.

*Proof*  We have unique $q,r \in R[x]$ such that $g(x) = (x-\alpha) q(x)+r(x)$ and $\deg(r) < \deg (x-\alpha)=1$ or $r=0$, so $r$ is a constant. Let $x=\alpha$, we get $r=g(\alpha)$. Hence $x − α$ divides $g(x)$ if and only if $g(α) = 0$. $\square$

> [!corollary]
> A polynomial in $R[x]$ of degree $n$ over a an integral domain $R$ has at most $n$ roots.

*Proof*  Suppose $f$ has more than $n$ roots $α_1, \dots, α_{m}$ ($m>n$). Then $f$ is divisible by $(x-α_1)(x-α_2) \cdots (x-α_{m})$, which has degree $n+1$. This is impossible since $\deg(f) = n$. $\square$

> [!definition] Multivariable Polynomials
> For $x_1,\dots,x_n$ and $i = (i_1,\dots,i_n) ∈ \mathbb{N}^n$ we write $x^{i}=x_1^{i_1} \dots x_n^{i_n}$. The degree of $x^i$ is $i_1+ \dots + i_n$. The collection of all these is called *the ring of polynomials in $n$ variables* with coefficients in $R$ and denoted $R[x_1,\dots,x_n]$.

> [!proposition]
> $$\frac{R[x,y]}{(f(x),g(y))}\cong\frac{(R[x]/(f(x)))[y]}{g(y)}$$
