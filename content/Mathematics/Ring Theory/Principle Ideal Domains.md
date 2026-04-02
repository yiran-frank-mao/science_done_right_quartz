> [!definition] Principal Ideal Domain
> A [[Ring, Field and Integral Domain#^domain|integral domain]] $R$ is called a principal ideal domain if every [[Homomorphisms and Ideals#^395472|ideal]] is principal. ^74559c

For example, both $\Z$ and the ring of polynomials $F[x]$ over a field $F$ are PIDs:

> [!proposition]
> $\Z$ is a principal ideal domain.

*Proof*  Suppose $I\triangleleft\Z$ is a non trivial ideal. There exists at least one positive integer in it. Pick the smallest positive integer $n\in I$. We claim $I=(n)$. For any $m\in I$, by the remainder theorem, we have $m=qn+r$ for some $q,r\in\Z$ with $0\leq r<n$. Since $n,m\in I$, it follows that $r=m-qn\in I$. As $n$ is the smallest positive integer in $I$, we must have $r=0$. Therefore $m=qn\in (n)$. $\square$  ^9b5851

> [!remark]
> Indeed, any Euclidean domain is a principle ideal domain. (See [[Factorization#^5f7518|proposition]].)

> [!proposition]
> Every field is a principal ideal domain.
> 

*Proof*  Let $I\triangleleft F$ be an ideal. If $I$ is non-trivial, then it contains a non-zero element $a$. Since $F$ is a field, $a$ is a unit, and thus $I=F$. So any field only has two trivial ideals: $\{0\}$ and $F$. $\square$

> [!proposition]
> $F[x]$ is a principal ideal domain for any field $F$.

*Proof*  

> [!algorithm] Euclidean Algorithm
> The gcd of polynomials $f,g ∈ F[x]$, and the linear combination that gives it can be found by the following algorithm. Compute $$ g=q_1f+r_1,~f=q_2r_1+r_2,~\cdots,~r_{n-3}=q_{n-1}r_{n-2}+r_{n-1},~r_{n-2}=q_nr_{n-1}+r_n,~r_{n-1}=q_{n+1}r_n. $$Then up to a unit $r_n$ is the gcd and backward substitution gives the linear combination.

> [!proposition]
> In an integral domain every [[Factorization#^d98fbf|prime]] is [[Factorization#^d98fbf|irreducible]].

*Proof*  Suppose $p$ is a prime with $p=ab$. Then $p\mid ab$ implies $p\mid a$ or $p\mid b$. Without loss of generality, suppose $p\mid a$. By the equation, $a\mid p$ as well, so $a$ and $p$ are associates, thus $b$ is a unit. $\square$

> [!definition] Nilpotent
> Let $R$ be a ring. $x\in R$ is nilpotent if there is $n∈\N$ such that $x^n =0$.

**Def** _Idempotent_
Let $R$ be a ring. $x\in R$ is idempotent if $x^2=x$.

> [!proposition]
> If $x ∈ R$ is nilpotent then $1 + x$ is invertible.

Recall the fundamental theorem of arithmetic:

![[Division and Prime#^ff714c|theorem]]

Similarly for polynomials:

> [!theorem]
> Let $F$ be a field. Every non-constant polynomial in $F[x]$ can be written uniquely (up to reordering) as $$ f=up_1^{e_1}\dots p_r^{e_r} $$for a unit $u\in F^{\times}$ and $r\in\N$, $p_i\in F[x]$ monic irreducible and $e_i\in \N$.

Both theorems are in fact one theorem:

> [!theorem] Unique Factorization in A PID
> Every principle ideal domain is a unique factorization domain.