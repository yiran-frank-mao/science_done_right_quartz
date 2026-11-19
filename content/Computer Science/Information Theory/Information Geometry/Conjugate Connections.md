---
created: 2024-10-15
updated: 2024-10-23
---
## Conjugate Connections

>[!definition] Conjugate Connections
>Let $M$ be a [[Manifolds, Atlases and Smooth Structures#^6ef2ef|smooth manifold]] with an [[Connections#^f86a0b|affine connection]] $\nabla$ and [[Riemannian Metrics#^c3ac13|metric]] $g$. The conjugate connection $\tilde{\nabla}$ relative to $g$ is determined by the equation $$X{g}(Y,Z)=g(\nabla_XY,Z)+g(Y,\tilde{\nabla}_{X}Z),\mathrm{~where~}X,Y,Z\in\mathcal{X}(M)$$We also say that $\nabla$ and $\tilde{\nabla}$ are dual with respect to $g$. ^98fcf9

> [!proposition]
> Given a manifold $(M,g, \nabla)$, the conjugate connection $\tilde{\nabla}$ is uniquely determined.

*Proof*  By the definition of conjugate connection, we can drive the coordinate form by $$\begin{aligned}
\partial_{i}(g_{jk}) &= g(\Gamma_{ij}^{l}\partial_{l}, \partial_{k}) + g(\partial_{j}, \tilde{\Gamma}_{ik}^{m}\partial_{m})\\
&= g_{kl}\Gamma_{ij}^{l}+g_{jm}\tilde{\Gamma}_{ik}^{m}\\
&= \Gamma_{kij} + \tilde{\Gamma}_{jik}
\end{aligned}$$Therefore the conjugate connection coefficients are uniquely determined. $\square$

> [!proposition]
> Conjugation is an involution: $\tilde{\tilde{\nabla}}=\nabla$.

**Proof**  By the definition of conjugate connection, we have $$g(\tilde{\tilde{\nabla}}_{X}Y,Z)+g(Y, \tilde{\nabla}_{X}Z)=X{g}(Y,Z)=g(\nabla_XY,Z)+g(Y,\tilde{\nabla}_{X}Z)$$Therefore, $g(\tilde{\tilde{\nabla}}_{X}Y-\nabla_{X}Y,Z)=0$ for all $X,Y,Z\in\mathcal{X}(M)$. Since the metric is non-degenerate, we have $\tilde{\tilde{\nabla}}=\nabla$. $\square$

> [!lemma]
> A pair of [[Conjugate Connections#^98fcf9|conjugate connections]] $(\nabla, \tilde{\nabla})$ on a manifold $(M,g)$ preserves the [[Riemannian Metrics#^c3ac13|metric]] $g$, in the sense that for all $u,v\in T_{p}M$, the [[Connections#^f4dfd3|parallel transport]] of $u$ and conjugate parallel transport of $v$ along any curve $\gamma\colon[0,1]\to M$ with $\gamma(0)=p$ doesn't change the inner product under $g$: $$\newcommand{\<}{\left\langle}\newcommand{\>}{\right\rangle} 
\< \prod_{\gamma(t)}^{\nabla} u, \prod_{\gamma(t)}^{\tilde{\nabla}} v \>=\<u,v\> \quad \text{ for all } t\in [0,1]$$ ^e7aaf0

*Proof*  Since $\nabla$ and $\tilde{\nabla}$ are conjugate, suppose $U$ and $V$ are corresponding parallel transport vector fields of $u$ and $v$. Then we have $$\newcommand{\<}{\left\langle}\newcommand{\>}{\right\rangle} \dot{\gamma}(t)\<U,V\>=\<\nabla_{\dot{\gamma}(t)} U, V\>+\< U, \nabla_{\dot{\gamma}(t)} V \>=0+0=0$$That is $\<U,V\>$ remains unchanged along $\gamma$. $\square$

> [!theorem]
> Conjugate of a flat connection is flat.

*Proof*  Suppose $\nabla$ is flat. By [[Conjugate Connections#^e7aaf0|the above lemma]], pick $u,v\in T_{p}M$, we have $$\< \prod_{\gamma(t)}^{\nabla} u, \prod_{\gamma(t)}^{\tilde{\nabla}} v \>=\<u,v\> \quad \text{ for all } t\in [0,1]$$holds for any curve $\gamma\colon[0,1]\to M$. For arbitrary curves $\gamma,\beta\colon[0,1]\to M$ with $\beta(1)=\gamma(1)$ and $\beta(0)=\gamma(0)$, we have $$\< \prod_{\gamma(1)}^{\nabla} u, \prod_{\gamma(1)}^{\tilde{\nabla}} v \> =\<u,v\> =\< \prod_{\beta(1)}^{\nabla} u, \prod_{\beta(1)}^{\tilde{\nabla}} v \>$$By flatness of $\nabla$, the parallel transport with respect to $\nabla$ is path independent. That is, $$\prod_{\gamma(1)}^{\nabla}u=\prod_{\beta(1)}^{\nabla}u$$Thus $$\< \prod_{\beta(1)}^{\nabla} u, \prod_{\beta(1)}^{\tilde{\nabla}} v - \prod_{\gamma(1)}^{\tilde{\nabla}} v \>=0$$It follows that $\prod_{\beta(1)}^{\tilde{\nabla}} v = \prod_{\gamma(1)}^{\tilde{\nabla}} v$, and hence the parallel transport with respect to $\tilde{\nabla}$ is also path independent, $\tilde{\nabla}$ is flat as well. $\square$

## Mean Connection

> [!definition] Mean Connection
> Suppose manifold $(M,g)$ is equipped with a pair of conjugate connections $(\nabla, \tilde{\nabla})$, then the mean connection $\bar{\nabla}$ is defined by the following equation: $$\bar{\nabla}:=\frac{1}{2}(\nabla+\tilde{\nabla})$$

> [!proposition]
> The mean connection is self-conjugate.

*Proof*  $$ \newcommand{\<}{\left\langle} \newcommand{\>}{\right\rangle} \begin{aligned}
\<\bar{\nabla}_{X}Y,Z\> + \<Y,\bar{\nabla}_{X}Z\> &= \frac{1}{2}\<\nabla_{X}Y+\tilde{\nabla}_{X}Y,Z\> + \frac{1}{2}\<Y,\nabla_{X}Z+\tilde{\nabla}_{X}Z\>\\
&= \frac{1}{2}\<\nabla_{X}Y,Z\> + \frac{1}{2}\<Y,\nabla_{X}Z\> + \frac{1}{2}\<\tilde{\nabla}_{X}Y,Z\> + \frac{1}{2}\<Y,\tilde{\nabla}_{X}Z\>\\
&= X\<Y,Z\>
\end{aligned}$$
> [!theorem]
> The mean connection coincides with the Levi-Civita metric connection if the conjugate connections are torsion-free.

*Proof*  Suppose $\nabla$ and $\tilde{\nabla}$ are torsion-free, then clearly the mean connection is torsion-free. By the [[Conjugate Connections#^e7aaf0|lemma]], the mean connection, which a linear combination of  $\nabla$ and $\tilde{\nabla}$, also preserves the metric. Therefore, the mean connection is the unique Levi-Civita metric connection. $\square$

> [!corollary]
> The Levi-Civita connection is self-conjugate.

