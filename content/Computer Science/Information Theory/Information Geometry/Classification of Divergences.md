**Def**  <i><u>Divergence</u></i>
The divergence is a real-valued function $\mathcal{D}(p: q)$ with $p$ and $q$ be two probability measures defined on the same measurable space. It satisfies
- $\mathcal{D}(p: q)\geq0$ with equality holds iff $p=q$.
- $\mathcal{D}$ may not be symmetric: $\mathcal{D}(p:q)\neq \mathcal{D}(q:p)$ in general.
- $\mathcal{D}$ may not satisfy the triangle inequality.
Therefore, $\mathcal{D}$ is not a metric distance.
![div|400](https://i.imgur.com/CSxW8uJ.png)

**Def**  <i><u>Locally-Rao</u></i>
A divergence $\mathcal{D}$ is called locally-Rao, if$$\mathcal{D}(\theta:\theta+\dd\theta)=\frac12\dd\theta^{\top}I(\theta)\dd\theta+O(\|\dd\theta\|^3).$$

**Def**  <i><u>$f$-Divergence</u></i>
For probability distribution $p\ll q$, we define:$$\mathcal{D}_f\left(p:q\right)=\int q(x)f\left(\frac{p(\chi)}{q(\chi)}\right)\dd\nu$$ where $f\colon(0,\infty)\to\R$ with properties that $f(1)=0$ and $f^{\prime\prime}(x)\geq 0$. Clearly $f$ is [[Convex Functions#^c53709|convex]] and we have $\E_{p}(f (x)) \geq f (\E_{p}[x] )$, yielding that $\mathcal{D}_{f}(p: q)\geq0$.

**Thrm**  $\mathcal{D}_{f}(p:q)$ is [[Convex Functions#^c53709|convex]] w.r.t. $p$.

**Prop**  $f$-divergence is locally-Rao.

**Def**  <i><u>$\alpha$-Divergence</u></i>
Suppose $\alpha\in\R\setminus\{-1,1\}$, plug $$f_\alpha(x)=\frac4{1-\alpha^2}\left(1-x^{\frac{1+\alpha}2}\right)$$into the definition of $f$-divergence, we get $$D_{\alpha}(p:q)=\frac4{1-\alpha^2}\left(1-\int p^{\frac{1+\alpha}2}(x)q^{\frac{1-\alpha}2}(x)\dd\nu\right)$$
**Prop**
- $f$-divergence with $f (t ) = t \log t$ is exactly the KL divergence.
- $f$-divergence with $f (t ) = − \log t$ is the reverse KL divergence.
- $\lim_{α→1}\mathcal{D}_α(p : q) = \mathcal{D}_{KL}(p : q)$.

**Prop**  <i><u>KL Divergence of Exponential Family</u></i>
The KL divergence of exponential family $p$ and $q$ is$$\mathcal{D}_{KL}(p:q)=\varphi(\eta_p)-\eta_p^\top\theta_q+\psi(\theta_q)$$
