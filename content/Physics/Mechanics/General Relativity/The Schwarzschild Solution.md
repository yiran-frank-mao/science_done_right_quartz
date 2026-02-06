An important solution to the vacuum Einstein equations is given by the Schwarzschild metric, which in so-called Schwarzschild coordinates.

##  Schwarzschild Spacetime

> [!definition] Schwarzschild Spacetime
> The Schwarzschild spacetime is a static, spherically symmetric vacuum solution $\newcommand{\pddf}[2]{\frac{\partial#1}{\partial#2}}\newcommand{\R}{\mathbb{R}}\newcommand{\d}{\mathrm{d}}\newcommand{\Sch}{\mathrm{Sch}}(M_{\Sch},g_{\Sch})$ with $M_{\Sch} \cong \R \times \R_{>0}\times S^2$, where in the standard global coordinates $(t,r,\theta,\phi)$, the Schwarzschild metric takes the form
> $$g_{\Sch} = -\left(1 - \frac{2\mathbf{G}\mathbf{M}}{r\mathbf{c}^{2}}\right)\mathbf{c}^{2} \d t^2 + \left(1 - \frac{2\mathbf{G}\mathbf{M}}{r\mathbf{c}^{2}}\right)^{-1} \d r^{2} + r^{2} \d\theta^{2} + r^2 \sin^2\theta \d\phi^{2},$$
> where $\mathbf{G}$ is the gravitational constant, $\mathbf{M}$ the mass of the gravitating body, and $\mathbf{c}$ the speed of light. For simplicity, we omit the physical constants and write
> $$g_{\Sch} = -\left(1 - \frac{2\mathbf{M}}{r}\right)\d t^2 + \left(1 - \frac{2\mathbf{M}}{r}\right)^{-1} \d r^{2} + r^{2} \d\theta^{2} + r^2 \sin^2\theta \d\phi^{2}.$$

> [!proposition] Eddington–Finkelstein Coordinates
> The Schwarzschild spacetime is isometric to $\R \times \R_{>0} \times S^2$ under a coordinate system $(u, r, \theta, \phi)$, called the Eddington–Finkelstein coordinates, in which the metric takes the form
> $$ g_{\Sch} = -\left(1 - \frac{2\mathbf{M}}{r}\right) \mathrm{d}u^2 \pm 2 \mathrm{d}u \mathrm{d}r + r^2 \mathrm{d}\Omega^2, $$
> where $\mathrm{d}\Omega^2 = \mathrm{d}\theta^2 + \sin^2\theta\,\mathrm{d}\phi^2$.

> [!definition] Spacelike Submanifold
> A three dimensional submanifold $S\subset M$ of a [[The Spacetime#^e502f4|spacetime]] $(M,g)$ is called a spacelike submanifold if the induced metric on $S$ is positive definite, i.e. $g|_{S}$ is a Riemannian metric. Equivalently, this means for all $p\in M$, the vectors in $T_{p}M$ which are orthogonal to the tangent space $T_{p}S$ are causal.

> [!definition] Cauchy Development
> The future (past) Cauchy development of a subset $S\subset M$ of a spacetime $M$ is the set of all points in $M$ that can be reached by a future (past) directed causal (i.e. non-spacelike) curve starting from $S$. The future and past Cauchy development is denoted by $\mathcal{D}^{+}(S)$ and $\mathcal{D}^{-}(S)$, respectively.

> [!definition] Cauchy Surface
> If $S\subset M$ is a spacelike submanifold such that $\mathcal{D}^{+}(S)\cup\mathcal{D}^{-}(S)=M$, then $S$ is called a Cauchy surface of the spacetime $M$.
> 

<u><b>e.g.</b></u>  In Minkowski spacetime, the constant time surfaces $\{t=\mathrm{Const}\}$ are Cauchy surfaces.

## Birkhoff's Theorem

> [!lemma]
> For a spherically symmetric 4 dimensional Lorentzian manifold, there exists a coordinate $(u,r,\theta,\phi)$ such that the metric $g$ has the form
> $$ g=E(u,r) \d u^2 + 2F(u,r)\d u\d r+ H^2(u,r)\d\Omega^2,$$
> with $E(u,r)\neq 0$, where $\d\Omega^2=\d\theta^2 + \sin^2\theta \d\phi^2$ is the standard metric on a 2-sphere.

*Proof*  See [[The Schwarzschild Solution#^c8a38a|Willem's proof]].

> [!theorem] Birkhoff's Theorem
> Any spherically symmetric, asymptotically flat, vacuum spacetime is locally isometric to the Schwarzchild spacetime.

*Proof*  Using the coordinate form of the metric from the above lemma, we compute the Ricci tensor components: $$\begin{aligned}R_{uu} &= \frac{1}{2F^3H} \Big( EFH \partial_r^2 E - 2EFH \partial_r \partial_u F + 2EF \partial_r E \partial_r H \\&\quad - 4EF \partial_u F \partial_r H - EH \partial_r E \partial_r F + 2EH \partial_u F \partial_r F \\&\quad - 4F^3 \partial_u^2 + 2F^2 \partial_u E \partial_r H - 2F^2 \partial_r E \partial_u H + 2F^2 \partial_u F \partial_u H \Big), \\R_{ur} &= \frac{1}{2F^2} \left( -H \partial_r E \partial_r F + 2H \partial_u F \partial_r F + FH \partial_r^2 E - 2FH \partial_r \partial_u F \right. \\&\quad \left. - 4F^2 \partial_r \partial_u H + 2F \partial_r E \partial_r H \right), \\R_{rr} &= \frac{2}{FH} \left( -F \partial_r^2 H + \partial_r F \partial_r H \right), \\R_{\theta\theta} &= \frac{1}{F^3} \left( EFH \partial_r^2 H + EF (\partial_r H)^2 - EH \partial_r F \partial_r H + F^3 - 2F^2 \partial_r \partial_u H \right. \\&\quad \left. - 2F^2 \partial_u H \partial_r H + FH \partial_r E \partial_r H \right), \\R_{\phi\phi} &= R_{\theta\theta} \sin^2(\theta),\end{aligned}$$with all other components vanishing. In vacuum, Einstein's field equations reduce to $$G_{ij} = R_{ij} - \frac{1}{2}g_{ij}(g^{kl} R_{kl}) = \frac{1}{2}R_{ij} = 0,$$so $R_{uu} = R_{ur} = R_{rr} = R_{\theta\theta} = R_{\phi\phi} = 0$. Consider $R_{rr} = 0$, yielding $$-F \partial_r^2 H + \partial_r F \partial_r H = 0.$$If $\partial_r H = 0$, then $R_{\theta\theta} = \frac{1}{F^3} \cdot F^3 = 1 \neq 0$, a contradiction. Hence $\partial_r H \neq 0$, and we obtain $$0 = \frac{-F \partial_r^2 H + \partial_r F \partial_r H}{(\partial_r H)^2} = \partial_r\left( \frac{F}{\partial_r H} \right),$$implying $F = f(u) \partial_r H$ for some function $f(u)$. Since $\d H = \partial_u H \d u + \partial_r H \d r$, we solve for $\d r$: $$\d r = \frac{\d H}{\partial_r H} - \d u.$$Substituting into the metric yields:$$\begin{aligned}g &= E \d u^2 + 2F \d u \d r + H^2 \d\Omega^2 \\&= E \d u^2 + 2F \d u \left( \frac{\d H}{\partial_r H} - \d u \right) + H^2 \d\Omega^2 \\&= (E - 2F) \d u^2 + 2f(u) \d u \d H + H^2 \d\Omega^2.\end{aligned}$$Introduce new coordinates $(\tilde{u}, \tilde{r})$ defined by $$\pddf{\tilde{u}}{u} = f(u), \quad \tilde{r}^2 = H^2.$$Then $\d\tilde{u} = f(u) \d u$ and $\d\tilde{r} = \pm \d H$, so the metric becomes $$g = \tilde{E} \d\tilde{u}^2 \pm 2 \d\tilde{u} \d\tilde{r} + \tilde{r}^2 \d\Omega^2, $$with $\tilde{E} := \frac{E - 2F}{f(u)}$. The metric retains the same functional form, so we reuse the Ricci components. In particular, $R_{\theta\theta} = 0$ gives $$\tilde{E} + 1 + \tilde{r} \partial_{\tilde{r}} \tilde{E} = 0,$$which rearranges to $$\frac{\partial_{\tilde{r}} \tilde{E}}{\tilde{E} + 1} = -\frac{1}{\tilde{r}}.$$Integrating yields $$\log(\tilde{E} + 1) = -\log(\tilde{r}) + \log(2\mathbf{M}),$$where $\mathbf{M}$ depends only on $\tilde{u}$. Thus, $$\tilde{E} = \frac{2\mathbf{M}}{\tilde{r}} - 1.$$Hence the metric becomes    $$g = \left( \frac{2\mathbf{M}}{\tilde{r}} - 1 \right) \d\tilde{u}^2 \pm 2 \d\tilde{u} \d\tilde{r} + \tilde{r}^2 \d\Omega^2,$$which is the Schwarzschild metric in Eddington–Finkelstein coordinates. $\square$


## References

[Willem van Oosterhout, Birkhoff’s theorem in general relativity](https://annegretburtscher.wordpress.com/wp-content/uploads/2019/11/willemvanoosterhout_bscthesis_2019.pdf) ^c8a38a