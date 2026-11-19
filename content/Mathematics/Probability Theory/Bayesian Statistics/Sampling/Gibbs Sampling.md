## Gibbs Sampler

**Algorithm**  <i><u>Gibbs Sampler</u></i>
Generates a sample from $\pi(X , Y)$ by sampling in turn from the conditional distributions $π(x|y)$ and $π(y|x)$:
1. Arbitrarily choose $y_{0}$.
2. For $t=0,\dots,T$:
	1. Draw $x_{t} \simπ(x\mid y_{t})$
	2. Draw $y_{t}\sim\pi(y\mid x_{t})$
3. Produces $(x_{0},y_{0}),(x_{1},y_{1}),\dots,(x_{T},y_{T})$
In general $p$-dimensional case, use the most up-to-date values of each parameter at each stage. Gibbs sampler works in an irreducible and aperiodic Markov chain that converges to a unique limiting distribution. Yet there would be more than one possible limiting distribution in general.

**Thrm**  <i><u>Hammersley-Clifford Theorem</u></i>
The following positivity condition is sufficient for the univariate conditionals to uniquely determine the joint distribution:$$f (θ)>0 \text{ for all } \theta \text{ such that each marginal } f (\theta_{1}), \dots , f (\theta_{p})>0$$

**Prop**  The rate of convergence of Gibbs sampler depends on the degree of dependence between model parameters.

## Assessing Convergence

**Algorithm**  <i><u>Burn In</u></i>
If convergence is slow, early chain values will not represent $π(X)$, so typically the first portion of each chain is discarded.
![burn-in|450](https://i.imgur.com/KjcocOu.png)

**Algorithm**  <i><u>Multiple Chains</u></i>
Start multiple chains at over dispersed starting points, and after convergence chains will be indistinguishable.
![multi-chain|520](https://i.imgur.com/KAF4Mt7.png)

## Convergence Diagnostics

**Fact**  There are many convergence diagnostics, operating the principal that if chains have converged, then diagnostic tests will be passed. However, the reverse is not true. So are necessary, but not sufficient indicators of sampler convergence.

**Def**  <i><u>Gelman-Rubin Ratio</u></i>
Denote $\psi_{ij}$ as $i$-th sample from $j$-th Markov chain. Each chain is length $n$ after discarding first half of sample path. The Gelman-Rubin ratio is given by$$\hat{R}=\sqrt{\hat{\Var}(\psi\mid y)/W}$$where$$\hat{\Var}(\psi|y)=\frac{n-1}n{W}+\frac1n{B}$$with the between chain variance $B$ be defined as$${B=\frac n{m-1}\sum_{j=1}^m(\bar{\psi}_{.j}-\bar{\psi}_{..})^2\text{ where }\bar{\psi}_{.j}=\frac1n\sum_{i=1}^n\psi_{ij},\bar{\psi}_{..}=\frac1m\sum_{j=1}^m\bar{\psi}_{.j}}$$and the within chain variance $W$ be defined as$${W=\frac1m\sum_{j=1}^ms_j^2,\text{ where }s_j^2=\frac1{n-1}\sum_{i=1}^n(\psi_{ij}-\bar{\psi}_{\cdot j})^2}$$

**Thrm**  <i><u>Gelman-Rubin Diagnostic</u></i>
If chains have converged, then the Gelman-Rubin ratio $\hat{R}$ decline to $1$ as $n\to\infty$.

## Blocking

**Fact**  If parameters $θ_{1}$ and $θ_{2}$ are highly correlated, then Gibbs sampling via $θ_{2}\mid\theta_{1}$ and $θ_{1}\midθ_{2}$ will converge slowly. If joint conditional distribution of $(θ_{1},θ_{2})\mid \text{rest}$ is available, joint (block) updates can avoid effect of high correlation.
![blocking|500](https://i.imgur.com/qNjcbx6.png)