---
created: 2024-09-30
updated: 2024-10-15
tags:
  - series
  - convergence
  - limit
completed: true
---
> [!definition] Doubly Infinite Series
> A doubly infinite series is a series of the form: $$\newcommand{\N}{\mathbb{N}}\newcommand{\Z}{\mathbb{Z}}\newcommand{\C}{\mathbb{C}}\newcommand{\dd}{\:\mathrm{d}}\sum_{n=-\infty}^{\infty}a_n$$And define the convergence of a doubly infinite series by breaking it into two series: $$\sum_{n=-\infty}^\infty a_n=\sum_{n=-\infty}^{k}a_n+\sum_{n=k+1}^\infty a_n$$and we say that the doubly infinite series converges (absolutely) if both series on the righthand side converge (absolutely).

> [!warning]+
> $\lim_{N\to\infty}\sum_{n=-N}^{N}a_{n}$ is a different notion of convergence.

> [!definition] Laurent Series
> A Laurent series centered at $a$ is a doubly infinite series of the form: $$f(z)=\sum_{n=-\infty}^{\infty}c_n(z-a)^n$$ ^b16114

> [!proposition]
> A Laurent series [[Normal Convergence of Holomorphisms#^dd2ac8|converges normally]] and absolutely on an annulus: $$\Delta(a,r_1,r_2):=\{z\in\mathbb{C}:r_1<|z-a|<r_2\}$$and diverges outside the annulus, as long as the series converges somewhere.

*Proof*  Any Laurent series can be written as follows: $$\sum_{n=-\infty}^\infty c_n(z-a)^n=\sum_{n=0}^\infty c_{-n-1}\big((z-a)^{-1}\big)^{n+1}+\sum_{n=0}^\infty c_n(z-a)^n$$The first series converges normally and absolutely if $|z−a|^{-1 }<R$, that is on $\Delta(a,1/R)$, and the second series converges absolutely on $\Delta(a,r_1)$, so the Laurent series converges absolutely on $\Delta(a,r_1,r_2)$, letting $R=1/r_2$.
Note that $r_{1}$ and $r_{2}$ are entirely independent, t is possible that $r_{1} ≥r_{2}$, in which case $∆(a,r_{1},r_{2}) = ∅$.

> [!corollary]
> The limit of a Laurent series lies in $H(\Delta(a,r_1,r_2))$, where $\Delta(a,r_1,r_2)$ is the annulus of convergence.

> [!theorem] Laurent Expansion
> Let $f\in H(\Delta(a,r_1,r_2))$. Then there is a unique Laurent series representation centered at $a$ that converges normally and absolutely to $f$. Explicitly, the coefficients are given by: $$c_n=\frac{1}{2\pi i}\int_{|\zeta-a|=\rho}\frac{f(\zeta)}{(\zeta-a)^{n+1}}\dd \zeta$$where $r_1<\rho<r_2$. ^b29923

*Proof*  Without loss of generality, assume $a=0$. Because every Laurent series converges normally and absolutely on its annulus of convergence, it suffices to show that there exists a Laurent series converging pointwise to $f$. Pick some $\rho_{1}$ and $\rho_{2}$ satisfying $r_{1}< \rho_{1}<\rho_{2}<r_{2}$. Since $f\in H(\overline{\Delta(a, \rho_{1}, \rho_{2})})$, we can apply the Cauchy integral formula: $$f(z)=\frac{1}{2\pi i}\int_{\partial \Delta(0,r_1,r_2)}\frac{f(\zeta)}{\zeta-z}\dd \zeta=\color{green}\frac{1}{2\pi i}\int_{|\zeta|=\rho_{2}}\frac{f(\zeta)}{\zeta-z} \dd\zeta\color{blue}-\frac{1}{2\pi i}\int_{|\zeta|=\rho_{1}}\frac{f(\zeta)}{\zeta-z} \dd\zeta$$for $z\in \Delta(0,\rho_{1},\rho_{2})$.
For the green term, we can write: $$\color{green}\begin{aligned}\frac{1}{2\pi i}\int_{|\zeta|=\rho_{2}}\frac{f(\zeta)}{\zeta-z} \dd\zeta &=\frac{1}{2\pi i}\int_{|\zeta|=\rho_{2}}\frac{f(\zeta)}{\zeta}\frac{1}{1-\frac{z}{\zeta}} \dd\zeta\\&=\frac{1}{2\pi i}\int_{|\zeta|=\rho_{2}}\frac{f(\zeta)}{\zeta}\sum_{n=0}^{\infty}\left(\frac{z}{\zeta}\right)^{n}\dd \zeta\\&=\sum_{n=0}^\infty\frac{z^{n}}{2\pi i}\int_{|\zeta|=\rho_{2}}\frac{f(\zeta)}{\zeta^{n+1}} \dd\zeta\end{aligned}$$where we used normal convergence to exchange the sum and the integral in the last equality. Similarly, we can write the blue term as: $$\color{blue}\begin{aligned}-\frac{1}{2\pi i}\int_{|\zeta|=\rho_{1}}\frac{f(\zeta)}{\zeta-z} \dd\zeta&=\frac{1}{2\pi i}\int_{|\zeta|=\rho_{1}}\frac{f(\zeta)}{z}\frac{1}{1-\frac{\zeta}{z}} \dd\zeta\\&=\frac{1}{2\pi i}\int_{|\zeta|=\rho_{1}}\frac{f(\zeta)}{z}\sum_{n=0}^{\infty}\left(\frac{\zeta}{z}\right)^{n}\dd \zeta\\&=\sum_{n=0}^\infty\frac{z^{-(n+1)}}{2\pi i}\int_{|\zeta|=\rho_{1}}f(\zeta)\zeta^{n}\dd\zeta\\&=\sum_{n=-\infty}^{-1}\frac{z^{n}}{2\pi i}\int_{|\zeta|=\rho_{1}}\frac{f(\zeta)}{\zeta^{n+1}}\dd\zeta\end{aligned}$$Therefore, we have: $$f(z)=\color{green}\sum_{n=0}^\infty\frac{z^{n}}{2\pi i}\int_{|\zeta|=\rho_{2}}\frac{f(\zeta)}{\zeta^{n+1}} \dd\zeta\color{blue}+\sum_{n=-\infty}^{-1}\frac{z^{n}}{2\pi i}\int_{|\zeta|=\rho_{1}}\frac{f(\zeta)}{\zeta^{n+1}}\dd\zeta$$Notice that by homotopy invariance, the integrals are independent of the choice of $\rho_{1}$ and $\rho_{2}$, so $$f(z)=\sum_{n=-\infty}^\infty\left(\frac1{2\pi i}\int_{|\zeta|=\rho}\frac{f(\zeta)}{\zeta^{n+1}}\dd\zeta\right)z^{n}$$for any $r_{1}<\rho<r_{2}$.
Now prove the uniqueness. Suppose $\sum_{n=-\infty}^{\infty}c_{n}z^{n}$ converges normally to $f$ on $\Delta(0,r_{1},r_{2})$. Then we can write: $$\small\frac1{2\pi i}\int_{|\zeta|=\rho}\frac{f(\zeta)}{\zeta^{n+1}}\dd\zeta=\frac1{2\pi i}\int_{|\zeta|=\rho}\left(\sum_{m=-\infty}^\infty c_m\zeta^m\right)\zeta^{-n-1}\dd\zeta =\sum_{m=-\infty}^\infty c_m\left(\frac1{2\pi i}\int_{|\zeta|=\rho}\zeta^{m-n-1}\dd\zeta\right)$$When $k\neq -1$, $\int_{|\zeta|=\rho}\zeta^{k}\dd\zeta=0$ since $\zeta\to \zeta^{k}$ has a primitive on $\C\setminus\{0\}$. When $k=-1$, $\int_{|\zeta|=\rho}\zeta^{-1}\dd\zeta=2\pi i$. Therefore, we have: $$\frac1{2\pi i}\int_{\large|\zeta|=\rho}\zeta^{m-n-1}\dd\zeta=\begin{cases}1&n=m\\0&n\neq m\end{cases}$$Thus $$\frac1{2\pi i}\int_{|\zeta|=\rho}\frac{f(\zeta)}{\zeta^{n+1}}\dd\zeta=\sum_{m=-\infty}^\infty c_m\left(\frac1{2\pi i}\int_{|\zeta|=\rho}\zeta^{m-n-1}\dd\zeta\right)=c_n$$Hence the coefficients are unique. $\square$
