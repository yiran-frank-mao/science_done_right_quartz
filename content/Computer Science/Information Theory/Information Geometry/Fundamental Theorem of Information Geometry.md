---
created: 2024-08-15
updated: 2024-10-23
---
> [!lemma]
> Let $R$ and $\tilde{R}$ be the [[Torsion and Curvature#^4605ee|curvature tensors]] of [[Conjugate Connections#^98fcf9|conjugate connections]] $\nabla$ and $\tilde{\nabla}$ on $(M,g)$, respectively. Then $$\langle R(X,Y)Z,W\rangle =- \langle Z, \tilde{R}(X,Y)W\rangle \quad \text{for all } X,Y,Z,W\in\mathfrak{X}(M)$$

*Proof*  First consider the left hand side: $$\begin{aligned}
&\langle R(X,Y)Z,W\rangle \\ =& \langle \nabla_{X}\nabla_{Y}Z - \nabla_{Y}\nabla_{X}Z - \nabla_{[X,Y]}Z,W\rangle \\
=& \langle \nabla_{X}\nabla_{Y}Z,W\rangle - \langle \nabla_{Y}\nabla_{X}Z,W\rangle - \langle \nabla_{[X,Y]}Z,W\rangle \\
\end{aligned}$$Since $\nabla$ and $\tilde{\nabla}$ are conjugate connections, we have $X\langle Y,Z\rangle=\langle \nabla_{X}Y,Z\rangle + \langle Y,\tilde{\nabla}_{X}Z\rangle$ for all $X,Y,Z\in \mathfrak{X}(M)$. Therefore, $$\begin{aligned}
&\langle R(X,Y)Z,W\rangle \\ =&  \langle \nabla_{X}\nabla_{Y}Z,W\rangle - \langle \nabla_{Y}\nabla_{X}Z,W\rangle - \langle \nabla_{[X,Y]}Z,W\rangle \\
=& (X\langle\nabla_{Y} Z,W\rangle - \langle\nabla_{Y}Z,\tilde{\nabla}_{X}W\rangle) - (Y\langle\nabla_{X} Z,W\rangle - \langle\nabla_{X}Z,\tilde{\nabla}_{Y}W\rangle) \\
&-( [X,Y]\langle Z,W\rangle -\langle Z, \tilde{\nabla}_{[X,Y]}W\rangle) \\
=& XY\langle Z,W\rangle -X \langle Z, \tilde{\nabla}_{Y}W\rangle - Y\langle Z , \tilde{\nabla}_{X}W\rangle + \langle Z, \tilde{\nabla}_{Y}\tilde{\nabla}_{X}W\rangle - YX\langle Z,W\rangle + \\
&Y\langle Z, \tilde{\nabla}_{X}W\rangle + X\langle Z, \tilde{\nabla}_{Y}W\rangle - \langle Z, \tilde{\nabla}_{X}\tilde{\nabla}_{Y}W\rangle - [X,Y]\langle Z,W\rangle + \langle Z, \tilde{\nabla}_{[X,Y]}W\rangle \\
=& \langle Z, \tilde{\nabla}_{Y}\tilde{\nabla}_{X}W\rangle -\langle Z, \tilde{\nabla}_{X}\tilde{\nabla}_{Y}W\rangle +\langle Z, \tilde{\nabla}_{[X,Y]}W\rangle\\
=& - \langle Z, \tilde{R}(X,Y)W\rangle
\end{aligned}$$$\square$

> [!theorem] Fundamental Theorem of Information Geometry
> A torsion-free affine connection $∇$ has constant curvature $\kappa$ if and only if its conjugate torsion-free connection $\tilde{\nabla}$ has the same constant curvature $κ$.

*Proof*  

> [!definition] $\alpha$-Flatness
> A [[Statistical Manifold#^f45770|statistical manifold]] $(M, \nabla, \tilde{\nabla}, g, C)$ is said to be $\alpha$-flat if the induced $\alpha$-connections are flat.
