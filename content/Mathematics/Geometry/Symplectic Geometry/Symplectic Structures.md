---
completed: true
updated: 2025-09-01
---
## The Symplectic Form

> [!definition] Symplectic Manifold
> Let $M$ be an even dimensional [[Manifolds, Atlases and Smooth Structures#^6ef2ef|smooth manifold]]. A symplectic structure on $M$ is a closed non-degenerate [[Differential Forms#^c6c1be|differential 2-form]] $\omega \in \Omega^{2}(M)$, called the *symplectic form*, such that $\newcommand{\d}{\mathrm{d}}\newcommand{\R}{\mathbb{R}}\d\omega=0$, and for all nonzero $v\in T_{p}M$, there exists $u\in T_{p}M$ so that $\omega(v,u)\neq 0$. The pair $(M,\omega)$ is called a *symplectic manifold*.
> We call a symplectic manifold *exact* if the symplectic form is [[Differential Forms#^c1760d|exact]]. ^b558c2

<u><b>e.g.</b></u>  
- Suppose $(x^{1},\dots,x^n,y^1,\dots,y^n)$ is a coordinate of $\R^{2n}$. Then $\omega=\sum_{i} \d x^{i}\wedge\d y^{i}$ is the standard symplectic form on $\R^{2n}$, with exact form $\lambda=\sum_{i} x^{i}\d y^{i}$. Clearly, $\d\omega=0$ by definition of the [[Differential Forms#^825b86|exterior derivative]].
- The cotangent bundle $T^{*}M$ of a smooth manifold $M$ has a natural exact symplectic structure. In fact, there is a canonical 1-form on $T^{*}M$, which can be defined as follows: suppose $\pi\colon T^{*}M\to M$ is the natural projection that maps any covector to the base point where it is defined. Then the canonical differential 1-form $\lambda\in\Omega^{1}(T^{*}M)$ is defined by $$\lambda_{\alpha}(\xi):=\alpha(\d\pi(\xi)),\quad \text{for all }\alpha\in T^{*}M, \xi\in T_{\alpha}(T^{*}M).$$It turns out that $\d\lambda$ is a symplectic form on $T^{*}M$. In fact, the cotangent bundle is identified as the [[Phase Space & Chaos#^e2ae52|phase space]] in [[Classical Mechanics|classical mechanics]].
$\quad$

> [!definition] Symplectomorphism
> A *symplectomorphism* is a [[Smooth Functions and Maps#^39ce42|diffeomorphism]] $f\colon M\to N$ between symplectic manifolds $(M,\omega_{M})$ and $(N,\omega_{N})$ such that $f^{*}\omega_{N}=\omega_{M}$. ^2dbbf4

> [!proposition]
> Given a diffeomorphism $f\colon M\to N$, there is a canonical diffeomorphism $F\colon T^{*}M\to T^{*}N$ such that $F^{*}\lambda_{N}=\lambda_{M}$, where $\lambda_{M}$ and $\lambda_{N}$ are the canonical 1-forms on $T^{*}M$ and $T^{*}N$ respectively. Thus $F$ is a symplectomorphism.
> 

## Hamiltonian Vector Fields

A Riemannian metric on a manifold establishes an isomorphism between the space of tangent vectors and the space of cotangent vectors (i.e. 1-forms). A symplectic structure establishes a similar isomorphism.

> [!lemma] Symplectic Duality
> Let $(M,\omega)$ be a symplectic manifold. To each vector $v\in T_{p}M$, we associate a 1-form $\alpha_{v}\in T_{p}^{*}M$ by the relation $$\alpha_{v}(u):=\omega(u,v), \quad\text{for all } u\in T_{p}M.$$Then the correspondence $v\mapsto\alpha_{v}$ is an isomorphism between $T_{p}M$ and $T_{p}^{*}M$. The isomorphism is called the symplectic duality, denoted as $\iota$. ^c6bf0f

*Proof*  This is straightforward from the construction. $\square$

> [!definition] Hamiltonian Vector Field
> Let $(M,\omega)$ be a symplectic manifold. The Hamiltonian vector field associated with a smooth function $H\colon M\to\R$, called the Hamiltonian function, is the vector field $X_{H}\in\mathfrak{X}(M)$ defined by $$ X_{H}:=\iota^{-1} (\d H).$$

> [!proposition] Equivalent Definition of Hamiltonian Vector Field
> Given a smooth function $H\colon M\to\R$ on a symplectic manifold $(M,\omega)$, the Hamiltonian vector field $X_{H}$ is the unique vector field such that $$ \d H =-i_{X_{H}}\omega=\omega(\cdot,X_{H}).$$

*Proof*  $X_{H}$ is the Hamiltonian vector field iff $$X_{H}=\iota^{-1} (\d H) \iff \d H=\iota(X_{H})=\omega(\cdot, X_{H}).$$$\square$

<u><b>e.g.</b></u>  
- Suppose $(p_{1},\dots,p_{n},q_{1},\dots,q_{n})$ is a coordinate for $\R^{2n}$, let the standard symplectic form be $\omega=\sum_{i}\d p_{i} \wedge \d q_{i}$. Then the vector field defined by the [[Hamiltonian & Symmetries#^5ef3ed|Hamilton's equations of motion]]: $$\newcommand{\pddf}[2]{\frac{\partial#1}{\partial#2}}\dot p_j = - \frac{\partial H}{\partial q_{j}},\quad \dot q_j = \frac{\partial H}{\partial p_{j}}$$is the Hamiltonian vector field $X_{H}$ associated with the Hamiltonian function $H\colon \R^{2n}\to\R$. We can show this by checking that the vector field defined by the Hamilton's equations of motion, say $$X(p_{1},\dots,p_{n},q_{1},\dots,q_{n}):=\sum_{i=1}^{n}\left(-\frac{\partial H}{\partial q_{i}}\pddf{}{p_{i}}+\pddf{H}{p_{i}}\pddf{}{q_{i}}\right)$$satisfies the equation $\d H =-i_{X_{H}}\omega=\omega(\cdot,X).$ Indeed, for any vector field $Y\in\mathfrak{X}(\R^{2n})$, we have $$\newcommand{\L}{\mathcal{L}}\begin{aligned}\omega(Y,X)&=\sum_{i}^{n}(\d p_{i} \wedge \d q_{i})(Y,X) \\ &= \sum_{i=1}^{n} \d p_{i}(Y)\d q_{i}(X) - \d p_{i}(X)\d q_{i}(Y) \\ &= \sum_{i=1}^{n} \d p_{i}(Y) X(q_{i}) - X(p_{i})\d q_{i}(Y) \\ &= \sum_{i=1}^{n} \d p_{i}(Y) \pddf{H}{p_{i}} + \pddf{H}{q_{i}} \d q_{i}(Y) \\ &= \d H(Y). \end{aligned}$$
- Consider the symplectic structure on the torus $\newcommand{\Z}{\mathbb{Z}}T^{2}=\R^{2}/\Z^{2}$ induced by the standard symplectic structure on $\R^{2}$, with coordinates $(p,q)$ and consider the vector field $X=\partial/\partial p$. The the flow of this vector field preserves the symplectic form: $$\begin{aligned}\L_{X}\omega&= \L_{X}(\d p\wedge\d q)\\ &= i_{X}\d\omega + \d (i_{X}(\d p\wedge \d q))\\&= \d((i_{X}\d p)\wedge \d q - \d p \wedge (i_{X}\d q))\\&= \d(\d q)\\&= 0.\end{aligned}$$But this vector field is not a Hamiltonian vector field, because if we assume $X$ is Hamiltonian, then we have $$-\d q=-i_{X}(\d p \wedge\d q)=\d H=\pddf{H}{p}\d p + \pddf{H}{q}\d q,$$it follows that $$\pddf{H}{p}=0,\quad \pddf{H}{q}=-1,$$which means $H(p,q)=-q+C$ for some constant $C\in\R$. Note that $T^{2}$ has no global chart, so $H$ can't be defined smoothly globally. In detail, at some point $z\in T^{2}$, the value of $H$ at $z$ must be the same for all charts that cover $z$. Since $(p,q)\mapsto-q+C$ is injective, these charts must be the same. However, $T^{2}$ has no global chart, so this is impossible. Alternatively, observe that $(p,q)\mapsto-q+C$ is strictly decreasing, so for some appropriate points $z_{1},z_{2}\in T^{2}$, under the chart $(p,q)$ at $z_{1}$ and $(p',q')$ at $z_{2}$, we might have $H(z_{1})<H(z_{2})$ and $H(z_{1})>H(z_{2})$ both hold. This is a contradiction, thus $X$ is not Hamiltonian.
$\quad$

## Conserved Quantities

> [!proposition]
> Suppose $X_{H}$ is a Hamiltonian vector field associated with a Hamiltonian function $H\colon M\to\R$ on a symplectic manifold $(M,\omega)$. Then $\L_{X_{H}}\omega=0$ and $\L_{X_{H}}H=0$. ^72585c

*Proof*  By [[Differential Forms#^04ae6c|Cartan's formula]], we have $$\L_{X_{H}}\omega=\d(i_{X_{H}}\omega)+i_{X_{H}}(\d\omega)=\d(i_{X_{H}}\omega)$$since $\d\omega=0$. By the definition of Hamiltonian vector field, we know that $i_{X_{H}}\omega=-\d H$. Therefore, we have $$\L_{X_{H}}\omega=\d(i_{X_{H}}\omega)=-\d(\d H)=0.$$For the second part, we have $$\L_{X_{H}}H=i_{X_{H}}(\d H)=\d H(X_{H})=\omega(X_{H},X_{H})=0.$$$\square$

> [!remark]+
> The second equation $\L_{X_{H}}H=0$ means that the Hamiltonian $H$ is conserved along the flow of the Hamiltonian vector field $X_{H}$. In a [[Lagrangian Dynamical System#^466228|natural Lagrangian system]], the Hamiltonian is the total energy of the system, and thus it is conserved. This is a manifestation of the conservation of energy in classical mechanics.
> 

> [!proposition] Symplectic Manifolds Have a Natural Volume Form
> If $(M,ω)$ is a symplectic manifold, then the $n$th wedge of $ω$ is a [[Differential Forms#^923fae|volume form]], and also the flow of $X_{H}$ preserves this volume form. ^bec446

*Proof*  Clearly $\omega^{n}$ is a $2n$-form on $M$. To see that it is a volume form, we need to check that it is non-degenerate. This follows from the fact that $\omega$ is non-degenerate. To see that the flow of $X_{H}$ preserves this volume form, we show that $\L_{X_{H}}\omega^{n}=0$: $$\begin{aligned}\L_{X_{H}}(\omega^{n})=\d (i_{X_{H}}\omega^{n})+ i_{X_{H}} \d \omega^{n} \end{aligned}.$$Note that $\d\omega^{n}=0$ since $\d\omega=0$. Therefore, we have $$\L_{X_{H}}(\omega^{n})=\d(i_{X_{H}}\omega^{n}).$$Moreover, $$\begin{aligned}\d(i_{X_{H}}\omega^{n})&=\d(i_{X_{H}}(\omega\wedge\omega^{n-1}))\\&=\d((i_{X_{H}}\omega)\wedge \omega^{n-1} + \omega\wedge i_{X_{H}}(\omega^{n-1}))\\&= \d(-\d H\wedge \omega^{n-1}) +\d(\omega\wedge i_{X_{H}}(\omega^{n-1}))\\ &= \d(\omega\wedge i_{X_{H}}(\omega^{n-1}))\\&= \d\omega \wedge i_{X_{H}}(\omega^{n-1}) +\omega\wedge \d(i_{X_{H}}(\omega^{n-1}))\\&=\omega\wedge \d(i_{X_{H}}(\omega^{n-1})), \end{aligned}$$so by induction, we have $\d(i_{X_{H}}\omega^{n})=0$. Thus $\L_{X_{H}}(\omega^{n})=0$. $\square$

> [!proposition]
> There are no compact exact symplectic manifolds.
> 

*Proof*  In fact, there is a unique vector field $X:=-\iota^{-1}(\lambda)$, such that $i_{X}\omega=\lambda$. So that $$\L_{X}\omega=\d(i_{X}\omega)+i_{X}\d\omega=\d\lambda=\omega.$$Hence, 

> [!definition] Action of a Loop
> Given an oriented closed loop $\gamma$ in an exact symplectic manifold $(M, \omega=\d\lambda)$, the action of $\gamma$ is defined as $$A(\gamma):=\int_{\gamma}\lambda.$$

> [!proposition]
> The flow of any Hamiltonian vector field preserves the action. 
> 

*Proof*  To show this, suppose $h_{t}$ is a flow of a Hamiltonian vector field $X_{H}$, we claim that $$\newcommand{\ddt}{\ddf{}{t}}\ddt A(h_{t}(\gamma))=\ddt\int_{h_{t}(\gamma)}\lambda=\ddt\int_{\gamma}h_{t}^{*}\lambda=\int_{\gamma}\ddt h_{t}^{*}\lambda=\int h_{t}^{*}(\L_{X_{H}}\lambda)$$
