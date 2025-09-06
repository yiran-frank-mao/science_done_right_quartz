The harmonic oscillator model is so important in physics. Consider the Taylor series expansion of an arbitrary potential $V(x)$ with a minimum at $x=x_{0}$:$$V(x)=V(x_{0})+\frac{\dd V}{\dd x}\Bigg|_{x=x_{0}}(x-x_{0})+\frac{1}{2}\frac{\dd^{2}V}{\dd x^{2}}\Bigg|_{x=x_{0}}(x-x_{0})^{2}+\cdots $$We can ignore higher order terms for small amplitude oscillations. We can also subtract the constant $V (x_{0})$ from the potential without changing the force experienced by the particle, leaving $$V(x)=\frac{1}{2}\frac{\dd^{2}V}{\dd x^{2}}\Bigg|_{x=x_{0}}(x-x_{0})^{2}\equiv\frac{1}{2}qx^{2}$$This is why harmonic oscillator is so important!

## The Analytical Method

>[!lemma] 
>**Lemma**  The Hamiltonian for a harmonic oscillator is given by $$\hat{H}=\frac{1}{2m}\Bigg(-ih\frac{\partial}{\partial x}\Bigg)^{2}+\frac{1}{2}m\omega^{2}x^{2}$$

*Proof*  Simply by $\hat{H}=\hat{T}+\hat{V}$ and the potential operator of a harmonic oscillator is $\hat{V}=\frac{1}{2}k\hat{x}^{2}$ with $\omega=\sqrt{k/m}$.

>[!theorem] 
> The energy eigenstates of a harmonic oscillator is given by $$\Psi_{n}(x)=\sqrt{\frac{1}{\sqrt{\pi}2^{n}n!x_{0}}}e^{-\frac12 (x/x_{0})^2}H_{n}\left(\frac{x}{x_{0}}\right)$$with corresponding energy eigenvalues: $$E_{n}= (n+\frac{1}{2})\hbar\omega,\quad n=0,1,2\dots$$where $H_{n}$ is the [[Hermite Polynomials#^a81ecc|Hermite polynomial]], and $x_0=\sqrt{\frac{\hbar}{m\omega}}$.

>[!proposition] 
>**Prop**  The $n$-th excited state of a harmonic oscillator has $n$ nodes.

>[!proposition] 
>**Prop**  On average, the energy is split evenly between the potential and the kinetic energy.

## The Algebraic Method

>[!definition] Creation Operator & Annihilation Operator
>The creation and annihilation operators are defined as: $$\begin{aligned} \hat{a}_{-}=\frac{1}{\sqrt{2m\hbar\omega}}(m\omega\hat{x}+i\hat{p})\\ \hat{a}_{+}=\frac{1}{\sqrt{2m\hbar\omega}}(m\omega\hat{x}-i\hat{p}) \end{aligned}$$

>[!proposition] 
> We have the following equations hold:
>- $[\hat{a}_{-},\hat{a}_{+}]=1$.
>- $\hat{a}_{-}\hat{a}_{+}=\frac{\hat{H}}{\hbar\omega}+\frac12$, $\hat{H}=\hbar\omega(\hat{a}_{-}\hat{a}_{+}-1/2)=\hbar\omega(\hat{a}_{+}\hat{a}_{-}+1/2)$.
>- $[\hat{H},\hat{a}_{-}]=-\hbar\omega\hat{a}_{-}$.
>- $\hat{V}=\frac14\hbar\omega(\hat{a}_{-}+\hat{a}_{+})^{2}$.
>- $\hat{x}=\sqrt{\frac{\hbar}{2m\omega}}(\hat{a}_{+}+\hat{a}_{-})$ and $\hat{p}=i\sqrt{\frac{m\hbar\omega}{2}}(\hat{a}_{+}-\hat{a}_{-})$.
>$\quad$

>[!theorem] 
> The creation and annihilation operators act on quantum states as follows: $$\begin{aligned}&\hat{a}_-|n\rangle=\sqrt{n}|n-1\rangle\\\\&\hat{a}_+|n\rangle=\sqrt{n+1}|n+1\rangle\end{aligned}$$

## Non-Stationary States

>[!proposition] 
> All energy eigenstates of the harmonic oscillator in 1D have no time dependent observables, thus are stationary states.

>[!definition] 
>**Def**  <i><u>Coherent State</u></i>
>A coherent state is a specific quantum state of a quantum harmonic oscillator, often described as a state that has dynamics most closely resembling the oscillatory behavior of a classical harmonic oscillator. Mathematically, we have $$\Psi(x,t)_{\text{coherent}}=\sum_{n}c_{n}\psi_{n}(x)e^{-iE_{n}t/\hbar},\quad\text{where }|c_{n}|^{2}=\frac{\langle n \rangle^{n}}{n!}e^{-\langle n \rangle}$$with $\langle n \rangle$ the mean of the quantum numbers $n$ and $\langle n \rangle \gg  1$.

>[!proposition] 
>**Prop**  The probability distribution of a coherent state forms a [[Poisson Distribution#^83c8e2|Poisson distribution]]. Thus it has mean $\langle n \rangle$ and standard deviation $\langle n \rangle^{1/2}$. The expectation value of the energy of a such state is $$\begin{aligned}\langle E\rangle&=\sum_{n}|c_{n}|^{2}E_{n}=\sum_{n}|c_{n}|^{2}(n+1/2)\hbar\omega\\&=(\langle n\rangle+1/2)\hbar\omega\end{aligned}$$and the uncertainty is $$\Delta E=\langle n\rangle^{1/2}\hbar\omega $$If $\langle n \rangle$ is large, then observe that $$\begin{aligned}\frac{\Delta E}{\langle E\rangle}& =\frac{\langle n\rangle^{1/2}\hbar\omega}{(\langle n\rangle+1/2)\hbar\omega} \approx\frac1{\langle n\rangle^{1/2}}\end{aligned}$$So the energy uncertainty becomes less important. The position and momentum uncertainties become "less important" as well, and therefore the motion of the particle described by the wavefunction $\Psi(x,t)_{\text{coherent}}$ approaches classical harmonic oscillation.

## 3D Harmonic Oscillator

**Prop**  The 3D harmonic oscillator have energy eigenstates characterized by three quantum numbers $n_x$, $n_y$ and $n_z$: $$\hat{H}\ket{n_{x},n_{y},n_{z}}=\left(n_{x}+n_{y}+n_{z}+\frac{3}{2}\right)\hbar\omega\ket{n_{x},n_{y},n_{z}}$$The solution in each spatial dimension can be solved independently and the spatial form of the wavefunction is just the product of the solution for each dimension: $$\psi(x,y,z)=X_{n_x}(x)Y_{n_y}(y)Z_{n_z}(z)$$

**Prop**  We can also solve 3D harmonic oscillator in terms of a radial quantum number $n_{r}$ and the angular momentum quantum numbers $l$ and $m$: $$E_{n_{r},l}=\left(2n_{r}+l+\frac{3}{2}\right)\hbar\omega$$