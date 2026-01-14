---
created: 2024-09-16
updated: 2024-10-24
completed: true
tags:
  - convergence
---
At the moment, the only examples of holomorphic functions that we have are polynomials, exponentials, and functions that we can build out of these using sums, products, and composites. Having a small supply of examples can make it challenging to construct holomorphic functions with certain specific behaviors. One way to expand our supply of examples of holomorphic functions is to think about when the limit of a sequence of holomorphic functions is again holomorphic.

> [!definition] Normal Convergence
> Let $\newcommand{\dd}{\:\mathrm{d}} \newcommand{\C}{\mathbb{C}} D\subset \C$ be a [[Holomorphic and Conformal Maps#^08ef59|domain]], and let $(f_{n})$ be a sequence of [[Relations and Functions#^862dba|functions]] on $D$. We say that the sequence $(f_{n})$ converges normally to $f\colon D\to \C$ or uniformly inside $D$ if for every [[Compactness of Metric Space#^f1fb8b|compact]] subset $K\subset D$, the sequence $(f_{n})$ [[Convergence of Functions#^a59a2d|converges uniformly]] on $K$ to $f$. ^dd2ac8

> [!theorem]
> $f_{n}\to f$ normally on a domain $D\subset \C$ is equivalent to for every $z\in D$, there is an open set $U\subset D$ such that $f_{n}\to f$ uniformly on $U$. ^f32fe1

*Proof*  First prove that local uniform convergence implies normal convergence. Let $K\subset D$ be compact. For each $z\in K$, there is an open set $U_{z}\subset D$ such that $f_{n}\to f$ uniformly on $U_{z}$. Then the collection $\{U_{z}\}_{z\in K}$ forms an open cover for $K$. By compactness, there is a finite subcover $\{U_{z_{1}},\ldots,U_{z_{m}}\}$. Let $U=\bigcup_{i=1}^{m}U_{z_{i}}$. Then $f_{n}\to f$ uniformly on $U$, and hence on $K$. Conversely, if $f_{n}\to f$ normally, then for each $z\in D$, since $D$ is open, there is some $\Delta(z,\epsilon)\subset D$. Notice that $\overline{\Delta(z,\epsilon/2)}\subset D$ is compact, so $f_{n}\to f$ uniformly on $\overline{\Delta(z,\epsilon/2)}$. Thus, $f_{n}\to f$ locally uniformly on the open neighbourhood $\Delta(z,\epsilon/2)$. $\square$

> [!proposition]
> Normal convergence implies [[Convergence of Functions#^6eed8e|pointwise convergence]].

> [!proposition]
> Let $(f_n)$ be a sequence of continuous functions on a domain $D\subset \C$ that converges normally to $f\colon D\to \C$. Then $f$ is continuous.

*Proof*  Fix some $z\in D$. Pick some $U\subset D$ such that $z\in D$ and $f_{n}\to f$ uniformly on $U$. Since $f_{n}$ is continuous, $f$ is continuous at $z$. Therefore $f$ is continuous on $D$. $\square$

> [!proposition]
> Let $D$ be a domain and let $(f_{n})$ be a sequence of functions on $D$ that converges normally to $f\colon D\to \C$. Suppose $\gamma\colon[0,1]\to D$ is a piecewise $C^{1}$ path. Then $$\int_{\gamma}f_{n}(z)\dd z\to\int_{\gamma}f(z) \dd z$$

*Proof*  We utilize ML estimate: $$\begin{aligned}\left|\int_{\gamma}f(z)\dd z-\int_{\gamma}f_{n}(z)\dd z\right|&=\left|\int_{\gamma}f(z)-f_{n}(z)\dd z\right|\\&\leq|\gamma|\sup_{z\in\gamma([0,1])}|f(z)-f_n(z)|\to0\end{aligned}$$since $f_{n}\to f$ uniformly on the compact set $\gamma([0,1])\subset D$. $\square$

>[!remark]
>The above arguments are just similar to the [[Convergence of Functions#^cd69c1|proposition]] in real analysis.

> [!theorem]
> Let $D$ be a domain, let $f_{n}\in H(D)$ for all $n\in\N$, and let $f\colon D \to \C$ be a function. If $f_{n}\to f$ normally on $D$, then $f\in H(D)$ and we have normal convergence of the derivatives: $f^{(k)}_{n}\to f^{(k)}$ normally on $D$.

*Proof*  Note that $f$ is continuous. Fix some $z_{0}\in D$, and pick some $\overline{\Delta(z_{0},r)}\subset D$. Then each $f_{n}\in H\left(\overline{\Delta(z_{0},r)}\right)$, by [[Cauchy Integral Formula for Disks#^80b053|Cauchy integral formula]], for any $z\in \Delta(z_{0},\epsilon)$ we have $$f_n^{(k)}(z)=\frac{k!}{2\pi i}\int_{\partial\Delta(z_0,r)}\frac{f_n(\zeta)}{(\zeta-z)^{k+1}}\dd \zeta$$Claim that $$\frac{k!}{2\pi i}\int_{\partial\Delta(z_0,r)}\frac{f_n(\zeta)}{(\zeta-z)^{k+1}}\dd\zeta\to\frac{k!}{2\pi i}\int_{\partial\Delta(z_0,r)}\frac{f(\zeta)}{(\zeta-z)^{k+1}}\dd\zeta $$uniformly on the smaller disk $\Delta(z_{0}, r/2)$. This can be proved by following arguments: $$\begin{aligned}\left|f_n^{(k)}(z)-\frac{k!}{2\pi i}\int_{\partial\Delta(z_0,r)}\frac{f(\zeta)}{(\zeta-z)^{k+1}}\dd\zeta\right|&=\left|\frac{k!}{2\pi i}\int_{\partial\Delta(z_0,r)}\frac{f_n(\zeta)-f(\zeta)}{(\zeta-z)^{k+1}}\dd\zeta\right|\\&\leq\frac{k!}{2\pi}\cdot2\pi r\cdot\sup_{|\zeta-z_0|=r}\frac{|f_n(\zeta)-f(\zeta)|}{|\zeta-z|^{k+1}}\end{aligned}$$where as $z\in \Delta(z_{0}, r/2)$, we have $|\zeta-z|\geq \frac{r}{2}$, so that $$\frac{k!}{2\pi}\cdot2\pi r\cdot\sup_{|\zeta-z_0|=r}\frac{|f_n(\zeta)-f(\zeta)|}{|\zeta-z|^{k+1}}\leq2\frac{k!}{r^k}\sup_{|\zeta-z_0|=r}|f_n(\zeta)-f(\zeta)|$$Now because $f_{n}\to f$ on the compact set $\partial\Delta(z_{0}, r)$, the right-hand side goes to zero as $n\to\infty$. Therefore the claim is proved.
Consider the case $k=0$, we obtain $$f_{n}(z) \to \frac1{2\pi i}\int_{\large|\zeta-z_0|=r}\frac{f(\zeta)}{\zeta-z}\dd\zeta $$uniformly on $\Delta(z_{0}, r/2)$. Since $f_{n}\to f$ normally, $f_{n} \to f$ pointwise on $\Delta(z_{0}, r/2)$, by uniqueness of the limit, we conclude that $$f(z)=\frac1{2\pi i}\int_{|\zeta-z_0|=r}\frac{f(\zeta)}{\zeta-z}\dd\zeta $$on $\Delta(z_{0}, r/2)$. It follows that $f$ is holonomic on $\Delta(z_{0}, r/2)$. Since $z_{0}$ is arbitrary, $f\in H(D)$. Then normal convergence of the derivatives follows from the above claim. $\square$
