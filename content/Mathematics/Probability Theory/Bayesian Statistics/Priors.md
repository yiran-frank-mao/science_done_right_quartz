---
created: 2024-01-23
updated: 2024-09-19
---
## Conjugate Priors

> [!definition] Conjugate Prior
> Suppose $\mathcal{F}$ is a class of sampling distributions (likelihoods) $L(x\mid \theta)$, and $\mathcal{P}$ is a class of prior distributions $\pi(\theta)$ for $\theta$, then the class $\mathcal{P}$ is conjugate for $\mathcal{F}$ if $$
> \pi(\theta\mid x) \in\mathcal{P} \quad \text{ for all } L(\cdot\mid\theta)\in\mathcal{F} \text{ and } \pi(\cdot)\in\mathcal{P} $$

**Lemma**  <i><u>Conjugation Property of Gaussian</u></i>
Suppose $x\in\mathbb{R}^d, \mu_i\in\mathbb{R}^d$ and $\sigma_i\in\mathbb{S}_d^{+}$ is positive semidefinite symmetric matrix. Then
$$
\prod_{i=1}^n\exp\left(-\frac12(x-\mu_i)^{\top}\sigma_i^{-1}(x-\mu_i)\right)=c\cdot\exp\left(-\frac12(x-\hat{\mu})^\top\hat{\sigma}^{-1}(x-\hat{\mu})\right) \\
$$
where $\hat{\sigma}=\left( \sum_{i=1}^n \sigma_i^{-1} \right)^{-1}$, $\hat{\mu} =\hat{\sigma}\left(\sum_{i=1}^n\sigma_{i}^{-1}\mu_i\right)$ and $c=\exp\left(\sum_{i=1}^n\mu_i^\top\sigma_i^{-1}\mu_i-\hat{\mu}^\top \hat{\sigma}^{-1}\hat{\mu}\right)$.
**Proof**  $$\begin{aligned}
   &\prod_{i=1}^n\exp(-\frac12(x-\mu_i)^{\top}\sigma_i^{-1}(x-\mu_i)) \\
   =&\exp\left(-\frac12\sum_{i=1}^n(x-\mu_i)^{\top}\sigma_i^{-1}(x-\mu_i)\right) \\
   =&\exp\left(-\frac12\sum_{i=1}^n\left(x^{\top}\sigma_i^{-1}x-\mu_i^{\top}\sigma_i^{-1}x-x^{\top}\sigma_i^{-1}\mu_i+\mu_i^{\top}\sigma_i^{-1}\mu_i\right)\right) \\
   =&\exp\left(-\frac12\left(x^{\top}\left(\sum_{i=1}^n\sigma_i^{-1}\right)x-2x^{\top}\left(\sum_{i=1}^n\sigma_i^{-1}\mu_i\right)+\sum_{i=1}^n\mu_i^{\top}\sigma_i^{-1}\mu_i\right)\right) \\
   =&\exp\left(-\frac12\left(x^{\top}\hat{\sigma}^{-1}x-2x^\top\hat{\sigma}^{-1}\hat{\mu}+\hat{\mu}^\top\hat{\sigma}^{-1}\hat{\mu}-\hat{\mu}^\top\hat{\sigma}^{-1}\hat{\mu}+\sum_{i=1}^n\mu_i^{\top}\sigma_i^{-1}\mu_i\right)\right)\\
   =&\exp\left(-\frac12\left((x-\hat{\mu})^{\top}\hat{\sigma}^{-1}(x-\hat{\mu})+\sum_{i=1}^n\mu_i^{\top}\sigma_i^{-1}\mu_i-\hat{\mu}^\top\hat{\sigma}^{-1}\hat{\mu}\right)\right)\\
   =&\exp\left(-\frac12(x-\hat{\mu})^{\top}\hat{\sigma}^{-1}(x-\hat{\mu})\right)\exp\left(\sum_{i=1}^n\mu_i^\top\sigma_i^{-1}\mu_i-\hat{\mu}^\top \hat{\sigma}^{-1}\hat{\mu}\right)
\end{aligned} $$

**Prop**  <i><u>Summary of Common Conjugate Priors</u></i>

| Prior | Likelihood | Posterior |
| ---- | ---- | ---- |
| $\theta\sim\text{Beta}(a,b)$ | $x\sim\text{Binomial}(n,\theta)$ | $\theta\mid x\sim\text{Beta}(a+x,b+n-x)$ |
| $\theta\sim\text{Gamma}(a,b)$ | $x_i\sim\text{Possion}(\theta)$ | $\theta\mid x\sim\text{Gamma}(a+\sum_{i}x_i,b+n)$ |
| $\theta\sim\text{Gamma}(a,b)$ | $x_i\sim\text{Gamma}(k,\theta)$ | $\theta\mid x\sim\text{Gamma}(a+kn,b+\sum_{i}x_i)$ |
| $\theta\sim\mathcal{N}(b,c^{-1})$ | $x_i\sim\mathcal{N}(\theta,\tau^{-1})$ | $\theta\mid x,\tau\sim\mathcal{N}(\frac{cb+n\tau\bar{x}}{c+n\tau},\frac{1}{c+n\tau})$ |
## Improper Priors
**Def**  <i><u>Improper Prior</u></i>
A prior distribution $\pi(θ)$ is improper if $\int\pi(\theta)\dd \theta=\infty$.

**Def**  <i><u>Sufficient</u></i>
We say that the empirical mean $\bar{x}$ is sufficient for parameter $\theta$ if the posterior depends on the data only through $\bar{x}$, rather than the each $x_{i}$.

## Jeffreys’ Prior
**Def**  <i><u>Jeffreys’ Prior</u></i>
The Jeffreys’ prior is defined as$$\pi_J(\theta)\propto\sqrt{|I(\theta)|}$$where $I(\theta)$ is the [[Fisher Information#^40ed31|Fisher information]].