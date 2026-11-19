## Curves in $\R^{3}$

> [!definition] Differentiable Curve
> A (parametrized) differentiable curve is an infinitely differentiable map $\gamma\colon I → \R^{3}$ of an interval $I= [a, b]$ of the real line $\R$ into $\R^{3}$. Say, $\gamma(t)=(\gamma_{x}(t),\gamma_{y}(t),\gamma_{z}(t))\in\R^{3}$. The variable $t$ is called the parameter of the curve. 
> $\gamma'(t)=\dot{\gamma}(t)$ is called the tangent vector of the curve at $t$. And the image $\gamma(I)$ is called the trace of the curve.

<u><b>e.g.</b></u>  The map $t\mapsto (t,|t|,0)$ is not a parametrized differentiable curve since it is not differentiable at $t=0$.

> [!definition] Singular Point and Regular Curve
> Let $\gamma\colon I\to \R^{3}$ be a differentiable curve. A point $t\in I$ is called a singular point of order $m$ of $\gamma$ if $\gamma^{m+1}(t)=0$. Specifically, a point $\gamma(t)$ is called a singular point (of order $0$) if $\gamma'(t)=0$.
> A curve is called regular if it has no $0$ order singular points.

> [!definition] Arc Length
> The arc length of a regular curve $\gamma\colon [a,b]\to \R^{3}$ from $t_{0}\in[a,b]$ is defined as $$s_{\gamma}^{t_{0}}(t):=\int_{t_{0}}^{t}\|\gamma'(t)\|\dd t$$ where $\|  \cdot \|$ is the Euclidean norm on $\R^{3}$. And write the whole arc length as $L(\gamma):=s_{\gamma}^{a}(b)$.

> [!proposition]
> The parameter $t$ is itself the arc length of the curve $\gamma$ if and only if $\|\gamma'(t)\|=1$ for all $t$.

*Proof*  If $\|\gamma'(t)\|=1$ for all $t$, then $L(\gamma)=\int_{a}^{b}1\,\mathrm{d}t=b-a$. Conversely, if arc length is $t$, then $\dd s_{\gamma}^{a}/\dd t=\|\gamma'(t)\|=1$ for all $t$. $\square$

> [!remark]+
> In this case, we write the tangent vector as $t(s):=\gamma'(s)$.

## Curvature

> [!definition] Curvature
> Let $\gamma\colon L\to \R^{3}$ be a regular curve parametrized by arc length. The curvature of $\gamma$ at a point $s\in L$ is defined as $$\kappa(s)=\|\gamma''(s)\|\in\R^{3}$$ And the inverse of curvature is called the radius of curvature.

<u><b>e.g.</b></u>  If $\gamma$ is a straight line, then $\gamma''=0$ and so $\kappa=0$ everywhere. Conversely, if $\kappa=0$ everywhere, then $\gamma$ is a straight line. A circle of radius $r$ has curvature $\kappa=1/r$.

> [!definition] Normal Vector
> Let $\gamma\colon L\to \R^{3}$ be a regular curve parametrized by arc length. The normal vector of $\gamma$ at a point $s\in L$ with nonzero curvature is defined as a unit vector: $$n(s):=\frac{\gamma''(s)}{\|\gamma''(s)\|}\in\R^{3}$$

> [!proposition]
> The normal vector $n(s)$ is orthogonal to the tangent vector $\gamma'(s)$.

*Proof*  Since $\gamma$ is parametrized by arc length, we have $\|\gamma'(s)\|=1$. So $\langle \gamma''(s), \gamma(s)'\rangle=0$. Then $\langle n(s),\gamma'(s)\rangle=\langle \gamma''(s),\gamma'(s)\rangle/\|\gamma''(s)\|=0$. $\square$

> [!lemma]
> The derivative of normal vector $n'(s)$ is orthogonal to $n(s)$.

*Proof*  We have $$\newcommand{\<}{\left\langle}\newcommand{\>}{\right\rangle}\begin{aligned}
\< n(s), n'(s)\> &=\< \frac{\gamma''(s)}{\|\gamma''(s)\|},\frac{\gamma'''(s)\|\gamma''(s)\|-\|\gamma''(s)\|'\gamma''(s)}{\|\gamma''(s)\|^{2}}\> \\
&=\frac{1}{\|\gamma''(s)\|^{3}} \<\gamma''(s),\gamma'''(s) \|\gamma''(s)\|-\|\gamma''(s)\|'\gamma''(s) \>\\
&= \frac{1}{\|\gamma''(s)\|^{3}} \left(\|\gamma''(s)\|\< \gamma''(s),\gamma'''(s)\>-  \|\gamma''(s)\|'\<\gamma''(s),\gamma''(s)\>\right)
\end{aligned}$$Moreover, compute the derivative: $$\|\gamma''(s)\|'=\frac{1}{2\|\gamma''(s)\|}\cdot 2\< \gamma'''(s),\gamma''(s) \> = \frac{\< \gamma'''(s),\gamma''(s) \>}{\|\gamma''(s)\|}$$Therefore, substituting back, we have $$\< n(s), n'(s)\> = \frac{1}{\|\gamma''(s)\|^{3}} \left(\< \gamma''(s),\gamma'''(s) \>- \< \gamma'''(s),\gamma''(s) \> \right) = 0$$$\square$

> [!definition] Osculating Plane, Binormal Vector
> Let $\gamma\colon L\to \R^{3}$ be a regular curve parametrized by arc length. At $s\in L$ with nonzero curvature, the plane spanned by the unit tangent and normal vectors, $\gamma'(s)$ and $n(s)$, is called the osculating plane at $s$.
> The binormal vector of $\gamma$ at $s$ is defined as the unit vector orthogonal to the osculating plane by cross product: $$b(s)=\gamma'(s)\times n(s)$$

> [!proposition]
> The derivative of binormal vector $b'(s)$ is parallel to $\gamma''(s)$.

*Proof*  We may write $$  b'(s)=t'(s) \times n(s) + t(s) \times n'(s)=t(s) \times n'(s) $$as $t'(s)=\gamma''(s)$ is parallel to $n(s)$. So $b'(s)$ is orthogonal to $t(s)$. Moreover, we have $$\begin{aligned}\<b'(s),b(s)\> &= \<t(s)\times n'(s), t(s)\times n(s) \> \\ &= \<t(s),t(s)\>\<n'(s),n(s)\>-\<n'(s),t(s)\>\<t(s),n(s)\> \\&= 0-0=0\end{aligned}$$Hence $b'(s)$ is orthogonal to $b(s)$. That is $b'(s)$ is parallel to $\gamma''(s)$. $\square$

## Torsion

> [!definition] Torsion
> Let $\gamma\colon L\to \R^{3}$ be a regular curve parametrized by arc length. The torsion of $\gamma$ at a point $s\in L$ with nonzero curvature is defined as $$\tau(s)=\frac{b'(s)}{\|b'(s)\|}$$

> [!remark]+ Geometric Interpretation of Torsion
> Intuitively, the torsion measures how the curve $\gamma$ twists around the binormal vector $b(s)$, and $|b'(s)|$ measures how rapidly the curve pulls away from the osculating plane. Specifically, if $\gamma$ is a plane curve, that is the trace of $\gamma$ is contained in a plane, then the plane of the curve agrees with the osculating plane everywhere and the torsion is zero. Converse is not true in general.

> [!definition] Rectifying Plane, Normal Plane
> Given a regular curve $\gamma\colon L\to \R^{3}$ parametrized by arc length, the rectifying plane at a point $s\in L$ is spanned by the tangent vector $t(s)=\gamma'(s)$ and the binormal vector $b(s)$. 
> The normal plane at $s$ is spanned by the normal vector $n(s)$ and the binormal vector $b(s)$.
> The lines parallel to $n(s)$ and pass through $\gamma(s)$ are called principal normal.
> The lines parallel to $b(s)$ and pass through $\gamma(s)$ are called binormal.

> [!theorem] Frenet Formulas
> A regular curve satisfies the following Frenet formulas: $$\begin{aligned}t'(s)&=k(s)n(s),\\ n'(s)&=-k(s)t(s)-\tau(s) b(s),\\ b'(s)&=\tau(s) n(s)\end{aligned}$$

> [!definition] Rigid Transformation
> A rigid transformation of a subset $X\subset \R^{3}$ is a transformation that preserves the Euclidean distance between any two points in $X$. Indeed, it is a composition of a translation, rotation, and reflection.

> [!proposition]
> Rigid transformations of a curve is a composite of an orthogonal transformation in $\R^{3}$ with positive determinant, and a translation. i.e. $\gamma_{1}$ is a rigid transformation of $\gamma_{2}$ if and only if there exists an orthogonal linear map $\rho\colon \R^{3}\to \R^{3}$ with $\det M(\rho)>0$ and a vector $b\in \R^{3}$ such that $\gamma_{1}(s)=\rho(\gamma_{2}(s))+b$ for all $s$.

> [!theorem] Fundamental Theorem of Curves
> Given differentiable functions $k(s)>0$ and $\tau(s)$, with $s\in L$. Then there exists a unique regular curve $\gamma\colon L\to \R^{3}$, up to a rigid transformation, such that $s$ is the arc length of $\gamma$ and the curvature and torsion of $\gamma$ are $k(s)$ and $\tau(s)$ respectively.

## Global Properties of Plane Curves

> [!theorem] Isoperimetric Inequality
> Let $\gamma\colon [a,b]\to \R^{2}$ be a regular simple closed curve with length $l$, and area $A$ enclosed by $\gamma$. Then the isoperimetric inequality holds: $$4\pi A\leq l^{2}$$with equality if and only if $\gamma$ is a circle.











