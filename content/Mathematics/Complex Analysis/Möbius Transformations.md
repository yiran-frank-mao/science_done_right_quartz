---
created: 2024-08-05
updated: 2024-10-31
completed: true
---
## Algebraic Structures

> [!definition] Möbius Transformations
> The set of *Möbius transformations* is given by $$\newcommand{\C}{\mathbb{C}}\newcommand{\hC}{\hat{\C}}\newcommand{\mob}{\mathrm{Möb}}\mob=\{\lambda_X\colon\hat{\mathbb{C}}\to\hat{\mathbb{C}}\mid X\in \mathrm{GL}_2(\mathbb{C})\}$$where for any $X=\begin{pmatrix}a&b\\ c&d\end{pmatrix}\in \mathrm{GL}_{2}(\C)$, $$\lambda_X(z)=\begin{cases}\frac{az+b}{cz+d}&z\neq\infty,-d/c\\\infty&z=-d/c\\a/c&z=\infty\end{cases}$$where $\mathrm{GL}_{2}(\C)$ is the [[Linear Groups#^264ff5|general linear group]] over $\C$. We will often write $\lambda_{X}(z)=\frac{az+b}{cz+d}$, since the other two cases are compatible with the limits of the fraction. ^da9a62

> [!lemma]
> Any Möbius transformation is a composite of translations, dilations, and inversions. ^57c4fc

*Proof*  Case $c\neq 0$, we can write $$\begin{aligned}
\lambda_{X}(z)&=\frac{az+b}{cz+d}=\frac ac-\frac{ad-bc}{cz+d}\\
&=\left(\left(w\mapsto(ad-bc)w+\frac{a}{c}\right) \circ  \left( w\mapsto \frac{1}{w}\right) \circ (w\mapsto (cw+d)) \right)(z)
\end{aligned}$$Otherwise, $\lambda_{X}(z)=\frac{az+b}{d}$, which is a dilation followed by a translation. $\square$

> [!proposition]
> Any Möbius transformation $\lambda_{X}$ is biholomorphic.

*Proof*  Case $c=0$. Then $\lambda_{X}(z)=\frac{az+b}{d}$, which is linear, and the inverse is also linear, so it suffices to show that $\lambda_{X}$ is holomorphic on $\hC$. The only thing that needs to be checked is $\C$-differentiability at $\infty$. Since $\lambda_{X}(\infty)=\infty$, we have to consider $1/\lambda_{X}(1/z)$ at $0$. That is $\frac z{\frac ad+\frac bdz}$, since $a\neq 0$ (as $X$ is invertible), this is $\C$-differentiable at $0$ by the quotient rule. 
Case $c\neq0$. Notice that when $X=\begin{pmatrix}0&1\\1&0\end{pmatrix}$, $\lambda_{X}(z)=1/z$, which is holomorphic. By the above lemma, $\lambda_{X}$ is a composition of holomorphic functions, hence holomorphic. $\square$

> [!proposition]
> $\mathrm{Möb}$ forms a group under function composite.

> [!proposition]
> Let $X_{1},X_{2} \in \mathrm{GL}_{2}(\C)$. Then $\lambda_{X_{1}}\circ\lambda_{X_{2}}=\lambda_{X_{1}X_{2}}$. Indeed $\lambda\colon \mathrm{GL}_{2}(\C)\twoheadrightarrow\mathrm{Möb}$ forms a surjective [[Homomorphisms, Normal Subgroup & Conjugation#^homo|group homomorphism]].

*Proof*  Suppose $X_{1}=\begin{pmatrix}a_{1}&b_{1}\\ c_{1}&d_{1}\end{pmatrix}$ and $X_{2}=\begin{pmatrix}a_{2}&b_{2}\\ c_{2}&d_{2}\end{pmatrix}$. Then $$(\lambda_{X_{1}}\circ\lambda_{X_{2}})(z)=\lambda_{X_{1}}(a_{2}z+b_{2})=\frac{a_{1}(a_{2}z+b_{2})+b_{1}}{c_{1}(a_{2}z+b_{2})+d_{1}}=\frac{(a_{1}a_{2}+b_{1})z+b_{1}d_{2}}{(c_{1}a_{2}+d_{1})z+c_{1}d_{2}}=\lambda_{X_{1}X_{2}}(z)$$$\square$

> [!proposition]
> Two Möbius transformations are equal if and only if their matrices are scalar multiples of each other: $$\lambda_{X_{1}}=\lambda_{X_{2}}\iff X_{1}=aX_{2} \text{ for some } a\in \C$$

*Proof*  This is clear from the expression of $\lambda_{X}$. $\square$

**Corollary**  The kernel of $\lambda\colon \mathrm{GL}_{2}(\C)\twoheadrightarrow\mathrm{Möb}$ is the set of scalar matrices in $\mathrm{GL}_{2}(\C)$: $$\ker\lambda=\{aI: a\in \C\setminus\{0\}\}$$

**Corollary**  The Möbius group is [[Homomorphisms, Normal Subgroup & Conjugation#^c32ca8|isomorphic]] to $\mathrm{PGL}_{2}(\C)$, the projective general linear group over $\C$: $$\mathrm{Möb}\cong \mathrm{GL}_2(\mathbb{C})/\{aI:a\in\mathbb{C}\setminus\{0\}\}=\mathrm{PGL}_{2}(\C)$$

> [!lemma]
> Let $\phi\in \mathrm{Möb}$, $\phi\neq \mathrm{id}$. Then $\phi$ has exactly one or two fixed points in $\hat{\C}$.

*Proof*  Suppose $\phi(z)=\frac{az+b}{cz+d}$. First consider the case when $c=0$. Then $\phi(z)=\frac{az+b}{d}$, which has one fixed point at $\infty$. For $z\in\C$, $z$ is a fixed point if and only if $\left(\frac{a}{d}-1\right)z+\frac{b}{d}=0$. If $a/d\neq 1$, this has a unique solution, giving a total of two fixed points in $\hC$; If $a/d=1$, we cannot have $b=0$ (otherwise $\phi$ is the identity), so there is exactly one fixed point $\infty$.
Now case $c\neq 0$. Then $\phi(\infty)=\frac{a}{c}\neq \infty$, so we only need to consider fixed points in $\C$. Moreover, $-\frac{d}{c}$ cannot be a fixed point because $\phi(-d/c)=\infty$. Thus $z\in\C\setminus\{-d/c\}$ is a fixed point if and only if $$z=\frac{az+b}{cz+d} \iff  cz^2+(d-a)z-b=0$$which has one or two solutions in $\C$. $\square$  

> [!proposition]
> Let $z_{1},z_{2},z_{3}\in \hat{\C}$ be distinct points, and let $w_{1},w_{2},w_{3}\in \hat{\C}$ be distinct points. Then there exists a unique Möbius transformation $\phi$ such that $\phi(z_{i})=w_{i}$ for $i=1,2,3$. ^c03a8a

*Proof*  Suppose $\phi,\psi\in \mathrm{Möb}$ both satisfy the conditions. Then $\phi^{-1}\circ\psi$ fixes $z_{1},z_{2},z_{3}$ more than two points, and hence is the identity by the above lemma. Thus $\phi=\psi$. 
Indeed, it is enough to show existence by the case when $w_{1}=1$, $w_{2}=0$, and $w_{3}=\infty$, since once we have maps $\theta_{1}$, $\theta_{2}$ such that $$\theta_{1}(z_{1})=1,\theta_{1}(z_{2})=0, \theta_{1}(z_{3})=\infty \text{ and } \theta_{2}(w_{1})=1, \theta_{2}(w_{2})=0, \theta_{2}(w_{3})=\infty$$then the composite $\theta_{2}^{-1}\circ\theta_{1}$ will be a Möbius transformation mapping $z_{i}\mapsto w_{i}$.
So without loss of generality, we assume $w_{1}=1$, $w_{2}=0$, and $w_{3}=\infty$.
Case $z_{1},z_{2},z_{3}\in\C$, then $\phi(z)=\frac{z_1-z_3}{z_1-z_2}\cdot\frac{z-z_2}{z-z_3}$ does the job.
The other cases are just imposing some of $z_{i}$ to be $\infty$. For example, if $z_{2}=\infty$, $z_{1},z_{3}\in\C$, then $\phi(z)=\frac{z-z_3}{z-z_1}$ does the job. $\square$

> [!comment]+
> Now we can roughly guess a Möbius transformation mapping the unit disk $\Delta$ to the upper half-plane $\newcommand{\H}{\mathbb{H}}\H$ by considering the Möbius transformation mapping $1, -i, i$ to $1, 0, \infty$: $$\phi(z)=\frac{1-i}{1+i}\frac{z+i}{z-i}=-i\frac{z-i}{z+i}$$Actually we are guessing it maps the circle to the real line, and the disk to the upper half plane. And we need to introduce the concept of generalized circles to make this precise.

## Generalized Circles

> [!definition] Line
> A line in $\C$ is the set of solutions to $Az+\overline{A}\overline{z}+c=0$ where $A\in \C \setminus \{ 0 \}$ and $c\in \R$.

> [!definition] Circle
> A circle in $\C$ is the set of solutions to $\left|z\right|^2+Az+\overline{A}\overline{z}+c=0$ where $A\in \C$ and $c\in \R$ with $c<\left|A\right|^2$.

> [!definition] Generalized Circle
> A generalized circle in $\hat{\C}$ is either a circle in $\C$ or a line in $\C$ plus the point at infinity. In fact, on the Riemann sphere, these all correspond to circles.

> [!theorem]
> A Möbius transformation maps generalized circles to generalized circles.

*Proof*  By the above [[Möbius Transformations#^57c4fc|lemma]], any Möbius transformation is a composite of ones of the form $z\mapsto z+ b$ and $z\mapsto  1/z$. Affine maps $az+b$ take circles to circles, lines to lines and infinity to infinity, so it is enough to show that $λ(z) = 1/z$ maps generalized circles to generalized circles. Case $C$ is a line and $0\notin C$, then we can write $C=\{z\in\mathbb{C}:Az+\bar{A}\bar{z}+c=0\}\cup\{\infty\}$ for some $A\in \C\setminus\{0\}$ and $c\in\R$, $c\neq 0$. Then $$\begin{aligned}λ(C)&=\{z\in\mathbb{C}:A/z+\bar{A}/\bar{z}+c=0\}\cup\{0\}\\
&=\{z\in\mathbb{C}:A\bar{z}+\bar{A}z+c\left|z\right|^2=0\}\\
&=\left\{z\in\mathbb{C}:\frac Ac\bar{z}+\frac {\bar{A}}{c}z+\left|z\right|^2=0\right\}
\end{aligned}$$which is a circle as $A\neq 0$ and so $|A|^{2}>0$.
Case $C$ is a line and $0\in C$, then $C=\{z\in\mathbb{C}:Az+\bar{A}\bar{z}=0\}\cup\{\infty\}$ for some $A\in \C\setminus\{0\}$, thus $$λ(C)=\{z\in\mathbb{C}:A/z+\bar{A}/\bar{z}=0\}\cup\{0\}\cup\{\infty\}=\{z\in\mathbb{C}:A\bar{z}+\bar{A}z=0\}\cup\{\infty\}$$which is a line.
Case $C$ is a circle and $0\notin C$, then $C=\{z\in\mathbb{C}:\left|z\right|^2+Az+\bar{A}\bar{z}+c=0\}$ for some $A\in \C$ and $c\in\R$, $c<\left|A\right|^2$. Then $$λ(C)=\left\{z\in\mathbb{C}:\frac{1}{c}+\frac{A}{c}\bar{z}+\frac{\bar{A}}{c}z+\left|z\right|^2=0\right\}$$which is a circle.
Case $C$ is a circle and $0\in C$, then $C=\{z\in\mathbb{C}:\left|z\right|^2+Az+\bar{A}\bar{z}=0\}$ for some $A\in \C$, thus $$λ(C)=\left\{z\in\mathbb{C}:1+A\bar{z}+\bar{A}z=0\right\}\cup\{\infty\}$$which is a line. $\square$

> [!warning]+
> If $C$ and $λ(C)$ are circles, $λ$ may not map the center of $C$ to the center of $λ(C)$.

> [!proposition]
> For all sets of three distinct points $z_{1},z_{2},z_{3} ∈ \hat{\C}$, there is a unique generalized circle containing them.

*Proof*  Existence: By the [[Möbius Transformations#^c03a8a|proposition]], there is a Möbius transformation $\lambda$ mapping $0$, $1$, $2$ to $z_{1}$, $z_{2}$, $z_{3}$. Then $\lambda(\R\cup\{\infty\})$ is a generalized circle containing $z_{1}$, $z_{2}$, $z_{3}$. Uniqueness: Suppose $C$ and $C'$ are two generalized circles containing $z_{1}$, $z_{2}$, $z_{3}$. There is a Möbius transformation $\phi$ such that $\phi(z_{1})=0$, $\phi(z_{2})=1$, $\phi(z_{3})=\infty$. Then $\phi(C)$ and $\phi(C')$ are generalized circles containing $0$, $1$, $\infty$. Since the real axis is the unique line containing $0$ and $1$, we have $\phi(C)=\R=\phi(C')$, and hence $C=C'$. $\square$

> [!corollary]
> If $z_{1},z_{2},z_{3} ∈C$ for $C$ a generalized circle, and $λ ∈\mob$, then $λ(C)$ is the generalized circle containing $λ(z_{1})$, $λ(z_{2})$, $λ(z_{3})$.

*Proof*  Direct consequence of the above proposition. $\square$

> [!definition] Generalised Disk
> A generalized disk is a connected component of $\hat{\C}\setminus C$, where $C$ is a generalized circle. ^391810

Each generalized circle bounds two generalized disks. If a Möbius transformation maps $C$ to $C'$, it must map $\hC\setminus C$ to $\hC\setminus C'$, and since it is a continuous bijection, it maps connected components to connected components. That is, Möbius transformations map generalized disks to generalized disks. So the Möbius transformation $$\lambda(z)=-i\frac{z+i}{z-i}$$maps $∆$ to $\H$ or $-\H$. We can decide which one by testing at a single point. We have $λ(0) = i$, so $λ(∆) =−\H$ is impossible, and we are left to conclude $λ(∆) = \H$.