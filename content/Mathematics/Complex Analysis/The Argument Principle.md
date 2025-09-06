---
created: 2024-10-14
updated: 2024-10-23
cssclasses:
  - img-grid
  - img-zoom
completed: true
---
## The Argument Principle

> [!lemma]
> Suppose $\newcommand{\C}{\mathbb{C}}\newcommand{\Ln}{\operatorname{Ln}}\newcommand{\res}{\operatorname{Res}}\newcommand{\ind}{\operatorname{ind}}f(z) = (z−a)^{d}p(z)$ with $p$ holomorphic in a neighborhood of $a$ and $p(a) \neq 0$. Then $f'/f$ has a pole of order $1$ at $a$ with residue $d$. ^3329f2

*Proof*  $$\frac{f^{\prime}(z)}{f(z)}=\frac{d(z-a)^{d-1}p(z)+(z-a)^{d}p^{\prime}(z)}{(z-a)^{d}p(z)}=\frac d{z-a}+\frac{p^{\prime}(z)}{p(z)}$$The function $p'(z)/p(z)$ is holomorphic in a neighborhood of $a$, thus it can be expressed as a power series, thus the principle part of the Laurent expansion at $a$ is $d/(z-a)$. This implies that the residue of $f'/f$ at $a$ is $d$. $\square$

> [!theorem] Argument Principle
> Let $D$ be a bounded Jordan domain, and let $a_{1},\dots,a_{n} ∈D$. Let $f ∈H(\overline{D}\setminus\{a_{1},\dots,a_{n}\})$, and assume that every $a_{j}$ is a pole of $f$, with order $N_{j}$). Let $b_{1},\dots,b_{k} ∈D$ be the zeroes of $f$, with orders $K_{j}$. Let $K=\sum_{j=1}^{k}K_{j}$ and $N=\sum_{j=1}^{n}N_{j}$. Suppose that f has no zeroes on $\partial D$. Then $$\newcommand{\dd}{\:\mathrm{d}}\int_{\partial D}\frac{f^{\prime}(z)}{f(z)}\dd{z}=2\pi i(K-N)$$

*Proof*  We have $f'/f\in H(\overline{D}\setminus\{a_1,\ldots,a_n,b_1,\ldots,b_k\})$. From the definition of orders of poles and zeroes, we can write $f(z)=(z-a_j)^{-N_j}p_j(z)$ where $p_{j}$ is holomorphic and non-zero near $a$, and similarly $f(z)=(z-b_{j})^{K_{j}}q_{j}(z)$. Thus by above [[The Argument Principle#^3329f2|lemma]], we have $\res_{a_{j}}\frac{f'}{f}=-N_{j}$ and $\res_{b_{j}}\frac{f'}{f}=K_{j}$. By the Residue Theorem, we then obtain $$\int_{\partial D}\frac{f^{\prime}(z)}{f(z)}\dd{z}=2\pi i\left(\sum_{j=1}^{k}K_{j}-\sum_{j=1}^{n}N_{j}\right)=2\pi i(K-N)$$$\square$

> [!remark] A Geometric Understanding of $\int_{\partial D} \frac{f'}{f} \dd z$
> The function $\frac{f'}{f}$ wants to be the derivative "$\frac{\dd}{\dd z} \Ln(z)$" if $\Ln(z)$ were holomorphic on the domain. What happens is that the integral $\int_{\partial D} \frac{f'}{f} \dd z$ picks up the change in value of $\Ln(z)$ as you follow the boundary path, i.e. you get a factor of $2πi$ for every time you loop counterclockwise around the origin.

## Winding Numbers

> [!definition] Winding Number (Index)
> Let $γ$ be a closed piecewise $C^{1}$ path in $\C \setminus\{0\}$. We define the *index* (or *winding number*) of $γ$ about $0$ as $$\ind_{0}\gamma=\frac1{2\pi i}\int_\gamma\frac1z\dd z.$$^03d006

> [!remark] Winding Number is Integer
> By the [[The Homotopy Invariance Theorem#^f5f4b6|homotopy theorem]], $\newcommand{\Z}{\mathbb{Z}}\ind_{0} γ∈\Z$, where $γ$ is [[The Homotopy Invariance Theorem#^fc0803|CP-homotopic]] to $\gamma_{n}$. This is capturing the idea of how many times $γ$ winds about the origin. ^38d7b1

> [!lemma]
> Let $f ∈H(D)$, let $γ$ be a closed path in $D$, and assume $f(γ(t)) \neq 0$ for all $t$ (so that $f \circγ$ is a closed path in $\C \setminus\{0\}$. Then $$\ind_0(f\circ\gamma)=\frac1{2\pi i}\int_\gamma\frac{f^{\prime}(z)}{f(z)}\dd{z}$$

*Proof*  We compute from the definitions:$$\begin{aligned}\ind_0f\circ\gamma&=\frac1{2\pi i}\int_{f\circ\gamma}\frac1z\dd{z}\\&=\frac1{2\pi i}\int_0^1\frac{f^{\prime}(\gamma(t))\gamma^{\prime}(t)}{f(\gamma(t))}\dd{t}\\&=\frac1{2\pi i}\int_\gamma\frac{f^{\prime}(z)}{f(z)}\dd{z}\end{aligned}$$$\square$

> [!definition]
> If $D$ is a bounded Jordan domain and $f$ is holomorphic and non-zero in a neighborhood of $∂D$, then we define $$\ind_{0}f(\partial D):= \sum_{i=1}^{n} \ind_{0} f(\Gamma_{i})$$where $\Gamma_{i}$ are boundary components of $D$. And the change in argument of $f$ along $∂D$ to be$$\Delta_{\partial D}f:=2\pi\ind_0f(\partial D)$$

> [!theorem] Argument Principle in Alternative Form
> Let $D$ be a bounded Jordan domain, and let $a_{1},\dots,a_{n} ∈D$. Let $f ∈H(\overline{D}\setminus\{a_{1},\dots,a_{n}\})$, and assume that every $a_{j}$ is a pole of $f$, with order $N_{j}$). Let $b_{1},\dots,b_{k} ∈D$ be the zeroes of $f$, with orders $K_{j}$. Let $K=\sum_{j=1}^{k}K_{j}$ and $N=\sum_{j=1}^{n}N_{j}$. Suppose that f has no zeroes on $\partial D$. Then $$\Delta_{\partial D}f=2\pi(K-N)$$

*Proof*  By previous version of argument principle, we have $$2\pi(K-N)=\frac{2\pi}{2\pi i}\int_{\partial D}\frac{f^{\prime}(z)}{f(z)}\dd{z}=2\pi\ind_0f(\partial D)=\Delta_{\partial D}f$$$\square$

<u><b>e.g.</b></u>  Let $f(z) = z^{2} + z$, $D_{1} = ∆(0,2)$, and $D_2 = ∆(0,\frac12)$.

<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/disks.svg" alt="disks" style="width:90%;"><img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/f_disks.svg" alt="f_disks" style="width:90%;">

This function has simple zeroes at $z = 0,−1$. So the image $f(∂D_{1})$ winds counterclockwise around the origin twice, and $f(∂D_{2})$ winds counterclockwise around the origin once.

## Rouché's Theorem

> [!definition]
> Let $D$ be a bounded Jordan domain, and let $f ∈H(D)$ with no zeroes on the boundary. Let $b_1,\dots,b_{k}$ be the zeroes of $f$ in $D$, with orders $K_{j}$. Then we define $$K_{f,D} = \sum_{j=1}^{k} K_{j}$$Immediately by the argument principle, we have that $$K_{f,D}=\frac1{2\pi i}\int_{\partial D}\frac{f^{\prime}(z)}{f(z)}\dd{z} = \ind_{0}f(\partial D)$$

> [!theorem] Rouché's Theorem
> Let $D$ be a bounded Jordan domain, let $f,g ∈H(\overline{D})$, and suppose that $|f(z)|>|g(z)|$ for $z ∈∂D$. Then $K_{f,D}= K_{f+g,D}$. ^fc2a0d

*Proof*  It suffices to show that for any boundary component $\Gamma$ with Jordan parameterization $\gamma$, $\ind_{0}(f+g)(\Gamma) = \ind_{0}f(\Gamma)$ holds. By definition, $$\ind_0f(\Gamma)=\ind_0f\circ\gamma=\frac1{2\pi i}\int_{f\circ\gamma}\frac1zdz$$and similarly $$\ind_0(f+g)(\Gamma)=\frac1{2\pi i}\int_{(f+g)\circ\gamma}\frac1z\dd{z}$$Let $\Lambda(s,t) = f(γ(t)) + sg(γ(t))$. Since $|f(γ(t))| > |g(γ(t))|$ on $\partial D$, we have $|f(\gamma(t)|>|g(\gamma(t))|$ for all $t\in [0,1]$, and so by the triangle inequality, $$|\Lambda(s,t)| \geq |f(γ(t))| - s|g(γ(t))|>0$$for all $s\in [0,1]$. Thus the range of $\Lambda$ lies in $\C\setminus\{0\}$, and so $\Lambda$ is a [[The Homotopy Invariance Theorem#^fc0803|CP-homotopy]] from $f$ to $f + g$ in $\C \setminus\{0\}$, therefore by [[The Homotopy Invariance Theorem#^16dbd8|homotopy invariance]], we have $\ind_{0}(f+g)(\Gamma) = \ind_{0}f(\Gamma)$. $\square$

<u><b>e.g.</b></u> Yet another proof of the [[Fields Construction#^4e12b7|fundamental theorem of algebra]]:
Let $p(z)=z^{M}+a_{M-1}z^{M-1}+\cdots+a_{1}z+a_{0}$ be a polynomial of degree $M$. Then let $f(z)=z^{M}$ and $g(z)=a_{M-1}z^{M-1}+\cdots+a_{1}z+a_{0}$. If we choose $R$ large enough such that $|g(z)|<|f(z)|$ when $|z|=R$, then by Rouché's theorem, $$K_{f+g,\Delta(0,R)}=K_{f,\Delta(0,R)}=M$$This does show that $p$ has $M$ roots (including multiplicity) in $\Delta(0,R)$. $\square$ ^89d738
