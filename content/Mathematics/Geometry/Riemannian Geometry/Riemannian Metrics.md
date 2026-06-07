There is one more crucial ingredient which we need to introduce for dealing with manifolds: lengths and angles. Given a smooth manifold, since we know what it means for a curve in the manifold to be smooth, and we have a well-defined notion of the tangent vector to a curve, all we need in order to have a notion of distance on the manifold is a way of defining the speed of a curve — that is, the length of its tangent vector.

## Metric Tensors

>[!definition] Metric Tensor & Semi-Riemannian Manifold
>A (Semi-Riemannian) metric tensor $g$ on $M$ is a $(0,2)$-[[Tensor Fields#^efc3f2|tensor]], which at each $p\in M$, takes a pair of tangent vectors $u,v\in T_{p}(M)$ and returns a [[Number Systems#^5fea5c|real number]] $g_{p}(u,v)$ such that
>- $g_{p}$ is symmetric, that is $g_{p}(u,v)=g_{p}(v,u)$.
>- $g_{p}$ is nondegenerate, that is for every $u \neq 0$, there is a $v$ such that $g_{p}(u,v)\neq 0$.
>
> A semi-Riemannian manifold is a [[Manifolds, Atlases and Smooth Structures#^6ef2ef|smooth manifold]] furnished with a metric tensor. ^c3ac13

>[!definition] Riemannian Metric &  Riemannian Manifold
> A Riemannian metric $g$ on a smooth manifold $M$ is a nonnegative metric tensor, that is $g_{p}(u,v)\geq 0$ for all $u\in T_{p}(M)$ and $g_{p}(u,u)=0$ if and only if $u=0$.
> A pair $(M,g)$ is called a Riemannian manifold. ^07b56e
>

<u><b>e.g.</b></u>  
- The standard inner product on Euclidean space is a trivial example of a Riemannian metric.
- Consider $S^{2}\subset\R^{3}$ with standard spherical coordinates $(\theta,\phi)$ with $\theta\in[0,\pi]$ and $\phi\in[0,2\pi]$, the metric tensor from $\R^{3}$ is given by $$g=\dd\theta^{2}+\sin^{2}\theta \dd\phi^{2}.$$

> [!definition] Metric Signature
> The signature of a metric tensor $g$ is the pair of integers $(p,q)$ (or sometimes the integer difference $p-q$) that records, respectively, the number of positive and negative eigenvalues of the symmetric matrix representation of the metric at a point.
> Sometimes it may also be denoted as an explicit list such as $(+, −, −, −)$ or $(−, +, +, +)$. ^48a20c

<u><b>e.g.</b></u>  A Riemannian metric has signature $(n,0)$.

> [!definition] Killing Vector Field
> A killing vector field on a semi-Riemannian manifold is a vector field $X$ for which the Lie derivative of the metric tensor $g$ vanishes: $\L_{X}g=0$.
> 

## Length and Distance

**Def**  <i><u>Length of a Curve</u></i>
Let $\gamma\colon[a,b]\to M$ be a piecewise smooth curve in a Riemannian manifold $(M,g)$. The length $L[\gamma]$ of $\gamma$ is defined by $$L[\gamma]=\int_{a}^{b}g_{\gamma(t)}(\gamma^{\prime}(t),\gamma^{\prime}(t))^{\frac{1}{2}}\dd t$$

**Def**  <i><u>Distance</u></i>
Given two points $p$ and $q$ in a Riemannian manifold $(M,g)$, the distance $d(p,q)$ between $p$ and $q$ is defined by $$d(p,q)=\inf\left\{ L[\gamma] | \gamma \colon [a,b]\to M \text{ piecewise smooth satisfying } \gamma(a)=p, \gamma(b)=q \right\}$$

**Prop**  If $M$ is a Riemannian manifold with metric $g$, then $M$ is a metric space with the distance function $d$ defined above. The metric topology agrees with the manifold topology.
