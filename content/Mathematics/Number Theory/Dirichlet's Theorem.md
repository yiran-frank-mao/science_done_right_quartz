---
created: 2024-01-30
updated: 2024-10-03
---
**Def**  <i><u>Dirichlet L-function</u></i>
The Dirichlet $L$-function is of the form: $$L(s,\chi)=\sum\limits_{n=1}^\infty\frac{\chi(n)}{n^{s}}$$where $\chi$ is a Dirichlet character and $s$ a complex variable with real part greater than $1$.

**Lemma**  Fix $(a,q)=1$. If $L(1,\chi)\neq0$, then $$\lim_{s\to1^+}{(s-1)\prod_{\chi\mod q}L(s,\chi)^{\overline{\chi(a)}}}\neq0$$**Proof**

**Lemma**  Suppose $s>1$, then we have $$\sum\limits_{\chi\mod q}\overline{\chi(a)}\log L(s,\chi)=\varphi(q)\sum_{n\geq1}\sum_{p^{n}\equiv a \mod q}\frac{1}{np^{ns}}$$**Proof**  

> [!theorem] Dirichlet's Theorem
> For coprime positive integers $(a,q)=1$, there are infinitely many primes that are congruent to $a$ modulo $q$.

*Proof*  
