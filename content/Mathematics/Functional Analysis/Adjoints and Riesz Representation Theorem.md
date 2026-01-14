## Riesz Representation Theorem

> [!definition] Linear Functional
> A linear functional $\ell$ is a linear transformation from a [[Hilbert Spaces#^ae0212|Hilbert space]] to the underlying field of scalars.

> [!theorem] Riesz Representation Theorem
> Let $\ell$ be a continuous linear functional on a Hilbert space $\newcommand{\H}{\mathcal{H}}\H$. Then, there exists a unique $g\in\H$, such that $\ell(f)=\langle f, g\rangle$ for all $f\in \H$. Moreover, $\|\ell\|=\|g\|$.

*Proof*  Consider the kernel of $\ell$, say $\S:=\ker \ell=\{f\in\H:\ell(f)=0\}$, which is a closed subspace of $\H$, so $\H=\S\oplus\S^{\bot}$. If $\S^{\bot}=\emptyset$, then $\ell=0$. Otherwise, pick some $h\in\S^{\bot}$ with $\|h\|=1$, and let $g:=\overline{\ell(h)}h$. Then if we let $u:=\ell(f)h-\ell(h)f$, observe that $u\in\S$ because $\ell(u)=\ell(f)\ell(h)-\ell(h)\ell(h)=0$, therefore, $$0=\langle u,h\rangle=\ell(f)\langle h,h\rangle - \langle f,\overline{\ell(h)}h\rangle=\ell(f)\langle h,h\rangle - \langle f,g\rangle,$$which shows that $\ell(f)=\langle f,g\rangle$. Moreover, if $g'\in\S^{\bot}$ is another element such that $\ell(f)=\langle f,g'\rangle$, then we have $$\ell(f)=\langle f,g\rangle=\langle f,g'\rangle,$$it follows that $\langle f,g-g'\rangle=0$ for all $f\in\H$, which implies that $g=g'$. $\square$

## Adjoint

> [!proposition] 
> Let $T\colon \H_{1}\to\H_{2}$ be a bounded linear map on separable Hilbert spaces. Then there exists a unique adjoint bounded linear map $T^{*}\colon \H_{2}\to\H_{1}$ such that $$\langle Tf,g\rangle=\langle f,T^{*}g\rangle$$ for all $f\in\H_{1}$ and $g\in\H_{2}$. This map $T^{*}$ is called the *adjoint* of $T$. ^671f74

*Proof*  Given $g\in \H_{2}$, the map $x\mapsto\langle Tx,g\rangle$ is a linear functional on $\H_{1}$. So by the Riesz representation theorem, there exists a unique $w\in \H_{2}$, such that $$\langle Tx,g\rangle=\langle x,w\rangle,$$ for all $x\in \H_{1}$. We define $T^{*}(g):=w$. This is a linear map from $\H_{2}$ to $\H_{1}$, because the inner product is linear. It is also bounded because $\|T\|=\|T^{*}\|$ (see below). $\square$

> [!proposition]
> For any bounded linear operator $T\colon \H_{1}\to \H_{2}$, there holds $\|T\|=\|T^{*}\|$, and $$\|T\|^{2}=\|T^{*}\|^{2}=\|T \circ T^{*}\|=\|T^{*} \circ T\|.$$
> 

*Proof*  We shall first show that $\|T\|=\|T^{*}\|$. In fact, by the [[Orthogonality and Bounded Linear Maps#^f6c4d5|lemma]] $$\|T\| = \sup_{\|f\|=1,\|g\|=1} |\langle Tf,g\rangle| = \sup_{\|f\|=1,\|g\|=1} |\langle f,T^{*}g\rangle| = \sup_{\|f\|=1,\|g\|=1} |\langle T^{*}g,f\rangle|=\|T^{*}\|.$$Now, for any $\|f\|=1$ and $\|g\|=1$, we have $$|\langle T( T^{*}f),g\rangle|=|\langle T^{*}f,T^{*}g\rangle|\leq \| T^{*}f\|\|T^{*}g\|\leq \|T^{*}\|^{2},$$thus $\|T\circ T^{*}\|=\sup |\langle T( T^{*}f),g\rangle|\leq\|T^{*}\|^{2}$. For the other direction, note that $$\|T\circ T^{*}\|\geq\langle T(T^{*}f),f\rangle=\langle T^{*}f,T^{*}f\rangle=\|T^{*}f\|^{2},$$so $\|T\circ T^{*}\|\geq \sup \|T^{*}f\|^{2}=\|T^{*}\|^{2},$ hence $\|T\circ T^{*}\|=\|T^{*}\|^{2}$. The same argument applies to $\|T^{*} \circ T\|$. $\square$

## Infinite Diagonal Matrix

> [!definition] Diagonalised Linear Operator
> Suppose $\H$ is a separable Hilbert space with orthonormal basis $\{e_{i}\}_{i=1}^{\infty}$. A linear operator $T\colon \H\to\H$ is diagonalised if there exists a sequence of scalars $\{\lambda_{i}\}_{i=1}^{\infty}\subset\C$ such that $$T(e_{i})=\lambda_{i}e_{i},\quad \text{for all } i.$$ ^b796c6

> [!proposition]
> Suppose $T\colon \H\to\H$ is a diagonalised linear operator on a separable Hilbert space $\H$ with orthonormal basis $\{e_{i}\}_{i=1}^{\infty}$. Then the following holds:
> - $\|T\|=\sup_{k}|\lambda_{k}|$,
> - $T^{*}$ is also diagonalised with $\bar{\lambda}_{k}$ as the diagonal entries. Hence, $T=T^{*}$ if and only if $\lambda_{k}\in\R$ for all $k$.
> - $T$ is unitary if and only if $|\lambda_{k}|=1$ for all $k$.
> - $T$ is an orthogonal projection if and only if $\lambda_{k}\in\{0,1\}$ for all $k$.
> $\quad$
