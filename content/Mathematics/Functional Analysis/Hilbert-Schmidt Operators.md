> [!definition] Hilbert-Schmidt Operator
> An operator on a [[Hilbert Spaces#^ae0212|Hilbert space]] ^5bb53a

> [!definition] Integral Operator
> On $\newcommand{\R}{\mathbb{R}}L^{2}(\R^d)$, we can define an operator $\newcommand{\dd}{\,\mathrm{d}}T_{K}\colon L^{2}(\R^{d})\to L^{2}(\R^{d})$ by the formula $$T_{K}(f):=\int_{\R^{d}} K(x,y)f(y)\dd y,$$ we call it an *integral operator* with associated *kernel* $K\colon \R^{d}\times\R^{d}\to\R$, where $K$ is a measurable function such that $\int_{\R^{d}}|K(x,y)|^{2}\dd y<\infty$ for almost every $x\in\R^{d}$.
> 

> [!definition] Hilbert-Schmidt Operator
> An integral operator $T_{K}$ is called a *Hilbert-Schmidt operator* if the associated kernel $K$ is an element of $L^{2}(\R^{d}\times \R^{d})$. 

> [!proposition]
> Let $T$ be a Hilbert-Schmidt operator on $L^{2}(\R^{d})$ with kernel $K$. Then 
> - for every $f\in L^{2}(\R^{d})$, and almost every $x\in \R^{d}$, the function $y\mapsto K(x,y)f(y)$ is integrable.
> - $T$ is bounded, and $\|T\|\leq\|K\|_{L^{2}(\R^{d}\times \R^{d})}$.
> - the adjoint of $T$ is also a Hilbert-Schmidt operator with kernel $\overline{K(y,x)}$.
> $\quad$
