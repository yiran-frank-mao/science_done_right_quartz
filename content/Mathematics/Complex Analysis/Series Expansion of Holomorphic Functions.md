---
created: 2024-09-23
updated: 2025-05-15
tags:
  - convergence
  - limit
completed: true
---
## Taylor Expansion

> [!proposition]
> Let $f\in H(\Delta(a,r))$ and suppose there is a power series $\sum_{n=0}^\infty c_n(z-a)^n$ converges on $\Delta(a,r)$ to $f$, then $c_n=\frac{f^{(n)}(a)}{n!}$.

*Proof*  By Abel's theorem, the power series converges absolutely and normally on $\Delta(a,r)$, so we can differentiate term by term to get $$f^{(k)}(z)=\sum_{n=0}^{\infty} n(n-1)\dots (n-k+1)c_{n}(z-a)^{n+k}$$Evaluating at $z=a$ yields $$f^{(k)}(a)=k!\cdot c_{k}$$Therefore $c_{n}=\frac{f^{(n)}(a)}{n!}$. $\square$

The above proposition shows that the power series representation of a holomorphic function is unique if it exists. Now let's consider the existence:

> [!proposition]
> Let $f\in H(\Delta(a,r))$. Then there exists a power series $\sum_{n=0}^\infty c_n(z-a)^n$ centered at $a$ converging to $f$ on $\Delta(a,r)$.

*Proof*  First consider the case $a=0$. Pick $\rho<r$, then $f\in H(\overline{\Delta(0,\rho)})$. Fix some arbitrary $z\in \Delta(0,\rho)$. By  [[Cauchy Integral Formula for Disks#^80b053|Cauchy integral formula]] we have $$\newcommand{\dd}{\:\mathrm{d}}f(z)=\frac1{2\pi i}\int_{|\zeta|=\rho}\frac{f(\zeta)}{\zeta-z}\dd\zeta$$For $|\zeta|>|z|$, we have $$\frac{f(\zeta)}{\zeta-z}=\frac{f(\zeta)}\zeta\frac1{1-\frac z\zeta}=\frac{f(\zeta)}\zeta\sum_{n=0}^\infty\left(\frac z\zeta\right)^n$$It follows that $$f(z)=\frac1{2\pi i}\int_{|\zeta|=\rho}\frac{f(\zeta)}{\zeta-z}\dd\zeta=\frac{1}{2\pi i}\sum_{n=0}^{\infty}\left(\int_{|\zeta|=\rho}\frac{f(\zeta)}{\zeta^{n+1}}\dd\zeta\right)z^{n} =\sum_{n=0}^\infty\frac{f^{(n)}(0)}{n!}z^{n}$$Since $z\in \Delta(0,\rho)$ is arbitrary, the power series converges to $f$ on $\Delta(0,\rho)$. As $\rho$ is also arbitrary, the power series converges to $f$ on $\Delta(0,r)$.
Now for the general case $\newcommand{\C}{\mathbb{C}}a\in \C$, we can consider the function $g(z)=f(z+a)$, which is holomorphic on $\Delta(0,r)$, and apply the above argument to get the desired result. $\square$

> [!proposition]
> Suppose the Taylor series of $f\in H(\Delta(a,r))$ centered at $a$ has radius of convergence $R\geq r$, then $\Delta(a,R)$ is the largest disk to which $f$ has a holomorphic extension.

<u><b>e.g.</b></u>
- What is the radius of convergence of the Taylor series of $z\mapsto \frac{1}{1+z^{2}}$ centered at $z = 0$?
  The disk of convergence is the largest disk centered at $0$ such that $z\mapsto \frac{1}{1+z^{2}}$ defined on some $\Delta(0,\varepsilon)$ has a holomorphic extension to. As the function blows up at $\pm i$, the radius of convergence is $1$. Now consider the real function $x\mapsto \frac{1}{1+x^{2}}$, which is smooth and at every point $\newcommand{\R}{\mathbb{R}}a ∈ \R$ its Taylor series converges to $\frac{1}{1+x^{2}}$. However, it has a radius of convergence of $1$. From the real number perspective, there do not appear to be any “problems” with the functions, but the radius of convergence knows about the distance to the nearest “problem point” for the function in the complex plane.
- Extend the above function to a more general case $z\mapsto \frac{1}{p(z)}$, where $p\in \R[z]$ is a polynomial with real coefficients, such that all roots $\lambda_{1}, \lambda_{2},\dots, \lambda_{n}$ lie in $\C\setminus\R$. Then the function $z\mapsto \frac{1}{p(z)}$ is smooth on $\R$, and at every point $a\in\R$ its Taylor series converges to $\frac{1}{p(z)}$. However, the radius of convergence of the Taylor series is the distance to the nearest root of $p$ in the complex plane, i.e. $\min_{1\leq i\leq n}|a-\lambda_{i}|$.
$\quad$

##  The Uniqueness Theorem

> [!theorem] Uniqueness Theorem
> Let $D$ be a [[Holomorphic and Conformal Maps#^c7e434|domain]], and let $f,g\in H(D)$. Suppose there exists a sequence $z_{1},z_{2}\dots \in D$ of distinct points that converges to a limit $a\in D$ such that $f(z_{i})=g(z_{i})$ for all $i$. Then $f=g$. ^b5768d

*Proof*  Without loss of generality, we may assume that $g =0$ (i.e. replace $f$ by $f−g$). Let $S=\{z\in D \mid f^{(n)}(z)=0 \text{ for all } n=0,1,2,\dots\}$. We will show that $S=D$. Since $D$ is connected, by [[Connectedness and Paths#^7a08b9|theorem]], it suffices to show that $S$ is non-empty, [[Open and Closed Sets#^e112b1|open]], and [[Open and Closed Sets#^e112b1|closed]] in $D$.
1. $S$ is non-empty: Suppose $z_{n}\to a$. Assume that $a\notin S$. Then we denote the smallest $n$ such that $f^{(n)}(a)\neq 0$ as $n_{0}$. Choose some $r>0$ such that $\Delta(a,r)\subset D$. For $z\in\Delta(a,r)$ we have a normally convergent power series representation: $$f(z)=\sum_{n=0}^{\infty} \frac{f^{(n)}(a)}{n!}(z-a)^{n}=\sum_{n=n_{0}}^{\infty}\frac{f^{(n)}(a)}{n!}(z-a)^{n}=(z-a)^{n_{0}}\sum_{n=0}^{\infty} \frac{f^{(n+n_{0})}(a)}{n!}(z-a)^{n}$$The power series $\sum_{n=0}^{\infty} \frac{f^{(n+n_{0})}(a)}{n!}(z-a)^{n}$ converges pointwise on $\Delta(a,r)$ as for any fixed $z$, $(z-a)^{n_{0}}$ is constant. Therefore it [[Normal Convergence of Holomorphisms#^dd2ac8|converges normally]] to a holomorphic function $h\in H(\Delta(a,r))$ with $h(a)=f^{(n_{0})}(a)\neq 0$, and we have $$f(z)=(z-a)^{(n_0)}h(z)$$Since $z_{n}$ are distinct and converge to $a$, infinitely many $z_n$ are not equal to $a$, and lie in $\Delta(a,r)$, we denote them as $(z_{k_{n}})_{n=0}^{\infty}$. It follows that for any $i\in \mathbb{N}$ $$0=g(z_{k_{i}})=f(z_{k_{i}})=(z_{k_{i}}-a)^{n_{0}}h(z_{z_{i}})$$It implies that $h(z_{k_{i}})=0$ for all $i$, so $$0=\lim_{i\to \infty } h(z_{k_{i}})=h(a)$$yielding a contradiction. Therefore $a\in S$, $S$ is non-empty.
2. $S$ is open: Fix $b\in S$, then there exists a disk $\Delta(b,r)\subset D$. Since $f$ is holomorphic, the Taylor series of $f$ centered at $b$ converges to $f$ on $\Delta(b,r)$: $$f(z)=\sum_{n=0}^{\infty}\frac{f^{(n)}(b)}{n!}(z-b)^{n}=0$$Therefore $f^{(n)}(z)=0$ for all $n=0,1,2,\dots$, so $z\in S$ for all $z\in \Delta(b,r)$. Hence $\Delta(b,r)\subset S$, $S$ is open.
3. $S$ is closed: Observe that $$S=\bigcap_{n=0}^{\infty}\left(f^{(n)}\right)^{-1}(\{0\})$$Since $f^{(n)}$ is continuous, [[Continuous Functions on Topological Spaces#^30fe04|the preimage of a closed set is closed]], so $S$ is closed.

We conclude that $S=D$, so $f=g$. $\square$

<u><b>e.g.</b></u>
- In fact, the complex exponential and trigonometric functions are the unique holomorphic extension of the corresponding real functions.
- If $f\in H(\overline{D})$, then by definition there exists an open set $U$ containing $\overline{D}$ and a holomorphic function $g\in H(U)$ such that $g|_{D}=f$. By the uniqueness theorem, one can pick a convergent sequence in $D$, therefore $g$ is unique for a given $U$.
$\quad$

> [!theorem] Liouville’s Theorem
> If $f ∈H(\C)$ is bounded, then it is constant. In general, if there exists positive $a,b\in\R$ such that $|f(z)|\leq a|z|^{n}+b$ for all $z\in\C$, then $f$ is a polynomial of degree at most $n$. ^a2323b

