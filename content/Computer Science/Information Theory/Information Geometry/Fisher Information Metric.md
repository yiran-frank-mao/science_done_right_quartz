---
created: 2024-09-18
updated: 2024-10-27
tags:
  - tensor
completed: true
---
## Tensorial Representation of Random Variables

> [!definition] Tensor Product of Vector Valued Random Variables
> Suppose $\newcommand{\var}{\mathrm{Var}}\newcommand{\cov}{\mathrm{Cov}}\newcommand{\R}{\mathbb{R}}\newcommand{\E}{\mathbb{E}} X$ is a finite [[Random Variable and Probability Space#^9cf9be|sample space]]. The tensor product of two [[Random Variable and Probability Space#^a0b9ff|random variables]] $v\colon X\to V$ and $w\colon X\to W$ with $V$ and $W$ being vector spaces is defined as $$v\otimes w \colon X\to V^{*}\otimes W,\quad x\mapsto v(x)\otimes w(x),$$
> where $V^{*}\otimes W$ is the [[Tensors and Tensor Products#^732917|tensor product]] of the [[Mathematics/Linear Algebra/Duality#^6c7627|dual space]] of $V$ and $W$. Notice that $v\otimes w$ is also a random variable.

> [!definition] General Expected Value
> Suppose $X$ is a finite sample space and $V$ is a vector space over $\R$. The expected value of a random variable $v\colon X\to V$ is defined as $$\E_{\mu}[v]:=\sum_{x\in X} \mu(x)v(x)\in V$$Naturally, if fixing some $v\colon X\to V$, then $\E[v]\colon \Omega\to V$ forms a map from the space of probability measures to $V$.

> [!definition] General Covariance
> Suppose $v\colon X\to V$ and $w\colon X\to W$ are two [[Random Variable and Probability Space#^a0b9ff|random variables]], with $V$ and $W$ being [[Vector Spaces#^f4b63e|vector spaces]] with standard $\sigma$-algebra of Borel sets. Then the covariance of $v$ and $w$ with respect to some probability measure $\mu$ is defined as $$\cov_{\mu}[v,w]:=\E_{\mu}\left[(v-\E_{\mu}[v])\otimes(w-\E_{\mu}[w])\right]$$where $(v-\E_{\mu}[v])\colon X\to V$ satisfying $(v-\E_{\mu}[v])(x):=v(x)-\E_{\mu}[x]$.
> Correspondingly, the variance of $v$ is defined as $\var_{\mu}[v]:=\cov_{\mu}[v,v]$. This aligns with the definition of covariance in $\R^{n}$, where $\otimes$ will degenerate to the vector outer product.

> [!remark]+
> Now according to the above definition, the covariance of two random variables $v$ and $w$ is tensorial, since the expected value  of a map $X\to V\otimes W$ will be in $V\otimes W$.

$\cov$ forms an inner product on the space of random variables $\mathcal{R}(X,V)$,

> [!lemma] Covariance Inequality
> For all random variables $v\colon X\to V$, $w\colon X\to W$ and $u\colon X\to U$, the covariance tensor satisfies the following identity: $$\cov[u,v]\succeq \cov[u,w]\cov^{-1}[w,w]\cov[w,v]$$ Alternatively, ^32d6c3

*Proof*  For any probability measure $\mu$, we have $$\begin{aligned}
\cov[u,v]&=\E[(u-\E[u])\otimes(v-\E[v])] \\
&= \E[(u-\E[u])\otimes(w-\E[w])\otimes(w-\E[w])^{-1}\otimes(w-\E[w])^{-1}\otimes(w-\E[w])\otimes(v-\E[v])] \\
\end{aligned}$$

## Fisher Information Metric

Now we will focus on a parameterized subspace of the space of probability measures, say $\Theta\subset \Omega$. For example, $\Theta$ could be the set of all normal distributions, parameterized by mean and standard deviation, which are both in $\R$. Notice that $\Theta$ is homeomorphic to some Euclidean space $\R^{n}$, and this is allowed as $\Omega$ is a manifold.

> [!definition] Fisher-Rao (Information) Metric
> Suppose $\Omega$ is the manifold of probability measures for finite $n$-point sample space $X$. Given any tangent vector $v$ at $\mu\in\Omega$, we can take derivative of the surprise in the direction of $v$, yielding a [[Measurable Spaces and Functions#^11c83a|measurable]] [[Fisher Information#^c3026b|score function]] $l_{v}\colon X\to \R$ such that $l_{v}(x_{i}):=-v(\log \mu_{i})$. And the Fisher information metric $I$ is defined as the expectation of the tensor product of the score functions: $$\langle v, w \rangle_{I_{\mu}}=I_{\mu}(v,w):=\E_{\mu}\left[l_{v}\otimes l_{w}\right]$$Notice that this definition agrees with the definition of [[Fisher Information#^40ed31|Fisher information matrix]].

> [!lemma]
> The expected value of the score function is zero.

*Proof*  For all $\mu\in\Omega$ and $v\in T_{\mu}\Theta$, we have $$\E_{\mu}[l_{v}] = \sum_{i} \mu_{i} l_{v}(x_{i}) = \sum_{i}\mu_{i} v(\log\mu_{i})=\sum_{i}v(\mu_{i})=v\left(\sum_{i}\mu_{i}\right)=v(1)=0$$

> [!corollary]
> The Fisher information metric is the covariance tensor of the score functions: $$I=\cov[l, l]$$

*Proof*  For all $\mu\in\Omega$ and $v,w\in T_{\mu}\Theta$, since the [[Probability Distributions#^2f930b|expected value]] of the score function is zero, we have the following identity: $$I_{\mu}(v,w)=\E_{\mu}\left[l_{v}\otimes l_{w}\right]=\E_{\mu}\left[(l_{v}-0)\otimes(l_{w}-0)\right]=\cov_{\mu}[l_{v},l_{w}]$$

> [!proposition]
> The [[Statistical Manifold#^f45770|statistical manifold]] $(\Omega,g,C)$ with Fisher information metric $g$ and totally symmetric cubic tensor $C$ such that $C_{\mu}(u,v,w):=\E_{\mu}[l_{u} \otimes l_{v} \otimes l_{w}]$ is equivalent to the [[Divergence and Bregman Geometry#^f96fd6|Bregman manifold]] using the negative [[Information Content and Entropy#^d1821a|Shannon entropy]] as potential function.

*Proof*  First show that the two metric tensor coincide. $$\begin{aligned}
I_{\mu}(\partial_{i}, \partial_{j})&=\mu_{k}\cdot l_{\partial_{i}}(x_{k})\otimes l_{\partial_{j}}(x_{k})\\&=\mu_{k}\cdot \partial_{i}(\log \mu_{k})\cdot \partial_{j}(\log \mu_{k}) \\ &= \mu_{k}\cdot \frac{1}{\mu_{k}}\partial_{i}(\mu_{k})\cdot \frac{1}{\mu_{k}}\partial_{j}( \mu_{k})\\&=\frac{1}{\mu_{k}}(\partial_{i}\mu_{k} \cdot \partial_{j} \mu_{k})
\end{aligned}$$On the other hand, the Bregman metric satisfies: $$\begin{aligned} g(\partial_{i}, \partial_{j})&=\partial_{ij} F\\ &=\partial_{i}(\partial_{j} (\mu_{k} \log \mu_{k}))\\ &=\partial_{i}((1+\log \mu_{k})\partial_{j}\mu_{k})\\ &=\frac{1}{\mu_{k}}(\partial_{i}\mu_{k} \cdot \partial_{j} \mu_{k})+(1+\log\mu_{k})\partial_{i}\partial_{j}\mu_{k}\\ &=\frac{1}{\mu_{k}}(\partial_{i}\mu_{k} \cdot \partial_{j} \mu_{k}) \end{aligned}$$Hence, the two metric tensors are the same. Now consider the cubic tensor: $$\begin{aligned} C_{\mu}(\partial_{i}, \partial_{j}, \partial_{k})&=\E_{\mu}[l_{\partial_{i}}\otimes l_{\partial_{j}}\otimes l_{\partial_{k}}]\\ &=\mu_{l}\partial_{i}(\log \mu_{l})\partial_{j}(\log \mu_{l})\partial_{k}(\log\mu_{l})\\&=-\frac{1}{\mu_{l}^{2}} \partial_{i}\partial_{j}\partial_{k}\mu_{l}\end{aligned}$$Similarly, the cubic tensor on the Bregman manifold is: $$\begin{aligned} C^{B_{F}}_{\mu}(\partial_{i}, \partial_{j}, \partial_{k})&=\partial_{i}\partial_{j}\partial_{k}F\\ &=\partial_{i}\partial_{j}((1+\log \mu_{l})\partial_{k}\mu_{l})\\ &=\partial_{i}\left(\frac{1}{\mu_{l}}\partial_{j}\mu_{l}\cdot \partial_{k}\mu_{l}\right)\\&=-\frac{1}{\mu_{l}^{2}}\partial_{i}\partial_{j}\partial_{k}\mu_{l}\end{aligned}$$Therefore, the cubic tensors are also the same, and the two manifolds are equivalent.

> [!theorem] Cramér–Rao Lower Bound
> [[Fisher Information#^cccdf2|Cramér–Rao lower bound]] holds for the Fisher information metric, based on the general covariance definition. i.e. The inverse of the Fisher information metric tensor is a general lower bound on the variance of any [[Bayesian Framework#^08fb7d|unbiased estimator]] $t\colon X\to\Theta$ of $\theta\in\Theta \subset \Omega$: $$\var[t]\succeq I^{-1}$$where $\succeq$ is the [[Convex Sets#^ae2029|generalized inequality]] for positive semi-definite tensors. ^f2b7f1

*Proof*  Fix some $\theta\in\Theta$. Suppose $t\colon X\to \Theta$ is an unbiased estimator for $\theta$. For any arbitrary tangent vector $v\in T_{\theta}\Theta$, we have $$\begin{aligned}
v(\theta)=v\left( \E_{\theta}[t] \right) &= v \left(  \sum_{i} \theta_{i}t(x_{i}) \right) \\ &= \sum_{i} v(\theta_{i}) t(x_{i}) \\ &= \sum_{i} \frac{\theta_{i}v(\theta_{i})}{\theta_{i}} t(x_{i}) \\ &= \sum_{i} \theta_{i} v(\log \theta_{i}) t(x_{i}) \\ &= -\E_{\theta}[l_{v} \otimes t]
\end{aligned}$$Furthermore, the covariance of $l_{v}$ and $t$ at $\theta$ is: $$\begin{aligned} \cov_{\theta}[l_{v}, t] &= \E_{\theta}\left[ (l_{v}-\E_{\theta}[l_{v}])\otimes (t-\E_{\theta}[t]) \right] \\ &= \E_{\theta}\left[ l_{v}\otimes (t-\theta) \right] \\ &= \E_{\theta}[l_{v}\otimes t] -\E_{\theta}[l_{v}] \cdot \theta \\ &= \E_{\theta}[l_{v}\otimes t]\end{aligned}$$Now replace directional derivative $v$ with derivative with respect to $\theta$, we have: $$\begin{aligned}\mathrm{id}_{T_{\theta}\Theta}&=\mathrm{D}_{\theta} \theta =- \E[l \otimes t] =-\cov[l,t] \end{aligned}$$where $l\colon T_{\theta}\Theta\times X \to \R$ is canonically defined as $(v,x)\mapsto l_{v}(x)$.
Hence by [[Fisher Information Metric#^32d6c3|lemma]],  we can write: $$\var[t]=\cov[t,t] \succeq \cov[t,l] \cov[l,l]^{-1} \cov[l,t]=\cov[l,l]^{-1}=I^{-1}.$$$\square$

## Maximum Likelihood Estimation

> [!proposition]
> If the maximum likely hood estimate achieves the Cramer-Rao lower bound on $X$ and $Y$, then it also achieves the Cramer-Rao lower bound on $X\times Y$.
