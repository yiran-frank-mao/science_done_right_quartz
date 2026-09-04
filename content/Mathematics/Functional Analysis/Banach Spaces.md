>[!definition]
> A [[Normed Spaces#^345fd3|normed space]] $(X,\|\cdot\|)$ is a Banach space if it is [[Complete Metric Space#^67b510|complete]] as a [[Metric Spaces#^0eacc7|metric space]]. ^7196a5

<u><b>e.g.</b></u>  
- Let $\Omega \subset \mathbb{R}^n$ be a domain and $\alpha \in (0,1]$. A function $f\colon \Omega \to \mathbb{R}$ is said to belong to the *Hölder space* $C^{0,\alpha}(\Omega)$ if $$\|f\|_{C^{0,\alpha}(\Omega)} := \sup_{x \in \Omega} |f(x)| + \sup_{\substack{x,y \in \Omega\\ x \neq y}} \frac{|f(x) - f(y)|}{|x-y|^\alpha} < \infty.$$
	- The first term $\sup_{x \in \Omega} |f(x)|$ measures the boundedness of $f$.
	- The second term $\sup_{x \neq y} \frac{|f(x) - f(y)|}{|x-y|^\alpha}$ measures the *$\alpha$-Hölder continuity* of $f$.
  Equipped with this norm, $C^{0,\alpha}(\Omega)$ is a Banach space.
- Suppose $(X,\mathcal{S},\mu)$ is a [[Measurable Spaces and Functions#^c2e020|measure space]], then $L^{p}(X,\mathcal{S},\mu)$ is a Banach space with norm $\|f\|_{p}:=\left(\int_{X}|f|^{p}\dd\mu\right)^{1/p}$. The proof of completeness will be provided later [[Banach Spaces#^63386a|here]] after we have established a tool for proving completeness of normed spaces.

> [!definition] Absolutely Convergent Series
> A series $\sum_{n=1}^{\infty}x_{n}$ in a [[Normed Spaces#^345fd3|normed space]] $(X,\|\cdot\|)$ is said to be *absolutely convergent* if the series $\sum_{n=1}^{\infty}\|x_{n}\|$ converges in $\R$.

> [!theorem]
> A [[Normed Spaces#^345fd3|normed space]] is Banach if and only if every absolutely convergent series in it converges.
> 

*Proof*  Suppose $X$ is a Banach space, and $\sum_{n=1}^{\infty}x_{n}$ is absolutely convergent, then $\sum_{n=1}^{\infty}\|x_{n}\|$ converges in $\R$. So the sequence of partial sum of norms is Cauchy in $\R$. Consider $\{s_{n}\}_{n=1}^{\infty}$, $s_{n}:=\sum_{i=1}^{n}x_{i}$, for any $N\leq m\leq n$, we have $$\|s_{n}-s_{m}\|=\left\| \sum_{i={m+1}}^{n} x_{i} \right\|\leq \sum_{i=m+1}^{n}\|x_{i}\| \to 0 \quad\text{as }N\to \infty,$$so $\{s_{n}\}_{n}$ is Cauchy in $X$, and hence convergent since $X$ is complete.
Conversely, we pick a Cauchy sequence in $X$, say $\{x_{n}\}_{n=1}^{\infty}$. We can pick a subsequence $\{x_{k_{n}}\}_{n}$ such that $\|x_{k_{n+1}}-x_{k_{n}}\|< 2^{-n}$. Define $y_{1}=x_{k_{1}}$, and $y_{i}=x_{k_{i+1}}-x_{k_{i}}$ for all $i>1$. Then the series $\sum_{n=1}^{\infty}y_{n}$ is absolutely convergent because $$\sum_{n=1}^{\infty}\|x_{k_{n+1}}-x_{k_{n}}\|<\sum_{n=1}^{\infty} 2^{-n}<\infty,$$and hence convergent. That is, the sequence of partial sums $\{s_{n}\}_{n}$, $s_{n}:=\sum_{i=1}^{n}y_{i}=x_{k_{n+1}}$ converges in $X$. Since $\{s_{n}\}_{n}$ is a subsequence of the original Cauchy sequence $\{x_n\}_{n}$, we conclude that $\{x_n\}_{n}$ converges in $X$. Hence, $X$ is Banach.  $\square$

<u><b>e.g.</b></u>  We now use this theorem to show that $L^{p}(X,\mathcal{S},\mu)$ is complete. Suppose $\sum_{n=1}^{\infty} f_{n}$ absolutely converges to $M>0$. We define $g_{n}:=\sum_{i=1}^{n}|f_{n}|$. By Minkowski's inequality, $$ \|g_{n}\|_{p}\leq \sum_{i=1}^{n} \|f_{i}\|_{p} \leq \sum_{i=1}^{\infty}\|f_{i}\|_{p}=M<\infty.$$Note that $g_{n}$ is increasingly convergent to $g=\sum_{i=1}^{\infty}|f_{i}|$, monotone convergence theorem gives $$\|g\|_{p}^{p}=\int g^{p}\dd\mu = \lim_{n\to \infty}\int g_{n}^{p}\dd\mu \leq M^{p}.$$Hence $g\in L^{p}(X,\mathcal{S},\mu)$, in particular, $g(x)=\sum_{i=1}^{\infty}|f_{i}(x)|<\infty$ a.e. Since absolute convergence implies convergence for series in $\R$, we can define $F(x):=\sum_{i=1}^{\infty}f_{i}(x)<\infty$ for a.e. $x$, also let $F_{n}(x):=\sum_{i=1}^{n}f_{i}(x)$ a.e. Note that $|F(x)|\leq g(x)$, by dominated convergence theorem, we have $$ ^63386a