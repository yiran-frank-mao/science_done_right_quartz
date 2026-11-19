## M-H Sampler
**Fact**  Gibbs sampler requires simulation from the full conditional distributions $π(θ_{i}\midθ_{−i})$ for all $i = 1,\dots,p$. As before these may not be available. Instead of sampling from $π(θ_{i}\midθ_{−i})$,
we can sample from $q(θ_{i} \midθ_{−i} )$ where $q$ is easy to sample from, then decide whether to accept sample as next point in Markov chain simulation, or to stay at the current point.

**Algorithm**  <i><u>Metropolis-Hastings Sampler</u></i>
For any proposed distribution $q(θ\midθ_{t})$ such that the Markov chain is still $π$-irreducible and aperiodic:
1. Initialize parameter vector $θ_{1}$. Set $t = 1$.
2. Generate proposed point $θ^\star \sim q(θ|θ_{t} )$
3. Generate $u \sim\mathcal{U}(0,1)$. If $u \leq \alpha(θ_t,θ^\star)$ where$$\alpha(\theta_t,\theta^{\star})=\begin{cases}\min\left(1,\frac{\pi(\theta^\star\mid)q(\theta_t\mid\theta^{\star})}{\pi(\theta_t|x)q(\theta^\star\mid\theta_t)}\right)&\text{if }\pi(\theta_{t}\mid x)q(\theta^{\star}\mid\theta_t)>0\\1&\text{otherwise}\end{cases}$$then accept $θ_{t+1} = θ^\star$. Else $\theta_{t+1}=\theta_{t}$.
4. Increment $t=t+1$ and repeat the above.

**Thrm**  <i><u>Detailed Balance</u></i>
Suppose $P(θ,θ^{\star})$ is a transition density for a given $θ$. Then a $P(θ,θ^\star)$ that satisfies the reversibility condition:$$\pi(\theta)P(\theta,\theta^*)=\pi(\theta^*)P(\theta^*,\theta)$$has $π(θ)$ as its invariant distribution.

##  M-H Special Cases
**Def**  <i><u>Random Walk Metropolis Sampler</u></i>
If $q(θ^{\star}\midθ_{t} ) = f (|θ^{\star} − θ_{t} |)$ for some arbitrary density $f$ then the M-H algorithm is a random walk as$$\theta^{\star}=\theta_{t}+\epsilon\quad\text{where }\epsilon\sim f$$we call it random walk metropolis sampler.

**Prop**  For random walk metropolis sampler, we have$$\alpha(\theta_t,\theta^{\star})=\min\left\{1,\frac{\pi(\theta^{\star})}{\pi(\theta_t)}\right\}$$