**Def**  <i><u>Continuity</u></i>
A function $f\colon X \to Y$ on $\R$ is continuous at $x_0$ if for every $\{a_{n}\} \subset X$ such that $a_{n} \to x_0$, we have $f(a_{n}) \to f(x_0)$. Equivalently, it is continuous at $x_0$ if for all $\varepsilon>0$ there exists $\delta>0$ such that if $|x-x_{0}|<\delta$ then $|f(x)-f(x_{0})|<\varepsilon$. We say $f$ is continuous on $X$ if it is continuous at every $x_0 \in X$.
<u><b>e.g.</b></u>  Polynomial functions are continuous on $\R$.

## Continuous Functions Theorems

> [!theorem]
> If $f\colon [a,b]\to \R$ is continuous, then $f$ is bounded, and both maximum and minimum exist.

> [!theorem] Intermediate Value Theorem
> If $f\colon [a,b]\to \R$ is continuous, then for any $\min(f(a),f(b))\leq y \leq\max (f(a),f(b))$, there exists $c\in (a,b)$ such that $f(c)=y$.

**Proof**  Without loss of generality, assume $f(a)<f(b)$. Let $A = \{x\in [a,b]:f(x)\leq \gamma\}$. As $A\subset[a,b]$, $A$ is bounded. Let $M= \sup (A)$. By lemma, there exists a sequence $\{a_{n}\} \subset A$ such that $a_{n} \to M$. As for all $n$, $f(a_{n})\leq \gamma$, we have $f(M)\leq \gamma$. So $M\in A$. Now because 