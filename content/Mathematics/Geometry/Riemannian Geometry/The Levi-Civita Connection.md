> [!definition] Compatibility
> Let $M$ be a smooth Riemannian manifold with metric $g$. A connection $∇$ on $M$ is said to be compatible with the metric $g$ if for every pair of vector fields $X$ and $Y$ on $M$, and every vector $Z ∈ \mathfrak{X}(M)$, $$Z\left(g(X,Y)\right)=g\left(\nabla_ZX,Y\right)+g\left(X,\nabla_ZY\right).$$

> [!remark]
> It is equivalent to say that $\nabla g=0$. However, this is not a good notation because it does not make sense to apply the affine connection on a $(0,2)$-tensor. It is meaningful once we define that $$\nabla g:=(\nabla^{*}\otimes\nabla^{*}) g,$$where $\nabla^{*}$ is the [[Connections#^944a20|dual connection]] of $\nabla$.
> 

> [!definition] Levi-Civita Connection
> An [[Connections#^f86a0b|affine connection]] defined on $(M,g)$ is called a Levi-Civita connection if it is compatible with the metric $g$ and it is [[Torsion and Curvature#^bec0c5|torsion free]]. ^c56d8f

> [!theorem] Fundamental Theorem of Riemannian Geometry
> Every Riemannian manifold admits a unique Levi-Civita connection. In particular, the unique Levi-Civita connection has the following coordinate expression: $$\Gamma_{ij}^{k}=\frac{1}{2}g^{kl}(\partial_{i}g_{jl}+\partial_{j}g_{il}-\partial_{l}g_{ij}).$$

