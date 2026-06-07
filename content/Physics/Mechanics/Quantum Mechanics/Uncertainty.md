## Compatible Observables

> [!definition] Compatible Observables
> A set of observables are called compatible observables if they can be determined without mutual interference. ^60a9fd

> [!definition] Commutator
> The commutator of two operators $\hat{A}$ and $\hat{B}$ is defined as: $$[\hat{A},\hat{B}]=\hat{A}\hat{B}-\hat{B}\hat{A}$$

> [!proposition]
> $[\hat{A},\hat{B}\hat{C}]=[\hat{A},\hat{B}]\hat{C}+\hat{B}[\hat{A},\hat{C}]$.

> [!theorem]
> Two observables $A$ and $B$, represented by two operators $\hat{A}$ and $\hat{B}$ are compatible only if $[\hat{A},\hat{B}]=0$.

>[!proposition] 
> Position $z$ and momentum $p$ are not compatible.

*Proof*  Calculate the commutator and we have $[\hat{z},\hat{p}]=i\hbar\neq0$. $\square$

## Simultaneous Eigenfunctions

>[!definition] Simultaneous Eigenfunction
>A simultaneous eigenfunction is an eigenfunction of two and more operators.
>

<u><b>e.g.</b></u>  Consider $|\alpha\rangle$ is an eigenfunction of both position $\hat{z}$ and $\hat{p}$: $$\hat{z}|\alpha\rangle = z_{\alpha}|\alpha\rangle, \quad \hat{p}|\alpha\rangle = p_{\alpha}|\alpha\rangle$$Then we have $$[\hat{z},\hat{p}]|\alpha\rangle = (z_{\alpha}p_{\alpha}-p_{\alpha}z_{\alpha})|\alpha\rangle=0=i\hbar|\alpha\rangle$$It indicates that $|\alpha\rangle=0$. Thus a quantum state with definite position and momentum does not exist.

>[!lemma] 
> Suppose $\hat{A}$ and $\hat{B}$ are [[Quantum State Space#^cd6aa6|Hermitian operators]], then we have the following inequality holds: $$\langle A^2\rangle\langle B^2\rangle\geq|\langle\psi|\hat{A}\hat{B}|\psi\rangle|^2$$

*Proof*  Let $|\alpha \rangle = \hat{A}|\psi\rangle$, $|\beta\rangle = \hat{B}|\Psi\rangle$, then $$\langle \alpha | = (| \alpha \rangle)^{\dagger} = \langle \Psi |\hat{A}^{\dagger} =  \langle\Psi |\hat{A}$$Similarly we have $\langle \beta | = \langle \Psi | \hat{B}$. By [[Inner Products#^aec3f8|Cauchy-Schwarz Inequality]], $$\langle \alpha |\alpha\rangle\langle \beta |\beta \rangle \geq |\langle \alpha |\beta\rangle|^{2}$$Therefore, $$\langle\psi|\hat{A}^{2}|\psi\rangle\langle\psi|\hat{B}^2|\psi\rangle\geq|\langle\psi|\hat{A}\hat{B}|\psi\rangle|^{2}$$By definition of expectation values, it follows that $$\langle A^2\rangle\langle B^2\rangle\geq|\langle\psi|\hat{A}\hat{B}|\psi\rangle|^2$$$\square$

>[!theorem] Heisenberg Uncertainty Principle
>Suppose $\hat{A}$ and $\hat{B}$ are [[Quantum State Space#^cd6aa6|Hermitian operators]], then we have the following inequality holds: $$\langle A^{2}\rangle \langle B^{2}\rangle \geq \left[ \frac{1}{2i} \left( \langle\Psi |[\hat{A},\hat{B}]|\Psi\rangle \right) \right]^{2}$$In particular,
> 1. One experiment cannot simultaneously determine the exact values of the position and momentum of a particle. The precision is inherently limited to $\Delta z\Delta p \geq \hbar / 2$.
> 2. The energy spread of a state and the characteristic time associated with it are similarly related: $\Delta E \delta t \geq \hbar / 2$.
> $\quad$

*Proof*  By Hermiticity of $\hat{A}$ and $\hat{B}$, we have $$\begin{aligned}\left(\langle\psi|\hat{A}\hat{B}|\psi\rangle\right)^{*}&=\left(\langle\psi|\hat{A}\hat{B}|\psi\rangle\right)^{\dagger}\\&=\left(\langle\psi|\hat{A}|\lambda\rangle\right)^{\dagger},\mathrm{~where~}|\lambda\rangle=\hat{B}|\psi\rangle\\&=\langle\lambda|\hat{A}^{\dagger}|\psi\rangle\\&=(\hat{B}|\psi\rangle)^{\dagger}\hat{A}^{\dagger}|\psi\rangle\\&=\langle\psi|\hat{B}^{\dagger}\hat{A}^{\dagger}|\psi\rangle\\&=\langle\psi|\hat{B}\hat{A}|\psi\rangle\end{aligned}$$ Thus, $$\begin{aligned}\langle A^2\rangle\langle B^2\rangle&\geq|\langle\psi|\hat{A}\hat{B}|\psi\rangle|^{2}\\&=\left[\frac{1}{2i}\Big(\left\langle\psi|\hat{A}\hat{B}|\psi\right\rangle-\left(\left\langle\psi|\hat{A}\hat{B}|\psi\rangle\right)^{*}\right)\right]^{2}\\&=\left[ \frac{1}{2i} \left( \langle\Psi |[\hat{A},\hat{B}]|\Psi\rangle \right) \right]^{2}\end{aligned}$$  Calculate the uncertainties in $z$ and $p$ for a particle represented by $|\psi\rangle$ as $$(\Delta z)^{2}=\langle |(z-\langle z\rangle^{2})|\psi\rangle,\quad (\Delta p)^{2}=\langle |(p-\langle p\rangle^{2})|\psi\rangle$$Hence $$\left(\Delta z\right)^2\left(\Delta p\right)^2\geq\left[\frac{1}{2i}\left(\left\langle\psi\left|i\hbar\right|\psi\right\rangle\right)\right]^{2}=\left[\frac{\hbar}{2}\langle\psi|\psi\rangle\right]^{2}=\frac{\hbar^{2}}{4}$$This implies $\Delta z\Delta p\geq\frac\hbar2$. $\square$
