## Sampling

**Def**  <i><u>Nyquist Frequency</u></i>
To pick out a frequency $f$, then your sampling frequency must be at least $2f$. Alternatively, for a sampling frequency $f$, the highest frequency you can correctly identify is $f/2$. This highest frequency (i.e. half the sampling frequency), is known as the Nyquist frequency.

**Def**  <i><u>Aliasing</u></i>
Aliasing is the overlapping of frequency components resulting from a sample rate below the Nyquist frequency. This overlap results in distortion or artifacts when the signal is reconstructed from samples which causes the reconstructed signal to differ from the original continuous signal.

## Discrete Fourier Transform

**Def**  <i><u>Discrete Fourier Transform</u></i>
The discrete Fourier transform transforms a sequence of $N$ complex numbers $\{x_n\}=x_0,x_1,\dots,x_{N−1}$ into another sequence of complex numbers, $\{X_k\}=X_0,X_1,\dots,X_{N−1}$,which is defined by $$
X_{k}=\sum_{n=0}^{N-1}x_{n}\cdot e^{-i\frac{2\pi}{N}kn}
$$
