---
created: 2024-07-28
updated: 2025-12-11
completed: true
---
## Holomorphic Functions

> [!definition] Domain
> A domain $D$ is a [[Connectedness and Paths#^946cc4|connected]] open subset of $\newcommand{\C}{\mathbb{C}}\C$. ^08ef59

> [!definition] Holomorphic Function
> A function $f \colon D → \C$ is called *holomorphic* on domain $D$ if it is $\C$-differentiable at every point in $D$. We write $H(D)$ for the set of functions that are holomorphic on $D$. We call a function $f ∈ H(\C)$ an *entire* function. ^c7e434

<u><b>e.g.</b></u>  The function $f(z)=e^{z}$ is entire. Polynomials and $\sin$, $\cos$ are also entire functions. 

> [!proposition]
> $H(D)$ yields a [[Ring, Field and Integral Domain#^178485|ring]] with pointwise addition and multiplication.

*Proof*  For all $f,g \in H(D)$, $f+g$ and $f\cdot g$ are also holomorphic. The additive identity is the zero function. The associative and distributive properties can be checked directly from the definition. $\square$

> [!definition] Biholomorphism and Conformally Equivalence
> Let $D, G ⊂ \C$ be domains. A function $f \colon D \to G$ is called *biholomorphic* (or a *conformal equivalence*) if $f$ is a [[Relations and Functions#^042daf|bijection]], and both $f$ and $f^{-1}$ are holomorphic. Two domains are called conformally equivalent if there exists a conformal equivalence between them. ^3dad2a

> [!proposition]
> Conformal equivalence is an [[Relations and Functions#^14741d|equivalence relation]] on the set of domains.

> [!proposition]
> If $f \colon D → G$ is a biholomorphism, the map $\Phi_{f}\colon H(G) \to H(D)$ given by $\Phi_{f}(g)=g\circ f$ is an [[Homomorphisms and Ideals#^16be07|isomorphism]] of [[Ring, Field and Integral Domain#^178485|rings]].

*Proof*  To see that it is an isomorphism, we can check that $(\Phi_f)^{-1}=\Phi_{f^{-1}}$. For any arbitrary $h\in H(D)$, we have $$\Phi_{f^{-1}}(h)=h \circ f^{-1}, \quad \Phi_{f}(h\circ f^{-1})= h \circ f^{-1} \circ f = h$$Thus $\Phi_{f^{-1}}$ is the inverse of $\Phi_f$. $\square$

> [!definition] Holomorphic Branch of The Logarithm
> If $D$ is a domain, a holomorphic branch of the logarithm on $D$ is a function $f ∈ H(D)$ such that $f(z) ∈ \operatorname{Ln}(z)$ for all $z ∈ D$.

<u><b>e.g.</b></u>  $\ln$ is not a holomorphic branch of the logarithm on $\C\setminus\{ 0 \}$, as it is not continuous thus not holomorphic.

To find holomorphic branches of the logarithm, we think about which domains the function $e^{z}$ is injective on. For $\alpha<\beta$, define the strip $\newcommand{\im}{\operatorname{Im}}S_{\alpha,\beta}:=\{ z\in\C\mid \alpha<\im(z)<\beta \}$. Recall [[Complex Numbers#^fa54fc|the proposition]] that $e^z=e^w$ iff $z-w=2\pi ik$ for $\newcommand{\Z}{\mathbb{Z}}k\in\Z$, so when $\beta-\alpha<2\pi$, $e^{z}\big|_{S_{\alpha,\beta}}$ is injective. The image of $e^{z}\big|_{S_{\alpha,\beta}}$ is the wedge bounded by the angles $\alpha$ and $\beta$, which we write as $A_{\alpha,\beta}$.
By the theorem above, such $e^{z}\big|_{S_{\alpha,\beta}}$ is biholomorphic, and its inverse exists. We denote this inverse as $\ln_{\alpha,\beta}\colon A_{\alpha,\beta}\to S_{\alpha,\beta}$, then we have $$\ln_{0,2\pi}=\ln\big|_{A_{0,2\pi}}$$*Proof*  Since we know that $\ln_{0,2π}$ is the inverse of $e^{z}\big|_{S_{0,2π}}$, we have $\ln_{0,2π}(e^{z})=z$. So $\ln_{0,2\pi}=\ln\big|_{A_{0,2\pi}}$ since the inverse is unique if it exists. $\square$
In fact $\ln_{\alpha,\beta}$ are holomorphic branches of the logarithm on $A_{\alpha,\beta}$.

## Conformal Maps

> [!lemma]
> Let $\newcommand{\R}{\mathbb{R}}M\in M_{2\times 2}(\R)$, then the following are equivalent:
> - $M=\begin{pmatrix} a & -b \\ b & a \end{pmatrix}$ for some not both zero $a,b\in \R$.
> - $M$ is the product of a rotation $R_\theta=\begin{pmatrix}\cos\theta&-\sin\theta\\\sin\theta&\cos\theta\end{pmatrix}$ and a scaling $\begin{pmatrix}\lambda&0\\0&\lambda\end{pmatrix}$ for $\lambda>0$.
> - For any non-zero $u,v ∈ \R^{2}$, the angle from $u$ to $v$ is the same as the angle from $Mu$ to $Mv$.
> $\quad$

*Proof*  We first show 1 implies 2. If $M$ is of the given form, then $$ M=\sqrt{a^2+b^2}\begin{pmatrix}\frac a{\sqrt{a^2+b^2}}&\frac{-b}{\sqrt{a^2+b^2}}\\\frac b{\sqrt{a^2+b^2}}&\frac a{\sqrt{a^2+b^2}}\end{pmatrix}=\begin{pmatrix}\sqrt{a^2+b^2}&0\\0&\sqrt{a^2+b^2}\end{pmatrix}R_\theta $$with $\theta=\arccos\frac a{\sqrt{a^2+b^2}}$. 
To see 2 implies 1, we have $$\begin{pmatrix}\lambda&0\\0&\lambda\end{pmatrix}R_\theta=\begin{pmatrix}\lambda\cos\theta&-\lambda\sin\theta\\\lambda\sin\theta&\lambda\cos\theta\end{pmatrix}$$
2 implies 3 is immediate since both scaling and rotations preserve angles. 
Now we show 3 implies 2. Suppose $M\in\R^{2\times 2}$ preserves angles. Let $e_{1}$ be the first standard basis vector in $\R^{2}$. Let $θ$ be an angle corresponding to the non-zero vector $Me_{1}$. Then we have $R_{-\theta}M e_{1} = \lambda e_1$ for some $\lambda>0$. Since $M$ preserves angles, $R_{-\theta}M$ also preserves angles.
If $v$ is any non-zero vector in $\R^{2}$, the angle from $R_{-\theta}Mv$ to $\lambda e_{1}$ is the same as the angle from $v$ to $e_{1}$, which means that $R_{-\theta}Mv$ is on the same ray as $v$, i.e. $v$ is an eigenvector of $M$.
As the above holds for any non-zero vector $v$, $R_{-\theta}M$ is a scaling matrix $\lambda I$, so $M=\lambda R_{\theta}$. $\square$

So the matrices corresponding to the Cauchy-Riemann equations are exactly the angle-preserving linear transformations. Now it is necessary to talk about angle-preserving maps that are not linear.

> [!definition] Path and Angle
> A path in a domain $D$ is a continuous function $\gamma\colon[0,1]\to D$. If $\gamma_{1}$ and $\gamma_{2}$ are two paths in $D$ and $z=\gamma_{1}(t_{1})=\gamma_{2}(t_{2})$, then we say that $(\gamma_{1},t_{1})$ and $(\gamma_{2},t_{2})$ cross at $z$. 
> If we have such crossing paths are non-zero, we define the angle from $\gamma_{1}$ to $\gamma_{2}$ at $z$ as the angle from tangent vectors $\gamma_{1}^{\prime}(t_{1})$ to $\gamma_{2}^{\prime}(t_{2})$ in $\R^{2}$.

> [!definition] Conformal Map
> Let $f\colon D\to \C$ be an $\R$ differentiable function, and let $z\in D$. Then $f$ is conformal at $z$ if whenever $\gamma_{1}$ and $\gamma_{2}$ are two paths in $D$ that cross at $z$, the angle from $\gamma_{1}$ to $\gamma_{2}$ at $z$ is the same as the angle from $f\circ\gamma_{1}$ to $f\circ\gamma_{2}$ at $f(z)$. A function $f$ is conformal if it is conformal at every point in $D$.

> [!theorem]
> Let $f \colon D → \C$ be an $\R$-differentiable function, and let $z ∈ D$. Then $f$ is conformal at $z$ if and only if $f$ is $\C$-differentiable at $z$ and $f^{\prime}(z)\neq 0$. So $f$ is conformal if and only if $f$ is holomorphic and $f^{\prime}(z)\neq 0$ at every point $z\in D$.

*Proof*  Let $(\gamma_{1},t_{1})$ and $(\gamma_{2},t_{2})$ be two crossing paths at $z$. Then the angle from $(f\circ \gamma_{1},t_{1})$ to $(f\circ \gamma_{2},t_{2})$ at $f(z)$ is the angle from $(f\circ \gamma_{1})^{\prime}(t_{1})$ to $(f\circ \gamma_{2})^{\prime}(t_{2})$ in $\R^{2}$. By the chain rule, we have $$(f\circ \gamma_{1})^{\prime}(t_{1})=f^{\prime}(\gamma_{1}(t_{1}))\gamma_{1}^{\prime}(t_{1})=J_{f}(z)\gamma_{1}^{\prime}(t_{1})$$and similarly for $(f\circ \gamma_{2})^{\prime}(t_{2})$. So the angle is preserved if and only if $J_{f}(z)$ is of the form $\begin{pmatrix} a & -b \\ b & a \end{pmatrix}$ for some not both zero $a,b\in \R$, which is equivalent to $f$ is $\C$-differentiable and $f^{\prime}(z)\neq 0$. $\square$

<u><b>e.g.</b></u>  The function $\C \to \C, z\mapsto ze^{ z }$ is conformal on $\C\setminus\{0\}$. Instead, $z\to \bar{z}$ reverses angles.

> [!corollary] 
> Biholomorphic maps are conformal.

*Proof*  Suppose $f \colon D → G$ is a biholomorphism. Then $f$ is a bijection, and both $f$ and $f^{-1}$ are holomorphic, we have $$z=f^{-1}(f(z)) \quad \forall z\in\C$$Now differentiate both sides, we obtain $$1=(f^{-1})^{\prime}(f(z))\cdot f^{\prime}(z)\quad \forall z\in\C$$Thus $f^{\prime}(z)\neq 0$, hence $f$ is conformal. $\square$




