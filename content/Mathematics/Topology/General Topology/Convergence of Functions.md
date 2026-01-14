---
created: 2024-04-26
updated: 2024-10-29
completed: false
---
## Pointwise and Uniform convergence

> [!definition] Pointwise Convergence
> Let $S$ be a set, $(Y,ρ)$ a [[Metric Spaces#^0eacc7|metric space]], and $f \colon S →Y$ a [[Relations and Functions#^862dba|function]]. Consider a sequence of functions $(f_{n})$ from $S$ to $Y$. We say $f_{n} → f$ pointwise if for all $x ∈ S$ there holds $$ρ(f_{n}(x),f (x)) → 0 \quad \text{as}\quad n\to\infty.$$ ^6eed8e

> [!definition] Uniform Convergence
> Let $S$ be a set, $(Y,ρ)$ a [[Metric Spaces#^0eacc7|metric space]], and $f \colon S →Y$ a [[Relations and Functions#^862dba|function]]. Consider a sequence of functions $(f_{n})$ from $S$ to $Y$. we say $f_{n} → f$ uniformly on $S$ if for any $ε >0$ there exists $N\in\N$ such that for all $n>N$ there holds $$\rho(f_n(x),f(x))<\varepsilon\quad\text{ for all }x\in S$$Equivalently, $$\sup_{x\in S}\rho(f_{n}(x), f(x))\to 0 \quad \text{as} \quad n\to \infty$$ ^a59a2d

> [!proposition]
>Uniform convergence implies pointwise convergence.

> [!theorem]
> Let $(X,d)$ and $(Y,ρ)$ be metric spaces, and let $f_{n} \colon X →Y$ be a sequence of continuous functions such that $f_n → f$ uniformly. Then $f$ is continuous.

> [!theorem]
> Let $f_{n} \colon [a, b] → \R$ be a sequence of continuous functions such that $f_{n} → f$ uniformly on $[a, b]$ for some function $f \colon [a, b] → \R$. Then $$\int_{a}^{b}f_{n}(x)\dd x\to\int_{a}^{b}f(x)\dd x.$$  ^cd69c1

*Proof*

**Def**  <i><u>Bounded Functions</u></i>
Let $(X,d)$ and $(Y,ρ)$ be metric spaces. Then

##  Arzela-Ascoli Theorem

>[!definition] Uniformly Equicontinuous
>Let $(X,d)$ and $(Y,ρ)$ be metric spaces. Let $\mathscr{F}$ be a set of functions from $X$ to $Y$. $\mathscr{F}$ is called uniformly equicontinuous if for any $ε > 0$ there exists $δ > 0$ such that for all $f\in\mathscr{F}$ for any $x,x^{\prime} ∈ X$ with $d(x,x^{\prime}) < δ$ there holds $$\rho(f(x),f(x^{\prime}))<\varepsilon$$

>[!proposition]
>If a set of functions from $X$ to $Y$, $\mathscr{F}$ is uniformly equicontinuous, then every $f\in \mathscr{F}$ is [[Continuity on Metric Spaces#^9947a1|uniformly continuous]].

>[!theorem] Arzela-Ascoli Theorem
>Let $(X,d)$ be a compact metric space and let $C(X,\R^{n})$ denote the set of continuous functions from $X$ to $\R^{n}$ equipped with the uniform metric. $\mathscr{F} ⊂C(X,\R^n)$ is closed, [[Open and Closed Sets#^7012df|bounded]] and uniformly equicontinuous iff $\mathscr{F}$ is compact in $C(X,\R^{n})$. ^5cb1ea

*Proof*



