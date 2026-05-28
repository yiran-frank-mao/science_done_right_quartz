## Compact Operators

We shall use the notion of [[Compactness of Metric Space#^f1fb8b|sequential compactness]] in a separable Hilbert space. An example would be the closed unit ball $\bar{B}$ in $\H$, which is not compact unless $\H$ is finite-dimensional. If $\H$ is finite-dimensional, then $\bar{B}$ is compact by the [[Continuous Functions on Topological Spaces#^6e5465|Hein-Borel theorem]]. Otherwise, $\H$ is infinite-dimensional. Suppose $\{e_{n}\}_{n=1}^{\infty}$ is an orthonormal basis, then no subsequence of the sequence $\{e_{n}\}_{n=1}^{\infty}$ will converge to any point in $\bar{B}$, because $\|e_{n}-e_{m}\|=\sqrt{2}$ for all $n\neq m$.

> [!definition] Compact Operator
> Suppose $V$ and $W$ are [[Normed Spaces#^345fd3|normed spaces]]. An operator $T\colon V\to W$ is compact if all bounded sequences $\{x_{n}\}$ in $V$ have a subsequence $\{x_{k_{n}}\}$ such that $\{T(x_{k_{n}})\}$ converges in $W$. Equivalently, $T$ is compact if the closure of the image of the unit ball in $V$ under $T$ is compact in $W$. ^67af67

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
 
## The Trace Class Operators

> [!definition] Trace Class Operator
> A bounded linear operator $T$ on a separable Hilbert space $\H$ is called a *trace class operator* if $$\sum_{i=1}^{\infty} s_{i}(T) <\infty,$$where the positive operator $|T|:=\sqrt{T^{*}T}$, and $s_{i}(T)$ are the singular values of $T$. In this case, the trace norm is defined as $$\|T\|_{\mathrm{tr}}:=\sum_{i=1}^{\infty}s_{i}(T).$$ ^3f3e2e

> [!proposition]
> The products of Hilbert–Schmidt operators are trace class.
> 
