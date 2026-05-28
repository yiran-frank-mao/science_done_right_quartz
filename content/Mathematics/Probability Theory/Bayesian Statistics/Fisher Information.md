---
created: 2024-02-05
updated: 2024-10-13
---
> [!definition] Score
> The score or informant is defined as the gradient of the log-likelihood with respect to the parameter:$$\nabla_{\theta} \log p(x\mid \theta)$$ ^c3026b

>[!remark]
> The score can be characterized as a set of vectors that is a basis for the tangent space of the statistical manifold at a point: $$l_{\alpha} := \frac{\partial l}{\partial \theta^{\alpha}}$$where $l$ is the log-likelihood and $\theta^{\alpha}$ are the parameters indexed by $\alpha$.

>[!proposition]
> The expectation value of the [[Fisher Information#^c3026b|score]] vanishes:$$\mathbb{E}_{x\mid\theta}\left[\nabla_{\theta} \log p(x\mid \theta)\right]=0$$

*Proof*  By the definition of the score, we have:$$\mathbb{E}_{x\mid\theta}\left[\nabla_{\theta} \log p(x\mid \theta)\right]=\int \nabla_{\theta} \log p(x\mid \theta) p(x\mid\theta)\dd x=\nabla_{\theta}\int p(x\mid\theta)\dd x=\nabla_{\theta}1=0$$$\square$

> [!definition] Fisher Information
> The Fisher information matrix of a parameter $\theta$ is defined as following:$$I_{ij}(\theta)=\mathbb{E}_{x\mid\theta}\left[ \frac{\partial\ell}{\partial\theta_i}\frac{\partial\ell}{\partial\theta_j}\right]$$where $\ell(\theta)=\log P(X\mid \theta)$ denotes the log-likelihood. ^40ed31

> [!theorem] Regularity Conditions
> The fisher information can also be written as$$I_{ij}(\theta)=-\mathbb{E}_{x\mid\theta}\left[\frac{\partial^2\log P(X\mid\theta)}{\partial\theta_{i}\partial \theta_{j}}\right]$$if $\log P(X\mid \theta)$ is twice differentiable with respect to $\theta$, and the following regularity conditions hold:
> 1. The partial derivative of $P(X\mid\theta)$ with respect to $\theta$ exists almost everywhere. (It can fail to exist on a null set, as long as this set does not depend on $\theta$)
> 2. The [[Integral#^e15bc4|integral]] of $P(X\mid\theta)$ can be differentiated under the integral sign with respect to $\theta$.
> 3. The [[Lebesgue Integration#^7e0caa|support]] of $P(X\mid\theta)$ does not depend on $\theta$.
> 
> $\quad$

> [!theorem] Cramér–Rao Lower Bound
> The inverse of the Fisher information matrix is a lower bound on the variance of any [[Bayesian Framework#^08fb7d|unbiased estimator]] $t$ of $\theta$:$$\mathrm{Var}(t)\succeq I(\theta)^{-1}$$More generally, for any biased estimator $t$ with [[Bayesian Framework#^08fb7d|bias]] $b(\theta)=\mathbb{E}_{x\mid\theta}[t]-\theta$, we have:$$\mathbb{E}_{x\mid\theta}\left(t-\mathbb{E}_p(t)\right)^2\geq\frac{\left(1+b^{\prime}(\theta)\right)^2}{n\mathbb{E}_{x\mid\theta}\left[\frac\partial{\partial\theta}\log p(x\mid\theta)\right]^2}$$ ^cccdf2

*Proof*  A proof of this theorem using [[Information Geometry|information geometry]] can be found [[Fisher Information Metric#^f2b7f1|here]]. $\square$