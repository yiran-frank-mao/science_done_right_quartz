> [!definition] Homotopy between Manifold
> A homotopy from a smooth function $f\colon M\to N$ to a smooth function $g\colon M\to N$ is a smooth function $\rho\colon M\times [0,1]\to N$ such that $\rho(x,0)=f(x)$ and $H(x,1)=g(x)$ for all $x\in M$.
> A homotopy is an isotopy if $\rho_{t}$ is an embedding for all $t\in[0,1]$.

> [!definition] Lagrangian Submanifold
> A Lagrangian submanifold of a symplectic manifold $(M,\omega)$ is a submanifold $L\subset M$ such that $\dim L=\frac{1}{2}\dim M$ and $\omega|_{L}=0$. In other words, the restriction of the symplectic form to $L$ vanishes.

## Moser’s Theorem

> [!theorem] Moser Relative Theorem
> Let $M$ be a manifold, $X$ a compact submanifold of $M$, $i\colon X \hookrightarrow M$ the inclusion map, $\omega_{0}$ and $\omega_{1}$ symplectic forms on $M$ such that $\omega_{0}|_{X}=\omega_{1}|_{X}$. Then there exists neighbourhoods $U_{0}$, $U_{1}$ of $X$ and a diffeomorphism $\varphi\colon U_{0}\to U_{1}$ such that the following diagram commutes:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/moser_relative_theorem.svg" alt="moser_relative_theorem" style="width:27%;"/>
> and $\varphi^{*}\omega_{1}=\omega_{0}$.

> [!theorem] Darboux Theorem
> Let $(M,ω)$ be a symplectic manifold, and let $p$ be any point in $M$. Then we can find a coordinate $(x_{1},\dots,x_{n},y_{1},\dots,y_{n})$ on $U$ containing $p$ such that $$\omega=\sum_{j=1}^{n}\d x_{j} \wedge \d y_{j}.$$ 

*Proof*  Apply the Moser relative theorem to $X=\{p\}$.