**Def**  <i><u>Hyperbolic Geometry</u></i>
The parallel postulate of Euclidean geometry is replaced with:
For any given line $R$ and point $P$ not on $R$, in the plane containing both line $R$ and point $P$ there are at least two distinct lines through $P$ that do not intersect $R$.

**Def**  <i><u>Hyperbolic 2-Space</u></i>
The hyperbolic 2-space $\mathbb{H}$ is defined to be the set of points in the upper half plane: $$\mathbb{H}^2=\{x+iy\in\mathbb{C}\mid y>0\}$$ equipped with the metric whose first fundamental form is given by $$\dd s^{2}=\frac{\dd x^{2}+\dd y^{2}}{y^2}$$Note that a point in $\mathbb{H}^2$ can either be thought of as a complex number $x + i y \in \mathbb{C}$ or as a point $(x, y) \in \R^2$. Both perspectives are useful: $\R^2$ leads more easily to coordinates and calculations, and C works seamlessly with our definition of isometries below.

**Prop**  <i><u>Arc length</u></i> and <i><u>Volume</u></i>
Suppose $\gamma(t)$ is a differentiable curve in $\mathbb{H}^2$ for $t\in[a,b]$, then we obtain a tangent vector $\gamma^\prime(t)$ in $\mathbb{H}^2$, called the velocity vector. The arc length of $\gamma$ for $t\in[a,b]$ is then
$$\begin{aligned}|
\gamma|=\int_{a}^{b}\sqrt{\left<\gamma^{\prime}(s),\gamma^{\prime}(s)\right>}\dd s=\int_{a}^{b}\sqrt{(\gamma_{x}'(s))^{2}+(\gamma_{y}'(s))^{2}}\frac1{\gamma_{y}(s)}\dd s
\end{aligned}$$ where $\gamma(t)=(\gamma_x(t),\gamma_y(t))$ and $\gamma^{\prime}(t)=\tr{(\gamma_x^{\prime}(t),\gamma_y^{\prime}(t))}$.
In the most general setting, if $R ⊂ M$ is contained in a coordinate neighborhood of the Riemannian manifold $M$, with coordinates $(x_{1},\dots,x_{n})$ and metric given by the matrix $g_{ij}$ in these coordinates, then we can compute the volume(area) of $R$ in $\mathbb{H}^2$ to be $$\begin{aligned}\text{vol}(R)=\int_Rd\:\text{vol}=\int_R\sqrt{\det(g_{ij})}\dd x_{1}\dots \dd x_{n}=\int_{R}\frac1{y^{2}}\dd x\dd y\end{aligned}$$
**Def**  <i><u>Boundary at Infinity</u></i>
We call $\R∪\{\infty\}$ the boundary at infinity for $\mathbb{H}^2$. Note it is homeomorphic to a circle $S^1$, and hence is sometimes called the circle at infinity. It is denoted by $S_{\infty}^{1}$ , $\partial\mathbb{H}^2$, and sometimes $\partial_\infty\mathbb{H}^2$.

**Def**  <i><u>Geodesic</u></i> and <i><u>Infinite Geodesic</u></i>
A geodesic between points $p$ and $q$ is a length minimizing curve between those points. An infinite geodesic is a curve $γ$ from $\R$ to a Riemannian manifold such that for any $s < t ∈ \R$, the curve $γ([s,t])$ minimizes the distance between $γ(s)$ and $γ(t)$.

**Thrm**  The infinite geodesics in $\mathbb{H}^2$ consist of vertical straight lines and semi-circles with center on the real line.

**Def**  Isometry