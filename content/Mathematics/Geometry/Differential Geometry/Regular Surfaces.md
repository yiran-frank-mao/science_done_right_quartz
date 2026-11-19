> [!definition] Differential
> Let $\newcommand{\R}{\mathbb{R}}f\colon U\subset\R^{n}\to \R^{m}$ be a differentiable map. To each $p\in U$, we associate a linear map $\dd f_{p}\colon \R^{n}\to \R^{m}$ called the differential of $f$ at $p$ and is defined as follows: For all $w\in\R^{n}$, and $\gamma\colon[-\varepsilon,\varepsilon]\to U$ be a differentiable curve such that $\gamma(0)=p$, $\gamma'(0)=w$, then $$\dd f_{p}(w):=(f\circ \gamma)'(0)$$

> [!definition] Regular Surface
> A subset $S\subset \R^{3}$ is a regular surface if 
> - for each $p\in S$, there exists a neighbourhood $V\subset \R^{3}$ of $p$ and a smooth homeomorphism $\mathbf{x}\colon U\to V\cap S$ such that $U\subset \R^{2}$ is an open set.
> - For each $q\in U$, the differential $\dd_{q} \mathbf{x}\colon \R^{2}\to\R^3$ is injective.
>
> Such mapping $\mathbf{x}$ is called a local coordinate system or a chart of $p$.