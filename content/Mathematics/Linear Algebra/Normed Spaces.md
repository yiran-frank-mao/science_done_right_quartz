---
created: 2023-12-07
updated: 2024-09-17
---
## Norm

>[!definition] Norm
>A norm on a [[Vector Spaces#^f4b63e|vector space]] $X$ is a map $\newcommand{\R}{\mathbb{R}}\|\cdot\|: X \to \R$ such that
>1. $\|x\|=0$ if and only if $x=0$.
>2. $\|\lambda x\|=|\lambda|\|x\|$ for every $\lambda\in \mathbb{C}$ and $x\in X$, we call this homogeneity .
>3. $\|x+y\| \leq \|x\|+\|y\|$ for every $x,y\in X$, we call this triangle inequality.
>
> If $X$ is a [[Vector Spaces#^f4b63e|vector space]] and $\|\cdot\|$ is a norm on $X$, then the pair $(X, \|\cdot\|)$ is called a normed space. ^345fd3

<u><b>e.g.</b></u>  We define $C[a,b]$ the [[Vector Spaces#^f4b63e|vector space]] of real-valued continuous functions on the interval $[a,b]$. The standard norm to use on $C[a,b]$ is the supremum norm: $$\newcommand{\dd}{\:\mathrm{d}}\|f\|_{\infty}=\sup_{x\in[a,b]}|f(x)|.$$ Another family of norms are defined on $C[a, b]$ using an integral: for $p \in[1, \infty)$ set $$\|f\|_{p}=\left( \int_{a}^{b}|f(x)|^{p} \dd x \right)^{1/p}$$And we can also define the inner product: $$\langle f, g \rangle = \int_{a}^{b}f(x)g(x)\dd x$$

> [!proposition]
> $\|x\|\geq 0$ for all $x\in X$ for norm $\|\cdot\|$.

> [!proposition]
> If $(X, \|\cdot\|)$ is a normed space and $Y$ is a subspace of $X$, then $(Y, \|\cdot\|)$ is also a normed space.

>[!definition] 
>**Def**  <i><u>Euclidean Norm</u></i>
>For $x ∈ \R^n$, we define the Euclidean ($L_{2}$) norm as $$\|x\|_2=\sqrt{x_1^2+\cdots+x_n^2}=\sqrt{\tr{x}x}$$

>[!definition] $L_p$ Norm
>The $L_p$ norm of $x\in\R^n$ is defined as $$\|x\|_p=\sqrt[p]{x_1^p+\cdots+x_n^p}$$Specifically, we have $\|x\|_1=|x_1|+|x_2|+\dots+|x_n|$ and $\|x\|_\infty=\max_i|x_i|$. Specially, we define the $L_0$ norm as the number of non-zero elements in a vector, and $L_{\infty}$ as $$\|x\|_{\infty}=\max\{|x_1|,\cdots,|x_n|\}$$

>[!theorem] Minkowski’s Inequality
>In $\R^n$, for all $1\leq p\leq \infty$, if $x,y\in \R^n$ then $$\sqrt[p]{(x_{1}+y_1)^{p}+\cdots+(x_{n}+y_n)^{p}} \leq \sqrt[p]{x_1^p+\cdots+x_n^p}+\sqrt[p]{y_1^p+\cdots+y_n^p}$$

## Sets from Norms

**Def**  <i><u>Closed Unit Ball</u></i>
The closed unit ball in a normed space $(X, \|\cdot\|)$ is the set $$\mathfrak{B}_{X}=\{x\in X \mid \|x\|\leq 1\}$$

**Lemma**  In any normed space $(X, \|\cdot \|)$, the closed unit ball $\mathfrak{B}_X$ is [[Convex Sets#^3a9d82|convex]].
**Proof**  For all $x,y \in X$, we have$$
\|\lambda x + (1-\lambda )y\|\leq |\lambda|\|x\|+|1-\lambda|\|y\|\leq \lambda + (1-\lambda)=1
$$ Hence $\lambda x + (1-\lambda )y \in \mathfrak{B}_X$.

**Lemma**  Suppose a function $N:X \to \R^+$ satisfies first and second properties of the definition of a norm and the set $\mathfrak{B}=\{x\in X \mid N(x)\leq 1\}$ is [[Convex Sets#^3a9d82|convex]] then $N$ satisfies the triangle inequality:$$
N(x+y) \leq N(x) + N(y)
$$ and so defines a norm on $X$.
**Proof**  Clearly if $x=0$ then we have $N(x+y)=N(y)+0=N(y)+N(x)$, satisfies the triangle inequality. So we can assume that $N(x)>0$ and $N(y)>0$. As $\mathcal{B}$ is [[Convex Sets#^3a9d82|convex]], we have$$\frac{N(x)}{N(x)+N(y)}\left(\frac x{N(x)}\right)+\frac{N(y)}{N(x)+N(y)}\left(\frac y{N(y)}\right)\in\mathfrak{B}$$ So $\frac{x+y}{N(x)+N(y)}\in\mathfrak{B}$, it follows that $$
N\left( \frac{x+y}{N(x)+N(y)} \right) \leq 1
$$ Hence by property of function $N$: $$N\left( \frac{x+y}{N(x)+N(y)} \right)=\frac{N(x+y)}{N(x)+N(y)} \leq 1 \implies N(x+y)\leq N(x)+N(y)$$
## Equivalence Relation of Norms

> [!definition] Comparable Norms
> Two norms $\|\cdot\|_1$ and $\|\cdot\|_2$ on vector space $X$ are comparable or equivalent if there exists constants $0\leq c_{1}\leq c_2$ such that $$c_1\|x\|_1\leq\|x\|_{2}\leq c_2\|x\|_1\quad\text{for all }x\in X$$ It is easy to check that this is an [[Relations and Functions#^14741d|equivalence relation]].

> [!proposition]
> Two norms are equivalent if and only there exist constants $0\leq c_{1}\leq c_2$ such that $$c_1\mathfrak{B}_{(X,\|\cdot\|_2)}\subset\mathfrak{B}_{(X,\|\cdot\|_1)}\subset c_2\mathfrak{B}_{(X,\|\cdot\|_2)}$$ where $\mathfrak{B}_{(X,\|\cdot\|_j)}$ is the closed unit ball in $(X, \|\cdot\|_j)$ with $j=1,2$.