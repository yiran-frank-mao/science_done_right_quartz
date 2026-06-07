
> [!definition] Symmetric Operator
> A densely defined operator on a [[Hilbert Spaces#^ae0212|Hilbert space]] $\H$ is *symmetric* if for all $f,g\in D(T)$, we have $\langle Tf,g\rangle=\langle f,Tg\rangle$. That is, $D(T)\subset D(T^{*})$, and $T|_{D(T)}=T^{*}|_{D(T)}$.

> [!definition] Self-Adjoint Operator
> A densely defined operator $T$ on $\H$ is *self-adjoint* if $T=T^{*}$. That is, $T$ is symmetric, and $D(T)=D(T^{*})$. ^450e4c

> [!attention]+
> Notice that when we say a symmetric (or self-adjoint) operator, we always mean a densely defined operator, unless otherwise specified.

> [!proposition] 
> A symmetric operator is always closable. In fact, we have $T\subset T^{**} \subset T^{*}$.
> Moreover, for closed symmetric operators, we have $T=T^{**}\subset T^{*}$.
> For self-adjoint operators, we have $T=T^{**}=T^{*}$.

*Proof*  For a symmetric operator $T$, $T^{*}$ is an extension of $T$, and $T^{*}$ is closed, hence $T$ is closable, and $T\subset T^{**} \subset T^{*}$ by [[Unbounded Operators#^113ce9|the theorem]]. $\square$

> [!definition] Essentially Self-adjoint Operator
> A symmetric operator $T$ is *essentially self-adjoint* if its closure $\bar{T}$ is self-adjoint. ^e5fbca

> [!definition] Core
> The *core* of an essentially self-adjoint operator refers to a dense subset of its domain on which the operator remains essentially self-adjoint when restricted to it.

> [!proposition]
> If $T$ is essentially self-adjoint, then it has a unique self-adjoint extension. Specifically, $$T\subset T^{**} = T^{*}.$$
> 

<u><b>e.g.</b></u>  Let $\hat{p}=-i\ddf{}{x}$ be the momentum operator with domain $D(\hat{p})=\{\varphi \mid \varphi\in AC[0,1], \varphi(0)=\varphi(1)=0\}$, where $AC[0,1]$ denotes the set of all absolute continuous functions on $[0,1]$. Then $\hat{p}$ is symmetric, but not self-adjoint. Indeed, we have $$\begin{aligned}\langle \phi, \hat{p}\psi\rangle &=\int^{1}_{0} \phi(x)\overline{-i\psi'(x)}\dd x\\&= \int_{0}^{1} i\phi(x)\overline{\psi'(x)}\dd x \\ &= i\phi(1)\overline{\psi(1)}-i\phi(0)\overline{\psi(1)} - \int_{0}^{1}i\phi'(x) \overline{\psi(x)} \dd x\\&= \langle \hat{p}\phi, \psi\rangle,\end{aligned}$$for all $\phi,\psi\in D(\hat{p})$, so $\hat{p}$ is symmetric. However, notice that we only require $\psi\in AC[0,1]$ to make the above derivation valid, hence $\hat{p}$ is not self-adjoint because $D(\hat{p})\supsetneq D(\hat{p}^{*})$. $\hat{p}$ has [[Equinumerous and Countability#^79eb6c|uncountably]] many different self-adjoint extensions, each corresponding to a different choice of boundary conditions, such as $\psi(0)=\alpha\psi(1)$ for some unit length [[Complex Numbers#^a81924|complex number]] $\alpha$. So it is not essentially self-adjoint.

## Criterion for Self-Adjointness

> [!theorem]
> Let $T$ be a symmetric operator on a [[Hilbert Spaces#^ae0212|Hilbert space]] $\H$, then the followings are equivalent:
> - $T$ is self-adjoint;
> - $T$ is closed and $\ker (T^{*}\pm \hat{i})=\{0\}$;
> - $\im (T\pm \hat{i})=\H$.
>$\quad$

*Proof*  