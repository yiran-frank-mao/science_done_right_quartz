Inner products generalize the idea of the dot product in $\R^{n}$ to more general vector spaces. They are useful in defining angles and lengths of vectors. ^ad5686

>[!definition] Inner Product
> Let $X$ be a [[Vector Spaces#^f4b63e|vector space]] on $F\in \{\R,\C\}$. A function $⟨\cdot,\cdot⟩\colon X\times X\to F$ is called an *inner product* on $X$ if it satisfies the following properties:
>1. Positivity: $⟨x,x⟩≥0$ for all $x ∈X$, and $⟨x,x⟩=0 \iff x =0$.
>2. Symmetry: $⟨x,y⟩ = \overline{⟨y,x⟩}$ for all $x,y ∈ X$.
>3. Sesquilinearity: for all $x,y,z ∈ X$ and $α,β,\lambda ∈ F$ there holds $$⟨αx +βy,z⟩ = α⟨x,z⟩+β⟨y,z⟩,\quad \langle u,\lambda v \rangle = \overline{\lambda}\langle u, v \rangle.$$
> 4. Induced Norm: inner product induces a [[Normed Spaces#^345fd3|norm]] $\|x\|:=\sqrt{\langle x,x\rangle}$.
> 
> A [[Vector Spaces#^f4b63e|vector space]] endowed with an inner product is called an *inner product space*. ^f0c22c

We shall verify that the induced norm is indeed a norm. Since $\overline{\langle x,x\rangle}=\langle x,x\rangle$, $\langle x,x\rangle$ is always real. So the norm is real as expected. The triangle inequality follows from the [[Inner Products#^aec3f8|Cauchy-Schwarz inequality]], which we will prove later. The homogeneity property follows from the linearity of the inner product. The positivity property follows from the definition of the inner product.

<u><b>e.g.</b></u>  $\R^{n}$ is an inner product space under the dot product.

> [!definition] Orthogonality
> Two vectors $x,y$ in an inner product space $X$, is said to be orthogonal if $⟨x,y⟩=0$.

> [!theorem] Pythagorean Theorem
> Let $x,y$ are two orthogonal vectors in an inner product space $X$, if and only if $$\|x+y\|^2=\|x\|^2+\|y\|^2$$ ^3c5c75

*Proof*  $$\|x+y\|^{2}=\langle x+y,x+y\rangle=\langle x,x\rangle + \langle x,y\rangle+\langle y,x\rangle+\langle y,y\rangle = \|x\|^{2}+\|y\|^{2},$$as $\langle x,y\rangle=\langle y,x\rangle=0$. $\square$

>[!theorem] Cauchy-Schwarz Inequality
>Let $(X,⟨·,·⟩)$ be an inner product space with induced norm $\|\cdot\|$. Then we have $$|\langle x,y\rangle|\leq\|x\|\|y\|\quad\text{for all } x,y\in X,$$with equality iff $x$ is a scalar multiplication of $y$. ^aec3f8

*Proof*  If $y=0$, then both sides are zero, so we can assume $y\neq0$. Then we can write $$x=\frac{\langle x,y\rangle}{\|y\|^2}y+\left(x-\frac{\langle x,y\rangle}{\|y\|^2}y \right).$$By denoting $w:=x-\frac{\langle x,y\rangle}{\|y\|^2}y$, we observe that $\langle x,h\rangle=0$, that is, they are orthogonal. Thus, by Pythagorean theorem, we have $$\|x\|^{2}=\left\| \frac{\langle x,y\rangle}{\|y\|^{2}}y \right\|^{2}+\|w\|^{2}\geq \frac{\langle x,y\rangle^2}{\|y\|^4}\|y\|^2=\frac{\langle x,y\rangle^2}{\|y\|^{2}}.$$Multiplying both sides of this inequality by $\|y\|^{2}$ and then taking square roots gives the desired inequality. And the equality holds iff $w=0$, i.e. $x$ is a scalar multiple of $y$. $\square$

> [!theorem] Jordan-von Neumann Theorem
> A norm on a vector space arises from an inner product if and only if the parallelogram law holds:$$\|x+y\|^2+\|x-y\|^2=2\left(\|x\|^2+\|y\|^2\right).$$If so, we have the induced inner product:$$\langle x,y\rangle:=\frac{1}{4}\left(\|x+y\|^{2}-\|x-y\|^{2}-i\|x-iy\|^{2}+i\|x+iy\|^{2}\right)$$

> [!definition] Orthogonal Transformation
> An orthogonal transformation is a linear transformation $T\colon V\to V$ on a inner product space $V$ that preserves the inner product, i.e. $⟨T(x),T(y)⟩=⟨x,y⟩$ for all $x,y\in V$. ^f76c1a

> [!proposition]
> In finite-dimensional vector spaces, the matrix representation (with respect to an orthonormal basis) of an orthogonal transformation is an orthogonal matrix.

## Adjoints

> [!theorem]
> A bounded linear map $P\colon V\to V$ on the inner product space $V$ is a projection if and only if $P\circ P=P$ and it is self-adjoint.
> 

*Proof*  If $P$ is a projection, then clearly $P\circ P=P$, and for all $x,y\in V$, we have $$⟨P(x),y⟩=⟨P(x),P(y)\rangle=⟨x,P(y)\rangle,$$so $P$ is self-adjoint. Conversely, if $P$ is self-adjoint and $P\circ P=P$, then consider $\newcommand{\id}{\mathrm{id}}U:=\ker(\id -P)$, for which any element is preserved by $P$. We claim that $U^{\perp}=\ker P$.
For all $v\in \ker P$ and $u\in U$, there holds $$\langle v,u\rangle=\langle v,P(u)\rangle=\langle P(v),u\rangle=\langle 0,u\rangle=0,$$thus $v\in U^{\perp}$ and $\ker P\subseteq U^{\perp}$.
Conversely, for any $v\in U^{\perp}$, we want to show that $P(v)\in U\cap U^{\perp}=\{0\}$. In fact, fix some $u\in U$, we have $$\langle P(v),u\rangle=\langle v,P(u)\rangle=\langle v,u\rangle=0,$$thus $P(v)\in U^{\perp}$. Moreover, since $P\circ P=P$, we have $P(P(v))=P(v)$, thus $P(v)\in U$. So $P(v)$ has to be zero, $v\in \ker P$, and we have $U^{\perp}\subseteq \ker P$.
Note that $U=\ker(\id-P)$ must be closed, thus $U\oplus U^{\perp}=V$, so we have for all $v\in V$, $$P(v)=P(v|_{U})+P(v|_{U^{\perp}})=v|_{U},$$which means $P$ is a projection onto $U$. $\square$

> [!corollary]
> Suppose $P_{1}$ and $P_{2}$ are projections. Then $P_{1}\circ P_{2}$ is a projection if and only if $P_{1}$ and $P_{2}$ commute.

*Proof*  If $P_{1}\circ P_{2}$ is a projection, then $$P_{2}\circ P_{1}=P_{2}^{*}\circ P_{1}^{*}=(P_{1}\circ P_{2})^{*}=P_{1}\circ P_{2}.$$Conversely, suppose $P_{1}$ and $P_{2}$ commutes, then $$(P_{1}\circ P_{2})\circ (P_{1}\circ P_{2})=(P_{1}\circ P_{1})\circ (P_{2}\circ P_{2})=P_{1}\circ P_{2}.$$Moreover, we have $$\langle (P_{1}\circ P_{2})(u),v\rangle = \langle P_{2}(u),P_{1}(v)\rangle=\langle u,(P_{2}\circ P_{1})(v)\rangle=\langle u,(P_{1}\circ P_{2})(v)\rangle.$$$\square$
