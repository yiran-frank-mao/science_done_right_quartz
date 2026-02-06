---
created: 2024-04-26
updated: 2024-09-25
completed: false
---
## Pointwise convergence

> [!definition] Pointwise Convergence
> Let $S$ be a set, $(Y,ρ)$ a [[Metric Spaces#^0eacc7|metric space]], and $f \colon S →Y$ a [[Relations and Functions#^862dba|function]]. Consider a sequence of functions $(f_{n})$ from $S$ to $Y$. We say $f_{n} → f$ pointwise if for all $x ∈ S$ there holds $$ρ(f_{n}(x),f (x)) → 0 \quad \text{as}\quad n\to\infty.$$ ^6eed8e

> [!definition] Uniform Convergence
> Let $S$ be a set, $(Y,ρ)$ a [[Metric Spaces#^0eacc7|metric space]], and $f \colon S →Y$ a [[Relations and Functions#^862dba|function]]. Consider a sequence of functions $(f_{n})$ from $S$ to $Y$. We say $f_{n} \to f$ uniformly on $S$ if for any $ε >0$ there exists $N\in\N$ such that for all $n>N$ there holds $$\rho(f_n(x),f(x))<\varepsilon\quad\text{ for all }x\in S.$$Equivalently, $$\sup_{x\in S}\rho(f_{n}(x), f(x))\to 0 \quad \text{as} \quad n\to \infty.$$ ^a59a2d

> [!proposition]
>Uniform convergence implies pointwise convergence.

> [!theorem]
> Let $(X,d)$ and $(Y,ρ)$ be metric spaces, and let $f_{n} \colon X →Y$ be a sequence of continuous functions such that $f_n → f$ uniformly. Then $f$ is continuous.

**Thrm**  Let $f_{n} \colon [a, b] → \R$ be a sequence of continuous functions such that $f_{n} → f$ uniformly on $[a, b]$ for some function $f \colon [a, b] → \R$. Then $$\int_{a}^{b}f_{n}(x)\dd x\to\int_{a}^{b}f(x)\dd x$$**Proof** ^cd69c1

**Def**  <i><u>Bounded Functions</u></i>
Let $(X,d)$ and $(Y,ρ)$ be metric spaces. Then