---
created: 2025-09-15
updated: 2025-09-15
tags:
  - functional-analysis
  - banach-spaces
  - hahn-banach-theorem
completed: false
---
## The Dual of a Normed Space

> [!proposition]
> If $X$ is a normed vector space over $\newcommand{\R}{\mathbb{R}}\R$ or $\newcommand{\C}{\mathbb{C}}\C$, then its dual space $X^*$ is a Banach space.

*Proof*  Let $X$ be a normed vector space.  The dual space $X^*$ is the space of all bounded linear functionals on $X$, equipped with the **operator norm**:
$$ \|f\|_{X^*} := \sup_{x \in X, \|x\|=1} |f(x)| $$
To show that $X^*$ is a Banach space, we need to prove it is **complete**.  Let $(f_n)_{n \in \mathbb{N}}$ be a **Cauchy sequence** in $X^*$.  This means that for every $\epsilon > 0$, there exists an $N \in \mathbb{N}$ such that for all $n, m \ge N$, we have:
$$ \|f_n - f_m\|_{X^*} < \epsilon $$
By the definition of the operator norm, this implies that for any $x \in X$ with $\|x\|=1$:
$$ |f_n(x) - f_m(x)| = |(f_n - f_m)(x)| \le \|f_n - f_m\|_{X^*} \|x\| < \epsilon $$
This shows that for each fixed $x \in X$, the sequence of scalars $(f_n(x))_{n \in \mathbb{N}}$ is a Cauchy sequence in $\R$ or $\C$.  Since $\R$ and $\C$ are complete, this sequence converges. We can therefore define a function $f: X \to \R$ (or $\C$) by the **pointwise limit**:
$$ f(x) := \lim_{n \to \infty} f_n(x) $$
The function $f$ is **linear** because each $f_n$ is linear.  We must now show two things:
1.  $f$ is bounded (i.e., $f \in X^*$)
2.  $f_n \to f$ in the norm of $X^*$

First, let's show $f_n \to f$ in $X^*$. From the inequality $|f_n(x) - f_m(x)| < \epsilon$ for $n,m \ge N$ and $\|x\|=1$, we can take the limit as $m \to \infty$:
$$ |f_n(x) - f(x)| = \lim_{m \to \infty} |f_n(x) - f_m(x)| \le \epsilon $$
This holds for all $n \ge N$ and for all $x \in X$ with $\|x\|=1$.  Taking the supremum over all such $x$ gives:
$$ \|f_n - f\|_{X^*} = \sup_{\|x\|=1} |f_n(x) - f(x)| \le \epsilon \quad \forall n \ge N $$
This is precisely the definition of convergence of $f_n$ to $f$ in the norm of $X^*$.

Second, we need to verify that our limit function $f$ is actually in $X^*$.  We know $f$ is linear; we just need to show it is bounded. We use the triangle inequality for any $n \ge N$:
$$ \|f\|_{X^*} \le \|f - f_n\|_{X^*} + \|f_n\|_{X^*} $$
From our previous step, we know $\|f - f_n\|_{X^*} \le \epsilon$. For instance, we can take $\epsilon = 1$.  Since $f_N$ is in $X^*$, its norm $\|f_N\|_{X^*}$ is finite. Therefore:
$$ \|f\|_{X^*} \le \epsilon + \|f_N\|_{X^*} < \infty $$
This shows that $f$ is a bounded linear functional, so $f \in X^*$.
Since every Cauchy sequence in $X^*$ converges to an element in $X^*$, the space is complete and is therefore a Banach space.  $\square$

## The Hahn-Banach Theorem

> [!theorem] Hahn-Banach Theorem (Real Vector Spaces)
> Let $X$ be a vector space over $\R$, $Y$ be a vector subspace of $X$. Suppose $p\colon X \to \R$ is a *sublinear functional*, meaning it satisfies:
> 1.  **Positive homogeneity**: $p(\lambda x) = \lambda p(x)$ for all $x \in X$ and $\lambda > 0$.
> 2.  **Subadditivity**: $p(x+y) \leq p(x) + p(y)$ for all $x,y \in X$.
> 
> If $L\colon Y \to \R$ is a linear functional that is dominated by $p$ on $Y$, i.e., $L(y) \le p(y)$ for all $y\in Y$, then there exists a linear extension $l\colon X \to \R$ of $L$ such that:
> 1.  $l(y) = L(y)$ for all $y \in Y$ ($l$ is an extension).
> 2.  $l(x) \le p(x)$ for all $x \in X$ (the extension is also dominated by $p$).
> $\quad$ ^d7e9d9

> [!remark]+
> In the setup of the theorem:
> - $X$ is a vector space, not necessarily normed or complete.
> - $Y$ is a subspace, not necessarily closed.
> - A typical example of a sublinear functional is $p(x) = C\|x\|$ for some constant $C$.
> $\quad$

> [!corollary]
> Let $Y$ be a subspace of a [[Normed Spaces#^345fd3|normed vector space]] $X$ over $\R$.  Every bounded linear functional $L \in B(Y,\R)$ can be extended to a bounded linear functional $l \in B(X,\R)$ such that the extension has the same norm:
> $$ \|l\|_{B(X,\R)} = \|L\|_{B(Y,\R)}. $$

*Proof*  Let us denote $X':=B(X,\R)$ and $Y':=B(Y,\R)$.  Let $L \in Y'$. We define a function $p: X \to \R$ by $p(x) = \|L\|_{Y'} \|x\|_X$.  This function $p$ is sublinear, as it is positively homogeneous and satisfies the triangle inequality.
For any $y \in Y$, we have $L(y) \le |L(y)| \le \|L\|_{Y'} \|y\|_Y = p(y)$.
The conditions for the Hahn-Banach theorem are met. Therefore, there exists a linear extension $l: X \to \R$ of $L$ such that $l(x) \le p(x)$ for all $x \in X$.  This gives us an upper bound for $l(x)$: $$ l(x) \le p(x) = \|L\|_{Y'} \|x\|_X $$For a lower bound, we consider $-x$: $$ -l(x) = l(-x) \le p(-x) = \|L\|_{Y'} \|-x\|_X = \|L\|_{Y'} \|x\|_X $$Combining these two inequalities, we get $|l(x)| \le \|L\|_{Y'} \|x\|_X$ for all $x \in X$.  This shows that $l$ is a bounded linear functional (so $l \in X'$) and that $\|l\|_{X'} \le \|L\|_{Y'}$. Since $l$ is an extension of $L$, its norm must be at least as large as the norm of $L$. That is, $$ \|l\|_{X'} = \sup_{\|x\|=1, x\in X} |l(x)| \ge \sup_{\|y\|=1, y\in Y} |l(y)| = \sup_{\|y\|=1, y\in Y} |L(y)| = \|L\|_{Y'} $$Thus, we conclude that $\|l\|_{X'} = \|L\|_{Y'}$. $\square$

> [!corollary]
> If $X$ is a normed vector space over $\R$, then for any non-zero $x_0 \in X$, there exists a functional $l \in X'$ such that:
> $$ \|l\|_{X'} = 1 \quad \text{and} \quad l(x_0) = \|x_0\|_X $$

> [!remark]
> This corollary is significant because it guarantees that the dual space $X'$ is non-trivial (if $X$ is non-trivial) and is "large enough" to separate points. It also shows that the supremum in the dual definition of the norm of an element $x_0$ (i.e., $\|x_0\| = \sup_{\|l\|=1} |l(x_0)|$) is actually **achieved**.

*Proof Sketch of the Hahn-Banach Theorem*
The full proof requires [[Order#^11e467|Zorn's Lemma]] to extend the functional from a subspace to the whole space by considering a partially ordered set of all valid extensions.  The key step, however, is to show that a functional can be extended by just one dimension.
Let $L: Y \to \R$ be the functional satisfying the theorem's hypotheses. Pick an element $x_0 \in X \setminus Y$.  We want to extend $L$ to the subspace $Y_1 = \text{span}\{Y, x_0\}$.  Any element in $Y_1$ can be uniquely written as $y + tx_0$ for $y \in Y$ and $t \in \R$.
For the extension, which we'll also call $L$, to be linear, it must have the form:
$$ L(y + tx_0) = L(y) + t \cdot L(x_0) $$
We need to define the value $L(x_0)$. Let's call this value $\gamma \in \R$.  Our task is to choose a $\gamma$ such that the extension condition $L(y + tx_0) \le p(y + tx_0)$ holds for all $y \in Y, t \in \R$.

By considering cases for $t>0$ and $t<0$ and rearranging, we find that $\gamma$ must satisfy for all $y, z \in Y$:
$$ L(z) - p(z-x_0) \le \gamma \le p(y+x_0) - L(y) $$
Such a $\gamma$ exists if and only if the supremum of the left side is less than or equal to the infimum of the right side.  This is equivalent to showing that for all $y, z \in Y$:
$$ L(z) - p(z-x_0) \le p(y+x_0) - L(y) \iff L(y+z) \le p(y+x_0) + p(z-x_0) $$
We know that $y+z \in Y$, so $L(y+z) \le p(y+z)$.  Also, by the subadditivity of $p$:
$$ p(y+z) = p((y+x_0) + (z-x_0)) \le p(y+x_0) + p(z-x_0) $$
Putting these together:
$$ L(y+z) \le p(y+z) \le p(y+x_0) + p(z-x_0) $$
The inequality holds, so a valid choice for $\gamma$ exists.  This completes the one-step extension. Zorn's Lemma is then invoked to show this process can be continued to cover the entire space $X$. $\square$
