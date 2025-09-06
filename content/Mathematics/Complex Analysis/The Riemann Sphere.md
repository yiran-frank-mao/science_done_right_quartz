---
completed: true
updated: 2024-10-29
---
In fact there exists a biholomorphic map between the unit disk $\Delta=\{|z|<1\}$ and the upper half plane $\newcommand{\im}{\operatorname{im}}\newcommand{\C}{\mathbb{C}}\mathbb{H}=\{z\in\C:\im(z)>0\}$. To see why this should be the case, we will turn to a new perspective on the complex plane.

> [!definition] Riemann Sphere and Stereographic Projection
> The Riemann sphere $\newcommand{\hC}{\hat{\C}}\hC$ is the complex plane $\C$ with an additional point $\infty$ added, satisfying $$ \infty+z=\infty, \quad \infty\cdot w = \infty \quad \text{for all }z,w\in\C, w\neq 0 $$
> We define the stereographic projection as the map $\pi\colon S^{2}\to\hat{\C}$ by $$\pi(x,y,w)=\frac{x}{1-w}+\frac{y}{1-w}i$$and its inverse as $$\pi^{-1}(x+iy)=\left(\frac x{1+x^2+y^2},\frac y{1+x^2+y^2},\frac{x^2+y^2}{1+x^2+y^2}\right)$$

![riemann_sphere.png|450](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/riemann_sphere.png)

We will not discuss rigorously about the sphere $S^{2}$, but you can have an idea of what angle between curves on its surface is. A key feature of stereographic projection is:

> [!proposition]
> The stereographic projection is conformal.

So if we have a conformal map $f\colon S^{2}\to S^{2}$, then $\pi \circ f\circ \pi^{-1}$ is a conformal map $\hC\to\hC$.
An obvious map to think about is the map $z \mapsto 1/z$, which is a $180$ degree rotation of the sphere, exchanging $0$ and $∞$.

> [!definition] Continuous, Differentiable and Conformal on $\hC$
> If $D\subset\hC$ is a domain, and $f\colon D\to \hC$, $z_{0}\in D$, we say that $f$ is continuous/$\C$-differentiable/conformal at $z_{0}$ if one of the following holds:
> - $z_0\in\C$ and $f(z_{0})\in\C$, and $f$ is continuous/$\C$-differentiable/conformal at $z_{0}$ in the usual sense.
> - $z_{0}\in\C$ but $f(z_{0})=\infty$, and $1/f$ is continuous/$\C$-differentiable/conformal at $z_{0}$.
> - $z_{0}=\infty$ but $f(z_{0})\in\C$, and $f(1/z)$ is continuous/$\C$-differentiable/conformal at $0$.
> - $z_{0}=\infty$ and $f(z_{0})=\infty$, and $1/f(1/z)$ is continuous/$\C$-differentiable/conformal at $0$.
> $\quad$

<u><b>e.g.</b></u>  Consider $z\mapsto\begin{cases}z^{2}-1 &\quad z\in\C \\ \infty &\quad z=\infty \end{cases}$. Case $z\in\C$, $f(z)\in\C$, so it is $\C$-differentiable at all points in $\C$, in addition, the derivative $2z$ is non-zero everywhere except at $z=0$, hence it is conformal on $\C\setminus\{0\}$. Case $z=\infty$, $f(z)=\infty$, so we consider $$1/f(1/z)=1/((1/z)^{2}-1)=z^{2}/(1-z^{2})$$which maps $0$ to $0$, and is $\C$-differentiable at $0$ with derivative $0$, hence it is $\C$-differentiable at $\infty$ but not conformal.