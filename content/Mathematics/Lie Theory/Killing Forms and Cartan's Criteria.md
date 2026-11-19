> [!definition] Killing Form
> Let $\newcommand{\g}{\mathfrak{g}}\g$ be a finite dimensional Lie algebra over a field $F$ of characteristic $0$. Then, the *Killing form* of $\g$ is a bilinear, symmetric, ad-invariant form
> $$\newcommand{\tr}{\operatorname{tr}}\newcommand{\ad}{\operatorname{ad}}\kappa_{\g}\colon \g \times \g \rightarrow F, \quad \kappa_{\g}(x, y):=\tr\left(\ad_{x} \ad_{y}\right)$$
> If the Lie algebra referred to is clear, we simply denote $\kappa_{\g}=\kappa$.

> [!theorem] Cartan's Criteria for Solvability
> If $\g$ is a finite dimensional Lie algebra over a field of characteristic $0$, then $$\g \text { is solvable } \Longleftrightarrow \kappa_{\g}([\g, \g], \g) = 0,$$
> that is, $\kappa_{\g}(x, y)=0$ for every $x \in[\g, \g], y \in \g$. ^125ec3

*Proof Sketch*  The proof for this is slightly complicated, but we show the (easier) forward direction: If $\g$ is solvable, then we have that $\ad(\g)$ is solvable, and hence $[\ad(\g), \ad(\g)]=\ad([\g, \g])$ is nilpotent. So, $[\ad(\g), \ad(\g)] \ad(\g)$ is a nilpotent matrix, and hence $$\operatorname{tr}([\ad(\g), \ad(\g)] \ad(\g))=\kappa([\g, \g], \g) = 0.$$$\square$

> [!corollary]
> $\newcommand{\gl}{\mathfrak{gl}} \g\leq \gl(V)$ over a field of characteristic $0$ is solvable if and only if $\newcommand{\tr}{\operatorname{tr}}\tr(xy)=0$ for all $x \in[\g, \g]$ and $y \in \g$.

> [!theorem] Cartan's Criteria for Semisimplicity
> If $\g$ is a finite dimensional Lie algebra over a field of characteristic $0$, then
> $$\g \text { is semisimple } \Longleftrightarrow \kappa_{\g} \text { is non-degenerate }.$$ ^411335

<u><b>e.g.</b></u>  We recall that $\mathfrak{s l}_{2}(F)$ is simple (and hence semisimple) when $\operatorname{char}(F) \neq 2$. Use the standard basis $\{x, h, y\}$. Then, using the commutator relations we can deduce $$\left[\operatorname{ad}_{x}\right]=\begin{bmatrix}0 & -2 & 0 \\0 & 0 & 1 \\0 & 0 &0\end{bmatrix},\quad\left[\operatorname{ad}_{y}\right]=\begin{bmatrix}0 & 0 & 0 \\-1 & 0 & 0 \\0 & 2 & 0\end{bmatrix}, \quad\left[\operatorname{ad}_{h}\right]=\begin{bmatrix}2 & 0 & 0 \\0 & 0 & 0 \\0 & 0 & -2\end{bmatrix}$$Using these matrices, we can compute the matrix $[\kappa]=\left[\kappa\left(v_{i}, v_{j}\right)\right]=\left[\operatorname{tr}\left(\operatorname{ad}_{v_{i}} \operatorname{ad}_{v_{j}}\right)\right]$ : $$[\kappa]=\begin{bmatrix}0 & 0 & 4 \\0 & 8 & 0 \\4 & 0 & 0\end{bmatrix}$$This has determinant $128=2^{7}$, which is nonzero exactly when $\operatorname{char}(F) \neq 2$. So, by Cartan's criterion, we know $\mathfrak{s l}_{2}(F)$ is semisimple if $\operatorname{char}(F) \neq 2$, which aligns with our previous findings.

*Proof*  