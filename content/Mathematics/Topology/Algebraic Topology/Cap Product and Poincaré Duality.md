> [!lemma]
> Let $M$ be an $n$-dimensional oriented [[Connectedness and Paths#^946cc4|connected]] [[Compactness of Topological Space#^da2511|compact]] [[Manifolds and Atlases#^3407e4|manifold]]. Then
> - If $M$ is $R$-orientable then $H_{n}(M;R)\cong R$ and $H_{n}(M;R) \to H_{n}(M|_{x};R)$ is an isomorphism for all $x \in M$.
> - If $M$ is not $R$-orientable then $H_{n}(M;R) \cong R[2]=\{r\in R: 2r=0\}$.
> - $H_{k}(M;R)\cong 0$ for all $k>n$.
> $\quad$

> [!definition] Fundamental Class
> Let $M$ be an $n$-dimensional oriented [[Connectedness and Paths#^946cc4|connected]] [[Compactness of Topological Space#^da2511|compact]] [[Manifolds and Atlases#^3407e4|manifold]]. The *fundamental class* of $M$, denoted $[M]$, is the unique generator of the top-dimensional homology group $H_n(M;R)$ that corresponds to the given orientation of $M$.
> 

## Cap Product

> [!definition] Cap Product
> For $k\geq l\geq 0$, we have a bilinear map called the *cap product*: $$ \smallfrown \colon C_{k}(X;R) \times C^{l}(X;R) \to C_{k-l}(X;R), $$ which sends $(\sigma, \varphi)$ to $\sigma \smallfrown \varphi = \varphi(\sigma|_{[v_0, \ldots, v_l]}) \cdot \sigma|_{[v_l, \ldots, v_k]}$.
> This induces a map on homology and cohomology: $$ \smallfrown \colon H_{k}(X;R) \times H^{l}(X;R) \to H_{k-l}(X;R). $$
> 

> [!proposition] Compatibility with Cup Product
> $x \smallfrown (\alpha \smallsmile \beta) = (x \smallfrown \alpha) \smallsmile \beta$.

> [!theorem] Poincaré Duality
> If $M$ is an $n$-dimensional oriented [[Compactness of Topological Space#^da2511|compact]] manifold, then the $k$th cohomology group of $M$ is isomorphic to the $(n-k)$th homology group of $M$: $$ H^{k}(M) \cong H_{n-k}(M). $$
> Specifically, this isomorphism is given by the cap product with the fundamental class $[M] \in H_n(M)$: $$ \varphi \mapsto \varphi \smallfrown [M], $$ where $\varphi \in H^{k}(M)$ and $\varphi \smallfrown [M] \in H_{n-k}(M)$.
> 
