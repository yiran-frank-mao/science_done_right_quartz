---
created: 2024-08-12
updated: 2024-11-01
completed: true
---
## Path Integral

>[!definition] Path
>A path in $\newcommand{\C}{\mathbb{C}}\C$ is a continuous function $\gamma\colon[a,b]\to \C$. The path is called piecewise $C^{1}$ if there exists a partition $a=t_0<t_1<\dots<t_n=b$ such that $\gamma\big|_{[t_{i-1},t_i]}$ is $C^{1}$ (i.e. differentiable with a continuous derivative) for all $i$. ^ea7ec8

<u><b>e.g.</b></u>  We write $|z-a|=r$ for the circular path $\gamma\colon[0,1]\to \C$ given by $\gamma(t)=a+re^{2\pi it}$. For $z_{1},z_{2}\in\C$, we write $[z_{1},z_{2}]$ for the straight line path from $z_{1}$ to $z_{2}$ at constant speed.

>[!definition] Path Integral
>The path integral of a function $f\colon D\to \C$ along a piecewise $C^{1}$ path $\newcommand{\dd}{\:\mathrm{d}}\gamma\colon[a,b]\to \C$ is defined as $$\int_{\gamma}f(z)\dd z=\int_{a}^{b}f(\gamma(t))\gamma^{\prime}(t)\dd t$$

<u><b>e.g.</b></u>  Let $γ \colon [0, 1] → \C$ be given by $γ(t) = e^{2πit}$. Then $$\int_\gamma\frac1z\dd z=\int_0^{1}\frac{1}{e^{2\pi it}}\cdot2\pi ie^{2\pi it}\dd t=2\pi i\int_{0}^{1}\dd t=2\pi i.$$
Recall the definition of a reversed path:

![[Homotopy Types#^2b9913]]

>[!proposition]
>Reversing the path changes the sign of the integral: if $f\colon D\to \C$ is continuous, $\gamma$ piecewise $C^{1}$ path in $D$, then $$\int_{\gamma}f(z) \dd z=-\int_{\gamma^{-}}f(z)\dd z$$

*Proof*  $$\begin{aligned}\int_{\gamma^{-}}f(z) \dd z&=\int_0^1f(\gamma^-(t))\gamma^{-\prime}(t)\dd t\\&=-\int_0^1f(\gamma(1-t))\gamma^{\prime}(1-t)\dd t\\&=\int_1^0f(\gamma(t))\gamma^{\prime}(t)\dd t\\&=-\int_0^1f(\gamma(t))\gamma^{\prime}(t)\dd t\\&=-\int_\gamma f(z)\dd z\end{aligned}$$$\square$

>[!definition] Path Length
>The length of a piecewise $C^{1}$ path $γ \colon [a, b] → \C$ is defined to be $|\gamma|=\int_{a}^{b}|\gamma'(t)| \dd t$.

>[!theorem] ML Estimation
>Suppose $D\subset \C$ is a domain, let $f\in C(D)$, $\gamma\colon[a,b]\to D$ be a piecewise $C^{1}$ path in $D$, and $M\geq|f(\gamma(t))|$ for $a\leq t\leq b$. Then $$\left|\int_{\gamma}f(z)\dd z\right|\leq M\cdot|\gamma|$$ ^3914d2

*Proof*  Let $\gamma\colon[a,b]\to D$ be a piecewise $C^{1}$ path, then $$\begin{aligned}\left|\int_{\gamma}f(z)\dd z\right|&=\left|\int_{a}^{b}f(\gamma(t))\gamma^{\prime}(t)\dd t\right|\\&\leq \int_{a}^{b}|f(\gamma(t))||\gamma^{\prime}(t)|\dd t\\&\leq M\int_{a}^{b}|\gamma^{\prime}(t)|\dd t\\&=M\cdot|\gamma|\end{aligned}$$$\square$

## Primitive

>[!definition] Primitive
>If $f ∈ C(D)$ and $F ∈ H(D)$ with $F^{\prime} = f$, then $F$ is called a primitive of $f$ on the domain $D$. ^f2c63f

>[!proposition]
>If $F$ and $G$ are primitives of $f$ on $D$, then $F - G$ is constant.

*Proof*  Since $F$ and $G$ are both primitives, then $F-G$ has derivative $0$ and is thus constant. Note that this only holds if $D$ is connected. $\square$

>[!proposition]
>If $f\in C(D)$ has a primitive $F$ on $D$, and $\gamma\colon[a,b]\to D$ is a piecewise $C^{1}$ path, then $$\int_\gamma f(z) z=F(\gamma(b))-F(\gamma(a))$$

*Proof*  This is simply by the fundamental theorem of calculus on $\mathbb{R}^{n}$ with the check of [[Complex Differentiability#^cf170c|Cauchy-Riemann equations]], but we have to be careful because it is mixing real and complex derivatives.

<u><b>e.g.</b></u>  Let $D ⊂\C \setminus\{0\}$be a domain, and suppose that $F ∈H(D)$ and $F'(z) = 1/z$ for all $z ∈D$. Then there exists a $c ∈\C$ such that $F(z) + c ∈\operatorname{Ln}(z)$ for all $z ∈D$.

*Proof*  Since $z\neq 0$ in $D$, we have $$\frac \dd{\dd z}\frac{e^{F(z)}}z=\frac{\frac1ze^{F(z)}z-e^{F(z)}}{z^2}=0$$Therefore $\frac{e^{F(z)}}z$ is constant, say $c$, and thus $e^{F(z)}=cz$. Since $e^{F(z)}$ is never zero, we have $c\neq 0$. So we can write $c=e^{-c'}$ for  constant some $c'\in \C$, and thus $e^{F(z)+c'}=z$, that is $F(z)+c'\in\operatorname{Ln}(z)$. $\square$

## Closed Path Integral and Primitives

> [!lemma]
> If $f ∈ C(∆(a, r))$ and for every oriented triangle $T ⊂ ∆(a,r)$ we have $$\int_{\partial T}f(z)\dd z=0$$then $f$ has a primitive on $∆(a,r)$. ^1fcaa7

*Proof*  Define $F\colon \Delta(a,r)\to \C$ by $$F(z):=\int_{[a,z]}f(w) \dd w$$We need to show that $F'(z)=f(z)$ for all $z\in \Delta(a,r)$. Let $z_{0}\in \Delta(a,r)$, it suffices to show $$\left|\frac{F(z_0+\Delta z)-F(z_0)}{\Delta z}-f(z_0)\right|=\frac{|F(z_0+\Delta z)-F(z_0)-f(z_{0})\Delta z|}{|\Delta z|}\to0 \text{ as } \Delta z\to 0$$We compute $$\begin{aligned}F(z_0+\Delta z)-F(z_0)&=\int_{[a,z_0+\Delta z]}f(w)\dd{w}-\int_{[a,z_0]}f(w)\dd{w}\\&=\int_{[a,z_0+\Delta z]}f(w)\dd{w}+\int_{[z_0,a]}f(w)\dd{w}\\&=-\int_{[z_0+\Delta z,z_0]}f(w)\dd{w}=\int_{[z_0,z_0+\Delta z]}f(w)\dd{w}\end{aligned}$$The last step used the fact that the integral around the triangle with vertices $a,z_0,z_0+\Delta z$ is zero. Thus $$\begin{aligned}\frac{|F(z_0+\Delta z)-F(z_0)-f(z_{0})\Delta z|}{|\Delta z|}&=\frac{1}{|\Delta{z}| }\left| \int_{[z_0,z_0+\Delta z]}f(w)\dd{w}-\int_{[z_0,z_0+\Delta z]}f(z_{0})\dd{w}\right| \\
&\leq \frac1{|\Delta z|}\left|\Delta z\right|\max_{w\in[z_0,z_0+\Delta z]}\left|f(w)-f(z_0)\right|\\
&= \max_{w\in[z_0,z_0+\Delta z]}\left|f(w)-f(z_0)\right|\to{0}\text{ as } \Delta z\to 0  \end{aligned}$$The second line is by [[Integration and Primitives#^3914d2|ML estimate]], and the last line is by continuity of $f$. Thus $F'(z)=f(z)$ for all $z\in \Delta(a,r)$, $F$ is a primitive of $f$ on $\Delta(a,r)$. $\square$

>[!definition] Closed Path
>A path $γ \colon [0,1] → \C$ is called closed if $γ(0) = γ(1)$. A pair of paths $γ, \tilde{\gamma} \colon [0, 1] → \C$ are said to have common endpoints if $γ(0) = \tilde{\gamma}(0)$ and $γ(1) = \tilde{\gamma}(1)$. ^3a89f0

>[!theorem] Morera's Theorem
>Let $f\in C(D)$, the following are equivalent: ^0e998c
>- $\int_\gamma f(z)\dd z=0$ whenever $\gamma$ is a piecewise $C^{1}$ closed path in $D$.
>- $\int_{\gamma}f(z)\dd z=\int_{\tilde{\gamma}}f(z)\dd z$ whenever $\gamma$ and $\tilde{\gamma}$ are piecewise $C^{1}$ paths with common endpoints. That is the integral is path independent.
>- $f$ has a primitive on $D$.
>$\quad$

*Proof*  First consider the equivalence of the first two statements. Suppose property (1) holds, $\gamma$ and $\tilde{\gamma}$ are piecewise $C^{1}$ paths with common endpoints. Then $$\tilde{\tilde{\gamma}}(t)=\begin{cases}\gamma(t)&0\leq t\leq1\\\tilde{\gamma}(2-t)&1\leq t\leq2\end{cases}$$is a continuous closed path $[0,2] \to D$. Thus $$0=\int_{\tilde{\tilde{\gamma}}}f(z)\dd z=\int_{\gamma}f(z)\dd z-\int_{\tilde{\gamma}}f(z)\dd z$$Indeed, the converse is also true since we can cut any closed path into two paths with common endpoints. (3) implies (2) is obvious as if $F$ is the primitive for $f$, we then have$$\int_{\gamma}f(z) \dd z = F(\gamma(1))-F(\gamma(0))\quad \text{ for all path } \gamma $$which shows that the integral is path independent.
Now we show that (2) implies (3). Fix some point $a\in D$, choose any piecewise $C^{1}$ path $\gamma$ in $D$ such that $\gamma(0)=a$ and $\gamma(1)=z$, then define $$F(z):=\int_{\gamma}f(z) \dd z$$This is indeed well-defined as by assumption the integral is path-independent. Fix $z_{0}\in D$. We are required to show that $F'(z_{0})=f(z_{0})$. Choose $r>0$ such that $∆(z_{0}, r) ⊂ D$. Fix a path $\gamma_{0}$ such that $\gamma_{0}(0)=a$ and $\gamma_{0}(1)=z_{0}$. Then for $z\in ∆(z_{0}, r)$, by path independence, we have $$F(z)=\int_{\gamma_0}f(w)\dd{w}+\int_{[z_0,z]}f(w)\dd{w}$$Notice that $f\big|_{\Delta(z_{0},r)}$ has the property that the integral around any closed triangle in $∆(z_{0},r)$ is zero by assumption, so we can apply the above [[Integration and Primitives#^1fcaa7|lemma]] to conclude that $$\frac{\dd}{\dd z}\int_{[z_0,z]}f(w)\dd{w}=f(z)$$Therefore, $$F'(z)=0+f(z)=f(z)$$Since this holds for all $z\in\Delta(z_{0},r)$ and $z_{0}$ is arbitrary, $F$ is a primitive of $f$ on $D$. $\square$

## Local Existence of Primitives

> [!lemma] Goursat’s Lemma
> Let $D$ be a domain, and $∆(a, r)\subset D$, let $f ∈ H(∆(a, r))$. Then $$\int_{\partial T}f\left(z\right) \dd z=0$$for all oriented triangles $T ⊂ ∆(a, r)$. ^ede159

*Proof*  ![goursat's_lemma.svg|240](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/goursat's_lemma.svg)
Let $T ⊂ ∆(a,r)$ be an oriented triangle, and let $M = \left|\int_{\partial T}f(z)\dd z\right|$. We wish to show that $M=0$. Divide $T$ into four triangles $T^{\prime}$, $T^{\prime\prime}$, $T'''$, and $T''''$ by connecting the midpoints of each side of $T$. Then $$\int_{\partial T}f(z)\dd{z}=\int_{\partial T'}f(z)\dd{z}+\int_{\partial T''}f(z)\dd{z}+\int_{\partial T'''}f(z)\dd{z}+\int_{\partial T''''}f(z)\dd{z}$$By the triangle inequality, we have $$\left|\int_{\partial T^{i}}f(z)dz\right|\geq M/4$$for at least one of the four triangles, i.e. $T^{i}\in \{T',T'',T''',T''''\}$.
Now we let $T_{0}:=T$, and $T_{1}$ be the triangle satisfying the above inequality. We continue this process to obtain a sequence of triangles $T_{n}\subset T_{n-1}\subset \dots \subset T_{0}$ such that
- $\left|\int_{\partial T_{n}}f(z)\dd{z}\right|\geq M/4^{n}$
- $\left|\partial T_n\right|=\left|\partial T_0\right|/2^n$
- $\newcommand{\diam}{\operatorname{diam}}\diam(T_{n})=\diam(T_{0})/2^{n}$

Claim that $\cap_{n=1}^{\infty}T_{n}=\{z_{0}\}$ for some $z_{0}\in T_{0}$. Indeed, given $\varepsilon>0$, pick a sequence $(w_n)$ such that $w_{n}\in T_{n}$. Choose $N$ such that $\diam(T_{N})<\varepsilon$, then for all $n,m\geq N$, $w_{n}\in T_{n}\subset T_{N}$, $w_{m}\in T_{m}\subset T_{N}$, and so $\left|w_{n}-w_{m}\right|<\varepsilon$. Thus $(w_{n})$ is a [[Complete Metric Space#^179eeb|Cauchy sequence]] and converges to some $z_{0}$. For each $n$, $w_{m}$ lies in $T_{n}$ for $m\geq n$, and since the triangles are [[Open and Closed Sets#^e112b1|closed]], the limit $z_{0}$ lies in $T_{n}$. But $n$ was arbitrary, so $z_{0}\in T_{n}$ for all $n$, and thus $z_{0}\in\cap_{n=1}^{\infty}T_{n}$. So by uniqueness of limit, $z_{0}$ is the only point in the intersection.
Now define $\alpha\colon \Delta(a,r)\to\C$ by $$\alpha(z)=\begin{cases}\frac{f(z)-f(z_0)}{z-z_0}-f'(z_0)&z\neq z_0\\0&z=z_0\end{cases}$$Since $f$ is $\C$-differentiable at $z_{0}$, $\alpha$ is continuous at $z_{0}$. So we have $$f(z)=f(z_0)+f'(z_0)(z-z_0)+\alpha(z)(z-z_0)\quad\forall z\in\Delta(a,r)$$For all $n$, we can now compute $$\begin{aligned}M/4^n&\leq\left|\int_{\partial T_n}f(z)\dd{z}\right|\\&=\left|\int_{\partial T_n}f(z_0)+f'(z_0)(z-z_0)\dd{z}+\int_{\partial T_n}\alpha(z)(z-z_0)\dd{z}\right|\\&=\left|\int_{\partial T_n}\alpha(z)(z-z_0)\dd{z}\right|\\&\leq|\partial T_n|\operatorname{diam}(T_n)\max_{z\in\partial T_n}|\alpha(z)|\\&=\frac{|\partial T_0|\operatorname{diam}(T_0)}{4^n}\max_{z\in\partial T_n}|\alpha(z)|\end{aligned}$$The third step uses the fact that $f(z_{0})+f'(z_{0})(z−z_{0})$ is a polynomial that has a primitive on $∆(a,r)$, and the fourth step uses the [[Integration and Primitives#^3914d2|ML estimate]]. It follows that $$M\leq\left|\partial T_0\right|\operatorname{diam}(T_0)\max_{z\in\partial T_n}\left|\alpha(z)\right|$$In fact, given $\varepsilon>0$, since $\alpha$ is continuous at $z_{0}$, and $\alpha(z_{0})=0$, there exists $\delta>0$ such that for all $z\in\Delta(z_{0},\delta)$, $\left|\alpha(z)\right|<\varepsilon$. Thus we can choose $n$ such that $\diam(T_{n})<\delta$, and so $$M\leq\left|\partial T_0\right|\operatorname{diam}(T_0)\varepsilon$$Since $\varepsilon$ was arbitrary, $M=0$. $\square$

> [!theorem]
> Let $∆(a,r) ⊂ \C$ be a disk. Then every $f ∈ H(∆(a,r))$ has a primitive on $∆(a, r)$. ^b63dd7

*Proof*  Since $f\in H(\Delta(a,r))$, $f\in C(\Delta(a,r))$, and so by [[Integration and Primitives#^ede159|Goursat's lemma]], the closed path integral of $f$ on any oriented triangle in $\Delta(a,r)$ is zero. By the previous [[Integration and Primitives#^1fcaa7|lemma]], $f$ has a primitive on $\Delta(a,r)$. $\square$



