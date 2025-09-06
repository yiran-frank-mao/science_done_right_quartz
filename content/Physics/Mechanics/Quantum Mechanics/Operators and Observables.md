---
created: 2024-04-18
updated: 2024-10-29
---
## Operators and Observables

>[!definition]
>**Def**  <i><u>Operator</u></i>
Operators are mathematical entities used to represent physical processes that result in the change of the state vector of the system, such as the evolution of these states with time.

>[!definition] Observable
>An observable is a physical property or physical quantity that can be measured. Observables manifest as linear [[Quantum State Space#^cd6aa6|Hermitian operators]] in the [[Quantum State Space#^00f394|quantum state space]].

>[!proposition] Expectation Value of Operator
>Given some operator $\hat{A}$, the expectation value is then given by $$\langle A\rangle = \int_{-\infty}^{\infty}\Psi ^{*}\hat{A} \Psi \dd z$$

>[!definition] Hamiltonian Operator
>The Hamiltonian operator is $$\hat{H}=-\frac{\hbar^{2}}{2m}\frac{\partial^{2}}{\partial z^{2}}+V(z)$$Thus the TISE reduces to $$\hat{H}\psi_{n}=E_{n}\psi_{n}$$

>[!definition] Energy Eigenstate
>An energy eigenstate is a quantum state where all observables (such as position, velocity, and spin) are independent of time. It is an eigenvector of the energy operator (Hamiltonian), meaning that it corresponds to a specific energy value (the eigenvalue) rather than a superposition of different energies. Formally, $\psi$ is an energy eigenstate if $$H \psi  = E \psi$$

## The Momentum Operator

>[!definition] Kinetic Energy Operator
>The kinetic energy operator is $$\hat{T}=-\frac{\hbar^{2}}{2m}\frac{\partial^{2}}{\partial z^{2}}$$

>[!definition] Momentum Operator
>The momentum operator can be reduced from the kinetic energy operator: $$\hat{P}=\sqrt{2m\hat{T}}=-i\hbar\nabla$$

>[!proposition]
>**Prop**  The free particle has a definite momentum.
>**Proof**  Let a free particle have $\Psi(z)=Ae^{-ikz}$. Then $$\hat{P}(\Psi(z))=-\hbar k \Psi(z)$$yielding a definite momentum $-\hbar k$.

## Time Dependent States

**Def**  <i><u>Energy Probability Amplitudes</u></i>
Energy probability amplitudes are the

>[!proposition]
>**Prop**  The mean energy can be obtained by $$E = \sum_{n}|c_{n}|^{2}E_{n}$$**Proof**  As $E = \int \Psi^{*} \hat{H} \Psi \dd z$, we can easily derive the above equation.

## Ehrenfest's Theorem

>[!theorem] Ehrenfest's Theorem
>Expectation or mean values of observables in quantum mechanics should obey the same relations as their classical counterparts.

<u><b>e.g.</b></u>  We can easily prove that $\langle p_{z} \rangle = m \frac{\dd \langle z \rangle}{\dd t}$: $$\begin{aligned}m \frac{\dd \langle z \rangle}{\dd t} &= m \frac{\dd}{\dd t} \int_{-\infty}^{\infty} \Psi^{*} z \Psi \dd z \\&=m\int_{-\infty}^{\infty} \frac{\partial\Psi^{*}}{\partial t} z\Psi \dd z + m \int_{-\infty}^{\infty}\Psi^{*}z \frac{\partial\Psi}{\partial t} \dd z\end{aligned}$$ Then by TDSE

>[!principle] Bohr's Correspondence Principle
>Tending towards a Newtonian universe, one in which $\hbar \to 0$. Like in Relativity where the scale is the speed of light, the scale in quantum mechanics is $\hbar$, so if $\hbar \to 0$, then every length scale is large and the universe is classical.
