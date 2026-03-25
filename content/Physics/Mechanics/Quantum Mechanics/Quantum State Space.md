## Dirac Notation

> [!example] Comment
> Dirac notation, is a notation for linear algebra and linear operators on complex vector spaces together with their dual space both in the finite-dimensional and infinite-dimensional case. In quantum mechanics, Dirac notation is used ubiquitously to denote quantum states. 

>[!definition] Bra and Ket
> A ket is of the form $|v\rangle$, it denotes a vector $v$ in a [[Complex Numbers#^a81924|complex]] [[Hilbert Spaces#^ae0212|Hilbert space]] $\newcommand{\H}{\mathcal{H}}\H$, and physically it represents a state of some quantum system.
> A bra is of the form $\langle f |$, it denotes a linear map $\newcommand{\C}{\mathbb{C}}\newcommand{\R}{\mathbb{R}}f\colon \H \to \C$. 
> Letting the linear functional $\bra{f}$ act on a vector $\ket{v}$ is written as $\langle f|v\rangle \in \C$. ^9686b5

>[!definition] Quantum State
> A quantum state is a quantum wavefunction $\Psi$, represented by a ket $| \Psi \rangle$. The inner product $\int\Psi_{1}^{*}\Psi_{2}\dd x$ is then written as $\langle \Psi_{1}|\Psi_{2}\rangle$. And the expectation value of some observable $\langle A\rangle = \langle\Psi | \hat{A}| \Psi \rangle$. The Schrödinger equation becomes $$i\hbar\frac{\dd}{\dd t}|\Psi\rangle = \hat{H}|\Psi\rangle$$

## Hilbert Space as Quantum State Space

>[!definition] Quantum State Space
A quantum state space is a [[Complex Numbers#^a81924|complex]] [[Hilbert Spaces#^acb78f|separable]] [[Hilbert Spaces#^ae0212|Hilbert space]] and eigenstates as axes that the state of system is represented by a column vector in this Hilbert space: $$|\Psi\rangle = \begin{pmatrix} c_{1} \\ c_{2}\\ c_{3} \\  \vdots \end{pmatrix}$$And the bra $\langle \Psi |$ is the Hermitian adjoint: $\langle \Psi |=\begin{pmatrix}c_{1}^{*}&c_{2}^{*}&c_{3}^{*}\dots\end{pmatrix}$. Thus it follows that $$\int_{-\infty}^{\infty}\Psi^{*}\Psi \dd z = \sum_{n}^{\infty}|c_{n}|^{2}=1$$Any operator then can be represented as a matrix: $$\hat A=\begin{pmatrix}A_{11}&A_{12}&A_{13}&\cdots\\A_{21}&A_{22}&A_{23}&\cdots\\A_{31}&A_{32}&A_{33}&\cdots\\\vdots&\vdots&\vdots&\ddots\end{pmatrix}$$ ^00f394

<u><b>e.g.</b></u>  For one degree of freedom this space can be taken to be the space of wave functions (complex-valued functions $\psi(q)$ of a position variable $q\in\R$) in [$L^{2}(\R)$](Hilbert%20Spaces#^ba55f5).

>[!proposition]
> The $ij$th entry of an operator $\hat{A}$ is given by $$A_{ij}=\langle \Psi_{i}|\hat{A}|\Psi_{j}\rangle$$

*Proof*  Can be easily shown by matrix multiplication.  $\square$

>[!proposition]
> An operator $A$ is diagonal in the representation of its observable.

<u><b>e.g.</b></u>  The energy operator $\hat{H}$ is diagonal in the energy representation.

>[!proposition]
> The identity operator can be written as $\hat{I}=\sum_{i}|\Psi_{i}\rangle\langle\Psi_{i}|$.

>[!definition] Unitary Operator
> A unitary operator $\hat{U}$ is an operator that satisfies: $$\hat{U}^{-1}=\hat{U}^{\dagger}$$That is its inverse is equal to its Hermitian adjoint.

>[!proposition]
> A unitary operator preserves the [[Inner Products#^f0c22c|inner product]]. Thus it does not change the length of a vector it operates on.

*Proof*  Consider the unitary operator $\hat{U}$ and two vectors $|f\rangle$ and $|g\rangle$. Then we have $$\left(\hat{U}|f\rangle\right)^{\dagger}= |f\rangle^{\dagger}\hat{U}^{\dagger}=\langle f|\hat{U}^{-1}$$Therefore, $$\langle f|g\rangle=\langle f| \hat{U}^{-1}\hat{U} |g\rangle= \left(\hat{U}|f\rangle\right)^{\dagger} \left(\hat{U}|g\rangle\right)$$

>[!theorem]
>  [[Time Dependent Schrödinger's Equation#^b6c546|Schrödinger's equation]] ensures unitary evolution.

*Proof*  Schrödinger's equation says you start with some state vector at $t_{0}$, this state vector then evolves by some complicated evolution, but the length of the vector, which is the probability density is conserved.

## Hermitian Operators and Observables

>[!definition] Hermitian Operator
>An operator $\hat{\Theta}$ is said to be Hermitian if it satisfies $$\langle\psi_{m}|\hat{\Theta}|\psi_{n}\rangle=\left(\langle\psi_{n}|\hat{\Theta}|\psi_{m}\rangle\right)^{*}$$ ^cd6aa6

>[!proposition] 
> The eigenvalues of Hermitian operators are real.

*Proof*  Suppose $\psi_{n}$ is a normalized eigenfunction of $\hat{\Theta}$ associated with eigenvalue $\lambda$, then $$\begin{aligned} && \langle\psi_{n}|\hat{\Theta}|\psi_{n}\rangle &=\left(\langle\psi_{n}|\hat{\Theta}|\psi_{n}\rangle\right)^{*} \\ \implies  && \lambda\langle\psi_{n}|\psi_{n}\rangle &= \lambda^{*}  \langle\psi_{n}|\psi_{n}\rangle \\ \implies&&\lambda &= \lambda^{*}   \end{aligned}$$$\square$

>[!lemma] 
> An operator is Hermitian iff the Hermitian adjoint of it is itself. i.e. $\hat{\Theta}^{\dagger}= \hat{\Theta}$.

>[!theorem] 
> In quantum mechanics, all operators which represent observables are both linear and hermitian.

>[!proposition] 
>The eigenfunctions of a Hermitian operator corresponding to different eigenvalues are orthogonal.

*Proof*  