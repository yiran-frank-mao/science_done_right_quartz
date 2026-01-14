## de Rham Complex

> [!definition] de Rham Complex
> Let $M$ be a [[Manifolds and Atlases#^6ef2ef|smooth manifold]]. The *de Rham complex* is the sequence of [[Differential Forms#^c6c1be|differential forms]] on $M$: $$0 \rightarrow \Omega^0(M) \xrightarrow{\d} \Omega^1(M) \xrightarrow{\d} \Omega^2(M) \xrightarrow{\d} \cdots$$where $\Omega^{k}(M)$ is the space of smooth differential $k$-forms on $M$, and $\d$ is the [[Differential Forms#^3f9e68|exterior derivative]].

> [!definition] de Rham Cohomology Group
> The $k$th *de Rham cohomology [[Groups, Order and Subgroups#^6e0960|group]]* of a smooth manifold $M$ is defined as the quotient $$H^k_{\mathrm{dR}}(M) = \frac{\ker(\d \colon \Omega^k(M) \to \Omega^{k+1}(M))}{\mathrm{im}(\d \colon \Omega^{k-1}(M) \to \Omega^k(M))}.$$ That is, it's the space of closed $k$-forms modulo the space of [[Differential Forms#^c1760d|exact]] $k$-forms.

^b54c25

## de Rham's theorem

> [!theorem] de Rham's Theorem
> Let $M$ be a smooth manifold. Then the de Rham cohomology groups $H^k_{\mathrm{dR}}(M)$ are isomorphic to the singular cohomology groups $H^k(M, \R)$ with real coefficients. In particular, they are independent of the choice of differential forms used to define them.
