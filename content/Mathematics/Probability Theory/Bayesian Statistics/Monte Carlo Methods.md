**Algorithm**  <i><u>Monte Carlo Integration</u></i>
Given a sample $x(1),\dots,x(N) \sim f(x)$, we gan approximate the theoretical mean by the sample mean to give: $$E_{f}[\phi(X)]=\int \phi(x)f(x)\dd x\approx\frac1N\sum_{i=1}^N\phi\left(x^{(i)}\right)$$

**Thrm**  By Monte Carlo Integration, we can derive the following approximation formulas: $$\begin{aligned}
\int_{a}^{b}g(x)\dd x=\int_{0}^{1}(b-a)g(a+u(b-a))\dd u \\
\int_{0}^{\infty} g(x)\dd x=\int_{0}^{1}\frac1{u^{2}}{g}\left(\frac1u-1\right)\dd u
\end{aligned}$$
<b><u>e.g.</u></b>  $\int_{0}^{2}\exp(x^{2})\dd x=2\int_{0}^{1}\exp(4u^{2})\dd u$, thus we can estimate the integral by the following R code:
```R
u=runif(5000)
mean(2*exp(4*u^2))
```

