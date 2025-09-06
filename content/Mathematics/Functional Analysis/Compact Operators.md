## Hilbert-Schmidt Operators

> [!definition] Integral Operator
> On $\newcommand{\R}{\mathbb{R}}L^{2}(\R^d)$, we can define an operator $\newcommand{\dd}{\,\mathrm{d}}T_{K}\colon L^{2}(\R^{d})\to L^{2}(\R^{d})$ by the formula $$T_{K}(f):=\int_{\R^{d}} K(x,y)f(y)\dd y,$$ we call it an integral operator with associated kernel $K\colon \R^{d}\times\R^{d}\to\R$, where $K$ is a measurable function such that $\int_{\R^{d}}|K(x,y)|^{2}\dd y<\infty$ for almost every $x\in\R^{d}$.
> 

> [!definition] Hilbert-Schmidt Operator
> An integral operator $T_{K}$ is called a Hilbert-Schmidt operator if the associated kernel $K$ is an element of $L^{2}(\R^{d}\times \R^{d})$. ^5bb53a

> [!proposition]
> Let $T$ be a Hilbert-Schmidt operator on $L^{2}(\R^{d})$ with kernel $K$. Then 
> - for every $f\in L^{2}(\R^{d})$, and almost every $x\in \R^{d}$, the function $y\mapsto K(x,y)f(y)$ is integrable.
> - $T$ is bounded, and $\|T\|\leq\|K\|_{L^{2}(\R^{d}\times \R^{d})}$.
> - the adjoint of $T$ is also a Hilbert-Schmidt operator with kernel $\overline{K(y,x)}$.
> $\quad$

## Compact Operators

We shall use the notion of [[Compactness of Metric Space#^f1fb8b|sequential compactness]] in a separable Hilbert space. An example would be the closed unit ball $\bar{B}$ in $\H$, which is not compact unless $\H$ is finite-dimensional. If $\H$ is finite-dimensional, then $\bar{B}$ is compact by the [[Continuous Functions on Topological Spaces#^6e5465|Hein-Borel theorem]]. Otherwise, $\H$ is infinite-dimensional. Suppose $\{e_{n}\}_{n=1}^{\infty}$ is an orthonormal basis, then no subsequence of the sequence $\{e_{n}\}_{n=1}^{\infty}$ will converge to any point in $\bar{B}$, because $\|e_{n}-e_{m}\|=\sqrt{2}$ for all $n\neq m$.

> [!definition] Compact Operator
> Suppose $V$ and $W$ are [[Normed Spaces#^345fd3|normed spaces]]. An operator $T\colon V\to W$ is compact if all bounded sequences $\{x_{n}\}$ in $V$ have a subsequence $\{x_{k_{n}}\}$ such that $\{T(x_{k_{n}})\}$ converges in $W$. Equivalently, $T$ is compact if the closure of the image of the unit ball in $V$ under $T$ is compact in $W$.

<u><b>e.g.</b></u>  
- $T$ is compact if $\newcommand{\rank}{\operatorname{rank}}\rank T$ (i.e. dimension of the image) is finite.
- Hilbert-Schmidt operators are compact. (See [[Compact Operators#^70449e|the corollary]])
$\quad$

> [!proposition]
> Composition of a compact operator of [[Orthogonality and Bounded Linear Maps#^f95b62|bounded operator]] is compact.

> [!theorem]
> Suppose $T\colon \H\to\H$ is a bounded linear operator on Hilbert space $\H$, then 
> - If $S$ is a compact operator on $\H$, then $ST$ and $TS$ are also compact.
> - If $\{T_{n}\}_{n=1}^{\infty}$ is a family of compact linear operators with $\|T_{n}-T\|\to 0$ as $n$ tends to infinity, then $T$ is compact.
> - Conversely, if $T$ is compact, there is a sequence $\{T_{n}\}$ of operators of finite rank such that $\|T_{n}-T\|\to 0$.
> - $T$ is compact if and only if $T^{*}$ is compact.
> $\quad$
> 

> [!corollary]
> Every Hilbert-Schmidt operator is compact. ^70449e

## Spectral Theorem

> [!lemma]
> Suppose $T$ is a bounded self-adjoint linear operator on a [[Hilbert Spaces#^ae0212|Hilbert space]] $\H$. Then any eigenvalue of $T$ is real, and if $f_{1}$ and $f_{2}$ are eigenvectors corresponding to two distinct eigenvalues, then $f_{1}$ and $f_{2}$ are orthogonal.

> [!theorem] Spectral Theorem of Compact Operators
> Suppose $T$ is a compact self-adjoint operator on a separable [[Hilbert Spaces#^ae0212|Hilbert space]] $\H$. Then there exits an orthonormal basis $\{e_{i}\}_{i=1}^{\infty}$ of $\H$, that consists of eigenvectors of $T$. Moreover, if $$T e_{k}=\lambda_{k}e_{k},$$then $\lambda_{k}\in \R$ and $\lambda_{k}\to 0$ as $k\to \infty$. Conversely, every operator of the above form is compact and self-adjoint. The collection $\{\lambda_{k}\}$ is called the spectrum of $T$.
 
