**Algorithm**  <i><u>Importance Sampling</u></i>
Given a distribution $f(x)$, and a proposed distribution $g(x)$:
1. For $i = 1, \dots, N$
	1. Generate $x^{(i)}$ from $g(x)$
	2. Give $x^{(i)}$ a weight $w^{(i)} ∝ \frac{f (x^{(i)})}{g (x^{(i)})}$
$(x^{(1)}, w^{(1)}), \dots , (x^{(N)}, w^{(N)})$ are weighted samples from $f (x)$.

**Prop**  Weighted expectations under $g(x)$ act as expectations under $f (x)$.
**Proof**  Suppose weights $w(x)=f(x)/g(x)$. Then$$\E_{g}[w(x)h(x)]=\int w(x)h(x)g(x)\dd x=\int h(x)f(x)\dd x=\E_{f}[h(x)]$$

**Fact**  <i><u>Variability of Weights</u></i>
If weights are highly variable (i.e. $\Var(w_{i} )$ is high), then it's bad for importance sampling. For best performance, we prefer low variability weights. ^2c85b6

**Def**  <i><u>Effective Sample Size</u></i>
The effective sample size is usually used to measure weights variance, higher effective sample size, lower variability of weights:$${\mathrm{ESS}}=\left[\sum_{i=1}^n(w_{i})^2\right]^{-1}$$where $w_{i} = W(x^{(i)})$ are normalized weights.
**Prop**  
- $1 ≤ {\mathrm{ESS}} ≤ n$
- $\mathrm{ESS}=1$ if $w_{i}=0$ for all $i$ except for some $w_{k}=1$
- $\mathrm{ESS}=n$ when $w_{i}= 1/n$ for all $i$
- To maximize $\mathrm{ESS}$, choose proposed $g(x)$ to closely match $f (x)$.


**Algorithm**  <i><u>Sequential Importance Sampling</u></i>
