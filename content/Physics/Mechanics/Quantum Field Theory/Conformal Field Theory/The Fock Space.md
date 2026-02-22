## Full Fock Space

> [!definition] Full Fock Space
> The *full Fock space* over a [[Hilbert Spaces#^ae0212|Hilbert space]] $\newcommand{\H}{\mathcal{H}}\H$ is the Hilbert space defined as the direct sum of tensor powers of $\H$: $$\newcommand{\F}{\mathcal{F}}\F(\H):=\bigoplus_{i=0}^{\infty}\otimes^{i} \H.$$
> By definition $\otimes^{0}\H$ is one-dimensional, and spanned by the *vacuum vector*, denoted $\ket{0}$ or $\Omega$.

## Fermionic Fock Space

> [!definition] Fermionic Fock Space
> The *fermionic Fock space* over a Hilbert space $\H$ is the Hilbert space defined as the direct sum of the exterior powers of $\H$: $$\newcommand{\F}{\mathcal{F}}\F_{-}(\H):=\bigoplus_{i=0}^{\infty}\wedge^{i} \H.$$
> In other words, it is the full Fock space $\F(\H)$ modulo the anticommutation relations $x\otimes y = -y\otimes x$ for all $x,y\in \H$.
> 

## Bosonic Fock Space

> [!definition] Bosonic Fock Space
> The *bosonic Fock space* over a Hilbert space $\H$ is the [[Hilbert Spaces#^ae0212|Hilbert space]] completion defined as the direct sum of the symmetric powers of $\H$: $$\newcommand{\F}{\mathcal{F}}\F_{+}(\H):=\bigoplus_{i=0}^{\infty}S^{i} \H,$$
> with inner product $$\langle x^{\otimes n}, y^{\otimes m} \rangle = \delta_{m,n} n! \langle x,y\rangle^{n}. $$
> In other words, it is the full Fock space modulo the commutation relations $x\otimes y = y\otimes x$ for all $x,y\in \H$. ^ecdf5b

> [!definition] Segal–Bargmann Space
> The *Segal–Bargmann space* is the space of holomorphic functions 

> [!proposition]
> The bosonic Fock space is isomorphic to the Segal-Bargmann space.
> 
