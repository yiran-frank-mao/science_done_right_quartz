**Fact**  Instead of discrete amplitude $C_n$ for each frequency $k_n$ at intervals of $k_0$, we have a continuous function $F(K)$  giving the amplitude of frequency $k$ over infinitesimal frequency intervals $\text{d}k$

**Def**  <i><u>Fourier Transform</u></i>
$$
\mathcal{F}[f(x)]=F(k)=\int_{-\infty}^{\infty} f(x) e^{-i k x} d x
$$
And the inverse Fourier transform is given by:
$$
\mathcal{F}^{-1}[F(k)]=f(x)=\frac{1}{2 \pi} \int_{-\infty}^{\infty} F(k) e^{i k x} d k
$$

**Prop**  $\mathcal{F}[cf(x)] = c\mathcal{F}[f(x)]$

## Tophat, **Dirac**Delta and Shah Function

**Def**  <i><u>Tophat Function</u></i>
Define the tophat function as:
$$
\text{п}(\frac{x}{2b})=\begin{cases}
1 \quad \text{if } x\in(-b,b)\\
0  \quad \text{otherwise}
\end{cases}
$$

**Def**  <i><u>DiracDelta Function</u></i>
Delta function $\delta(x)$ is an even function that is zero everywhere except at the origin and has area one. That is:
$$
\int^{\infty}_{-\infty}\delta(x)\text{d}x = 1
$$

**Prop**  By the property of delta function, we can get that:
$$
\begin{aligned}\int_{-\infty}^{\infty} \delta(x) f(x) d x & =\int_{-\infty}^{\infty} \delta(x) f(0) d x & \\& =f(0) \int_{-\infty}^{\infty} \delta(x) d x & \\& =f(0) \end{aligned}
$$
Generally, we can offset the delta function and get the following:
$$
\int_{-\infty}^{\infty} \delta\left(x-x_0\right) f(x) d x=f\left(x_0\right)
$$

**Prop**  
- $\delta(ax)=\frac{\delta(x)}{|a|}$
- $\int_{-\infty}^{\infty} f(x) \delta^{\prime}(x) d x=-f^{\prime}(0)$
- The Fourier Transform of the delta function is 1: $\mathcal{F}[\delta(t)]=1$
- The Inverse Fourier Transform of the delta function is $\frac{1}{2\pi}$: $\mathcal{F}^{-1}[\delta(t)]=\frac{1}{2\pi}$
- $\mathcal{F}[1]=2\pi \cdot \delta(t)$

**Def**  <i><u>Shah Function</u></i>
The Shah function is defined by an infinite series of delta functions:
$$
\amalg_T(t)=\sum_{n=-\infty}^{\infty} \delta(t-n T)
$$

**Prop** The Fourier Transform of a Shah is a Shah.
$$
\mathcal{F}\left[\amalg_T(t)\right]=\frac{2 \pi}{T} \amalg_{\frac{2 \pi}{T}}(\omega)
$$

## Linearity, Symmetry and Duality

**Prop**  The Fourier transform is linear:

$$
{\mathcal{F}}[a f(t)+b g(t)]=a{\mathcal{F}}[f(t)]+b{\mathcal{F}}[g(t)]
$$

**Prop**  The scaling of Fourier Transform:

$$
{\mathcal{F}}[f(a x)]={\textstyle\frac{1}{|a|}}F\left({\frac{k}{a}}\right)
$$

**Corollary**  ${\mathcal{F}}[f(-x)]=F(-k)$

**Prop**  <i><u>Symmetries</u></i> ^ecbc8f
<table class="center">
    <tr>
        <td><span class="math display">f(t)</span> is real</td>
        <td>Real part of <span class="math display">F(\omega)</span> is even; Imaginary part is odd</td>
    </tr>
    <tr>
        <td><span class="math display">f(t)</span> is real and even</td>
        <td><span class="math display">F(\omega)</span> is real and even</td>
    </tr>
    <tr>
        <td><span class="math display">f(t)</span> is real and odd</td>
        <td><span class="math display">F(\omega)</span> is imaginary and odd</td>
    </tr>
</table>

It is equivalent to say that:
$$
F(\omega) = \widetilde{F}(-\omega)
$$
where $\widetilde{F}$ is the complex conjugate of $F$.
For a real-valued function $f(t)$, the negative frequency components of the Fourier transform must be complex conjugate of the positive frequency components.

**Prop**  <i><u>Duality</u></i>
If $\mathcal{F}[f(t)]=F(\omega)$ then $\mathcal{F}[F(t)]=2\pi f(-\omega)$

**Prop**  <i><u>Coordinate Shift</u></i>
$$
{\mathcal{F}}[f(x-x_{0})]=e^{-i k x_{0}}F(k), \quad {\mathcal{F}}[e^{i k_{0}x}f(x)]=F(k-k_{0})
$$

## Convolution

Recall that convolution is the integral of the product of two functions after one is reversed and shifted:
![[The Space of Integrable Functions#^472754]]

It has the following properties:
![[The Space of Integrable Functions#^f5d23e]]

**Thrm**  <i><u>Convolution Theorem</u></i>
The convolution is function multiplication in Fourier space: $${\mathcal{F}}[f(x)*g(x)]=F(k)G(k), \quad
{\mathcal{F}}[f(x)g(x)]=\frac{1}{2\pi}F(k)*G(k) $$where $*$ is the convolution operator.

## Derivatives of Fourier

**Prop**  If $\mathcal{F}[f(t)]=F(\omega)$ and the first derivative of $f$ exists, then $\mathcal{F}[f^\prime(t)]=i\omega F(\omega)$. More generally, $\mathcal{F}[f^{(n)}(t)]=(i\omega)^nF(\omega)$
**Proof**  
$$
\begin{aligned} & f(t) = \mathcal{F}^{-1}[F(\omega)] = \frac{1}{2\pi}\int_{-\infty}^{\infty}F(\omega)e^{i\omega t}d\omega \\ \implies & f^{\prime}\left(t\right)=\frac{1}{2\pi}\int_{-\infty}^{\infty}i\omega F(\omega)e^{i\omega t}d\omega={\mathcal{F}}^{-1}[i\omega F(\omega)] \\ \implies &{\mathcal{F}}[f^{\prime}(t)]=i\omega F(\omega) \end{aligned}
$$
## Energy and Parseval’s Theorem

**Thrm**  <i><u>Parseval’s Theorem</u></i>
If $v(t)$ is some finite signal, then the energy will be finite. Parseval’s theorem says:
$$
\int_{-\infty}^{\infty}|f(t)|^{2}\mathrm{d}t={\frac{1}{2\pi}}\int_{-\infty}^{\infty}|F(\omega)|^{2}\mathrm{d}\omega
$$