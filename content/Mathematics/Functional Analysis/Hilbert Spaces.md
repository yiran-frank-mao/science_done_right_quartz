## Hilbert Spaces and Separability

> [!definition] Hilbert Space
> A *Hilbert space* is a [[Number Systems#^5fea5c|real]] or [[Complex Numbers#^a81924|complex]] [[Inner Products#^f0c22c|inner product space]] that is also [[Complete Metric Space#^67b510|complete]] with respect to the [[Metric Spaces#^0eacc7|metric]] induced by the [[Inner Products#^f0c22c|inner product]]. ^ae0212

> [!definition] Separable Normed Space
> A [[Normed Spaces#^345fd3|normed space]] is *separable* if it has a [[Equinumerous and Countability#^79eb6c|countable]] [[Closure, Interior and Boundary#^b560bf|dense]] subset. i.e. it contains a countable subset whose closure is the entire space. ^acb78f

<u><b>e.g.</b></u>
- The finite dimensional complex spaces $\newcommand{\H}{\mathcal{H}}\C^{n}$ are separable Hilbert spaces, with the inner product being $$\langle (a_{1},\dots,a_{n}),(b_{1},\dots,b_{n})\rangle=\sum_{i=1}^{n}a_{i}\bar{b}_{i}.$$
- An infinite-dimensional analogue of the above example is the space $$\ell^{2}(\Z):=\left\{(\dots,a_{-2},a_{-1},a_{0},a_{1},a_{2},\dots):a_{i}\in\C,\sum_{i=-\infty}^{\infty}|a_{i}|^{2}<\infty\right\}$$with the inner product $$\langle (a_{n})_{n\in\Z},(b_{n})_{n\in\Z}\rangle=\sum_{i=-\infty}^{\infty}a_{i}\bar{b}_{i}.$$
- The space of all complex-valued measurable function $f$ on $\R^{d}$ such that $\int_{\R^{d}}|f(x)|^{2}<\infty$, modulo the [[Relations and Functions#^14741d|equivalence relation]] of being equal almost everywhere, denoted as $L^{2}(\R^d)$, is a prime example of a separable Hilbert space. The inner product is defined as $$\langle f,g\rangle=\int_{\R^{d}}f(x)\overline{g(x)}\dd x.$$We shall first check that $L^{2}(\R^{d})$ is a vector space, and $\langle\cdot,\cdot\rangle$ is a well-defined inner product. 
  For any $f,g\in L^{2}(\R^{d})$, we have $$\int_{\R^{d}}|f+cg|^{2} \leq 4 \int_{\R^{d}}|f|^{2}+4|c|^{2}\int_{\R^{d}}|g|^{2} <\infty, $$so $f+cg\in L^{2}(\R^{d})$ for all $c\in\C$, hence $L^{2}(\R^{d})$ is a [[Vector Spaces#^f4b63e|vector space]]. Moreover, $$\begin{aligned} \langle f+cg,h\rangle&=\int_{\R^{d}}(f+cg)\overline{h}=\int_{\R^{d}}f\overline{h}+c\int_{\R^{d}}g\overline{h}=\langle f,h\rangle + c\langle g,h \rangle, \\ \langle f,\lambda g\rangle &=\int_{\R^{d}}f\overline{\lambda g}=\overline{\lambda}\int_{\R^{d}}f\overline{g}=\overline{\lambda}\langle f,g\rangle, \\ \langle f,g\rangle &=\int_{\R^{d}}f\overline{g}=\int_{\R^{d}}\overline{\overline{f}g}=\overline{\langle g,f\rangle}.\end{aligned}$$So the inner product is well-defined. Now we verify that $L^{2}(\R^{d})$ is complete. ^ba55f5
- Indeed, $L^{p}(\R^{d})$ is a Hilbert space if and only if $p=2$. For $p\neq 2$, $L^{p}(\R^{d})$ is only a [[Banach Spaces#^7196a5|Banach space]].
$\quad$

## Orthonormal Basis

> [!proposition] Bessel's Inequality
> Let $\H$ be a Hilbert space, and let $\{e_{k}\}_{k=1}^{\infty}$​ be an orthonormal set in $\H$. For any $f\in H$, there holds $$\sum_{k=1}^\infty|\langle f,e_k\rangle|^2\leq\|f\|^2.$$

> [!proposition] Characterisation of Orthonormal Basis in Hilbert Space 
> The following properties of a countable orthonormal set $\{e_{i}\}_{i\in I}$ in a Hilbert space $\H$ are equivalent:
> - $\{e_{i}\}_{i\in I}$ forms a basis.
> - The [[Vector Spaces#^ce69a9|span]] of $\{e_{i}\}_{i\in I}$ is [[Closure, Interior and Boundary#^b560bf|dense]] in $\H$.
> - If $f\in H$ and $\langle f,e_{i}\rangle=0$ for all $i\in I$, then $f=0$.
> - If $f\in H$, and $S_{n}(f):=\sum_{i=1}^{n}\langle f, e_{i}\rangle e_{i}$, then $S_{n}(f)\to f$ as $n\to\infty$.
> - For all $f\in H$, $\|f\|^{2}=\sum_{i=1}^{\infty}|\langle f, e_{i}\rangle|^{2}$. This is called the Parseval's identity
>
> $\quad$

*Proof*  The Parseval's identity is a direct result of the [[Inner Products#^3c5c75|Pythagorean theorem]].

> [!theorem]
> A Hilbert space has an orthonormal basis if and only if it is separable.
> 

*Proof*  Suppose $\H$ is a separable Hilbert space and $\{f_{1},f_{2},\dots\}$ is a countable subset of $\H$ whose closure equals $\H$. We will inductively define an orthonormal basis $\{e_{i}\}_{i=1}^{\infty}$ such that $\span\{f_1,\ldots,f_n\}\subseteq\span\{e_1,\ldots,e_n\}$ for all $n\in\N$. This will imply that $\overline{\span\{e_{i}\}_{i=1}^{\infty}}=\H$, which will mean that $\{e_{i}\}_{i=1}^{\infty}$ is an orthonormal basis.
Without loss of generality, assume that $f_{1}\neq 0$. First set $e_{1}:=f_{1}/\|f_{1}\|$. Then suppose for some $n\in\N$, $\{e_{1},\dots,e_{n}\}$ is an orthonormal set such that $\span\{f_1,\ldots,f_n\}\subseteq\span\{e_1,\ldots,e_n\}$. If $f_{k} \in\span\{e_{1}, \dots , e_{n}\}$ for every  $k \in\N$, then $\{e_{1},\dots,e_{n}\}$ is an orthonormal basis of $\H$ and  the process should be stopped. Otherwise, let $m$ be the smallest positive integer such that $$f_{m}\in\{e_{1},\dots,e_{n}\}.$$Define $e_{n+1}$ as follows: $$e_{n+1}=\frac{f_m-\langle f_m,e_1\rangle e_1-\cdots-\langle f_m,e_n\rangle e_n}{\|f_m-\langle f_m,e_1\rangle e_1-\cdots-\langle f_m,e_n\rangle e_n\|}.$$Clearly $\|e_{n+1}\|=1$, $\langle e_{n+1},e_{k}\rangle=0$ for all $k\leq n$, our choice of $f_{m}$ guarantees there is no division by $0$, and $$\mathrm{span}\{f_1,\ldots,f_{n+1}\}\subseteq\mathrm{span}\{e_1,\ldots,e_{n+1}\},$$completing the induction. $\square$

> [!remark]+ Same Gram-Schmidt Procedure in Linear Algebra
> This is actually the same Gram-Schmidt procedure in linear algebra.

<u><b>e.g.</b></u>  Consider the space $L^{2}(S^{1})$, the set $\{z\mapsto z^{n}\}_{n\in\Z}$ is an orthonormal basis, and for each function $f\in L^{2}(S^{1})$, the corresponding $n$th coefficient is the $n$th Fourier coefficient: $$a_{n}(f)=\frac{1}{2\pi}\int_{-\pi}^{\pi}f(x)e^{-inx}\dd x.$$This can be seen by the following two facts:
 - The Parseval's identity holds for $L^{2}(S^{1})$: $$\sum_{n=-\infty}^{\infty}|a_{n}(f)|^{2}=\frac{1}{2\pi}\int^{\pi}_{-\pi} |f(x)|^{2}\dd x.$$
 - The Fourier series converges to $f$ in the $L^{2}$ norm: $$\lim_{N\to 0}\frac{1}{2\pi}\int^{\pi}_{-\pi}\left|f(x)-\sum_{n\leq N}a_{n}e^{inx}\right|^{2}\dd x =0$$
 
Indeed, the mapping $f\mapsto \{a_{n}(f)\}_{n\in \Z}$ makes $L^{2}(S^{1})$ [[Hilbert Spaces#^68e362|(unitarily) "equivalent"]] to $\ell^{2}(\Z)$, we shall seriously define this equivalence, and prove this in the next section. (See [[Hilbert Spaces#^b796c6|the proposition]].)

## Unitary Mappings

> [!definition] Unitary Mapping
> A mapping $U\colon \H_{1}\to \H_{2}$ between two Hilbert spaces is called *unitary* if it is a vector space isomorphism and preserves the inner product, i.e. $$\langle U(x),U(y)\rangle_{\H_{2}}=\langle x,y\rangle_{\H_{1}}$$for all $x,y\in \H_{1}$. We call two Hilbert spaces *unitarily equivalent* if there exists a unitary mapping between them. ^68e362

> [!theorem]
> Any two separable Hilbert spaces are unitarily equivalent if and only if they have the same dimension.
> 

*Proof*

> [!proposition]
> $L^{2}(S^{1})$ is unitarily equivalent to $\ell^{2}(\Z)$ under the mapping $f\mapsto\{a_{n}(f)\}$, where $a_{n}(f)=\frac{1}{2\pi}\int_{\pi}^{\pi}f(x)e^{-inx}\dd x$. ^b796c6

*Proof*

## Pre-Hilbert Spaces

> [!definition] Pre-Hilbert Space
> A Pre-Hilbert space is a [[Number Systems#^5fea5c|real]] or [[Complex Numbers#^a81924|complex]] [[Inner Products#^f0c22c|inner product space]] that is not necessarily complete.

> [!proposition] Every Pre-Hilbert Space Can be Completed
> Suppose we are given a pre-Hilbert space $(\H_{0},\langle\cdot,\cdot\rangle_{0})$. Then there exists a unique (up to unitarily equivalence) Hilbert space $(\H,\langle\cdot,\cdot\rangle)$, such that $\H_{0}\subset\H$ is dense, and $\langle\cdot,\cdot\rangle_{0}$ is the restriction of $\langle\cdot,\cdot\rangle$ to $\H_{0}$.

*Proof*  

## Fatou's Theorem

> [!theorem] Fatou's Theorem
> A bounded holomorphic function $F(re^{i\theta})$ on the unit disk has radial limits at almost every $\theta$.

