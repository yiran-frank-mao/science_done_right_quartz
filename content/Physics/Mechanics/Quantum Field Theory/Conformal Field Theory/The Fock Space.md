## Full Fock Space

> [!definition] Full Fock Space
> The *full Fock space* over a [[Hilbert Spaces#^ae0212|Hilbert space]] $\newcommand{\H}{\mathcal{H}}\H$ is the Hilbert space defined as the direct sum of tensor powers of $\H$: $$\newcommand{\F}{\mathcal{F}}\F(\H):=\bigoplus_{i=0}^{\infty}\otimes^{i} \H.$$
> By definition $\otimes^{0}\H$ is one-dimensional, and spanned by the *vacuum vector*, denoted $\ket{0}$ or $\Omega$.

## Fermionic Fock Space

> [!definition] Fermionic Fock Space
> The *fermionic Fock space* over a [[Hilbert Spaces#^ae0212|Hilbert space]] $\H$ is the Hilbert space defined as the direct sum of the exterior powers of $\H$: $$\newcommand{\F}{\mathcal{F}}\F_{-}(\H):=\bigoplus_{i=0}^{\infty}\wedge^{i} \H.$$
> In other words, it is the full Fock space $\F(\H)$ modulo the anticommutation relations $x\otimes y = -y\otimes x$ for all $x,y\in \H$.
> 

## Bosonic Fock Space

> [!definition] Bosonic Fock Space
> The *bosonic Fock space* over a separable [[Hilbert Spaces#^ae0212|Hilbert space]] $\H$ is the [[Hilbert Spaces#^ae0212|Hilbert space]] completion defined as the direct sum of the symmetric powers of $\H$: $$\newcommand{\F}{\mathcal{F}}\F_{+}(\H):=\overline{\bigoplus_{i=0}^{\infty}S^{i} \H},$$
> with inner product $$\langle x^{\otimes n}, y^{\otimes m} \rangle = \delta_{m,n} n! \langle x,y\rangle^{n}. $$
> In other words, it is the full Fock space modulo the commutation relations $x\otimes y = y\otimes x$ for all $x,y\in \H$. 
> On the bosonic Fock space, we can define *annihilator* $\hat{a}$ and *creator* $\hat{a}^{*}$ as follows: $$\newcommand{\pddf}[2]{\frac{\partial#1}{\partial#2}} \hat{a}_{n}=\varepsilon(n)\pddf{}{x_{n}},\quad \hat{a}^{*}_{n}=f\mapsto \varepsilon(n)^{-1}nx_{n}f, $$ for all $n>0$ and some $\varepsilon\colon \Z\to \R$. Usually (and here) we set $\varepsilon(n)=n$ for all $n\in\Z$.
> Even more formally, we can treat $\hat{a}$ as a map that assigns each $x\in\H$ to an annihilation operator $\hat{a}(x)$, and each $x\in \H$ to a creation operator $\hat{a}^{*}(x)$, such that $\hat{a}(x)$ is linear in $x$, $\hat{a}^{*}(x)$ is conjugate-linear in $x$, and they satisfy the canonical commutation relations $$[\hat{a}(x), \hat{a}^{*}(y)]=\langle x,y\rangle,\quad [\hat{a}(x), \hat{a}(y)]=0,\quad [\hat{a}^{*}(x), \hat{a}^{*}(y)]=0.$$ $\hat{a}_{n}$ and $\hat{a}^{*}_{n}$ are the annihilation and creation operators associated to some orthonormal basis $\{e_{n}\}_{n\in\N}$ of $\H$.
> ^ecdf5b

> [!definition] Second Quantization
> Suppose $A\in B(\H)$ is a bounded operator on $\H$, then the *second quantization* of $A$ is the operator $\Gamma(A)\in B(\F_{+}(\H))$ defined as $$\Gamma(A)(x_{1}\odot \cdots \odot x_{n}):= Ax_{1}\odot \cdots \odot Ax_{n}.$$
> 

> [!definition] Segal–Bargmann Space
> The *Segal–Bargmann space* is the space of holomorphic functions 

> [!proposition]
> The bosonic Fock space is isomorphic to the Segal-Bargmann space.
> 
