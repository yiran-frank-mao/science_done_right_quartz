---
updated: 2025-02-16
tags:
  - algebra
---
## Rings

>[!definition] Ring
>A ring $R$ is a set equipped with two laws of composition $+$ and $\cdot$, called addition and multiplication, satisfying the following axioms:
>- $(R,+)$ is an abelian group with identity $0$, called zero.
>- The multiplication is associative: $a(bc)=(ab)c$  for all $a,b,c \in R$.
>- Distributivity: $(a+b)c = ac+bc$ for all $a,b,c \in R$.
>
> If $R$ has identity $1$ with respect to multiplication we say that $R$ is unital. ^178485

>[!definition] Commutative Ring
>A ring $R$ is commutative if the multiplication is commutative.

<b><u>e.g.</u></b>  The integers $\mathbb{Z}$ is a commutative unital ring.

>[!attention] 
>We will restrict to commutative unital rings and just call them rings.

>[!definition] Subring
>A subset $S$ in a ring $R$ is called a subring if $S$ is closed under addition, subtraction, multiplication and contains $1$.

>[!definition] Unit
>An element of a ring $R$ is called a unit if it is invertible with respect to multiplication. The set of invertible elements is a [[Groups, Order and Subgroups#^6e0960|group]] called the the group of units in $R$ and denotes $R^{\times}$. ^c4d0ce

## Field and Domain

> [!definition] Zero Divisor & Integral Domain
> A zero divisor in a ring $R$ is a non-zero element $a$ such that $ab = 0$ for some non-zero $b \in R$. A ring without zero divisors is called an integral domain. In other words, an integral domain is a ring in which the product of any two non-zero elements is non-zero. ^domain

> [!definition] Field
> A field is a [[Ring, Field and Integral Domain#^178485|ring]] $F$ in which $1 \neq 0$ and every non-zero element is invertible, that is $F^× = F \backslash \{0\}$. ^575174

<u><b>e.g.</b></u>  The rational numbers $\mathbb{Q}$ is a field.

> [!proposition]
> Any field is an integral domain.

*Proof*  Suppose $ab=0$, $a$ can be either $0$ or a unit, if it is not $0$, then $a^{-1}ab=b=0$. $\square$

> [!proposition]
> $\mathbb{Z}_n$ is a field if and only if $n$ is a prime. ^9aa68f

*Proof*  Suppose $n$ is prime, then every non-zero element $[a] \in \mathbb{Z}_n$ satisfies $a^{n-1}\equiv 1 \mod n$ by [[Division and Prime#^5214dc|Fermat's Little Theorem]]. Therefore $[a]^{-1} = [a]^{n-2}$. Conversely, if $n$ is not prime, then there exists $[a],[b] \in \mathbb{Z}_n$ such that $[a][b] = [n]=0$ but $a,b \neq 0$, so $\Z_{n}$ is not even an integral domain. $\square$

> [!proposition] Cancellation Law
> An integral domain $R$ satisfies the cancellation law: if $ab = ac$ and $a \neq 0$ then $b = c$.

*Proof*  Suppose $ab = ac$ and $a \neq 0$. Then $ab - ac = a(b - c) = 0$. Since $a \neq 0$ and $R$ is an integral domain, $b - c = 0$. $\square$

> [!definition] Divisibility in Rings
> Let $R$ be a ring. An element $a ∈ R$ divides $b ∈ R$ if there exists $c ∈ R$ with $b = ac$.

## Ordered Field

>[!definition] Ordered Field
>An ordered field is a field $F$ along with a subset $P$ of $F$, called the positive subset, with the following properties:
>- if $a∈F$, then $a∈P$ or $a=0$ or $−a∈P$.
>- if $a∈P$, then $−a\notin P$.
>- if $a,b∈P$, then $a+b∈P$ and $ab∈P$.
>
Equivalently, a field $F$ together with a [[Order#^a8688d|total order]] $\leq$ on $F$ is an ordered field if the order satisfies the following properties for all $a,b,c\in F$:
>- $a\leq b \implies a+c \leq b+c$.
>- $0\leq a,0\leq b \implies 0\leq ab$.
>$\quad$

^43843e

> [!proposition]
> The positive subset $P$ is closed under multiplicative inverse. i.e. Suppose $F$ is an ordered field with positive subset $P$. Then $1∈P$ and $a^{-1}\in P$ for all $a\in F$.

