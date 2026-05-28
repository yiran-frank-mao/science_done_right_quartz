---
created: 2024-07-22
updated: 2024-10-29
completed: true
---
## The Complex Plane

> [!definition] Complex Numbers
> The [[Ring, Field and Integral Domain#^575174|field]] of complex numbers, denoted by $\newcommand{\C}{\mathbb{C}}\C$, is the usual Euclidean space $\newcommand{\R}{\mathbb{R}}\R^{2}$ endowed with the additional operation of multiplication of vectors defined as follows: $$(x_{1},y_{1})\cdot (x_{2},y_{2})=(x_{1}x_{2}-y_{1}y_{2},x_{1}y_{2}+x_{2}y_{1})$$And we write $i$ for $(0,1)$, $1$ for $(1,0)$. Therefore $x+yi$ denotes $(x,y)$. ^a81924

> [!remark]+ Alternative Algebraic Definition
> Instead, algebraists define $\C$ as $\R[x]/(x^{2}+1)$ (See [[Relations and Maximal Ideals#^a4b259|here]]). This is equivalent to the above definition, but more algebraic.
> 

> [!definition] Real Part & Imaginary Part
> For any complex number $z=x+iy\in\C$, we call $x$ the real part of $z$, denoted by $\operatorname{Re} z$, and $y$ the imaginary part of $z$, denoted by $\operatorname{\mathrm{Im}} z$. If $\operatorname{\mathrm{Im}} z=0$, the complex number is called real. If $\operatorname{\mathrm{Re}} z=0$, then $z$ is said to be imaginary.

> [!definition] Complex Conjugate
> For complex number $z=x+yi$, we call $\bar{z}=x-yi$ the complex conjugate of $z$.

^50b19e

> [!definition] Modulus
> Define the modulus, or absolute value, of $z=x+yi$ by $$|z|=\sqrt{ z\bar{z} } =\sqrt{ x^2+y^2 }$$ ^add791

> [!proposition]
> $\C$ yields a [[Metric Spaces#^0eacc7|metric space]] by the metric defined by modulus of difference: $$d(z,w)=|z-w|,\quad \text{for all } z,w\in\C$$

*Proof*  Straightforward by definition. $\square$

> [!definition] Reciprocal and Ratio
> The reciprocal or inverse of $z$, denoted by $z^{-1}$, is the unique complex number $w$ such that $wz=1$. The ratio of two complex number is then naturally defined as $$\frac{z_{1}}{z_{2}}=z_{1}z_{2}^{-1}$$

> [!proposition]
> $z^{-1}=\frac{\bar{z}}{|z|^{2}}$.

*Proof*  We have $z\bar{z}=|z|^{2}$, hence $z\cdot\frac{\bar{z}}{|z|^{2}}=1$. $\square$

## The Argument

> [!proposition]
> Given a non-zero $z ∈ \C$, it can be determined by its length $|z|$ and an angle $θ$.

> [!definition] Principle Argument
> There are infinitely many angles that correspond to any arbitrary point $z$, but we distinguish the appropriate angle in $[0, 2π)$, called as the (principal) argument of $z$. And denote $\arg(z)$ with function $\arg\colon\C\setminus \{ 0 \}\to[0,2\pi)$. And define $$\newcommand{\Arg}{\operatorname{Arg}}\newcommand{\Z}{\mathbb{Z}} \Arg(z):=\{  \arg(z)+2\pi k : k\in\Z \}$$

> [!proposition]
> Function $\arg$ is not continuous.

*Proof*  Consider the sequence $z_n=1+i/n$ and $w_n=1-i/n$. Then $\lim_{n\to\infty}z_n=\lim_{n\to\infty}w_n=1$, but $\lim_{n\to\infty}\arg(z_n)=0$ and $\lim_{n\to\infty}\arg(w_n)=2\pi$. $\square$

> [!proposition]
> Let $\Phi \colon \R →\R$ be a continuous function with $\Phi(x) ∈\Arg(e^{ix})$. Then $\Phi(x) = x + 2πk$ for some $k ∈\Z$ independent of $x$.

## Exponential, Logarithm and Powers

> [!definition] Complex Exponential
> Define the exponential function on complex numbers in the following way: $$e^{ x+iy }=e^{ x }\left( \cos(y)+i\sin(y) \right) $$where $e^{ x }$ is the exponential of real numbers. Note that for any $z\in\C\setminus \{ 0 \}$, we have $$z=|z|e^ {i\arg(z)}$$

>[!remark]+
>The differential equations $$\frac{\mathrm{d}}{\mathrm{d}t}e^{ tz }=ze^{ tz },\quad e^{ 0 }=1$$ uniquely determine the form of the function. We actually had no choice, as this function is the unique extension of $e^x$ to $\C$ which is differentiable. See [[Series Expansion of Holomorphic Functions#^b5768d|uniqueness theorem]].

> [!proposition]
> For any $z_{1},z_{2}\in \C$, we have $e^{ z_{1}+z_{2} }=e^{ z_{1} }e^{ z_{2} }$.

*Proof*  We write $z_{1}=x_{1}+iy_{1}$ and $z_{2}=x_{2}+iy_{2}$. Then using the fact that the above property holds for real exponential, and the angle sum formula for sine and cosine, we obtain that: $$\begin{aligned}e^{z_1}e^{z_2}& =e^{x_1}(\cos(y_1)+i\sin(y_1))e^{x_2}(\cos(y_2)+i\sin(y_2)) \\&=e^{x_1+x_2}(\cos(y_1+y_2)+i\sin(y_1+y_2)) \\&=e^{z_1+z_2}\end{aligned}$$$\square$

> [!proposition]
> When multiplying complex numbers, the lengths multiply and the angles add: $$z_{1}z_{2}=|z_{1}||z_{2}|e^{ i(\arg(z_{1})+\arg(z_{2})) }$$

*Proof*  Clearly obtained from the definition of complex multiplication and exponential. $\square$

> [!proposition]
> The complex exponential function is not injective. ^fa54fc

*Proof*  We have $e^{ i\theta }=e^{ i(\theta+2\pi) }$. Indeed $e^{ z_{1} } = e^{ z_{2} }$ if and only if $x_{1} = x_{2}$ and $y_{1}= y_{2} + 2πk$ for some integer $k$. $\square$

> [!definition] Complex Logarithm
> Define the complex logarithm function as follows: $$\ln(z)=\ln|z|+i\arg(z)$$where $\ln|z|$ is the natural logarithm of a positive real number. And define $$\newcommand{\Ln}{\operatorname{Ln}}\Ln(z):=\{ w\in \C : e^{w} =z \}=\{\ln|z|+i\arg(z)+i2\pi k:k\in\mathbb{Z}\}$$

> [!proposition]
> Complex logarithm is the right inverse of complex exponential: $$e^{ \ln z }=z$$

*Proof*  $$e^{ \ln z }=e^{ \ln|z|+i\arg(z) }=|z|e^{ i\arg(z) }=z$$
> [!proposition]
> The range of complex logarithm is the strip $\{ z\in\C : 0<\operatorname{\mathrm{Im}} z<2\pi \}$.

*Proof*  The range of $\arg$ is $[0,2\pi)$, so the range of $\ln$ is $\{ z\in\C : 0<\operatorname{\mathrm{Im}} z<2\pi \}$. $\square$

> [!definition] Complex Powers
> For any complex number $z$ and $w$, we define $z^{w}:=e^{w\ln(z)}$.

> [!proposition]
> The following hold for complex powers:
> - $z^{w_1}z^{w_2}=z^{w_{1}+w_{2}}$.
> - If $n$ is a positive integer, then $z^{nw} = (z^w)^{n}$.
>$\quad$

*Proof*  $$z^{w_1}z^{w_2}=e^{w_1\ln(z)}e^{w_2\ln(z)}=e^{(w_1+w_2)\ln(z)}=z^{w_{1}+w_{2}}$$

## Trigonometric Functions

> [!definition] Complex Trigonometric Function
> Define the complex trigonometric functions as follows: $$\begin{aligned}\sin(z)&:=\frac{e^{iz}-e^{-iz}}{2i}\\\cos(z)&:=\frac{e^{iz}+e^{-iz}}{2}\\\tan(z)&:=\frac{\sin(z)}{\cos(z)}\end{aligned}$$

> [!proposition]
> The complex trigonometric functions align with the real trigonometric functions when $z$ is purely real.

*Proof*  Straightforward by definition. $\square$
