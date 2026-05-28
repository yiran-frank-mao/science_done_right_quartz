---
created: 2024-04-25
updated: 2024-09-25
---
## Cauchy Sequence

>[!definition] Cauchy Sequence
Let $(X,d)$ be a [[Metric Spaces#^0eacc7|metric space]]. A sequence $(x_{n})$ in $X$ is called a Cauchy sequence if for any $ε > 0$ there exists $N$ such that $d(x_{n},x_{m}) < ε$ for all $n,m > N$. ^179eeb

>[!theorem]
>[[Sequence and Convergence#^f71e2a|Convergent sequences]] in metric spaces are Cauchy sequences. ^ad57d2

*Proof*  Suppose $(x_{n})$ is convergent with $x_{n} → x$. Then for any $ε > 0$, there exists $N$ such that $d(x_{n},x) < ε/2$ for all $n > N$. Therefore, for all $n,m > N$, we have $$d(x_{n},x_{m})\leq d(x_{n},x)+d(x,x_{m})<ε/2+ε/2=ε$$Thus $(x_{n})$ is a Cauchy sequence. $\square$

>[!proposition]
>Cauchy sequences in metric spaces are bounded.

*Proof*  Let $(x_{n})$ be a Cauchy sequence. Then there exists $N$ such that $d(x_{n},x_{N})<1$ for all $n≥N$. Let $$R=\max\left\{d(x_1,x_N),\cdots,d(x_{N-1},x_N)\right\}+1$$Then $d(x_{n},x_{N}) < R$ for all n. Therefore $x_{n} ∈ B_{R}(x_{N})$ for all $n$, i.e. $(x_{n})$ is bounded. $\square$

>[!theorem]
> Let $(X,d)$ be a metric space and let $(x_{n})$ be a Cauchy sequence in $X$. If $(x_{n})$ has a convergent subsequence, then $(x_{n})$ is convergent. ^80b2f4

*Proof*  Let $(x_{n})$ be a Cauchy sequence and let $(x_{n_k})$ be a convergent subsequence of $(x_{n})$ with $x_{n_k} → x$. We have $$d(x_n,x)\leq d(x_n,x_{n_k})+d(x_{n_k},x)\leq\sup_{m\geq n}d(x_n,x_m)+d(x_{n_k},x)$$for sufficiently large $k$. By taking $k → ∞$ and using $d(x_{n_k} ,x) → 0$, we obtain $$d(x_n,x)\leq\sup_{m\geq n}d(x_n,x_m)$$Since $(x_{n})$ is Cauchy, the right hand side goes to $0$ as $n → ∞$. Therefore $d(x_{n},x)→0$ as $n→∞$, that is $x_{n} →x$. $\square$

>[!theorem]
> Every Cauchy sequence in $\R^{k}$ is convergent.

*Proof*  Let $(x_{n})$ be a Cauchy sequence in $\R^{k}$. Then $(x_{n})$ is bounded. Thus, it follows from [[Sequence and Convergence#^75364e|Bolzano-Weierstrass theorem]] that $(x_{n})$ has a convergent subsequence. Consequently, by invoking [[Complete Metric Space#^80b2f4|previous theorem]], $(x_{n})$ is convergent.

## Completeness

>[!definition] Complete Metric Space
A metric space $(X,d)$ is called complete if every Cauchy sequence in $X$ is convergent. ^67b510

<u><b>e.g.</b></u> 
- $\R^{k}$ with the Euclidean metric is complete.
- $(0,1)$ with the induced Euclidean metric is not complete.
- $C[−1,1]$ is complete under the metric $$d_\infty(f,g)=\max_{x\in[-1,1]}|f(x)-g(x)|$$
$\quad$ 

>[!theorem]
>Let $(X,d)$ be a complete metric space and $S ⊂ X$. Then $(S,d)$ is complete iff $S$ is closed in $X$.

*Proof*  Let $(x_{n})$ be a sequence in $S$ with $x_{n} →x ∈X$. Then $(x_{n})$ is a Cauchy sequence in $X$ and hence is a Cauchy sequence in $S$. Since $S$ is complete, $x_{n} → \tilde{x}$ for some $\tilde{x}\in S$. By uniqueness of limit, we have $x=\tilde{x}$ and thus $x ∈ S$ . This shows that $S$ is closed by [[Sequence and Convergence#^7f5b74|corollary]]. Conversely, let $(x_{n})$ be a Cauchy sequence in $(S,d)$. Then $(x_{n})$ is also a Cauchy sequence in $(X,d)$. Since $(X,d)$ is complete, $x_{n} → x$ for some $x ∈ X$. Since $S$ is closed, $x ∈ S$. Therefore $(S,d)$ is complete. $\square$

>[!theorem]
>Every metric space $(X,d)$ has a completion, i.e. there exists a complete metric space $(\tilde{X},\tilde{d})$ and an injection $f \colon X → \tilde{X}$ such that $$d(x,y)=d(f(x),f(y)),\quad \forall x,y\in X$$and $\overline{f(X)}=\tilde{X}$.

## Contraction

>[!definition] Fixed Point
Let $(X,d)$ be a metric space and $f \colon X →X$ a map. A point $x ∈X$ is called a fixed point of $f$ if $f(x)=x$.

>[!definition] Contraction
Let $(X,d)$ be a metric space and $f \colon X →X$ a map. $f$ is called a contraction if there exists $q ∈ (0, 1)$ such that $$d(f(x),f(y))\leq qd(x,y),\quad\forall x,y\in X$$where $q$ is called the contraction rate of $f$.

>[!theorem] Contraction Mapping Theorem
Let $(X,d)$ be a complete metric space. If $f \colon X → X$ is a contraction, then it has a unique fixed point.