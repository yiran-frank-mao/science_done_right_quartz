Exterior differential forms arise when concepts such as the work of a field along a path and the flux of a fluid through a surface are generalized to higher dimensions. Each of differential forms assigns an exterior form to each [[Tangent Vectors and Spaces#^76649d|tangent space]] of a manifold.

## Differential Forms

> [!definition] Differential Forms
> A differential $k$-form on a [[Manifolds, Atlases and Smooth Structures#^6ef2ef|smooth manifold]] $M$ of dimension $n$ is a smooth map $$\newcommand{\R}{\mathbb{R}}\omega\colon TM\to \R,$$that is an [[Exterior Forms#^794521|exterior form]] restricted to each [[Tangent Vectors and Spaces#^76649d|tangent space]] $T_{p}M$ at each point $p\in M$. 
> The exterior and interior product of differential forms inherits from the exterior and interior product of exterior forms respectively. ^c6c1be

<u><b>e.g.</b></u> 
- The simplest example of a differential form is the differential of a function. Specifically, if $f\colon \R^{n}\to \R$ is a smooth map, then $\nabla f$ is a [[Vector Fields and Lie Algebra#^a87ff1|vector field]] with the property that for any vector field $X$,  $$\newcommand{\d}{\mathrm{d}}\d f(X) = \langle \nabla f,X\rangle$$
- Every differential $1$-form on $\R^{n}$ with a given coordinate system $(x^{1},\dots,x^{n})$ can be expressed uniquely as $$\omega(v) = \sum_{i=1}^{n} a_{i}(v)\d x^{i},$$where $a_{i}$ are smooth functions on $\R^{n}$ and $\d x^{i}$ are the coordinate [[Tangent Vectors and Spaces#^c1b44c|differentials]]. In fact, every differential $k$-form on the space $\R^{n}$ with a coordinate system $(x^{1},\dots,x^{n})$ can be expressed uniquely as $$\omega(v) = \sum_{i_{1}<\cdots<i_{k}} a_{i_{1},\cdots,i_{k}}(v)\d x^{i_{1}}\wedge\cdots\wedge \d x^{i_{k}},$$where $a_{i_{1},\cdots,i_{k}}$ are smooth functions on $\R^{n}$ and $\d x^{i_{1}}\wedge\cdots\wedge \d x^{i_{k}}$ are the coordinate differentials.  ^b84dd7

$\quad$

> [!definition] Volume Form
> A volume form is a top degree differential form on a [[Manifolds, Atlases and Smooth Structures#^6ef2ef|smooth manifold]] $M$ of dimension $n$, that is non-vanishing everywhere. ^923fae

> [!proposition]
> Given a differential $k$-form $\omega$, and [[Vector Fields and Lie Algebra#^a87ff1|vector fields]] $X_{1},\dots,X_{k}$, there is a canonical way to evaluate $\omega$ on $X_{1},\dots,X_{k}$, denoted by $\omega(X_{1},\dots,X_{k})$, which is a smooth function on $M$.
> This is skew-symmetric, and respects the multiplication by smooth functions.
> 

*Proof*  The canonical evaluation is given by $$\omega(X_{1},\dots,X_{k})(p) := \omega_{p}(X_{1}(p),\dots,X_{k}(p)),$$where $\omega_{p}$ is the $k$-form at point $p$. The skew-symmetry follows from the skew symmetry of $\omega_{p}$. The evaluation respects the multiplication by smooth functions because $\omega_{p}$ is $k$-linear: $$\begin{aligned}\omega(fX_{1},\dots,X_{k})(p)&= \omega_{p}(f(p)\cdot X_{1}(p),\dots,X_{k}(p))\\ &= f(p)\cdot\omega_{p}(X_{1}(p),\dots,X_{k}(p)).\end{aligned}$$ $\square$

> [!proposition]
> [[Differential Forms#^c6c1be|Differential forms]] on a [[Manifolds, Atlases and Smooth Structures#^6ef2ef|smooth manifold]] $M$ forms a super-commutative [[Grading and Filtration#^9b78c3|graded algebra]] over the ring of smooth functions on $M$ with the exterior product $\wedge$ as multiplication. ^143f20

## Pullback Invariance

> [!definition] Pullback of Differential Forms
> Given a smooth map $F\colon M\to N$ between smooth manifolds, the pullback of a differential $k$-form $\omega$ on $N$ is a differential $k$-form on $M$, defined as $$F^{*}\omega(X_{1},\dots,X_{k})=\omega(F_{*}X_{1},\dots,F_{*}X_{k}),$$where $F_{*}X_{i}$ is the pushforward of the vector field $X_{i}$ on $M$ to $N$.

> [!proposition] Pullback Preserves the Exterior Product and Addition
> For any two differential forms $\omega_{1},\omega_{2}$ on $N$, we have $$F^{*}(\omega_{1}\wedge\omega_{2})=F^{*}\omega_{1}\wedge F^{*}\omega_{2}, \quad F^{*}(\omega_{1}+\omega_{2})=F^{*}\omega_{1}+F^{*}\omega_{2}.$$
> 

*Proof*  This directly follows from the [[Exterior Forms#^bfacb5|pullback invariance of exterior forms]]. $\square$

> [!remark]+ A Smooth Function is a Differential $0$-Form
> We can treat any smooth function $g\in C^{\infty}(N)$ as a differential $0$-form, so that $$F^{*}(g\omega)=F^{*}(g\wedge\omega)=F^{*}g\wedge F^{*}\omega=(g\circ F) F^{*}\omega.$$

> [!proposition] Pullback Preserves The Differential
> For a smooth function $g\in C^\infty(N)$ and a smooth map $F\colon M\to N$, there holds $$F^{*}\d g=\d(F^{*}g).$$
> 

*Proof*  By definition of the pullback, we have $$F^{*}\d g(X)=\d(g\circ F)=\d (F^{*}g)$$ $\square$

<u><b>e.g.</b></u>  We can use the above properties to determine the pullback of a differential form. For example, if $F(p,q)=(p^{2},q^{2},p+q,p-q)$, then $$\begin{aligned} &\,F^{*}(\d x_{1}\wedge\d x_{2}+\d x_{3}\wedge\d x_{4})\\=&\,F^{*}\d x_{1}\wedge F^{*}\d x_{2} + F^{*}\d x_{3} \wedge F^{*}\d x_{4} \\ =&\, \d(x_{1}\circ F) \wedge \d(x_{2}\circ F) + \d (x_{3}\circ F)\wedge \d(x_{4}\circ F) \\ =&\, \d p^{2}\wedge \d q^{2} + \d(p+q) \wedge \d(p-q)\\ =&\, 2p\d p \wedge 2q\d q - \d p\wedge \d q+ \d q \wedge \d p \\ =&\, (4pq) (\d p\wedge \d q) - 2 (\d p\wedge \d q) \\ =&\, (4pq-2)(\d p\wedge \d q) \end{aligned}$$

> [!lemma]
> Suppose $A_{t}\colon V\to W$ is a smooth family of linear maps, $\omega$ is a $k$-form on $W$. We define $$\newcommand{\D}{\mathrm{D}}\newcommand{\ddf}[2]{\frac{\mathrm{d}#1}{\mathrm{d}#2}}\newcommand{\ddt}[1]{\ddf{#1}{t}}\newcommand{\ddtz}{\ddt{}\bigg|_{t=0}}\D^{A_{t}}\omega:=\ddt{}\bigg|_{t=0}A_{t}^{*}\omega.$$Then $\D^{A_{t}}\omega$ is a $k$-form on $V$, and that $\D^{A_{t}}$ is a linear map from $k$-forms on $W$ to $k$-forms on $V$, and $$\D^{A_{t}}(\omega_{1}\wedge\omega_{2})=(\D^{A_{t}}\omega_{1})\wedge A_{0}^{*}\omega_{2} + A_{0}^{*}\omega_{1}\wedge \D^{A_{t}}\omega_{2}.$$
> 

## Lie Derivative of Differential Forms

> [!lemma]  
> Given vector spaces $V_1$, $V_2$, and $V_3$, a bilinear map $h \colon V_1 \times V_2 \to V_3$, and smooth families of vectors $v_1(t) \in V_1$ and $v_2(t) \in V_2$, there holds
> $$\ddt{} h(v_1(t), v_2(t)) = h\left( \ddt{v_1(t)}, v_2(t) \right) + h\left( v_1(t), \ddt{v_{2}(t)} \right).$$

> [!proposition] 
> Suppose $f\colon M\to N$ is a diffeomorphism, and $v$ is a vector field on $N$, then $$f^{*}(i_{v}\omega)=i_{f^{*}v}f^{*}\omega, \quad\text{for all }\omega\in\Omega^{k}(N).$$ ^bfdff9

*Proof*  For all $p\in M$, we have LHS$$\begin{aligned}f^{*}(i_{v}\omega)\bigg|_{p}(u_{1},u_{2},\dots,u_{k-1})&=i_{v}\omega(\d_{p}f(u_{1}),\dots,\d_{p}f(u_{k-1}))\\ &=\omega(v(f(p)),\d_{p}f(u_{1}),\dots,\d_{p}f(u_{k-1})),\end{aligned}$$and RHS$$\begin{aligned}i_{f^{*}v}f^{*}\omega\bigg|_{p}(u_{1},u_{2},\dots,u_{k-1})&=f^{*}\omega((f^{*}v)(p),u_{1},\dots,u_{k-1})\\ &=\omega(\d_{p}f((\d_{p}f)^{-1}(v(f(p)))),\d_{p}f(u_{1}),\dots,\d_{p}f(u_{k-1}))\\ &=\omega(v(f(p)),\d_{p}f(u_{1}),\dots,\d_{p}f(u_{k-1})).\end{aligned}$$ $\square$

> [!definition] Lie Derivative of Differential Forms
> Suppose $M$ is a [[Manifolds, Atlases and Smooth Structures#^6ef2ef|smooth manifold]], and $\{f_{t}\}_{t\in\R}$ is a [[Integral Curves and Flows#^990d6a|global flow]] on $M$. Let $v$ be a [[Vector Fields and Lie Algebra#^a87ff1|vector field]] generated by $\{f_{t}\}_{t\in\R}$, then we define the Lie derivative of a differential form $\omega$ on $M$ as $$\newcommand{\L}{\mathcal{L}}\L_{v}\omega:=\ddf{}{t}\bigg|_{t=0} f^{*}_{t} \omega.$$

We can get the following property of the Lie derivative immediately from the definition:

> [!proposition]
> Suppose $\{f_{t}\}_{t\in\R}$ is a [[Integral Curves and Flows#^990d6a|global flow]] on $M$. Let $v$ be a [[Vector Fields and Lie Algebra#^a87ff1|vector field]] generated by $\{f_{t}\}_{t\in\R}$, then $$\ddt{}\bigg|_{t=s}f_{t}^{*}\omega=f_{s}^{*}\L_{v}\omega.$$
> 

*Proof*  $$\begin{aligned}\ddt{}\bigg|_{t=s}f_{t}^{*}\omega &= \ddtz f_{s+t}^{*}\omega\\ &= \ddtz (f_{s}^{*}\circ f_{t}^{*}) \omega \\ &= f_{s}^{*}\left( \ddtz f_{t}^{*}\omega \right)\\&= f_{s}^{*}\L_{v}\omega.\end{aligned}$$$\square$

> [!lemma]
> For a smooth function $x\in C^{\infty}(M)$, there holds $\L_{v}x=i_{v}\d x$, and $\L_{v}\d x=\d(i_{v}\d x)$. ^aca94f

*Proof*  This is in fact a special case of the [[Differential Forms#^04ae6c|Cartan's formula]]. $\square$

<u><b>e.g.</b></u>  We can use these two properties to evaluate a Lie derivative. Suppose $v:=\partial_{1}+x_{2}\partial_{2}-x_{3}\partial_{3}$, then $$\begin{aligned}&\,\L_{v}(\d x_{1}\wedge \d x_{2}+\d x_{2} \wedge  \d x_{3}) \\ =&\, \L_{v}(\d x_{1}\wedge \d x_{2}) + \L_{v}(\d x_{2}\wedge\d x_{3}) \\ =&\, \L_{v}\d x_{1} \wedge \d x_{2} + \d x_{1} \wedge \L_{v}\d x_{2}+\L_{v}\d x_{2} \wedge \d x_{3} + \d x_{2} \wedge \L_{v}\d x_{3} \\ =&\, \d(i_{v}\d x_{1}) \wedge \d x_{2} + \d x_{1} \wedge \d(i_{v}\d x_{2}) + \d (i_{v}\d x_{2}) \wedge \d x_{3} + \d x_{2} \wedge \d (i_{v}\d x_{3}).\end{aligned}$$Note that $$i_{v}\d x_{1}=\d x_{1}(\partial_{1}+x_{2}\partial_{2}-x_{3}\partial_{3})=(\partial_{1}+x_{2}\partial_{2}-x_{3}\partial_{3})x_{1}=1,$$and similarly, $i_{v}\d x_{2}=x_{2}$, $i_{v}\d x_{3}=-x_{3}$. So we have $$\begin{aligned}&\,\L_{v}(\d x_{1}\wedge \d x_{2}+\d x_{2} \wedge  \d x_{3}) \\ =&\, \d(1)\wedge \d x_{2} + \d x_{1}\wedge \d(x_{2}) + \d(x_{2})\wedge\d x_{3} + \d x_{2}\wedge\d(-x_{3}) \\ =&\, 0+\d x_{1}\wedge\d x_{2} + \d x_{2}\wedge\d x_{3} -\d x_{2}\wedge\d x_{3} \\ =&\, \d x_{1}\wedge\d x_{2}.\end{aligned}$$

> [!proposition]
> $\L_{v}(i_{w}\eta) = i_{L_{v}w}\eta + i_{w}\L_{v}\eta$ for any differential $k$-form $\eta\in\Omega^{k}(M)$. ^d9e627

*Proof*  By the [[Differential Forms#^bfdff9]|proposition]], we know that $f_{t}^{*}(i_{w}\eta)=i_{f^{*}w}f^{*}\eta$, substituting into the LHS, we obtain $$L_{v}(i_{w}\eta)=\ddt{}\bigg|_{t=0}f_{t}^{*}(i_{w}\eta) = \ddt{}\bigg|_{t=0}i_{f_{t}^{*}w}f_{t}^{*}\eta.$$Note that $i$ is bilinear as a map $\mathfrak{X}(M)\times\Omega^{k}(M)\to\Omega^{k-1}(M)$, so by question (9), we can write $$\ddt{}\bigg|_{t=0}i_{f_{t}^{*}w}f_{t}^{*}\eta=i_{\ddt{}\bigg|_{t=0}f_{t}^{*}w}f_{0}^{*}\eta+i_{f_{0}^{*}w} \ddt{}\bigg|_{t=0}f_{t}^{*}\eta=i_{L_{v}w}\eta + i_{w}L_{v}\eta,$$where the last equality holds because $f_{0}$ is the identity map. $\square$

> [!proposition]
> For all $x\in C^{\infty}(M)$, and [[Vector Fields and Lie Algebra#^a87ff1|vector fields]] $v,w\in\mathfrak{X}(M)$, $$\L_{v}xw=(\L_{v}x)w + x \L_{v}w.$$ ^c06166

*Proof*  Fix some arbitrary $p\in M$, consider the vector field $L_{v}xw$ at $p$: $$\begin{aligned}
(L_{v}xw)(p)&= \ddtz (f_{t}^{*}xw)(p)\\
&= \ddtz (\d_{p}f_{t}^{*})^{-1} [(xw)(f_{t}(p))] \\
&= \ddtz (\d_{p}f_{t}^{*})^{-1} [x(f_{t}(p))\cdot w(f_{t}(p))]\\
&= \ddtz x(f_{t}(p))\cdot  (\d_{p}f_{t}^{*})^{-1} [w(f_{t}(p))]\\
&= \ddtz (f_{t}^{*}x)(p)\cdot  (f_{t}^{*}w)(p)\\
&= \ddtz(f_{t}^{*}x)(p) \cdot (f_{0}^{*}w)(p) + (f_{0}^{*}x)(p) \cdot \ddtz(f_{t}^{*}w)(p)\\
&= (L_{v}x)(p)w(p)+x(p)(L_{v}w)(p),
\end{aligned}$$where the fourth equation follows from linearity of $(\d_{p}f_{t}^{*})^{-1}$, and the sixth equation is by the product rule. Since the above holds for all $p\in M$, we have $$L_{v}xw=(L_{v}x)w + x L_{v}w.$$$\square$

> [!corollary] Identifying Lie Derivative with Lie Bracket
> For any smooth function $x\in C^{\infty}(M)$, and vector fields $v,w\in\mathfrak{X}(M)$, $$\L_{\L_{v}w}x=(\L_{v}\L_{w}-\L_{w}\L_{v})x.$$If we identify vector fields $v$ with their action $\L_{v}$ on functions, this is the formula $$\L_{v}w=[v,w].$$

*Proof*  By the [[Differential Forms#^c06166|above proposition]], for the 1-form $\d x$, we have: $$\L_v (i_w\,\mathrm{d}x) = i_{L_{v} w}\d x + i_{w} (\L_{v}\d x).$$Using [[Differential Forms#^aca94f|the lemma]], we identify the terms as follows: $$i_{w}\d x = \L_w x, \quad i_{\L_{v} w}\d x = \L_{\L_{v} w} x, \quad i_{w} (\L_{v}\d x) = \L_{w} \L_{v} x.$$Substituting into the original equation yields: $$\L_v \L_w x = \L_{\L_v w} x + \L_w \L_v x.$$Rewriting, we find: $$\L_{\L_v w} x = (\L_v \L_w - \L_w \L_v) x,$$which implies $\L_v w=[v, w]$ as expected. $\square$

<u><b>e.g.</b></u>  $\L_{x_{1}\partial_{1}+x_{2}\partial_{2}}x_{2}\partial_{1}+x_{1}\partial_{2}$ can be seen easily as $0$ because $x_{1}\partial_{1}+x_{2}\partial_{2}$ commutes with $x_{2}\partial_{1}+x_{1}\partial_{2}$.

## The Exterior Derivative

On a smooth manifold, the exterior derivative extends the concept of the [[Tangent Vectors and Spaces#^c1b44c|differential]] of a function to differential forms of higher degree:

> [!definition] Exterior Derivative of Differential Forms
> The exterior derivative of a differential $k$-form is a differential $k+1$-form. It satisfies the following properties:
> - The exterior derivative of a $0$-form (i.e. smooth functions on $M$) is its differential.
> - It is a degree $1$ derivation of the graded commutative algebra $\Omega(M)$, $$\d (\omega_{1}\wedge\omega_{2})=\d\omega_{1}\wedge\omega_{2}+(-1)^{\deg\omega_{1}}\omega_{1}\wedge\d\omega_{2}.$$
> - $\d(\d f)=0.$
> - $\d$ is local in the sense that if $\omega$ vanishes on a neighborhood of $p\in M$, $\d\omega$ vanishes on a neighborhood of  $p\in M$.
>$\quad$ ^825b86

<u><b>e.g.</b></u>  We can use the above properties to compute: $$\begin{aligned}&\,\d(x\d y\wedge \d z+ x\d x\wedge \d z)\\=&\,\d(x\d y \wedge\d z)+\d(x\d x\wedge\d z)\\=&\, \d(x\d y) \wedge \d z + \d(x\d x)\wedge\d z\\=&\, \d x \wedge\d y\wedge \d z \end{aligned}$$

> [!proposition] Exterior Derivative Commutes with Pullback
> For any smooth map $f\colon M\to N$, and a differential form $\omega$ on $N$, we have $$f^{*}(\d\omega)=\d(f^{*}\omega).$$ ^3f9e68

> [!definition] Exact Form
> We call a differential form $\omega$ exact, if there exists a differential form $\lambda$, such that $\omega=\d\lambda$. ^c1760d

> [!theorem] Cartan's Formula
> Suppose $M$ is a smooth manifold, and $v$ is a vector field on $M$. Then for any differential form $\omega$, $$L_{v}\omega=\d(i_{v}\omega)+i_{v}(\d\omega).$$ ^04ae6c