**Algorithm**  <i><u>Reversible Jump MCMC</u></i>
1. Initialise $k$ and $θ_{k}$ at iteration $t = 1$.
2. For iteration $t \geq 1$ perform
	1. Within-model move: with a fixed model $k$, update the parameters $θ_{k}$ according to any MCMC updating scheme.
	2. Between-models move: simultaneously update model indicator $k$ and the parameters $θ_{k}$ according to the general reversible proposal/acceptance mechanism.
3. Increment iteration $t=t+1$. If $t<N$,go to Step 2.

## Dimension Matching
**Fact**  In order to match dimensions between the two model states, a random vector $u$ of length $d_{k\to k^\prime} = n_{k^\prime} − n_{k}$ is generated from a known density $q(u)$. The current state $θ_{k}$ and the random vector $u$ are then mapped to the new state $\theta^{\prime}_{k^\prime} = g_{k\to k^\prime}(θ_{k},u)$ through a one-to-one mapping function $g_{k \to k ^\prime} \colon \R^{n_{k}} \times \R^{d_{k}} \to \R^{n_{k^\prime}}$.

<u><b>e.g.</b></u> Suppose that model $M_{1}$ has states $(k = 1, θ_1 ∈\R)$ and model $M_2$ has states $(k = 2,θ_{2} ∈ \R^2)$. Let $(1, θ^\star)$ denote the current state in $M_{1}$ and $(2, (θ^{(1)}, θ^{(2)}))$ denote the proposed state in $M_{2}$. Under dimension matching with a simple split/merge move, we might generate a random scalar $u$, and let $θ^{(1)} = θ^\star + u$ and $θ^{(2)} = θ^{\star} − u$, with the reverse move given deterministically by $θ^{\star} = \frac12(θ^{(1)} +θ^{(2)})$. For the same setup but with a simple birth/death move, we might specify $θ^{(1)} = θ^{\star}$ and $θ^{(2)} = θ^{\star} + u$, with the reverse move given deterministically by $θ^{\star} = θ^{(1)}$.

