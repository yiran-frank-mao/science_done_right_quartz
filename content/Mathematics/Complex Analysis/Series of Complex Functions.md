---
created: 2024-09-16
updated: 2024-10-15
completed: true
tags:
  - series
  - convergence
---
## Series of Functions

A particular important class of sequence of functions are series of functions. The series $\newcommand{\R}{\mathbb{R}}\newcommand{\N}{\mathbb{N}}\newcommand{\C}{\mathbb{C}}\sum_{n=0}^{\infty}f_{n}$ refers to the limit of sequence of partial sums $\lim_{N\to \infty}\sum_{n=0}^{N}f_{n}$, and the series is said to converge pointwise/uniformly/normally if the sequence of partial sums converges pointwise/uniformly/normally.

> [!definition] Absolute Convergence of Series of Functions
> A series of functions $\newcommand{\N}{\mathbb{N}}\newcommand{\R}{\mathbb{R}}\newcommand{\C}{\mathbb{C}}\newcommand{\dd}{\:\mathrm{d}}\sum_{n=0}^{\infty}f_{n}$ is said to converge absolutely on a set $S$ if it converges pointwise absolutely, that is, if the series $\sum_{n=0}^{\infty}|f_{n}(z)|$ converges for each $z\in S$.

> [!proposition]
> We have the following properties for complex series:
> 1. Let $\sum_{n=0}^{\infty}z_{n}$ be an absolutely convergent series. Then any reodering of the series converges to the same value.
> 2. If $\sum_{n,m=0}^\infty|z_{n,m}|$ converges, then $$\sum_{n=0}^\infty\left(\sum_{m=0}^\infty z_{n,m}\right)=\sum_{m=0}^\infty\left(\sum_{n=0}^\infty z_{n,m}\right)=\sum_{n,m=0}^\infty z_{n,m}$$
> 3. If both $\sum_{n=0}^{\infty}z_n$ and $\sum_{n=0}^\infty w_n$ converge absolutely, then $$\left(\sum_{n=0}^\infty z_n\right)\left(\sum_{n=0}^\infty w_n\right)=\left(\sum_{n,m=0}^\infty z_nw_m\right)$$
>$\quad$

> [!proposition] Weierstrass M-test for Numbers
> Let $z_{k}\in \C$ be a sequence, and suppose $a_{k}\in \R$ are nonnegative numbers such that $|z_{k}|\leq a_{k}$ for all $k$ and such that $\sum_{k=0}^{\infty}a_{k}$ converges, then $\sum_{k=0}^{\infty} z_{k}$ converges.

*Proof*  We're aiming to show that partial sum $\sum_{k=0}^{n}z_{k}$ is Cauchy. Let $\varepsilon>0$, $t=\sum_{k=0}^{\infty}a_{k}$ and let $t_{n}=\sum_{k=0}^{n}a_{k}$. Pick $N\in\N$ such that $n\geq N$ implies that $|t-t_{n}|=t-t_{n}<\varepsilon$. Then for $m\geq n\geq N$ we have $$\left|\sum_{k=0}^mz_k-\sum_{k=0}^nz_k\right|=\left|\sum_{k=n+1}^mz_k\right|\leq\sum_{k=n+1}^m|z_k|\leq\sum_{k=n+1}^ma_k\leq\sum_{k=n+1}^\infty a_k=t-t_n<\varepsilon$$Hence the sequence of partial sums is [[Complete Metric Space#^179eeb|Cauchy]] and therefore convergent. $\square$

> [!theorem] Weierstrass M-test for Functions
> Let $S$ be a set, and let $f_{k}\colon S\to \C$ be a sequence of functions indexed by $k$. Let $a_k\in\R$ be a sequence of nonnegative real numbers such that $|f_{k}(z)|\leq a_{k}$ for all $z\in S$ and $\sum_{k=0}^{\infty} a_{k}$ converges. Then the series $\sum_{k=0}^{\infty}f_{k}$ [[Convergence of Functions#^a59a2d|converges uniformly]] and absolutely on $S$.

*Proof*  Apply Weierstrass M-test for numbers to the series $\sum_{k=0}^{\infty} |f_{k}(z)|$ to see that $\sum_{k=0}^{\infty}f_{k}(z)$ converges absolutely.
Now define $F\colon S\to \C, z\mapsto \sum_{k=0}^{\infty}f_{k}(z)$. We just need to check $\sum_{k=0}^{\infty}f_{k}\to F$ uniformly. Let $\varepsilon>0$, $t=\sum_{k=0}^{\infty}a_k$, $t_{n}=\sum_{k=0}^{n}a_k$. Since $\sum_{k=0}^{\infty}a_{k}$ converges, we can find $N\in\N$ such that $n\geq N$ implies that $|t-t_{n}|=t-t_{n}<\varepsilon/2$. Then for $m\geq n\geq N$ we have $$\left|\sum_{k=0}^m f_k(z)-\sum_{k=0}^n f_k(z)\right|=\left|\sum_{k=n+1}^m f_k(z)\right|\leq\sum_{k=n+1}^{m}|f_{k}(z)|\leq\sum_{k=n+1}^{m} a_{k}\leq t-t_n<\varepsilon$$Hence now take the limit as $m\to\infty$ to see that $$\left|F(z)-\sum_{k=0}^nf_k(z)\right|\leq\varepsilon/2<\varepsilon$$Clearly $N$ did not depend on $z$, so the convergence is uniform. $\square$

> [!remark]
> Note that the M-test can only be used on domains where you expect to get uniformly convergence. If you expect to get normal convergence but not uniform convergence, you have to apply the M-test on subdomains. The following example is typical:
> <u><b>e.g.</b></u>  Let $(c_{n})\subset\C$  be a sequence with $|c_{n}|\leq M$. Then $\sum_{n=0}^{\infty}c_{n}z^{n}$ [[Normal Convergence of Holomorphisms#^dd2ac8|converges normally]] and absolutely on $\Delta(0,1)$. Clearly in the case $c_{k}=1$ that the corresponding series does not converge uniformly on $∆(0,1)$. But we can consider the subdomain $∆(0,r)$ for $0<r<1$ and apply the M-test to show that the series converges uniformly on $∆(0,r)$. Since every $z ∈∆(0,1)$ lies in some $∆(0,r)$, this shows that the series converges normally on $∆(0,1)$.

## Complex Power Series

We have seen power series in real analysis before (see [[Series]]). Indeed, the formula for the radius of convergence is the same.

> [!definition] Complex Power Series
> A series of the form $\sum_{n=0}^{\infty}c_{n}(z-a)^{n}$ for $z\in\C$ is called a *power series centered at $a$*. ^4e8565

> [!theorem] Abel's Theorem
> If the power series $\sum_{n=0}^{\infty}c_{n}(z_{0}-a)^{n}$ converges pointwisely for fixed $z_{0}\in\C$, then it converges absolutely and normally on $\Delta(a, |z_{0}-a|)$. ^615906

*Proof*  Fix some arbitrary $0<r<1$ and consider the disk $\Delta(a,r|z_{0}-a|)$. Since $\sum_{n=0}^{\infty}c_{n}(z_{0}-a)^{n}$ converges, we have $$c_{n}(z_{0}-a)^{n}\to 0$$so $|c_{n}(z_{0}-a)^{n}|\leq M$ for some $M>0$. Then for any $z\in \Delta(a,r|z_{0}-a|)$, $$|c_{n}(z-a)^{n}|=|c_{n}(z_{0}-a)^{n}|\cdot \frac{|c_{n}(z-a)^{n}|}{|c_{n}(z_{0}-a)^{n}|}\leq M r^{k}$$. Hence by M-test, $\sum_{n=0}^{\infty}c_{n}(z-a)^{n}$ converges uniformly and absolutely on $\Delta(a,r|z_{0}-a|)$, thus it converges normally and absolutely on $\Delta(a, |z_{0}-a|)$. $\square$

> [!corollary]
> For any power series $\sum_{n=0}^{\infty}c_{n}(z-a)^{n}$ there is a number $R\in[0,\infty]$ such that the series converges absolutely and normally on $\Delta(a,R)$ and diverges when $|z-a|>R$.

*Proof*  Let $S=\left\{z\in\C\mid \sum_{n=0}^{\infty}c_{n}(z-a)^{n} \text{ converges} \right\}$. Let $R=\sup_{z\in S}|z-a|$. By definition of supremum, we may choose a sequence $(z_{n})\subset S$ such that $|z_{n}-a|\to R$. By Abel's theorem, the series converges absolutely and normally on $\Delta(a,|z_{n}-a|)$ for all $n$, so it converges absolutely and normally on $\Delta(a,R)=\bigcup_{i=1}^{\infty} \Delta(a,|z_{i}-a|)$. On the other hand, if $|z-a|>R$, then $z\notin S$, so the series diverges. $\square$

> [!remark]
> Note that $\Delta(a,\infty)=\C$ and $\Delta(a,0)=\emptyset$. This number $R$ is called the *radius of convergence* of the power series, and the disk $\Delta(a,R)$ is called the disk of convergence.

> [!proposition]
> For any $R\in[0,\infty]$, there is a power series $\sum_{n=0}^{\infty}c_{n}(z-a)^{n}$ with radius of convergence $R$.

*Proof*  The power series $\sum_{n=0}^{\infty}n!z^n$ has radius of convergence $0$, as it diverges. Any polynomial has radius of convergence $\infty$, as polynomial is finite, therefore converges anywhere. For $0<R<\infty$, the power series $\sum_{n=0}^{\infty}\frac{z^n}{R^{n}}$ has the radius of convergence $R$.  $\square$

> [!theorem]
> Let $\sum_{n=0}^\infty c_n(z-a)^n$ be a power series, then its radius of convergence is $$R=\left(\lim\sup_{n\to\infty}|c_n|^{1/n}\right)^{-1}.$$ ^2b3316

*Proof*  Notice that $$\lim\sup_{n\to\infty}\left|c_n(z-a)^n\right|^{1/n}=\left|z-a\right|\left(\lim\sup_{n\to\infty}\left|c_n\right|^{1/n}\right)$$By the root test, the series converges if $\left|z-a\right|\left(\lim\sup_{n\to\infty}\left|c_n\right|^{1/n}\right)<1$ and diverges if $\left|z-a\right|\left(\lim\sup_{n\to\infty}\left|c_n\right|^{1/n}\right)>1$. That is $|z-a|<R$ if the series converges and $|z-a|>R$ if the series diverges, yielding the desired result. $\square$
