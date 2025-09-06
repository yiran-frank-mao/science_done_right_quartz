---
created: 2024-07-26
updated: 2024-10-19
completed: true
---
## Complex Differentiability

>[!definition] $\C$-Differentiability
>Suppose $U\subset \C$ is open, a function $f\colon U \to \C$ is $\C$-differentiable at $z_{0\in}U$ if $$\lim_{\Delta z\to0}\frac{f(z_0+\Delta z)-f(z_0)}{\Delta z}$$exists, in which case we call the limit $f^{\prime}(z_{0})$. Equivalently, $f$ is $\C$-differentiable if there exists a complex number $f'(z_0)$ such that $$\lim_{\Delta z\to0}\frac{|f(z_0+\Delta z)-f(z_0)-f'(z_0)\Delta z|}{|\Delta z|}=0$$ ^44f14c

<u><b>e.g.</b></u> $z \mapsto \bar{z}$ is $\R$-differentiable but not $\C$-differentiable. 

## The Cauchy-Riemann Equations

>[!definition] Cauchy-Riemann Equations
>Let $U\in \C$ be open, let $f\colon U \to \C$, and let $z_{0}=x_{0}+iy_{0}\in U$. Write $f(x+iy)=u(x,y)+i\cdot v(x,y)$. Then the Cauchy-Riemann equations are $$\frac{\partial u}{\partial x}(x_0,y_0)=\frac{\partial v}{\partial y}(x_0,y_{0})=a,\quad \frac{\partial v}{\partial x}(x_0,y_0)=-\frac{\partial u}{\partial y}(x_0,y_0)=b$$ ^cf170c

> [!definition] Dolbeaut Operators
> The Dolbeaut operators for some complex functions are defined as: $$\begin{align}\frac{\partial f}{\partial z}:=\frac12\left(\frac{\partial f}{\partial x}-i\frac{\partial f}{\partial y}\right)\\\frac{\partial f}{\partial\bar{z}}:=\frac12\left(\frac{\partial f}{\partial x}+i\frac{\partial f}{\partial y}\right)\end{align}$$

<u><b>e.g.</b></u>  $$\begin{aligned} \frac{\partial \bar{z}^{2}}{\partial \bar{z}} &= \frac{\partial}{\partial\bar{z}} ((x^2-y^2)+i(-2xy))\\&=\frac12((2x-2iy)+i(-2y-2ix))\\&=2x-2iy=2\bar{z}\end{aligned}$$This agrees with how we think differentiating with respect to $\bar{z}$ should work, and indeed the same goes for applying $\frac{\partial}{\partial z}$ and $\frac{\partial}{\partial \bar{z}}$ to polynomials in $z$ and $\bar{z}$. We will see for one thing that $z\mapsto\bar{z}^{n}$ is $\C$-differentiable only at $z = 0$ by the following theorem:

> [!theorem] 
> Let $U\in \C$ be open, let $f\colon U \to \C$, and let $z_{0}=x_{0}+iy_{0}\in U$. Write $f(x+iy)=u(x,y)+i\cdot v(x,y)$. Then the following are equivalent:
> - $f$ is $\C$-differentiable at $z_{0}$ and $f^{\prime}(z_{0})=a+ib$.
> - $f$ is $\R$-differentiable at $z_{0}$ and the Jacobian $J_{f}(x_{0},y_{0})=\begin{pmatrix}a & -b \\ b & a\end{pmatrix}$.
> - $f$ is $\R$-differentiable at $z_{0}$, and we have the Cauchy-Riemann equations hold.
> - $f$ is $\R$-differentiable at $z_{0}$, and $\frac{\partial f}{\partial\overline{z}}=0$. In this case $f^{\prime}(z_0)=\frac{\partial f}{\partial z}(z_0)$.
>$\quad$ ^754871

*Proof*  The last three arguments are equivalent simply by definition of Jacobian. To see the first two are equivalent, suppose $f'(z_0)=a+ib$, we just check this is equivalent to the Jacobian in terms of multiplication:$$f'(z_0)\Delta{z}=(a\Delta x-b\Delta y)+i(b\Delta x+a\Delta y)$$and accordingly in $\R^{2}$, we have $$\begin{pmatrix}a\Delta x-b\Delta y\\b\Delta x+a\Delta y\end{pmatrix}=\begin{pmatrix}a&-b\\b&a\end{pmatrix}\begin{pmatrix}\Delta x\\\Delta y\end{pmatrix}$$$\square$

<u><b>e.g.</b></u>  Consider $z\mapsto e^{z}$. Cleary $e^{x+iy}=e^{x}(\cos y + i \sin y)$ is  $\R$-differentiable. Now check that the Cauchy-Riemann equation holds: $$\frac{\partial (e^{x}\cos y)}{\partial x}= e^{x}\cos y=\frac{\partial (e^{x}\sin y)}{\partial y},\quad \frac{\partial (e^{x}\sin y)}{\partial x}=e^{x}\sin y=-\frac{\partial (e^{x}\cos y)}{\partial y}$$So $z\mapsto e^{z}$ is $\C$-differentiable everywhere.

> [!corollary]
> $\C$-differentiable functions are [[Continuity on Metric Space#^d3351a|continuous]].

*Proof*  $\C$-differentiability implies $\R$-differentiability, and $\R$-differentiability implies continuity. $\square$

