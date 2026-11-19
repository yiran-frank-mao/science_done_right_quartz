Suppose $M$ is a smooth manifold. If $\gamma\colon I\to M$ is a smooth curve, then for each $t\in I$, the velocity vector $\dot{\gamma}(t)$ is a vector in $T_{\gamma(t)}M$. In this section we describe a way to work backwards: given a tangent vector at each point, we seek a curve whose velocity at each point is equal to the given vector there.

## ODEs on Manifolds

> [!definition] Integral Curve
> An integral curve of a vector field $V\in\mathfrak{X}(M)$ is a smooth curve $\gamma\colon I\to M$ such that $\dot{\gamma}(t)=V(\gamma(t))$ for all $t\in I$. ^8974d8

> [!theorem]
> Suppose $M$ is a smooth manifold. For any vector field $V\in\mathfrak{X}(M)$ and any $p\in M$, there exists a unique solution of the initial value problem for $V$ at $p$. That is, there exists an integral curve $\gamma\colon [0,\varepsilon]\to M$ of $V$ for some $\varepsilon>0$ such that $\gamma(0)=p$.

*Proof*  In fact, this is a local problem at $p$. We choose a [[Manifolds, Atlases and Smooth Structures#^441ce2|chart]] at $p$, say $\varphi\colon U\to \R^{n}$, then the initial value problem becomes a [[Ordinary Differential Equations#^0c9610|first order ODE]] in $\R^{n}$, which has a unique solution by [[Ordinary Differential Equations#^0a1064|the theorem]]. $\square$

<u><b>e.g.</b></u>  Let $M=\R$ and $V(x)=x^{2}\partial_{x}$. Fix some initial point $x_{0}\in\R$, choose $\id\colon\R\to\R$ as a chart, we solve the ODE $\dot{\gamma}(t)=\gamma(t)^{2}$ to get $\gamma(t)=\frac{1}{c-t}$ for some constant $c\in\R$. Now let $x_{0}=\gamma(0)$, we obtain $c=\frac{1}{x_{0}}$, so $\gamma(t)=\frac{1}{1/x_{0} -c}$, which indicates that the maximal interval of the integral curve is $[0,1/x_{0})$.

> [!lemma] Rescaling Lemma
> Let $V$ be a smooth vector field on a smooth manifold $M$, let $J \subseteq \R$ be an interval, and let $\gamma \colon J \to M$ be an integral curve of $V$. For any $a \in \R$, the curve $\tilde{\gamma} \colon \tilde{J} \to M$ defined by $\tilde{\gamma}(t) = \gamma(at)$ is an integral curve of the vector field $aV$, where $\tilde{J} = \{t : at \in J\}$.

> [!lemma] Translation Lemma
> Let $V$, $M$, $J$, and $\gamma$ be as in the preceding lemma. For any $b \in \R$, the curve $\hat{\gamma} \colon \hat{J} \to M$ defined by $\hat{\gamma}(t) = \gamma(t + b)$ is also an integral curve of $V$, where $\hat{J} = \{t : t + b \in J\}$.

Another good property of solutions to initial value problems is that they depend smoothly on the initial point:

> [!proposition] Vector Fields Generate Local Flows
>  For any vector field $V\in\mathfrak{X}(M)$ and any $p\in M$, there exists a neighbourhood $U$ of $p$, such that if $\Phi\colon U\times I\to M$ satisfies $\Phi(x,t)$ is an integral curve of $V$ at $x\in U$, then $\Phi_{t}:=\Phi(-,t)$ is a [[Differential Calculus#^2d0ba0|local diffeomorphism]] for all $t$, and $$\Phi_{t}\circ \Phi_{s}=\Phi_{t+s},$$ whenever $t+s\in I$. ^58f6d4

## Global Flows

An important special case is where the manifold $M$ is compact, or more generally where the support of the vector field is compact: In this case we have a globally defined flow.

> [!definition] Diffeomorphism Group of a Manifold
> Let $M$ be a smooth manifold. Then, the diffeomorphism group of $M$, denoted as $\newcommand{\Diff}{\mathrm{Diff}}\Diff(M)$, is the group of all diffeomorphisms $f\colon M\to M$ with the operation of composition.

> [!definition] Global Flow
> A global flow on $M$ is a smooth one parameter group of diffeomorphisms $f_{t}\colon M\to M$. This means that $\newcommand{\id}{\mathrm{id}}f_{0}=\id$ and $f_{t+s}=f_{t}\circ f_{s}$ for all $t,s\in \R$, and $(t,p)\mapsto f_{t}(p)$ is smooth on $\R\times M$. In other words, it is a continuous left [[Group Actions#^4047e8|action]] of $\R$ on $M$. ^990d6a

## Fundamental Theorem on Flows

> [!definition] Maximal Integral Curve & Maximal Flow
> A maximal integral curve is one that cannot be extended to an integral curve on any larger open interval, and a maximal flow is a flow that admits no extension to a flow on a larger flow domain.

> [!theorem] Fundamental Theorem on Flows
> Let $V$ be a smooth vector field on a smooth manifold $M$. There is a unique smooth maximal flow. 

## Complete Vector Field

> [!definition] Complete Vector Field
> A vector field $V\in \mathfrak{X}(M)$ is complete if it generates a global flow on $M$.

> [!proposition] Compactly Supported Vector Fields Generate Global Flows
> Suppose $V\in\mathfrak{X}(M)$ has compact support, that is, $\supp(V)=\overline{\{x\in M:V(x)\neq 0\}}$ is a [[Compactness of Topological Space#^da2511|compact subset]] of $M$. Then $V$ is complete.
> 

> [!proposition]
> Every smooth vector field on a compact manifold without boundary (i.e. $\partial M=\emptyset$) is complete. 
> In general, if $M$ is a compact manifold with boundary, then every smooth vector field on $M$ is complete if and only if it is tangent to the boundary $\partial M$.
> 

## Commuting Vector Fields

> [!theorem] Canonical Form for Commuting Vector Fields
> Let $M$ be a smooth $n$-manifold, and let $(V_1, \ldots, V_k)$ be a linearly independent $k$-tuple of smooth commuting vector fields on an open subset $W \subseteq M$. For each $p \in W$, there exists a smooth coordinate chart $(U, (s^i))$ centered at $p$ such that $V_i = \partial/\partial s^i$ for $i = 1, \ldots, k$.  
> If $S \subseteq W$ is an embedded codimension-$k$ submanifold and $p$ is a point of $S$ such that $T_pS$ is complementary to the span of $(V_1|_p, \ldots, V_k|_p)$, then the coordinates can also be chosen such that $S \cap U$ is the slice defined by $s^1 = \cdots = s^k = 0$.

## Lie Derivatives

> [!definition] Lie Derivative of Vector Fields
> Suppose $M$ is a [[Manifolds, Atlases and Smooth Structures#^6ef2ef|smooth manifold]], and $\{f_{t}\}_{t\in\R}$ is a [[Integral Curves and Flows#^990d6a|flow]] on $M$. Let $v$ be a vector field defined by $v(p):=\ddf{}{t}\bigg|_{t=0}f_{t}(p)$, then we define the Lie derivative of a [[Vector Fields and Lie Algebra#^a87ff1|vector field ]] $w$ on $M$ as $$L_{v}w:=\ddf{}{t}\bigg|_{t=0} f^{*}_{t} w.$$


