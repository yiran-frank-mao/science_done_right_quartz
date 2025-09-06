
> [!theorem] Closed Graph Theorem
> Let $X$ and $Y$ be Banach spaces and $T$ a linear map of $X\to Y$. Then $T$ is bounded if and only if the graph of $T$ is closed.

> [!corollary] Helinger-Toeplitz Theorem
> Let $A$ be an everywhere defined linear operator on a Hilbert space $\newcommand{\H}{\mathcal{H}}\H$ such that $\langle x, Ay\rangle=\langle Ax,y\rangle$ holds for all $x,y\in\H$. Then $A$ is bounded. ^1d50d9

*Proof*  By the closed graph theorem, it suffices to show $\Gamma(A)$ is closed in $\H\times\H$. Suppose $\{(x_{n},Ax_{n})\}_{n=1}^{\infty}$ is a sequence in $\Gamma(A)$ that converges to $(x, y)$. Then $x_{n}\to x$ and $Ax_{n}\to y$. By the continuity of the inner product, we have $$\langle A(x_{n}-x),A(x_{n}-x)\rangle = \langle A^{2}(x_{n}-x),x_{n}-x\rangle\to 0.$$Therefore by triangle inequality, we have $$\|y-Ax\|\leq\|y-Ax_{n}\|+\|Ax_{n}-Ax\|\to 0.$$This shows that $y=Ax$, hence $(x,y)\in \Gamma(A)$, which implies that $\Gamma(A)$ is closed. $\square$

