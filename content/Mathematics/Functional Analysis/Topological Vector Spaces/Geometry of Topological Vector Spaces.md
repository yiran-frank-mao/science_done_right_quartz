## Seperation


## Balanced and Absorbing Sets

> [!definition] Balanced Set
> A set $B$ in a real or complex vector space $X$ is called *balanced* if for every $x\in B$ and every scalar $\lambda$ with $|\lambda|\leq 1$, we have $\lambda x\in B$.
> 

> [!proposition]
> Suppose $B$ is a balanced set. Then $\lambda_{1}B\subset \lambda_{2}B$ for all scalars $\lambda_{1}$, $\lambda_{2}$ with $|\lambda_{1}|\leq |\lambda_{2}|$.
> 

*Proof*  As $|\lambda_{1}/\lambda_{2}|=|\lambda_{1}|/|\lambda_{2}|$, for any $\lambda_{1}x\in \lambda_{1}B$, we have $$\frac{\lambda_{1}}{\lambda_{2}}x\in B \implies \lambda_{1}x\in \lambda_{2}B.$$So $\lambda_{1}B\subset \lambda_{2}B$.  $\square$

> [!definition] Absorbing Set
> A set $A$ in a real or complex vector space $X$ is called *absorbing* if for every $x\in X$, there exists a $\lambda>0$ such that $x\in t A$ for all $|t|\geq \lambda$.
> 

It is quite easy to see that absorbing sets, balanced sets, and convex sets (containing $0$) are similar and related. However, it turns out that they are completely different, satisfying one or two of the properties does not imply the other. Here are some classical examples that can help to gain some intuition.

> [!remark]
> Every balanced set in $\mathbb{C}$ (as a complex vector space) is convex. However, this is not true in higher dimensional, nor when regarding $\mathbb{C}$ as a two-dimensional real vector space.
> 

|                                                                                                                                                                                | Real/Complex | Absorbing | Balanced | Convex |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------ | --------- | -------- | ------ |
| Open unit disk in $\R^{2}$                                                                                                                                                     |              | ✅         | ✅        | ✅      |
| Star shape: <br><img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/star_shape.svg" alt="star_shape" style="width:100%;">                   | Real         | ✅         | ✅        | 🚫     |
| Closed unit disk with a point:<br><img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/unit_disk_with_a_dot.svg" alt="" style="width:100%;"> |              | ✅         | 🚫       | 🚫     |
| $\{(z,0):\|z\|\leq 1\}\cup \{(0,w):\|w\|\le 1\}\subset\mathbb{C}^{2}$                                                                                                          | Complex      | 🚫        | ✅        | 🚫     |
| Unit cross:<br><img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/unit_cross.svg" style="width:100%;"/>                                    | Real         | 🚫        | ✅        | 🚫     |
| Unit interval in $\mathbb{C}$                                                                                                                                                  | Complex      | 🚫        | 🚫       | ✅      |
|                                                                                                                                                                                |              |           |          |        |

> [!proposition]
> Let $X$ be a [[Topological Vector Spaces#^dd5802|topological vector space]], and $V$ be an open neighborhood of $0$, then $X=\bigcup_{n=1}^{\infty}t_{n} V$ for any sequence $\{t_{n}\}$ of real numbers with $t_{n}\to \infty$. In particular, every open neighbourhood of $0$ is absorbing.
> 

*Proof*  Let $x\in X$, consider $A=\{t\in\C \mid tx\in V\}$. Note that $0\in A$. Define $f\colon \C\to X$, $t\mapsto tx$, then $f$ is continuous and $A=f^{-1}(V)$ is open. Since $(t_{n})_{n=1}^{\infty}$ diverges, there exists $N$ such that $1/t_{n} \in A$ for all $n\geq N$. Thus $x\in t_{n}V$ for all $n\geq N$. $\square$

> [!proposition]
> Let $X$ be a [[Topological Vector Spaces#^dd5802|topological vector space]], and $V$ be an open neighborhood of $0$, then $X=\bigcup_{n=1}^{\infty}t_{n} V$ for any sequence $\{t_{n}\}$ of real numbers with $t_{n}\to \infty$. In particular, every open neighbourhood of $0$ is absorbing. Every topological vector space has a basis of balanced neighborhoods.

*Proof*  It suffices to show a balanced basis at the origin. 

## Boundedness

> [!definition] Boundedness in Topological Vector Spaces
> A subset of a topological vector space $A$ is *bounded* if for all open neighbourhood $V$ of the origin, there exists a scalar $\lambda>0$ such that $A\subset tV$ for all $|t|\geq \lambda$. 

> [!lemma]
> Translation and scalar multiplication of bounded sets are bounded. More generally, if $A$ is bounded and $B$ is bounded, then $A+\lambda B$ is bounded for all scalars $\lambda$.
> 

*Proof*  It suffices to only prove the general case, and assume that $\lambda\neq 0$. Let $U$ be an open neighborhood of $0$. By continuity of addition, we can find an open neighbourhood $V$ of $0$ such that $V+V\subset U$. Since $A$ is bounded, there exists $r_{1}>0$ such that $A\subset t V$ for all $|t|>r$. Similarly, there exists $r_{2}>0$ such that $B\subset t \lambda^{-1}V$ for all $|t|>r_{2}$, that is, $\lambda B\subset t V$ for all $|t|>r_{2}$. Let $r=\max\{r_{1},r_{2}\}$, then for all $|t|>r$, we have $$A+\lambda B\subset t V+tV =t (V+V) \subset t U.$$So $A+\lambda B$ is bounded. $\square$

Form the lemma, we immediately have

> [!proposition]
> $A$ in a topological space $X$ is bounded if and only if it is bounded by neighbourhoods at the origin, thus all points in $X$.
> 

> [!proposition]
> Finite union of bounded sets is bounded.
> 

*Proof*  Suppose $I$ is some finite index set and $A$ is a bounded set. Then for any open neighbourhood $U$ of $0$, there exists a scalar $\lambda_{i}>0$ such that $A_{i}\subset tU$ for all $|t|\geq \lambda_{i}$. Let $\lambda=\max_{i\in I}\lambda_{i}$, then for all $|t|\geq \lambda$, we have $\bigcup_{i\in I} A_{i}\subset tU$. So $\bigcup_{i\in I} A_{i}$ is bounded. $\square$