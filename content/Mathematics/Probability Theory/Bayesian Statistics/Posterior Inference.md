## Loss Function
**Def**  <i><u>Loss Function</u></i>
For a decision $d \in \mathcal{D}$, a loss function $L(\theta, d)$ defines the penalty in taking decision $d$ given parameter value $\theta$. In Bayesian scenario, we have $d=\hat{\theta}$ to be the point estimate.

**Def**  <i><u>Quadratic Loss</u></i>
We define the quadratic loss as$$L(\theta, d) = (\theta − d)^{2}$$**Prop**  Quadratic loss is minimized when $d = \mathbb{E}[\theta\mid X]$.

**Def**  <i><u>Linear Loss</u></i>
We define the linear loss:$$L(\theta,d)=\begin{cases}g(d-\theta)&\mathrm{~if~}d>\theta\\h(\theta-d)&\mathrm{~if~}d<\theta\end{cases}$$For given scalars $g$ and $h$.
**Prop**  Linear loss is minimized at $d=q$, where $q$ is the $\frac{h}{g+h}$ quantile of the posterior.

**Def**  <i><u>Absolute Error Loss</u></i>
Absolute error loss is a special case of the linear loss when $g=h=1$:$$L(θ, d) = |θ − d|$$**Prop** The posterior median minimizes absolute error loss.

**Def**  <i><u>0-1 Loss</u></i>
The 0-1 loss is defined as follows:$$L(\theta,d)=\begin{cases}0&\mathrm{~if~}|d-\theta|\leq\epsilon\\1&\mathrm{~if~}|d-\theta|>\epsilon\end{cases}$$**Prop**  $\mathbb{E}[L(\theta,d)]=\pr(|\theta-d|>\epsilon)$
**Prop**  The posterior mode minimizes 0-1 loss when choosing $\epsilon$ arbitrarily small.

## Predictive Inference
**Def**  <i><u>Predictive Density Function</u></i>
Predictive density function of a future observation $y$ is$$f(y\mid X)=\int f(y\mid\theta)\pi(\theta\mid x)\dd\theta$$<u><b>e.g.</b></u> Suppose we have $x \sim \text{Binomial}(n, \theta)$ with conjugate prior $\theta\sim \text{Beta}(a, b)$. Then we know that $\theta\mid x\sim\text{Beta}(a+x,b+n-x)$. Now suppose we intend to make $N$ further observations, let $y$ be the number of successes, $y\mid\theta\sim\text{Binomial}(N,\theta)$. Hence$$f(y\mid\theta)=\binom{N}{y}\theta^{y}(1-\theta)^{N-y}$$So for $y = 0,1,...,N$,$$\begin{aligned}f(y|x)&=\int_{0}^{1}{\binom Ny}\theta^y(1-\theta)^{N-y}\times\frac{\theta^{a+x-1}(1-\theta)^{b+n-x-1}}{B(a+x,b+n-x)}\dd\theta\\&=\binom{N}{y}\frac{\text{Beta}(y+a+x,N-y+b+n-x)}{\text{Beta}(a+x,b+n-x)}\end{aligned}$$<u><b>e.g.</b></u>  Suppose $y\mid\theta\sim \mathcal{N}(\theta,\sigma_{y}^2)$ and $\theta\mid x\sim \mathcal{N}(\mu_\theta,\sigma_\theta^2)$, then we can derive that $y\mid x\sim \mathcal{N}(\mu_\theta,\sigma_\theta^2+\sigma_y^2)$.


**Algorithm**  <i><u>Sampling from Posterior Predictive Distributions</u></i>
1. Obtain posterior samples $\theta_{i} \sim \pi(\theta|x)$
2. For each $\theta_{i}$ we can generate $y_{i} \sim f (y|\theta_{i})$
3. This gives us joint samples $(\theta_{i},y_{i})\sim f(y|\theta)\pi(θ|x)$
4. To obtain samples from $f(y|x)$, integrate out $\theta$ (discard the $\theta_{i}$ values), leave $y_{i}\sim f (y|x)$ only.