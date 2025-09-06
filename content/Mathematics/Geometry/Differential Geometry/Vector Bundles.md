---
created: 2024-08-01
updated: 2024-09-26
---
>[!definition] Vector Bundle
>A vector bundle of rank $k$ over a base [[Topological Spaces#^65c94a|topological space]] $X$ (usually a [[Manifolds and Atlases#^6ef2ef|smooth manifold]]) consists of the following information: 
>- [[Topological Spaces#^65c94a|topological spaces]] $X$ and $E$;
>- a [[Continuous Functions on Topological Spaces#^33ee5a|continuous]] [[Relations and Functions#^042daf|surjection]] $\pi \colon E \to X$, called the bundle projection;
>- for every $x\in X$, the fiber $\pi^{-1}(\{x\})$ yields a finite-dimensional real [[Vector Spaces#^f4b63e|vector space]],
>
> such that $\pi$ is locally trivialisable. That is, for every point $p\in X$, there is an [[Closure, Interior and Boundary#^eda962|open neighbourhood]] $U\subseteq X$ of $p$, a [[Number Systems#^b4eff7|natural number]] $k$, and a [[Isometries and Homeomorphisms#^85034b|homeomorphism]] $\newcommand{\R}{\mathbb{R}}\Phi \colon \pi^{-1}(U) \to U \times \R^{k}$ that for all $x\in U$, $\Phi\bigg|_{\pi^{-1}(\{x\})}$ is a linear isomorphism onto $\{x\}\times \R^{k}$.
> In other words, the following diagram commutes: 
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/vector_bundle.svg" style="width:40%;"/>
> ^9cb683

> [!remark]
> Intuitively, the local trivialisation means that locally, the vector bundle doesn't twist or bend in a complicated way. So, local trivialization is the property that allows us to study the vector bundle piece by piece, using the familiar structure of product spaces in each piece, even if the entire bundle has a more complex, "twisted" global structure.

>[!definition] Section
>A section $s\colon X\to E$ of a vector bundle $E$ over $X$ through $\pi$ is essentially an assignment to choose one vector from each fiber of the bundle in a smooth manner, such that $\pi\circ s=\id$. ^947478

<u><b>e.g.</b></u> A vector bundle $E$ over a manifold $M$ with section $s$ and fibers $E_{m_{i}}$:
![|350](https://i.imgur.com/TTlaMBP.png) 

> [!proposition]
> Let $\pi\colon E\to X$ be a vector bundle. The space of sections, denoted $\Gamma(E)$, is a vector space, with a [[Modules#^697aa9|module]] structure over the [[Ring, Field and Integral Domain#^178485|ring]] $C^{\infty}(M)$.
> 

> [!definition] Frame of a Vector Bundle
> Let $E$ be a vector bundle on a smooth manifold $M$. A local frame over an open subset $U\subset M$, is a set of $k$ smooth sections $\{s_{1},s_{2},\dots,s_{k}\}$ of $E$ such that for every $x\in U$, the vectors $\{s_{1}(x),s_{2}(x),\dots,s_{k}(x)\}$ form a basis of the fiber $E_{x}$. ^9cb683
>

> [!remark]
> A frame provides a way to trivialise the bundle locally, giving a smooth choice of basis for each vector space fiber over an open set of the base manifold.
> 

On an $n$-manifold, given two coordinate charts $$\varphi_{\alpha}=(x^{1}_{\alpha},x^{2}_{\alpha},\dots,x^{n}_{\alpha})\colon U_{\alpha} \to \R^{n},\quad \varphi_{\beta}=(x^{1}_{\beta},x^{2}_{\beta},\dots,x^{n}_{\beta})\colon U_{\beta} \to \R^{n},$$the coordinate change $$\varphi_{\alpha}\circ\varphi_{\beta}^{-1}\colon \varphi_{\beta}(U_{\alpha}\cap U_{\beta}) \to \varphi_{\alpha}(U_{\alpha}\cap U_{\beta})$$induces a corresponding change of basis: $$\begin{pmatrix}\pddf{}{x^{1}_{\alpha}} \\ \pddf{}{x^{2}_{\alpha}} \\  \vdots \\ \pddf{}{x^{n}_{\alpha}}\end{pmatrix} = \begin{pmatrix} \frac{\partial x^{1}_{\beta}}{\partial x^{1}_{\alpha}} & \frac{\partial x^{2}_{\beta}}{\partial x^{1}_{\alpha}} & \cdots & \frac{\partial x^{n}_{\beta}}{\partial x^{1}_{\alpha}} \\ \frac{\partial x^{1}_{\beta}}{\partial x^{2}_{\alpha}} & \frac{\partial x^{2}_{\beta}}{\partial x^{2}_{\alpha}} & \cdots & \frac{\partial x^{n}_{\beta}}{\partial x^{2}_{\alpha}} \\ \vdots & \vdots & \ddots & \vdots \\  \frac{\partial x^{1}_{\beta}}{\partial x^{n}_{\alpha}} & \frac{\partial x^{2}_{\beta}}{\partial x^{n}_{\alpha}} & \cdots &  \frac{\partial x^{n}_{\beta}}{\partial x^{n}_{\alpha}}\end{pmatrix}\begin{pmatrix}\pddf{}{x^{1}_{\beta}} \\ \pddf{}{x^{2}_{\beta}} \\  \vdots \\ \pddf{}{x^{n}_{\beta}}\end{pmatrix}.$$And we can identify the change of basis matrix $\left(\pddf{x^{i}_{\beta}}{x^{j}_{\alpha}}\right)_{n\times n}$ as a smooth map $U_{\alpha}\cap U_{\beta} \to \mathrm{GL}(n,\R)$.

> [!definition] Subbundle
> $F\to X$ is called a subbundle of $E\to X$ if for every $x\in X$, the fiber $F_{x}$ is a linear subspace of the fiber $E_{x}$. ^c5246b

> [!definition] Quotient Bundle
> Given a subbundle $F\to X$ of a vector bundle $E\to X$, the quotient bundle $E/F$ is the vector bundle over $X$ whose fibers are the quotient spaces $E_{x}/F_{x}$, for all $x\in X$.

>[!definition] Dual Bundle
>The dual bundle of a vector bundle $E$ over $X$ is the vector bundle $E^{*}$ over $X$ whose fibers are the dual spaces to the fibers of $E$. ^3c3b98

> [!definition] Pullback Bundle & Pullback Section
> Suppose $\pi\colon E\to N$ is a vector bundle on a manifold $N$, and $F\colon M\to N$ is a local diffeomorphism map. Then the pullback bundle $F^{*}E$ is a vector bundle over $M$ whose fibers are the pullbacks of the fibers of $E$. That is, for each $p\in M$, the fiber $(F^{*}E)_{p}$ is defined as $(F^{*}E)_{p}:=E_{F(p)}$. A section $s$ of $E$ induces a section $F^{*}s$ of $F^{*}E$ by $$F^{*}s(p):=s(F(p)).$$ ^3c3b98
