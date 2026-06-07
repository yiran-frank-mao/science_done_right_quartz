> [!definition] Liouville measure
> Let $(M,\omega)$ be a symplectic manifold. The Liouville measure (or symplectic measure) of a Borel subset $U$ of $M$ is defined as $$m_{\omega}(U)=\int_{U}\frac{\omega^{n}}{n!}.$$

> [!theorem] Duistermaat-Heckman Theorem
> The Duistermaat-Heckman measure is a piecewise polynomial multiple of Lebesgue (or euclidean) measure $m_0$ on $\mathfrak{g}^* \cong \R^n$, that is, the Radon-Nikodym derivative
> $$ f = \frac{\d m_{DH}}{\d m_{0}} $$
> is piecewise polynomial. More specifically, for any Borel subset $U$ of $\mathfrak{g}^*$,
> $$ m_{DH}(U) = \int_U f(x)\,dx, $$
> where $\d x = \d m_{0}$ is the Lebesgue volume form on $U$ and $f\colon \mathfrak{g}^* \cong \R^n \to \R$ is polynomial on any region consisting of regular values of $\mu$.

> [!corollary] Symplectic Volume of Toric Symplectic Manifolds
> In the case of a [[Toric Symplectic Manifold#^4025d9|toric symplectic manifold]], the Duistermaat-Heckman polynomial is a universal constant equal to $(2\pi)^{n}$ when its [[Toric Symplectic Manifold#^f18435|corresponding Delzant polytope]] $\Delta$ is $n$-dimensional. Thus the symplectic volume of $(M_{\Delta},\omega_{\Delta})$ is $(2\pi)^{n}$ times the euclidean volume of $\Delta$.

<u><b>e.g.</b></u>  
- For $\C P^{n-1}$ with the standard toric symplectic structure, the moment map is given by $$\mu([z_{1}:\dots:z_{n}])=\left(\frac{|z_{1}|^{2}}{2\left(\sum_{k}|z_{k}|^{2}\right)},\dots,\frac{|z_{n}|^{2}}{2\left(\sum_{k}|z_{k}|^{2}\right)}\right),$$and the moment polytope is the simplex with vertices $(0,\dots,0)$ and $(1,0,\dots,0)$, $(0,1,0,\dots,0)$, $\dots$, $(0,\dots,0,1)$. So the Euclidean volume of the simplex is $\frac{1}{n!}$. The symplectic volume of $\C P^{n-1}$ is then $\frac{(2\pi)^{n}}{n!}$.
- We can verify this in $\C P^{2}$. 