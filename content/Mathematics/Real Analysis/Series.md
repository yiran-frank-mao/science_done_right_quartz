## Series and Its Convergence

> [!definition] Series Convergence
> Let $\{a_j\}\in\R^n$ and $S_n=\sum_{j=1}^{n}a_j$. We say that the terms $S_n$ are the *partial sums of the series $\sum_{j=1}^{\infty}a_j$*. 
> We say the series $\sum_{j=1}^{\infty}a_j$ *converges* if $\lim_{n\to\infty}S_{n}$ exists, and diverges otherwise.

<u><b>e.g.</b></u>
- Geometric series $\sum_{j=0}^{\infty}a r^{j}$ converges to $\frac{a}{1-r}$ for $|r|<1$ and diverges otherwise.
- Harmonic series $\sum_{j=1}^{\infty}\frac{1}{j}$ diverges.
$\quad$

> [!definition] Absolute Convergence
> A series $\sum_{j=1}^{\infty}a_j$ *converges absolutely* if $\sum_{j=1}^{\infty}|a_j|$ converges.
> A series $\sum_{j=1}^{\infty}a_j$ *converges conditionally* if it converges, but not absolutely.

## Tests for Convergence

> [!theorem] Integral Test
> Suppose $a_{n}=f(n)$ where $f$ is a positive non-increasing integrable function on $[N,\infty)$. Then $\sum_{n=1}^{\infty}a_n$ converges if and only if the improper integral $\int_{N}^{\infty}f(x)\dd x$ converges.

<u><b>e.g.</b></u>  The $p$-series $\sum_{n=1}^{\infty}\frac{1}{n^p}$ converges if and only if $p>1$.

> [!theorem] Simple Comparison Test
> Suppose $\sum_{n=1}^{\infty} a_{n}$ and $\sum_{n=1}^{\infty} b_{n}$ are series with ultimately non-negative terms.
> If $0\leq a_{n} \leq b_{n}$​ for all sufficiently large $n$, and $\sum_{n}b_{n}$​ converges, then $\sum_{n}a_{n}$​ also converges.
> Conversely, if $0\leq b_{n}\leq a_{n}$ for all sufficiently large $n$, and $\sum_{n}b_{n}$ diverges, then $\sum_{n}a_{n}$ also diverges.

There is also a limit version of the comparison test:

> [!theorem] Limit Comparison Test
> Suppose $\sum_{n=1}^{\infty} a_{n}$ and $\sum_{n=1}^{\infty} b_{n}$ are series with ultimately non-negative terms. 
> If $0\leq \lim_{n\to\infty}\frac{a_n}{b_n}<\infty$ then $\sum_{n=1}^{\infty} b_{n}$ converging implies $\sum_{n=1}^{\infty} a_{n}$ converges.
> If $0<\lim_{n\to\infty}\frac{a_n}{b_n}\leq \infty$ then $\sum_{n=1}^{\infty} b_{n}$ diverging implies $\sum_{n=1}^{\infty} a_{n}$ diverges.

<u><b>e.g.</b></u>  Consider $a_{n}=\frac{8n}{9n^{3}+5n^{2}-1}$. Let $b_{n}=\frac{1}{n^{2}}$. Then $\lim_{n\to\infty}\frac{a_n}{b_n}=\lim_{n\to\infty}\frac{8n^3}{9n^{3}+5n^{2}-1}=\frac{8}{9}$. Since $\sum_{n=1}^{\infty} b_{n}$ converges, so does $\sum_{n=1}^{\infty} a_{n}$.

> [!theorem] Ratio Test
> Suppose $\sum_{n=1}^{\infty} a_{n}$ is a series and let $\rho:=\lim_{n\to \infty}\left|\frac{a_{n+1}}{a_{n}}\right|$. Then $\sum^{\infty}_{n=1}a_{n}$ converges absolutely if $\rho<1$, diverges if $\rho>1$, undetermined if $\rho=1$.
> 

## Power Series

> [!definition] Radius of Convergence
> Let $x\mapsto\sum_{n=0}^{\infty}a_n (x-c)^n$ be a power series that converges absolutely for $|x-c|<R$ and diverges for $|x-c|>R$. Such an $R$ is called the *radius of convergence* of the power series.
> 

> [!proposition] Calculating The Radius
> For the power series $\sum_{n=0}^{\infty}a_n (x-c)^n$, the radius of convergence $R$ is given by $$\frac{1}{R}=\limsup_{n\to\infty}|a_n|^{1/n}=\lim_{n\to \infty}\left|\frac{a_{n+1}}{a_{n}}\right|.$$

*Proof*  The first formula comes from the root test, and the second from the ratio test. $\square$

> [!remark]
> Power series has nicer properties in the complex case. In fact, this formula of the radius of convergence can be extended to the complex power series. (See [[Series of Complex Functions#^2b3316|theorem]])
> 
