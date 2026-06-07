---
created: 2024-07-26
updated: 2024-10-23
---
> [!definition] Connection
> A connection on a [[Vector Bundles#^9cb683|vector bundle]] $E$ over smooth manifold $M$ is a map $\nabla\colon \mathfrak{X}(M) \times \Gamma(E) \to \Gamma(E)$, such that the following hold:
>- $C^{\infty}(M)$-linearity in the first argument: $\nabla_{fX}s=f\nabla_{X}s$ for any $f\in C^{\infty}(M)$;
>- $\R$-linearity in the second argument: $\nabla_X(as+bt)=a\nabla_Xs+b\nabla_Xt$;
>- Leibniz rule: $\nabla_X(fs)=f\nabla_Xs+(Xf)s$ for any $f\in C^{\infty}(M)$.
>$\quad$
> 

An important special case of a connection is the affine connection or covariant derivative:

>[!definition] Affine Connection
>Let $M$ be a smooth manifold. An affine connection on $M$ is a connection on the [[Tangent Vectors and Spaces#^e3492e|tangent bundle]]. Explicitly, it is a map $\nabla\colon \mathfrak{X}(M) \times \mathfrak{X}(M) \to \mathfrak{X}(M)$, such that the following hold:
>- Linearity in the first argument: $\nabla_{aX+bY}Z=a\nabla_XZ+b\nabla_YZ$;
>- Leibniz rule: $\nabla_X(fY)=f\nabla_XY+(Xf)Y$ for any $f\in C^{\infty}(M)$.
>
> Affine connection is also called the covariant derivative. ^f86a0b

> [!definition] Section
> A section $s$ of the vector bundle $E$ is called parallel (with respect to a connection $\nabla$) if $\nabla_X s=0$ for all $X\in \mathfrak{X}(M)$.

**Def**  <i><u>Covariant Derivative of Real Functions</u></i>
Given a point $p\in M$ of the manifold $M$, a real function $f\colon M\to \R$ on the manifold and a tangent vector $v\in T_{p}M$, the covariant derivative of $f$ at $p$ along $v$, denoted $\nabla_{v}f$, is a scalar that represents the principal part of the change in the value of $f$ when the argument of $f$ is changed infinitesimally in the same direction  as the displacement vector $v$. Formally, there is a differentiable curve $\gamma\colon[-1,1]\to M$ such that $\gamma(0)=p$ and $\gamma^{\prime}(0)=v$, and the covariant derivative of $f$ at $p$ is defined by $$\nabla_{v}f=v(f)=\left(f\circ\gamma\right)^{\prime}(0)=\lim_{t\to0}\frac{f(\gamma\left(t\right))-f(p)}t$$When $X\colon M \to TM$ is a vector field on $M$, the covariate derivative $\nabla_{X} f\colon M \to \R$ is the function that assigns each point $p$ a scaler $\nabla_{X(p)}f$. Notice that this derivative exists without a definition of connection. So we simply write $Xf$ instead of $\nabla_{X}f$.

## Connection Coefficients

>[!definition] Christoffel Symbols of The Second Kind
>Suppose we are working in a chart $φ \colon U → V ⊂ \R^{n}$ for $M$, with corresponding coordinate tangent vectors $∂_{1},\dots,∂_{n}$, and write $\nabla_{j}$ for $\nabla_{\partial_{j}}$. The Christoffel symbols (of the second kind) or connection coefficients of a connection $∇$ with respect to this chart are defined by $$\nabla_{i}\partial_j={\Gamma^{k}_{ij}}\partial_k$$^2f05b3

>[!proposition]
> The connection is determined on $U$ by the connection coefficients.

*Proof*  Write $X = X^{i}∂_{i}$. Then we have for any vector $v = v^{k}∂_{k}$, $$\nabla_vX=\nabla_v\left(X^i\partial_i\right)=v(X^i)\partial_i+X^i\nabla_v\partial_i=v(X^i)\partial_i+v^kX^i{\Gamma_{ki}}^j\partial_j$$

## Parallel Transport

>[!definition] Parallel
>Let $M$ be a manifold with an affine connection $\nabla$ Then a vector field $X$ is said to be parallel if for any vector field $Y$, $∇_{Y}X = 0$.

>[!remark]
>Intuitively, parallel vector fields have all their derivatives equal to zero and are therefore in some sense constant.

>[!definition] Parallel Transport
>If $\gamma\colon I \to M$ is a smooth map parameterized by an interval $I=[a, b]$ and $\xi\in T_{\gamma(a)}M$, then a vector field $X$ along $\gamma$ is called the parallel transport of $\xi$ along $\gamma$ if it satisfies the following conditions:
>- $\nabla_{\gamma^{\prime}(t)}X=0$ for all $t\in[a,b]$;
>- $X\big|_{\gamma(a)}=\xi$.
>
>![|200](https://svgshare.com/i/18cS.svg)
> ^f4dfd3

> [!definition] Geodesic
> A curve $\gamma\colon [0,1]\to M$ on a smooth manifold with an affine connection $\nabla$ is a geodesic if $\nabla_{\dot{\gamma}}\dot{\gamma}=0.$

## Natural Dual Connection

>[!definition] Dual Connection
>Given a connection $\nabla$ on a vector bundle $E$ over manifold $M$, the dual connection $\nabla^{*}$ on the [[Vector Bundles#^3c3b98|dual bundle]] is naturally defined by the following equation: $$(\nabla^{*}_{X}\varphi)(v)=X(\varphi(v))+\varphi(\nabla_{X}v)$$for all $X\in\mathcal{X}(M)$. ^944a20

