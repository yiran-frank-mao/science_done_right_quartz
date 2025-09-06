---
created: 2023-12-08
updated: 2024-09-17
---
## Convergent Sequence

**Def**  <i><u>Sequence</u></i>
Let $\require{mhchem}\newcommand{\R}{\mathbb{R}}\newcommand{\N}{\mathbb{N}}\newcommand{\S}{\mathbb{S}}\newcommand{\Z}{\mathbb{Z}}\newcommand{\C}{\mathbb{C}}\newcommand{\E}{\mathbb{E}}\newcommand{\Q}{\mathbb{Q}} X$ be a set. A sequence in $X$ is a [[Relations and Functions#^862dba|function]] $f \colon \N\to X$. We usually write $x_{n} = f (n)$ and write the sequence as $(x_{n})$ or $(x_{n})_{n=1}^{\infty}$ or $(x_{n})_{n\in\N}$.

> [!definition] Subsequence
> If $(x_n )$ is a sequence, a subsequence of $(x_n )$ is a sequence $(x_{k_{n}} )$, where $(k_{n} )$ is a strictly increasing sequence in $\N$.

**Def**  <i><u>Convergence</u></i>
A sequence $(x_{n})_{n=1}^{\infty}$ in metric space $(X,d)$ converges to $x \in X$ if $$\lim_{n\to\infty}d(x_{n},x)=0$$ In terms of open balls, this can be phrased as for every $\epsilon>0$, exists $N\geq1$ such that $$
x_n\in B(x,\epsilon),\quad\text{ for all }n\geq N $$
**Lemma**  A sequence in a [[Metric Spaces#^0eacc7|metric space]] can have at most one limit. ^f71e2a

**Def**  <i><u>Bounded Sequence</u></i>
Let $(X,d)$ be a metric space. A sequence $(x_{n})$ in $X$ is called bounded if the subset $\{x_n\}$ of $X$ consisting of all elements from $(x_{n})$ is bounded, i.e. there exist $\bar{x} ∈ X$ and $R >0$ such that $x_{n} ∈B_R(\bar{x})$ for all $n$.

**Thrm**  In metric spaces convergent sequences must be bounded.
**Proof**  Assume $x_{n} \to x$. Then there exists $N$ such that $d(x_n,x)<1$ for all $n>N$. Let $R=\max\{d(x_1,x),\cdots,d(x_N,x),1\}$. Then $d(x_{n}, x)<R$ for all $n$ and hence $x_{n} ∈ B_{R+1}(x)$ for all $n$. The boundedness of $(x_n)$ thus follows.

**Thrm**  In any metric space $(X,d)$ we have $$x_{n}\to x, y_{n}\to y \implies d(x_{n},y_{n})\to d(x,y)$$**Proof**  

**Thrm**  Let $(X,\|\cdot\|)$ be a [[Normed Spaces#^345fd3|normed vector space]] on $\R$. If $x_n →x$ and $y_n →y$ in $X$ and $α_n → α$ in $\R$, then $$x_n+y_n\to x+y,\quad\alpha_nx_n\to\alpha x$$

**Thrm**  Let $(X,⟨·,·⟩)$ be an inner product space. If $x_{n} \to x$ and $y_{n} \to y$, then $⟨x_n,y_n⟩ \to ⟨x,y⟩$.
**Proof**  We have $$\begin{aligned}\langle x_n,y_n\rangle-\langle x,y\rangle&=\langle x_n,y_n\rangle-\langle x,y_n\rangle+\langle x,y_n\rangle-\langle x,y\rangle\\&=\langle x_n-x,y_n\rangle+\langle x,y_n-y\rangle\end{aligned}$$Therefore, by the Cauchy-Schwarz inequality, we have $$|\langle x_n,y_n\rangle-\langle x,y\rangle|\leq\|x_n-x\|\|y_n\|+\|x\|\|y_n-y\|\to0$$because $x_{n} \to x$, $y_{n} \to y$ and $(y_n)$ is bounded.

## Convergence and Closeness 

**Thrm**  Let $(x_{n})_{n=1}^{\infty}$ be a sequence in a metric space $(X,d)$. We have $x_{n} \to x$, as $n \to \infty$ if and only if for every [[Open and Closed Sets#^e112b1|open set]] $U$ containing $x$ there is an $N\geq1$ such that $x_{n} \in U$ for all $n\geq N$.
**Proof**  

**Thrm**  Let $(X,d)$ be a metric space and $A⊂X$. Then $$x\in \overline{A} \iff \exists(x_{n})\in A^{\infty}\text{ s.t. } x_{n}\to x$$**Proof**  We have $$\begin{aligned}x\in\overline{A}&\Longrightarrow B_{1/n}(x)\cap A\neq\emptyset\text{ for all }n\in\mathbb{N}\\&\Longrightarrow\exists x_n\in B_{1/n}(x)\cap A\text{ for all }n\\&\Longrightarrow\exists(x_n)\subset A\text{ with }d(x_{n},x)<1/n\\&\Longrightarrow\exists(x_{n})\subset{A}\text{ such that }x_n\to x\end{aligned}$$Thus proved the proposition. ^527a6d

**Corollary**  Let $(X,d)$ be a metric space and $A ⊂ X$. Then $A$ is closed iff the limit of every convergent sequence in $A$ is still in $A$.
**Proof**  Assume $A$ is closed. If $(x_{n})$ is a sequence in $A$ with $x_n \to x$, then we have $x ∈A$. Since $A$ is closed, $A=\overline{A}$ and hence $x ∈A$. Conversely, assume every convergent sequence in $A$ has its limit in $A$. If $x ∈ A$, by [[Sequence and Convergence#^527a6d|theorem]] there is a sequence $(x_{n})$ in $A$ such that $x_n \to x$. Thus $x ∈ A$ by the given assumption. This means that $\overline{A} ⊂ A$ and hence $A = \overline{A}$. That is $A$ is closed. ^7f5b74

**Thrm**  Every sequence in $\R$ has a monotone subsequence.
**Proof**  Let $(x_{n})$ be a sequence in $\R$. Let $S=\{n\in\mathbb{N}:x_n\geq x_k\text{ for all }k\geq n\}$. Then Then $S$ is a subset of $\N$ which can be finite or infinite. If $S$ is infinite, say $S=\{n_1,n_2,\cdots\}$, then $(x_{n_j} )$ is a subsequence of $(x_n)$ that is decreasing. If $S$ is finite, there is $N$ such that $n\notin S$ for any $n>N$. Take $n_{1} >N$. Since $n_{1} \notin S$, there is $n_{2} >n_{1}$ such that xn1 <xn2. Since n2 ̸∈S, there is n3 >n2 such that xn2 < xn3 . By repeating this procedure, we can obtain a subsequence (xnj ) of (xn) that is strictly increasing.

**Thrm**  <i><u>Bolzano-Weierstrass Theorem</u></i>
Every bounded sequence in $\R^{k}$ has a convergent subsequence. ^75364e