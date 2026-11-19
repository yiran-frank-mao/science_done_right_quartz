In this section, we will see various kinds of ideals and their correspondence to the quotient ring. We spoil the upshot here:

| Ideal $I$                                                       | $\iff$ | Quotient Ring $R/I$                                                                  |
| --------------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------ |
| radical                                                         | $\iff$ | reduced                                                                              |
| [[Principle Ideal Domains and Various Ideals#^da4561\|prime]]   | $\iff$ | [[Mathematics/Ring Theory/Ring, Field and Integral Domain#^domain\|integral domain]] |
| [[Principle Ideal Domains and Various Ideals#^ee0592\|maximal]] | $\iff$ | [[Mathematics/Ring Theory/Ring, Field and Integral Domain#^575174\|field]]           |

Before we proceed, we introduce the notion of *principal ideal domain*.

## Principle Ideal Domains

> [!definition] Principal Ideal Domain
> An [[Ring, Field and Integral Domain#^domain|integral domain]] $R$ is called a *principal ideal domain* if every [[Ring Homomorphisms and Ideals#^395472|ideal]] is [[Ring Homomorphisms and Ideals#^027c69|principle]]. ^74559c

<u><b>e.g.</b></u>
- Every field is a principal ideal domain. In fact, let $I\triangleleft F$ be an ideal, if $I$ is non-trivial, then it contains a non-zero element $a$. Since $F$ is a field, $a$ is a unit, and thus $I=F$. So any field only has two trivial ideals: $\{0\}$ and $F$;
- $\Z$ is a PID, we will prove this in the next proposition;
- $F[x]$ is a PID for any field $F$; ^1848b4
- $F[x,y]$ for some field $F$ is not a principal ideal domain. The ideal $I=(x,y)$ is not principle;
- In $\Z[x]$, $(2,x)$ is not principle.
$\quad$

> [!proposition]
> $\Z$ is a [[Principle Ideal Domains and Various Ideals#^74559c|principal ideal domain]]. ^a3b745

*Proof*  Suppose $I\triangleleft\Z$ is a non trivial ideal. There exists at least one positive integer in it. Pick the smallest positive integer $n\in I$. We claim $I=(n)$. For any $m\in I$, by the remainder theorem, we have $m=qn+r$ for some $q,r\in\Z$ with $0\leq r<n$. Since $n,m\in I$, it follows that $r=m-qn\in I$. As $n$ is the smallest positive integer in $I$, we must have $r=0$. Therefore $m=qn\in (n)$. $\square$  ^9b5851

> [!remark]
> Indeed, any Euclidean domain is a principle ideal domain. (see [[Factorization#^5f7518|proposition]].)

> [!algorithm] Euclidean Algorithm
> The gcd of polynomials $f,g ∈ F[x]$, and the linear combination that gives it can be found by the following algorithm. Compute $$ g=q_1f+r_1,~f=q_2r_1+r_2,~\cdots,~r_{n-3}=q_{n-1}r_{n-2}+r_{n-1},~r_{n-2}=q_nr_{n-1}+r_n,~r_{n-1}=q_{n+1}r_n. $$Then up to a unit $r_n$ is the gcd and backward substitution gives the linear combination.

> [!proposition]
> In an integral domain every [[Factorization#^d98fbf|prime]] is [[Factorization#^d98fbf|irreducible]].

*Proof*  Suppose $p$ is a prime with $p=ab$. Then $p\mid ab$ implies $p\mid a$ or $p\mid b$. Without loss of generality, suppose $p\mid a$. By the equation, $a\mid p$ as well, so $a$ and $p$ are associates, thus $b$ is a unit. $\square$

## Radical Ideals and Reduced Ring

> [!definition] Nilpotent & Idempotent
> Let $R$ be a ring. $x\in R$ is *nilpotent* if there is $n\in\N$ such that $x^n =0$. $x\in R$ is *idempotent* if $x^{2}=x$.

> [!proposition]
> If $x \in R$ is nilpotent then $1 + x$ is invertible.

> [!definition] Radical Ideal
> The *radical* $\newcommand{\rad}{\operatorname{rad}}\rad(I)$ of an ideal $I$ in a commutative ring is defined as 
> $$\rad(I):=\{r\in R \mid r^{n}\in I \text{ for some }n\in \N \}.$$
> If an ideal $I$ satisfies $\rad (I)=I$, then we call it a *radical ideal* or a *semisimple ideal*.

> [!proposition]
> The radical of an ideal is also an ideal.
> 


> [!definition] Reduced Ring
> 


## Prime and Maximal Ideals

> [!definition] Prime Ideal
> Let $R$ be a ring. An ideal $P \triangleleft R$ is *prime* if $P \neq R$ and $ab \in P$ implies that either $a \in P$ or $b \in P$. ^da4561

> [!theorem]
> Let $R$ be a commutative unital ring. $P \triangleleft R$ is prime if and only if $R/P$ is an integral domain.
> 

*Proof*  $P\triangleleft R$ is prime iff $a\notin P$, $b\notin P$ implies $ab\notin P$, iff nonzero $(a+P)$ and $(b+P)$ has multiplication $ab+P\neq P$. $\square$

> [!definition] Maximal Ideal
> Let $R$ be a ring. An ideal $M \triangleleft R$ is *maximal* if $M \neq R$ and there is no other ideal $I$ such that $M \subsetneq I \subsetneq R$. ^ee0592

<u><b>e.g.</b></u> $M \triangleleft \Z$ is maximal iff $M =(p)=p\Z$ for a prime $p$. In general, we have the following theorem holds:

> [!theorem]
> Let $I \triangleleft R$ be an ideal. Then $I$ is maximal iff $R/I$ is a [[Ring, Field and Integral Domain#^575174|field]].

*Proof*  $R/I$ is a field iff every non-zero element $a+I$ has a multiplicative inverse, iff for every $a\notin I$ there exist $b\in R$ such that $ab-1\in I$. If $I$ is maximal, then for any $a\notin I$, the ideal generated by $I$ and $a$ is the whole ring, so there exist $i\in I$ and $r\in R$ such that $i+ra=1$, which implies that $(r+I)(a+I)=1+I$. Conversely, if $R/I$ is a field, then for any ideal $J$ containing $I$, if there exists some $a\in J\setminus I$, then $(a+I)$ is non-zero in the field, so $ab-1\in I$ for some $b\in R$, which means that $1\in J$, $J=R$, so $I$ is maximal. $\square$

> [!corollary]
> Every maximal ideal is prime. In a PID, conversely, every non-zero prime ideal is maximal. ^0ddaa4

*Proof*  Every maximal ideal is prime is clear because every field is an integral domain. $\square$

> [!proposition]
> Let $R$ be a principle ideal domain, then $(a) \triangleleft R$ is maximal if and only if $a$ is irreducible. ^85722a

*Proof*  In a PID, we have that $(a)\subset(b)$ iff $b \mid a$. It follows that $(a)$ is maximal iff there is no proper divisor $b\mid a$, which means $a$ is irreducible. $\square$

> [!corollary]
> If $F$ is a field, then $M = (f (x)) \triangleleft F [x]$ is maximal iff $f (x)$ is irreducible.

*Proof*  $F[x]$ is a PID, so $(f(x))$ is maximal iff $f(x)$ is irreducible. $\square$