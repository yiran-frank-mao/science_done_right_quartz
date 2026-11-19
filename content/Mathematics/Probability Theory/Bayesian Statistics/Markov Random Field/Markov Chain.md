**Def**  <i><u>Period</u></i>
The period $d_{x}$ of state $x$, is the largest common divisor of the set:$$\{n ≥ 1 \mid \pr^{n}(x,x) > 0\}$$We say that state $x$ is aperiodic if $d_{x} = 1$. If a Markov chain is periodic then there are parts of the state space that the chain can visit only at regular intervals.
**Prop**  $\pr(x,x) > 0$ implies that $d_{x} = 1$.

**Def**  <i><u>Irreducibility</u></i>
A Markov chain is said to be $π$-irreducible if for every $x,y \in E$,$$\pi(y)>0\implies\Pr(x_{n}=y\mid x_{0}=x)>0$$Irreducibility means that the chain can move from anywhere to anywhere else in a finite number of steps.

**Thrm**  <i><u>Limit Theorem of Markov Chain</u></i>
If $X_{t}$ is a $π$-irreducible Markov chain with transition kernel $P$ and invariant distribution $π$, and $g$ is a real valued function with $\int |g(x)|\pi(\dd x) < ∞$, then$$\lim_{N\to\infty}\frac1N\sum_{t=1}^Ng(X_t)=\int g(x)\pi(x)dx<\infty $$If the chain is also aperiodic, then there is convergence in total variation: $$\lim_{n\to\infty}||P^{n}(X_{0},\cdot)-\pi(\cdot)||=0$$That is the Markov chain sample path mimics a random sample from $π$, and the distribution of the realization converges to $π$.

**Corollary**  For an aperiodic and $\pi$-irreducible Markov chain, $π(X)$, is also the limiting distribution of successive chain iterates, regardless of the starting values of the chain.