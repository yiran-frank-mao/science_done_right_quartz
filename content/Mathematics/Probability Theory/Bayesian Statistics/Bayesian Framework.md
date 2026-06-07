---
created: 2024-01-16
updated: 2024-09-24
---
## The Bayesian Theorem

> [!theorem] Bayesian Theorem
> The Bayesian theorem states the following equation:$$\pr(A|B)=\frac{\pr(B|A)\pr(A)}{\pr(B)}$$where
> - $\pr(A\mid B)$ is a conditional probability, also called posterior.
> - $\pr(B\mid A)$ is also a conditional probability, also called the likelihood.
> - $\pr(A)$ and $\pr(B)$ are probabilities of observing $A$ and $B$ respectively without any given conditions, are known as the prior probability and marginal probability.
>$\quad$

## Bayesian Inference

> [!definition] Estimator
> Suppose a fixed parameter $\theta$ needs to be estimated. An estimator of $\theta$, written as $\hat{\theta}$ is a function that maps the observation space to the parameter space, which is naturally a [[Random Variable and Probability Space#^a0b9ff|random variable]].

> [!definition] Bias
> The bias of an estimator $\hat{\theta}$ is defined as $$b(\theta)=\mathbb{E}_{x|\theta}[\hat{\theta}]-\theta$$ If $b(\theta)=0$, then we call the estimator unbiased, otherwise it is biased. ^08fb7d

