---
created: 2024-08-14
updated: 2024-10-23
---
## Divergence

>[!definition] Divergence
>A divergence $D\colon M\times M \to [0,\infty)$ is a $C^3$ function on a [[Manifolds and Atlases#^3407e4|manifold]] $M$, it satisfies the following properties:
>- $D(p:q) = 0$ if and only if $p = q$;
>- $\frac{\partial^{2}}{\partial q^{i}\partial q^{j}}D(p:q)|_{p=q}$ is positive definite.
>
>Given a divergence $D$, the dual divergence $D^*$ is defined by $$D^*(p:q) := D(q:p).$$

<u><b>e.g.</b></u>  The Euclidean distance is a [[Metric Spaces#^0eacc7|metric distance]] but not a divergence; The squared Euclidean distance is a non-metric symmetric divergence.

>[!proposition]
>$\frac{\partial^{2}}{\partial p^{i}\partial p^{j}}D(p:q)|_{p=q}=-\frac{\partial^{2}}{\partial p^{i}\partial q^{j}}D(p:q)|_{p=q}$

*Proof*  On the diagonal, the first order derivatives vanish, so it is constant, thus: $$\begin{aligned}&\frac{\partial}{\partial p^{i}}\left(\frac{\partial}{\partial p^{j}}+\frac{\partial}{\partial q^{j}}\right)D(p:q)|_{p=q}=0\\ \implies& \frac{\partial^{2}}{\partial p^{i}\partial p^{j}}D(p:q)|_{p=q}=-\frac{\partial}{\partial p^{i}}\frac{\partial}{\partial q^{i}}D(p:q)|_{p=q}\\ \implies &\frac{\partial^{2}}{\partial p^{i}\partial p^{j}}D(p:q)|_{p=q}=-\frac{\partial^{2}}{\partial p^{i}\partial q^{j}}D(p:q)|_{p=q}\end{aligned}$$

>[!theorem] Divergence-Induced Statistical Manifold
>Suppose $D$ is a divergence. Then $(M, g^{D}, \nabla^{D}, \nabla^{D^{*}} , C)$ is a statistical manifold with $$\begin{aligned}
g_{ij}^{D} :&= -\frac{\partial^{2}}{\partial p^{i} \partial q^{j}} D(p:q)\big|_{p=q}\\
\Gamma^{D}_{ijk}:&= -\frac{\partial^{3}}{\partial p^{i}\partial p^{j} \partial q^{k}} D(p:q)\big|_{p=q}\\
\Gamma^{D^{*}}_{ijk}:&= -\frac{\partial^{3}}{\partial q^{i}\partial q^{j} \partial p^{k}} D(p:q)\big|_{p=q}\\
C_{ijk}^{D}&=\Gamma^{D}_{ijk}-\Gamma^{D^*}_{ijk}
\end{aligned}$$We will use $(M, D)$ to denote the such divergence-induced statistical manifold.

*Proof*  Clearly the constructed connections are torsion-free. We need to check that the induced connections are conjugate to each other: $$\begin{aligned}
\Gamma_{kij}^{D} + \tilde{\Gamma}_{jik}^{D^{*}}&=-\frac{\partial^{3}}{\partial p^{k}\partial p^{i}\partial q^{j}} D(p:q)\big|_{p=q}-\frac{\partial^{3}}{\partial q^{j}\partial q^{i}\partial p^{k}} D(p:q) \big|_{p=q}\\
&= -\left(\frac{\partial}{\partial p^{i}}+\frac{\partial}{\partial q^{i}}\right)\frac{\partial^{2}}{\partial p^{k} \partial q^{j}}D(p:q)\big|_{p=q}\\
&= \partial_{i}\left( -\frac{\partial^{2}}{\partial p^{k} \partial q^{j}}D(p:q)\big|_{p=q} \right)\\
&= \partial_{i}(g_{jk}^{D})
\end{aligned}$$ $\square$

## Bregman Geometry

>[!definition] Bregman Divergence
>Suppose $M$ is a [[Manifolds and Atlases#^6ef2ef|smooth manifold]]. Let $U\subset M$ be a neighbourhood of some point homeomorphic to some Euclidean space under local [[Manifolds and Atlases#^441ce2|chart]] (coordinate) $\theta$. Given a [[Convex Functions#^c53709|strictly convex]] smooth function $F \colon \Theta \to \R$ called a potential function, where $\Theta\subset \theta(U)$ is an open convex domain. The Bregman divergence corresponding to this $F$ and coordinate $\theta$ is defined to be: $$B_{F}(p:q)=F(\theta(p))-F(\theta(q))-\langle (\theta(p)-\theta(q)), \nabla F(\theta(q))\rangle$$

>[!proposition]
>The Bregman divergence with negative [[Information Content and Entropy#^d1821a|Shanon entropy]] as potential function is the [[Information Content and Entropy#^b73be4|Kullback-Leibler divergence]].

*Proof*  Let $F(p) = \sum_{i}p_{i}\log p_{i}$, then we have: $$\nabla_{j} F(p)=1+\log p_{j}$$Therefore, $$\begin{aligned}
B_F(p:q)&=\sum_{i} \left(p_{i}\log p_{i} - q_{i}\log q_{i} \right)- \left\langle p-q, \nabla F(q)\right\rangle \\
&= \sum_{i} (p_{i}\log p_{i}-q_{i}\log q_{i}-p_{i}\log q_{i}-p_{i}+q_{i}+q_{i}\log q_{i})\\
&= \sum_{i}\left(p_{i}\log \frac{p_i}{q_i}\right)\\
&= D_{\mathrm{KL}}(p:q) \\
\end{aligned}$$ $\square$

>[!Definition] Bregman Manifold
>We call the statistical manifold induced by a Bregman divergence with potential $F$ a Bregman manifold. It satisfies $$\begin{aligned} g^{B_F}&=\nabla^{2} F \\ \Gamma_{ijk}^{B_{F}}&=0\\ C_{ijk}^{B_{F}}&=\partial_{i}\partial_{j}\partial_{k}F(\theta)\\ \end{aligned}$$So it is $\nabla^{B_{F}}$-flat. ^f96fd6

*Proof*

## Duality

>[!definition] Dual Potential
> The dual potential $F^{*}$ of a potential function $F$ with chart $\theta$ on $U\subset M$ is defined as its [[Convex Functions#^745078|Legendre-Fenchel transformation]]: $$F^{*}\colon \eta(U)\to \R, \quad F^{*}(\eta(p))=\sup_{\theta} \left\{\langle\theta(p),\eta(p) \rangle - F(\theta(p)) \right\}$$And we call $\eta$ the dual coordinate. To simplify our notation, we write $\eta_{p}$ for $\eta(p)$, and $\theta_{p}$ for $\theta(p)$.

>[!proposition]
> Suppose $F\colon \theta(U)\to \R$ is a potential function, where $\theta$ is an affine coordinate. Then the relation between the dual coordinate $\eta$ and coordinate $\theta$ is: $$\eta_{p} = \nabla F(\theta_{p}), \quad \theta_{p} = \nabla F^{*}(\eta_{p}) \quad \text{for all } p\in U$$

*Proof*  In the definition of dual potential, $\langle \theta_{p},\eta_{p}\rangle  - F(\theta_{p})$ achieves supremum when $\nabla F(\theta_{p})=\eta_{p}$. Since Legendre-Fenchel transformation is involutive, we have $\nabla F^{*}(\eta_{p})=\theta_{p}$. $\square$

> [!proposition] Crouzeix Identity
> The following identity holds, relating Hessians of the potential functions: $$\nabla^{2}F(\theta)\nabla^{2}F^{*}(\eta)=I$$

>[!corollary]
> On a Bregman manifold, suppose $e_{i}$ and $\tilde{e}_{j}$ are basis vectors for some tangent space under the original and dual coordinates, then $$\langle e_{i} , \tilde{e}_{j} \rangle = \delta_{ij}$$ Furthermore,  $$\tilde{e}_{j} = g^{ik}e_{k}, \quad \langle \tilde{e}_{i}, \tilde{e}_{j}\rangle = g^{ij}$$

*Proof*  Since on a Bregman manifold, $g=\nabla^{2}F$. Thus by Crouzeix identity, we immediately have $\langle e_{i} , \tilde{e}_{j} \rangle = \delta_{ij}$. Now write $\tilde{e}_{j}=c^{k}e_{k}$. Then we have $$\delta_{ij}=\langle e_{i} , \tilde{e}_{j} \rangle = g_{ik}c^{k}$$Thus $c^{k}=g^{jk}$, it follows that $\tilde{e}_{j}=g^{jk}e_{k}$. Therefore, we have $\langle \tilde{e}_{i}, \tilde{e}_{j}\rangle =g^{ik}g_{kl}g^{lj} = g^{ij}$. $\square$

> [!proposition]
> Dual Bregman divergence in the original coordinate is the Bregman divergence of the dual potential in the dual coordinate: $$B_{F^{*}}(\eta_{p}:\eta_{q})=B_{F}(\theta_{q}:\theta_{p})$$

*Proof*  $$\begin{aligned}
B_{F^{*}}({p}: {q}) &= F^{*}(\eta_{p})-F^{*}(\eta_{q})-\langle \eta_{p}-\eta_{q}, \nabla F^{*}(\eta_{q})\rangle\\
&= \langle \theta_{p}, \eta_{p}\rangle - F(\theta_{p}) - \langle  \theta_{q}, \eta_{q} \rangle + F(\theta_{q}) -\langle \eta_{q}-\eta_{p}, \theta_{q}\rangle\\
&= F(\theta_{q}) - F(\theta_{p}) - \langle \theta_{q}-\theta_{p}, \eta_{p}\rangle\\
&= F(\theta_{q}) - F(\theta_{p}) - \langle \theta_{q}-\theta_{p}, \nabla F(\theta_{p})\rangle\\
&= B_{F}({q}: {p})
\end{aligned} $$ $\square$

>[!theorem] Pythagorean Theorem for Bregman Manifold
> On a Bregman manifold, let $D$ and $D^{*}$ be the divergence and dual divergence, the Pythagorean theorem holds in the sense that $$D(p:r)=D(p:q)+D(q:r),\quad D^{*}(p:r)=D^{*}(p:q)+D^{*}(q:r)$$if the geodesic from $p$ to $q$ and the dual geodesic from $q$ to $r$ are orthogonal.
> ![pytha_bregman_manifold.svg|140](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/pytha_bregman_manifold.svg)

*Proof*  By definition of the Bregman divergence, we have $$\begin{aligned}
&D(p:r)=D(p:q)+D(q:r)  \\
\iff&  \langle \theta_{p}-\theta_{r}, \nabla F(\theta_{r})\rangle = \langle \theta_{p}-\theta_{q}, \nabla F(\theta_{q})\rangle -\langle \theta_{q}-\theta_{r}, \nabla F(\theta_{r})\rangle  \\
\iff& \langle \theta_{p}-\theta_{q}, \nabla F(\theta_{r}) -\nabla F(\theta_{q})\rangle = 0
\end{aligned}$$Notice that the two curves are perpendicular at $q$, so $\langle \dot{\gamma}_{1}(q), \dot{\gamma}_{2}(q)\rangle=0$. Since $\gamma_{1}$ and $\gamma_{2}$ are geodesics and dual geodesics, and both connection and dual connection are flat, $\gamma_{1}$ and $\gamma_{2}$ are lines in the corresponding coordinate systems. Thus $\dot{\gamma}_{1}(q)=\theta(p)-\theta(q)$ and $\dot{\gamma}_{2}(q)=\eta_{r}-\eta_{q}=\nabla F(\theta_{r})-\nabla F(\theta_{q})$, so the Pythagorean theorem is satisfied.  $\square$
