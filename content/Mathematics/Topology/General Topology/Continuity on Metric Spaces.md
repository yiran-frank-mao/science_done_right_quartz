---
updated: 2025-09-07
---
## Limit and Continuity

>[!definition] Limit
>Let $(X,d_{X})$ and $(Y,d_{Y})$ be metric spaces and let $f : X \to Y$ be a function. For $p\in X$, we say that $\lim_{x\to p}f(x)=y\in Y$ if for every $\epsilon>0$ there exists $\delta>0$ such that $$0<d_{X}(x,p)<\delta \implies d_{Y}(f(x),y)<\epsilon.$$

>[!definition] Continuity
>Let $(X,d_X)$ and $(Y,d_Y)$ be [[Metric Spaces#^0eacc7|metric spaces]] and let $f : X \to Y$ be a function. Then $f$ is
>- continuous at $p \in X$ if $\lim_{x\to p}f(x)=f(p)$.
>- continuous on $X$ if it is continuous at every point of $X$.
>$\quad$ ^d3351a

>[!definition] 
>**Def**  <i><u>Neighbourhood</u></i>
>Let $(X,d)$ be a metric space and $a ∈ X$. A set $U ⊂ X$ is called a neighborhood of $a$ if there is an open ball $B_{r}(a)$ with $B_{r}(a)⊂U$.

>[!theorem] 
>**Thrm**  Let $(X,d)$ and $(Y,ρ)$ be metric spaces, let $f \colon X →Y$ be a function, and let $a ∈ X$. The following statements are equivalent:
>- $f$ is continuous at $a$.
>- For any sequence $(x_{n})$ in $X$ with $x_{n} → a$ there holds $f (x_{n}) → f (a)$.
>- For any neighborhood $U$ of $f (a)$, $f^{ −1}(U)$ is a neighborhood of $a$.
>
>**Proof**

>[!theorem] 
>**Thrm**  Let $(X,d)$ and $(Y,ρ)$ be metric spaces and let $f \colon X →Y$ be a function. The following are equivalent:
>- $f$ is continuous on $X$.
>- For every open set $O$ in $Y$, $f^{−1}(O)$ is open in $X$.
>- For every closed set $C$ in $Y$, $f^{−1}(C)$ is closed in $X$.
>$\quad$

>[!theorem] 
>**Thrm**  Let $(X,d)$ be a metric space.
>1. If $f,g:X\to\R$ are continuous then $f+g$ and $fg$ are continuous and $f/g$ is continuous at all points $x$ where $g(x) \neq 0$.
>2. If $(Y,\|\cdot\|$) is a [[Normed Spaces#^345fd3|normed vector space]] and $f,g : X \to Y$ are continuous then $f +g$ is continuous.
>$\quad$

>[!theorem] 
>**Thrm**  Let $X,Y,Z$ be metric spaces. If $f \colon X →Y$ is continuous at $a$ and $g \colon Y →Z$ is continuous at $f (a)$, then $g \circ f$ is continuous at $a$.
>**Proof**  Let $(x_{n})$ be any sequence with $x_{n} → a$. By the continuity of $f$ at $a$, we have $f (x_{n}) → f (a)$. Next, by the continuity of $g$ at $f (a)$ we have $$(g\circ f)(x_n)=g(f(x_n))\to g(f(a))=(g\circ f)(a)$$Therefore $g\circ f$ is continuous at $a$.

>[!theorem] 
> Let $(X,d)$ and $(Y,ρ)$ be metric spaces and let $f \colon X →Y$ be continuous. If $K ⊂ X$ is compact, then $f (K )$ is [[Compactness of Topological Space#^da2511|compact]] in $Y$ ^3a05b1

>[!theorem] 
> Let $(X,d)$ be a metric space and let $f \colon X → \R$ be a continuous function. If $K ⊂ X$ is compact, then $f$ is bounded above and below and achieves its maximum and minimum values on $K$.

## Uniform Continuity

>[!definition] Uniform Continuity
>Let $(X,d)$ and $(Y,ρ)$ be metric spaces and $A⊂X$. A function $f \colon X →Y$ is called uniformly continuous on $A$ if for any $ε > 0$, there is a $δ > 0$ such that for any $x,x^{\prime} ∈ A$ with $d(x,x^{\prime}) < δ$: $$\rho(f(x),f(x^{\prime}))<\varepsilon $$^9947a1

>[!theorem] Heine-Cantor Theorem
> Let $(X,d)$ and $(Y,ρ)$ be metric spaces. If $f \colon X →Y$ is continuous and $K ⊂X$ is compact, then $f$ is uniformly continuous on $K$. ^d7d908

## Lipschitz Continuity

>[!definition] Lipschitz Continuity
>A function $f : X \to Y$ is Lipschitz continuous or just Lipschitz if there exists $C\geq0$ such that $$d_Y(f(x),f(y))\leq Cd_X(x,y)\quad\text{ for all } x,y\in X$$ We say that $C$ is a Lipschitz constant for $f$.

<b><u>e.g.</u></b>  
- Let $(X,d)$ be a metric space. Suppose $A\subset X$ is non-empty. Then we can define the distance of $x$ from $A$ by setting $d(x,A)=\inf_{z\in A}d(x,z)$. Then the function $x \mapsto d(x,A)$ is Lipschitz with Lipschitz constant $1$. For all $x,y\in X$ we have $$d(x,A)\leq d(x,z)\leq d(x,y)+d(y,z)\leq d(x,y)+d(y,A)$$ Hence $d(x,A)-d(y,A)\leq d(x,y)$. Similarly, $d(y,A)-d(x,A)\leq d(x,y)$. Thus $$d_{\R}(d(x,A),d(y,A))=|d(x,A)-d(y,A)|\leq d(x,y).$$
- Lipschitz continuity is strictly stronger than the other two, even if the domain is compact. Consider $f(x)=\sqrt{x}$ on $[0,1]$. Then $f$ is continuous and uniformly continuous on $[0,1]$, but it is not Lipschitz. One way to see that is to consider $$\frac{|f(1/n^{2})-f(0)|}{|1/n^{2}-0|}=\frac{1/n}{1/n^{2}}=n$$for some positive integer $n$. It can be arbitrarily large, so $f$ cannot be Lipschitz.
- In one-dimensional real analysis, a classical result is that if $f\colon [a,b]\to \R$ is differentiable with bounded derivative, then $f$ is continuous. This is easy to see by the [[Differentiation of Real Functions#^1a7318|mean value theorem]].
$\quad$

>[!proposition] 
> A Lipschitz continuous function is continuous.

*Proof*  Suppose $f:X\to Y$ is Lipschitz. Then for all $p\in X$ and $\epsilon>0$, let $\delta=\frac{\epsilon}{C}$, then $$d_{X}(x,p)<\delta=\frac{\epsilon}{C} \implies d_{Y}(f(x),f(p))<C\cdot\frac{\epsilon}{C}=\epsilon$$$\square$

## Topologically Equivalent Metrics

>[!lemma] 
>**Lemma**  Suppose that $d_{1}$ and $d_{2}$ are two metrics on $X$. Then the following statements are equivalent:
>- Every set that is open in $(X, d_{2})$ is open in $(X, d_{1})$
>- For any metric space $(Y, d_{Y})$, if $g : X \to Y$ is continuous from $(X, d_{2})$ to $(Y, d_{Y})$ then $g$ is continuous from $(X, d_1)$ to $(Y, d_Y)$
>- For any metric space $(Y, d_{Y})$, if $f : Y \to X$ is continuous from $(Y, d_{Y})$ to $(X, d_1)$ then $f$ is continuous from $(Y, d_Y)$ into $(X, d_2)$.
>$\quad$

>[!theorem] 
> Suppose that $d_{1}$ and $d_2$ are two metrics on $X$. Then the following statements are equivalent:
>- The open sets in $(X, d_{1})$ and $(X, d_{2})$ coincide
>- For any metric space $(Y, d_Y)$, a function $g : X \to Y$ is continuous from $(X, d_1)$ into $(Y, d_Y)$ if and only if $g$ is continuous from $(X, d_2)$ into $(Y, d_Y)$
>- For any metric space $(Y, d_{Y})$, a function $f : Y \to X$ is continuous from $(Y, d_Y)$ into $(X, d_1)$ if and only if $f$ is continuous from $(Y, d_Y)$ into $(X, d_2)$.
>$\quad$

>[!definition] Topologically Equivalence
>Two metrics $d_{1}$ and $d_{2}$ on $X$ are called topologically equivalent, or just equivalent, if the open sets in $(X, d_1)$ and $(X, d_2)$ coincide.

>[!definition] Lipschitz Equivalence
>Two metrics $d_1$ and $d_2$ on $X$ are called *Lipschitz equivalent* if there exist $0 < c \leq C < 1$ such that $$ cd_1(x,y)\leq d_2(x,y)\leq Cd_1(x,y)\quad\text{ for all } x,y\in X$$

**Lemma**  Let $d_1$ and $d_2$ be two metrics on $X$ that are Lipschitz equivalent on $X$. Then $d_1$ and $d_2$ are topologically equivalent.
**Corollary**  The metrics induced by equivalent norms are topologically equivalent.

**Lemma**  If $X$ is a vector space and two norms $\|\cdot \|_1$ and $\|\cdot \|_2$ on $X$ induce topologically equivalent metrics then the norms are equivalent.

