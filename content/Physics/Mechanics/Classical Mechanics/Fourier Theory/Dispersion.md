**Def**  <i><u>Dispersion</u></i>
The phenomenon where different frequencies travel at different speeds is called dispersion. We call the relation between angular frequency $\omega$ and wave number $k$ the dispersion relation. ^079ed8

**Thrm** For a wave with general dispersion that $\omega(k)$ is a function of $k$ and $k(w)$ is a function of $\omega$ we have:
$$ \begin{aligned}
f(x,t)={\frac{1}{2\pi}}\int_{-\infty}^{\infty}F(k,0)e^{-i\omega(k)t}e^{i k x}\,d k \\ f(x,t)={\frac{1}{2\pi}}\int_{-\infty}^{\infty}\!F(0,\omega)e^{-i k(\omega)x}e^{i\omega t}\,d\omega 
\end{aligned}$$
**Proof**  Take a wave shaped in space, $f(x,0)$ with Fourier transform $F(k,0)$. Then by definition of Fourier transform, we have
$$ f(x,0) = {\frac{1}{2\pi}}\int_{-\infty}^{\infty}F(k,0)e^{i k x}\,d k $$
To find the shape of the wave in space at a time $t$, rotate each $k$ with the right phase, which depends on $\omega$:
$$ f(x,t)={\frac{1}{2\pi}}\int_{-\infty}^{\infty}F(k,0)e^{-i\omega t}e^{i k x}\,d k $$
Since $\omega$ is dependent on $k$ by dispersion, we have:
$$ f(x,t)={\frac{1}{2\pi}}\int_{-\infty}^{\infty}F(k,0)e^{-i\omega(k) t}e^{i k x}\,d k $$
Similarly, we can get the second formula.

**Def**  <i><u>Narrow-Band Pulses</u></i>
The narrow-band pulses are the pulses that the period is much smaller than the pulse width.

## Group and Phase Velocity

**Def**  <i><u>Group Velocity</u></i>
For a pulse with $w$ and $k$ dependent, the group velocity is defined as $v_{g}={\frac{\mathrm{d}\omega}{\mathrm{d}k}}\bigg|_{k_c}$, which indicates the velocity of envelope. ^2f2e58

**Def**  <i><u>Phase Velocity</u></i>
The velocity of the ripples under the envelope are given by $v_{ph}=\frac{w_c}{k_c}$. We call this the phase velocity.

**Prop** For any pulse $f(x,t)$ in the time and spacial space, we have:
$$ f(x,t)={\frac{1}{2\pi}}e^{i k_{c}(v_{g}-\ v_{p h})t}\int_{-\infty}^{\infty}\!F(k)e^{i k(x-v_{g}t)}\,d k $$

>[!remark]
>The pulse $f(x,t)$ should be a real function. Actually the Fourier transform of the negative frequencies is missing in our formula. The correct answer should be added by the complex conjugate. [Symmetries](Fourier%20Transform.md#^ecbc8f)