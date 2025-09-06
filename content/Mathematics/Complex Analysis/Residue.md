---
created: 2024-10-04
updated: 2024-11-05
completed: true
---
Our next topic in the course is based on the idea of using isolated singularities and Laurent expansions to evaluate contour integrals, which goes by the name “Residue Theory.” This is a very widely applicable toolkit that gets used extensively in parts of physics and electrical engineering.

## The Residue Theorem

> [!definition] Residue
> If $\newcommand{\C}{\mathbb{C}}\newcommand{\H}{\mathbb{H}}\newcommand{\im}{\operatorname{im}}\newcommand{\res}{\operatorname{Res}}f\in H(D)$ and $\Delta(a,0,r)\subset D$, then the residue of $f$ at $a$ is $$\newcommand{\dd}{\:\mathrm{d}}\operatorname{Res}_{a}f=\frac1{2\pi i}\int_{|z-a|=\rho}f(z)\dd z$$for any $0<\rho<r$. The residue is independent of the choice of $\rho$ by homotopy invariance. Note that the residue is just the coefficient of $z^{-1}$ in the [[Laurent Series#^b29923|Laurent expansion]] of $f$ centered at $a$.

> [!definition]
> If $D$ is a domain, and $a_{1},\dots a_{n}\in D$, then $f\in H(\overline{D}\setminus\{a_1,\dots,a_n\})$ means there exists an open set $U$ containing $\overline{D}$ such that $f$ has a holomorphic extension to $U \setminus\{a_{1},\dots,a_{n}\}$.

> [!theorem] Residue Theorem
> Let $D$ be a bounded Jordan domain, let $a_{1},\dots,a_{n} ∈D$, and let $f \in H(D\setminus\{a_{1},\dots,a_{n}\})$. Then $$\int_{\partial D}f(z)\dd{z}=2\pi i\sum_{j=1}^{n}\operatorname{Res}_{a_{j}}f.$$

>[!remark]+ Residue Theorem Generalises Cauchy Integral Formula
>This is a generalization of the [[Cauchy Integral Formula for Jordan Domains#^8728b8|Cauchy integral formula]], which says that the integral on the left-hand side is zero if there are no singularities inside the domain.

*Proof*  Choose some $r>0$, such that $\overline{\Delta(a_{j},r)}\setminus\{a_j\}\subset D$ for all $j$, and let $$\tilde{D}:=D\setminus\left(\overline{\Delta(a_1,r)}\cup\cdots\cup\overline{\Delta(a_n,r)}\right)$$Clearly $\tilde{D}$ is a Jordan domain. Then by Cauchy integral formula, we have $$0=\int_{\partial\tilde{D}}f(z)\dd{z}=\int_{\partial D}f(z)\dd z-\left(\sum_{j=1}^n\int_{|z-a_j|=r}f(z)\dd{z}\right)$$where the minus sign arises from different orientations. Since by definition of residue, we have $\int_{|z-a_j|=r}f(z)\dd{z}=2\pi i\operatorname{Res}_{a_j}f$ for all $j$, it follows that $$\int_{\partial D}f(z)\dd{z}=2\pi i\sum_{j=1}^n\operatorname{Res}_{a_j}f$$$\square$

<u><b>e.g.</b></u>  Let $D$ be a bounded [[Cauchy Integral Formula for Jordan Domains#^df720b|Jordan domain]] and let $f\in H(\overline{D}\setminus\{a_1,\ldots,a_n\})$. Then at each $a_{i}$, we have the [[Laurent Series#^b29923|Laurent series]]:  $$f(z)=\sum_{n=-\infty}^{\infty}c_{n}^{(i)}(z-a_{i})^{n}$$Take the derivative, we have the coefficient of $(z-a_{i})^{-1}$ disappear. That is, the residue of $f'$ at $a_{i}$ is zero. Therefore, by the residue theorem, we have $$\int_{\partial D}f'(z)\dd{z}=2\pi i\sum_{j=1}^{n}\res_{a_{j}}f'=0$$which aligns with the fact that, $f$ is a [[Integration and Primitives#^f2c63f|primitive]] of $f'$, so the closed path integral of $f'$ is zero.

## Residue Computation

> [!proposition]
> Suppose $f$ and $g$ are holomorphic on a neighborhood $∆(a,r)$ of $a$, with $f(a) \neq 0$ and $g(a) = 0$ of order $1$. Then $$\res_{a}\frac{f}{g}=\frac{f(a)}{g'(a)}$$ ^789b12

*Proof*  Since $f,g\in H(\Delta(a,r))$ and $g$ has a simple zero at $a$, we can write the Taylor expansions: $$f(z)=c_{0}+c_{1}(z-a)+\cdots,\quad g(z)=(z-a)p(z)$$with $p(a)\neq 0$. $\frac{1}{p}$ is holomorphic on $\Delta(a,r)$, so we can write$$\frac{1}{p(z)}=e_{0}+e_{1}(z-a)+\cdots$$Then we have $$\begin{aligned} \frac{f(z)}{g(z)}=\left(c_{0}+c_1(z-a)+\cdots\right)\cdot\frac1{z-a}\cdot\left(e_{0}+e_1(z-a)+\cdots\right) \end{aligned}$$Note that the residue of $\frac{f}{g}$ at $a$ is the coefficient of $\frac{1}{z-a}$, that is $c_{0}e_{0}$. Since $c_{0} =f(a)$ and $e_{0}=\frac{1}{p(a)}=\frac{1}{g'(a)}$, the result follows. $\square$

<u><b>e.g.</b></u>  
- Let $f(z)=1$ and $g(z)=z^{2}+1$. $g$ has a simple zero at $i$, apply the proposition, we have $$\res_{i}\frac{1}{z^{2}+1}=\frac{1}{2i}$$Furthermore, by the residue theorem, we have $$\int_{|z-i|=\frac12}\frac{1}{z^{2}+1}\dd{z}=2\pi i\res_{i}\frac{1}{z^{2}+1}=\pi$$
##  Contour Integration

We will now see some examples to illustrate how to apply these techniques to compute certain kinds of real integrals in surprising and powerful ways:

> [!proposition]
> Let $\H= \{z \in\C : \im(z) >0\}$ be the upper half-plane. Suppose we have a function $f\in H(\overline{H}\setminus \{a_{1},\dots a_{n}\})$ and $\lim_{R\to \infty}\int_{\gamma_{R}} f(z) \dd z = 0$ with $\gamma_{R}\colon [0,1]\to \C$ satisfying $\gamma_{R}(t) = Re^{\pi i t}$, parameterising the upper semicircle of radius $R$. Then $$\int_{-\infty}^{\infty}f(x) \dd x = 2\pi i\sum_{j=1}^n\res_{a_j}f$$

*Proof*  Let $\rho_{R}$ be the concatenation of $\gamma_{R}$ and the line segment $[-R,R]$, i.e. $\rho_{R}$ is the boundary of the upper half-disk of radius $R$. Then by the residue theorem, we have $$\begin{aligned}&\int_{-\infty}^{\infty}f(x) \dd x\\ =&\lim_{R\to\infty}\int_{[-R,R]}f(z)\dd{z}\\=&\lim_{R\to \infty}\left(\int_{[-R,R]}f(z)\dd{z}+\int_{\gamma_{R}}f(z)\dd{z}\right)\\=&\lim_{R\to \infty}\int_{\rho_{R}}f(z)\dd{z}\\=&2\pi i\sum_{j=1}^{n}\res_{a_j}f\end{aligned}$$$\square$

> [!corollary] 
> Suppose $f(z)=\frac{p(z)}{q(z)}$ where $p$ and $q$ are polynomials with $q(x)\neq0$ for all $x\in \R$ and $\deg q \geq \deg p+2$, all of the roots of $q$ in the upper half-plane have multiplicity $1$. Then $$\int_{-\infty}^{\infty}f(x)\dd{x}=2\pi i\sum_{j=1}^n\frac{P(a_j)}{Q^{\prime}(a_j)}$$where $a_{1},\dots,a_{n}$ are the roots of $q$ in the upper half-plane.

*Proof*  Since $\deg q \geq \deg p+2$, we have $|f(z)|\leq \frac{C}{|z|^2}$ for some real constant $C$. Therefore, by ML estimation, $$\left|\int_{\gamma_R}f(z)dz\right|\leq\pi R\cdot C\cdot\frac1{R^{2}}=\frac{\pi C}{R} \to 0 \quad\text{as}\quad R\to \infty$$Thus we can apply the proposition, and get $$\int_{-\infty}^{\infty}f(x)\dd{x}=2\pi i\sum_{j=1}^n\res_{a_j}f$$Notice that the residue is given by [[Residue#^789b12|the proposition]], and the result follows. $\square$

<u><b>e.g.</b></u>
- $$\int_{-\infty}^\infty\frac1{1+x^{2}}\dd{x}=2\pi i\operatorname{Res}_{i}\frac1{1+x^{2}}=2\pi i\frac1{2i}=\pi$$since $1 + x^{2}$ has only one root in the upper half-plane.
- Consider $\int_{-\infty}^{\infty}\frac{1}{1+x^{4}} \dd x$. The roots of $1+x^{4}$ in the upper half-plane are given by $\frac{\pm 1+i}{\sqrt{2}}$. Hence $$\operatorname{Res}_{\frac{\pm 1+i}{\sqrt{2}}}\frac{1}{1+x^{4}}=\frac{1}{4z^{3}}\bigg|_{z=\frac{\pm 1+i}{\sqrt{2}}}=\frac{-z}{4}\bigg|_{z=\frac{\pm 1+i}{\sqrt{2}}}$$Therefore, the integral is $$\int_{-\infty}^{\infty}\frac{1}{1+x^{4}} \dd x=2\pi i\left(\frac{-\frac{1+i}{\sqrt{2}}}{4}+\frac{-\frac{-1+i}{\sqrt{2}}}{4}\right)=\frac{\pi}{\sqrt{2}}$$


