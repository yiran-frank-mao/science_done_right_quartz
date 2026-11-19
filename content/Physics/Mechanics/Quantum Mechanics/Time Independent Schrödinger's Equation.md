> <p style="text-align: left;"><em>We want an analogous differential equation for quantum mechanics, which we can solve to find the form of the wave functions describing particles experiencing a force or potential gradient.</em></p><div align="right">---- Schrödinger</div>


>[!definition] Time Independent Schrödinger's Equation
>Suppose a particle in energy eigenstate with quantum wave $\psi(x,y,z)$, potential energy $V$ and definite total energy $E$, then we have the following equation hold: $$-\frac{\hbar^{2}}{2m} \nabla^{2}\psi+V\psi=E\psi $$In one dimension, it deduces to $$\left(-\frac{\hbar^{2}}{2m}\frac{\partial^{2}}{\partial z^{2}}+V(z)\right)\psi=E\psi$$

## The Infinite Square Well

**Def**  <i><u>Infinite Square Well</u></i>
Suppose we have a particle trapped in a potential where$$V(z)=\begin{cases}
0 , \quad & 0<z<a \\ +\infty, \quad &\text{otherwise}\end{cases}$$The solution to the infinite square well problem is simply:$$\psi_{n}(z)=\sqrt{\frac2a}\sin(k_{n}z), \quad k_{n}= \frac{n\pi}{a}$$We call it ground state if $n=1$, and all others excited states. And the number of zeros of $\Psi(z)$ aside from $0$ and $a$ is called nodes.
**Prop**  The number of nodes is $n-1$, $\Psi(z)$ is symmetric if $n$ is odd, antisymmetric if $n$ is even.
**Prop**  Each solution $\psi_{n}$ to the infinite square well problem forms an energy eigenstate, the energy spanning from $0$ to $a$ is definitely given by $E_{n}=\frac{n^2\hbar^2\pi^2}{2ma^2}$.

## Orthogonality of Energy Eigenstates

**Def**  <i><u>Kronecker Delta</u></i>
For a set of normalized, mutually orthogonal eigenfunctions, we can thus write$$\int\psi_{m}(z)^{*}\psi_{n}(z)\dd z=\delta_{mn}$$ where $\delta_{mn}$ is defined as Kronecker delta, $$\delta_{mn}=\begin{cases}1 \quad \text{if } m=n\\ \\0 \quad \text{otherwise}\end{cases}$$

**Prop**  The solutions to the time independent Schrödinger's equation form a [[Inner Products#^f0c22c|inner product space]] of eigenfunctions as orthonormal basis, where the inner product is defined as $$\langle\Psi_{1},\Psi_{2}\rangle=\int\Psi_{1}(z)^{*}\Psi_{2}(z)\dd z$$

## Properties of Energy Eigenstates

**Def**   <i><u>Bound States</u></i>
Bound states are states in the potential, that is $V_{\text{max}}>E>V_{\text{min}}$. It is unbounded or scattering if $E>V_\text{max}$.

**Def**  <i><u>Degeneracy</u></i>
The two different energy eigenstates are degenerate if they yield same energy.

> [!proposition]
> There is no degeneracy for bound states in one-dimensional potentials.
 
*Proof*  Define scaled energy and scaled potential respectively: $$\mathcal{E}=\frac{2m}{\hbar^2}E,\quad\mathcal{V}=\frac{2m}{\hbar^{2}}V(x)$$Suppose there is such a degeneracy so that there are $\psi_{1}(x)$ and $\psi_{2}(x)$, different from each other and both corresponding to the same energy $E$, thus the same value of $\mathcal{E}$. We have that the following equations hold: $$\begin{aligned}\psi_1^{\prime\prime}+(\mathcal{E}-\mathcal{V}(x))\psi_1=0\\\psi_2^{\prime\prime}+(\mathcal{E}-\mathcal{V}(x))\psi_2=0\end{aligned}$$Multiplying the top equation by $\psi_{2}$ and the bottom equation by $\psi_{1}$ and subtracting we get: $$\psi_2\psi_1^{\prime\prime}-\psi_1\psi_2^{\prime\prime}=0$$It follows that $(\psi_2\psi_1^{\prime}-\psi_1\psi_2^{\prime})^{\prime}=0$, hence $\psi_2\psi_1^{\prime}-\psi_1\psi_2^{\prime}=c$. The constant can be evaluated by examining the LHS for $|x|\to\infty$. We then have that $\psi_{1} \to\infty$ and $\psi_2\to\infty$, since they are bound states, while the derivatives are bounded. It follows then that the LHS vanishes as $|x|\to\infty$ and $c=0$ therefore. That is $\psi_2\psi_1^{\prime}-\psi_1\psi_2^{\prime}=0$. Hence, $$\frac \dd{\dd x}(\ln\psi_1-\ln\psi_2)=0$$This implies exists some constant $c^{\prime}$:$$\ln \psi_{1} = \ln \psi_{2}+ \ln c^\prime$$And thus $$\psi_{1}= c^{\prime}\psi_{2}$$Therefore we have shown that the wave functions $\psi_{1}$ and $\psi_{2}$ are equivalent, they indicate the same energy eigenstate. $\square$

> [!theorem]
> The energy eigenstates can be chosen to be real.

*Proof*  Consider an eigenstate of the TISE given by $\psi$. Then we have $$\begin{aligned}\psi^{\prime\prime}+(\mathcal{E}-\mathcal{V}(x))\psi=0\\(\psi^*)^{\prime\prime}+(\mathcal{E}-\mathcal{V}(x))\psi^{*}=0\end{aligned}$$Now if $\psi^{*}$ is different from $\psi$ then it must be a degenerate solution. By superposition we can get two real degenerate solutions: $$\psi_{r}=\frac12(\psi+\psi^{*}),\quad \psi_{im}=\frac1{2i}(\psi-\psi^{*})$$$\square$


**Corollary**  If dealing with a 1-D potential with bound states, any energy eigenstate is real up to a phase.
**Proof**  By theorem, in a 1-D potential with bound states, we have $$\psi_{im}=c\psi_{r},\quad\text{with }c\in\mathbb{R}$$Thus $\psi=\psi_{r}+i\psi_{im}=(1+ic)\psi_{r}=\sqrt{1+c^{2}}e^{i\beta}\psi_{r}$. Hence since $\beta$ is real, $\psi$ is up to a phase equal to a real solution.

**Thrm**  If the potential is an even function of $x$ (i.e. $V(x)=V(-x)$), the eigenstates can be chosen to be even or odd under reflection. Specially, if we are dealing with a 1-D symmetric potential, then any bound state must be even or odd.
**Proof**  

## The Finite Square Well

**Def**  <i><u>Finite Square well</u></i>
Suppose we have a particle in a space with potential where$$V(z)=\begin{cases}
-V_0 , \quad & -a<z<a \\ 0, \quad &\text{otherwise}\end{cases}$$The odd solutions are $$\psi(z)=\begin{cases}
Ae^{-\kappa z} \quad & z\geq a  \\
C\sin(lz) \quad & 0<z<a
\end{cases}$$where $l=\frac{\sqrt{2m(E+V_0)}}{\hbar}$. And the unique energies for the even case are given by $$\frac{\sqrt{-2mE}}\hbar=\frac{\sqrt{2m(E+V_0)}}\hbar\tan\left(\frac{\sqrt{2m(E+V_0)}}\hbar a\right)$$
