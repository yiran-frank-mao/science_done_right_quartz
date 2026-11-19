---
created: 2024-02-29
updated: 2024-10-29
---
## de Broglie's Postulates

> [!theorem] de Broglie's Postulates
> de Broglie postulated that particles of matter have wave nature: $$\begin{aligned}E=\hbar\omega&=h\nu\implies\nu=\frac{E}{h}=\frac{p^2}{2mh}\\p=\hbar k&=\frac{h}{\lambda}\implies\lambda=\frac{h}{p}=\frac{h}{\sqrt{2mE}}\end{aligned}$$

> [!proposition]
> The [[Dispersion#^079ed8|dispersion relation]] for non-relativistic particle is $$\omega = \frac{p^{2}}{2m\hbar}=\frac{\hbar k^{2}}{2m}$$Thus the [[Dispersion#^2f2e58|group velocity]] can be derived:$$v_{g}=\frac{\partial \omega}{\partial k}=\frac{\hbar k}{m}$$

## Free Particle de Broglie Waves

> [!quote] From the standpoint of our quantum mechanics, there is no quantity which causally fixes the effect of a collision in an individual event.

> [!comment]+
> In Max Born's statistical interpretation, the state of a particle is represented by a complex function $\Psi(r,t)$ such that $|\Psi(r,t)|^{2}\dd V$ is the probability of finding that particle at the time $t$ in the volume element $\dd V$ at the point $r$.

<u><b>e.g.</b></u>  In one dimensional case, we have the probability of finding the particle between $a$ and $b$ at $t$ is given by$$\int^{b}_{a}|\Psi(x,t)|^{2}\dd x$$

>[!proposition]
>The mean position is given by $$\langle x\rangle=\int^{b}_{a}x|\Psi(x,t)|^{2}\dd x$$

>[!theorem] Momentum Space Wave Function
> Given the wave function $\Psi(k)$, we can use Fourier transform to obtain the wave function in the momentum space:$$\Phi(p,t)=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}\Psi(x)e^{-ikx}\dd x$$