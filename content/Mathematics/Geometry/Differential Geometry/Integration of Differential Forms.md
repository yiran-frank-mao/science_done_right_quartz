## Orientability

> [!theorem]
> A [[Manifolds, Atlases and Smooth Structures#^6ef2ef|smooth $n$-manifold]] $M$ is orientable if and only if there exists an differential $n$-form $\eta$ which is nowhere vanishing on $M$. Such an $\eta$ corresponds to an *orientation* of $M$, and we call $(M,\eta)$ an *oriented* manifold.
> 

## Integral of a Differential $k$-Form on $\R^k$

> [!definition] Integral of a Differential $k$-Form on $\R^k$
> As in $\R^{k}$, every differential $k$-form $\omega$ can be represented as $$\omega = f(x^{1},\cdots,x^{k})\d x^{1} \wedge \cdots \wedge \d x^{k}$$where $f$ is a smooth function on $\R^{k}$ (See [[Differential Forms#^b84dd7|example]]). The integral of $\omega$ over a region $D\subseteq \R^{k}$ is defined as $$\int_{D}\omega:=\int_{D}f(x^{1},\cdots,x^{k})\d x^{1} \cdots \d x^{k},$$where the right-hand side is the [[Lebesgue Integration#^f4d3e6|Lebesgue integral]] of $f$ over $D$.

> [!definition]
> Let $M$ be an oriented smooth $n$-manifold, and $\omega$ be a differential $n$-form on $M$. The integral of $\omega$ over $M$ is defined as $$\int_{M}\omega:=\int_{f^{-1}(D)}\omega$$where $f\colon M\to D$ is a smooth chart of $M$, and the right-hand side is the integral of $\omega$ over the region $D\subseteq \R^{k}$.
> 

> [!theorem] Change of Variables Formula
> Suppose $D\subseteq M$ is a region in a smooth manifold $M$, and $f\colon M\to N$ is an orientation-preserving diffeomorphism onto its image. Then $$\int_{D} \omega = \int_{f^{-1}(D)} f^{*}\omega,$$where $\omega$ is a differential form on $N$. ^74d864

> [!theorem] Stokes' Theorem
> Suppose $M$ is a smooth manifold with boundary, and $\omega$ is a differential form on $M$. Then $$\int_{M} \d\omega = \int_{\partial M} \omega.$$ ^33d2f3

<u><b>e.g.</b></u>  In fact, the [[Integral#^433cc4|fundamental theorem of calculus]] is an example of the Stoke's theorem. To see this, consider $[a,b]$ as a manifold with boundary. The standard orientation on $[a,b]$ is given by the $1$-form $\d x$, where $x\colon [a,b] \to \R$ is the standard increasing coordinate. Equivalently, we can declare $\pddf{}{x}$ to be positive. Then the induced orientation on the boundary $\partial[a,b]=\{a,b\}$ is that $b$ is positively oriented while $a$ is negatively oriented. Then the Stoke's theorem implies $$ \int_{[a,b]} f'(x)\dd x =  f(b)-f(a).$$

> [!proposition]
> For a [[Compactness of Topological Space#^da2511|compact]] smooth $n$-manifold $M$ with boundary $\partial M$, a vector field $v$ tangent to the boundary $\partial M$, and an $n$-form $\omega$. Then $$\int_{M} \mathcal{L}_{v}\omega=0.$$

*Proof*  By [[Differential Forms#^04ae6c|Cartan's formula]], we have $$L_{v}\omega=\d(i_{v}\omega)+i_{v}\d\omega.$$Therefore, $$\int_{M} L_{v}\omega=\int_{M} \d(i_{v}\omega)+\int_{M} i_{v}\d\omega=\int_{\partial M} i_{v}\omega+\int_{M} i_{v}\d\omega,$$where the second equality holds by [[Integration of Differential Forms#^33d2f3|Stokes' theorem]]. Note that $\d\omega$ is an $(n+1)$-form on $M$, so it vanishes, $\int_{M} i_{v}\d\omega=0$. For any vector fields $u_{1},u_{2},\dots u_{n-1}\in\mathfrak{X}(\partial M)$, fix some $p\in\partial M$, $$i_{v}\omega(u_{1}(p),u_{2}(p),\dots,u_{n}(p))=\omega(v(p),u_{1}(p),\dots,u_{n-1}(p)).$$Note that since $v$ is tangent to the boundary $\partial M$, $v(p)$ is a vector in $T_{p}(\partial M)$, which is of dimension $(n-1)$. Therefore, $\{v(p),u_{1}(p),\dots,u_{n-1}(p)\}$ must be linearly dependent, and thus $i_{v}\omega=0$ on $\partial M$. $\square$

> [!remark]+
> We can also achieve this directly by definition of Lie derivative. Since $M$ is compact and the vector field $v$ is tangent to the boundary, the associated flow $\{f_{t}\}$ of $v$ is global (i.e. $f_{t}$ exists for all $t$ and defines a one-parameter group of diffeomorphisms of $M$ onto itself). Without loss of generality, assume each $f_{t}$ is orientation-preserving. Then by definition of Lie derivative, $$\int_{M} L_{v}\omega=\int_{M}\ddt{}\bigg|_{t=0}f_{t}^{*}\omega.$$ Since $M$ is compact and all objects are smooth, we can interchange the differentiation with respect to $t$ and the integration over $M$: $$\int_{M} L_{v}\omega=\ddt{}\bigg|_{t=0}\int_{M} f_{t}^{*}\omega.$$
> Use the [[Integration of Differential Forms#^74d864|change of variables theorem]] for integration of differential forms, we obtain:
> $$\int_{M} f_{t}^{*}\omega=\int_{f_{t}(M)}\omega.$$
> Thus, $$\int_{M} L_{v}\omega=\ddt{}\bigg|_{t=0}\int_{f_{t}^{-1}(M)}\omega=\ddt{}\bigg|_{t=0}\int_{M}\omega=0,$$where the last equality holds because $\int_{M}\omega$ is independent of $t$. $\square$