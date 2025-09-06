
>[!definition] Time Dependent Schrödinger's Equation
>$$-\frac{\hbar^2}{2m}\frac{\partial^2\Psi}{\partial z^2}+V(z,t)\Psi=i\hbar\frac{\partial\Psi}{\partial t}$$The general solution of TDSE is given by $$\Psi(x,t) = \sum_{n} c_{n}\psi_{n}(z)e^{-i\omega_{n}t}$$where $\psi_{n}$ are the solutions to the TDSE and $\omega_{n}= \frac{E_{n}}{\hbar}$. Given the initial wave function $\Psi(z,0)$, we can obtain all the coefficients $c_{n}$: $$c_{n}=\int_{-\infty}^{\infty}\psi_{n}^{*}\Psi(z,0) \dd z$$^b6c546

>[!proposition] 
>**Prop**  Linear superposition of any solutions to the TDSE is still a solution.

>[!lemma] 
>**Lemma**  Given any potential $V$, that is real and time independent, the separable solutions of the TDSE $\Psi(x,t)=\phi(x) f(t)$ are valid.
>**Proof**  If the potential only depends on position, we are able to write the TDSE as an equation where each side depends on different variables: $$\frac{\hbar^{2}}{2m}\frac{1}{\phi}\frac{\dd^{2}\phi}{\dd x^{2}}+V(x)=i\hbar\frac{1}{f(t)}\frac{\dd f}{\dd t}$$So we can see that separable solutions satisfy the TDSE if the potential is time-independent.

>[!proposition] 
>**Prop**  All solutions of the time-independent Schrödinger's equation have the time dependence of the form $f(t)=e^{-i\omega_{n} t}$ where $\omega_{n}=E_{n}/\hbar$.

>[!proposition] 
>**Prop**  A wave function is normalized at time $t=0$ then it is normalized for all time.
>**Proof**  Consider the derivative of normalization: $$\begin{aligned}
>\frac{\dd}{\dd t}\int_{-\infty}^{\infty}|\Psi(z,t)|^{2}\dd z &= \int_{-\infty}^{\infty}\frac{\partial}{\partial t}|\Psi(z,t)|^{2}\dd z \\
>&=\int_{-\infty}^{\infty} \left(\Psi^{*}\frac\partial{\partial t}\Psi+\Psi\frac\partial{\partial t}\Psi^{*}\right) \dd z
>\end{aligned}$$By TDSE, we have $$\frac{\partial \Psi}{\partial t} = \frac{1}{i\hbar}\left(-\frac{\hbar^{2}}{2m}\frac{\partial \Psi}{\partial z^{2}}+V \Psi \right),\quad \frac{\partial \Psi^{*}}{\partial t} = -\frac{1}{i\hbar}\left(-\frac{\hbar^{2}}{2m}\frac{\partial \Psi^{*}}{\partial z^{2}}+V \Psi^{*} \right)$$Substitute into the integral, we then get $$\frac{\dd}{\dd t}\int_{-\infty}^{+\infty}|\Psi(z,t)|^2dz=\frac{i\hbar}{2m}\left[\Psi^*\frac{\partial}{\partial z}\Psi-\Psi\frac{\partial}{\partial z}\Psi^*\right]_{-\infty}^{+\infty}=0$$

>[!proposition] 
>**Prop**  The normalization condition for the wave function obtained by linear superposition is $$\int_{-\infty}^{\infty}\Psi^{*}\Psi\dd z=\sum_{n} |c_{n}|^{2}=1$$

>[!definition] 
>**Def**  <i><u>Stationary State</u></i>
>We say that a particle is in the stationary state if observable properties of the particle do not change with time.

## Expansion Using The Energy Basis
