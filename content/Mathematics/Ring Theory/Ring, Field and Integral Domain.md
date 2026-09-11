---
updated: 2025-02-16
tags:
  - algebra
---
## Rings

>[!definition] Ring
>A *ring* $R$ is a set equipped with two laws of composition $+$ and $\cdot$, called addition and multiplication, satisfying the following axioms:
>- $(R,+)$ is an [[Groups, Order and Subgroups#^6d511a|abelian group]] with identity $0$, called *zero*;
>- The multiplication is associative: $a(bc)=(ab)c$  for all $a,b,c \in R$;
>- Distributivity: $(a+b)c = ac+bc$ and $c(a+b)=ca+cb$ for all $a,b,c \in R$.
>
> If $R$ has an identity $1$ with respect to multiplication, we say that $R$ is *unital*.
> A ring $R$ is *commutative* if the multiplication is commutative. ^concept-b822d04b4a4b

<b><u>e.g.</u></b>  
- The integers $\mathbb{Z}$ is a commutative unital ring, any $\newcommand{\Z}{\mathbb{Z}}\Z/n\Z$ is a commutative unital ring.
- The set of 2×2 matrices with real entries $M_{2}(\R)$ is a non-commutative unital ring.
$\quad$

>[!definition] Subring
>A subset $S$ in a ring $R$ is called a *subring* if $S$ is closed under addition, subtraction, multiplication and contains $1$ (if $R$ is unital).

>[!definition] Unit
>An element of a ring $R$ is called a *unit* if it is invertible with respect to multiplication. The set of invertible elements is a [[Groups, Order and Subgroups#^6e0960|group]] called the the group of units in $R$ and denotes $R^{\times}$. ^c4d0ce

> [!proposition]
> For any (non-unital) ring $R$, $\Z\times R$ is a unital ring with multiplicative identity $(1,0)$ under the multiplication 
> $$ (m,r)(n,s):= (mn, m\cdot s + n \cdot r + rs), $$
> where for any $k\in\Z$, $k\cdot x$ is a shorthand for $x+x+\cdots+x$ ($k$ times) if $k>0$, $0$ if $k=0$, and $-((-k)\cdot x)$ if $k<0$. ([[Modules#^a2dd74|any abelian group is a $\Z$-module]]) ^c4d0ce

*Proof*  This is easy to check.  $\square$

From the above proposition, we can see that any ring can be enlarged into a unital ring. So we can just focus on unital rings most of the time. From now on,

>[!attention] 
> We shall sometimes just call commutative unital rings "rings", and emphasize the other cases when necessary.

## Field and Domain

> [!definition] Zero Divisor & Integral Domain
> A *zero divisor* in a ring $R$ is a non-zero element $a$ such that $ab = 0$ for some non-zero $b \in R$. A ring without zero divisors is called an *integral domain*. In other words, an integral domain is a ring in which the product of any two non-zero elements is non-zero. ^domain

> [!proposition] Cancellation Law
> An integral domain $R$ satisfies the cancellation law: if $ab = ac$ and $a \neq 0$ then $b = c$.

^8b4305

*Proof*  Suppose $ab = ac$ and $a \neq 0$. Then $ab - ac = a(b - c) = 0$. Since $a \neq 0$ and $R$ is an integral domain, $b - c = 0$. $\square$

> [!definition] Field
> A field is a [[Ring, Field and Integral Domain#^concept-b822d04b4a4b|ring]] $F$ in which $1 \neq 0$ and every non-zero element is invertible, that is $F^× = F \backslash \{0\}$. ^575174

<u><b>e.g.</b></u>  The rational numbers $\mathbb{Q}$ is a field.

> [!proposition]
> Any field is an integral domain.

*Proof*  Suppose $ab=0$, $a$ can be either $0$ or a unit, if it is not $0$, then $a^{-1}ab=b=0$. $\square$

> [!proposition]
> $\mathbb{Z}_n$ is a field if and only if $n$ is a prime. ^9aa68f

*Proof*  Suppose $n$ is prime, then every non-zero element $[a] \in \mathbb{Z}_n$ satisfies $a^{n-1}\equiv 1 \mod n$ by [[Division and Prime#^5214dc|Fermat's Little Theorem]]. Therefore $[a]^{-1} = [a]^{n-2}$. Conversely, if $n$ is not prime, then there exists $[a],[b] \in \mathbb{Z}_n$ such that $[a][b] = [n]=0$ but $a,b \neq 0$, so $\Z_{n}$ is not even an integral domain. $\square$

> [!proposition]
> Every finite integral domain is a [[Ring, Field and Integral Domain#^575174|field]].
> 

*Proof*  Suppose $R$ is an integral domain with finitely many elements. Let $a \in R$ be a non-zero element. Consider the function $f\colon R \to R$ defined by $f(x) = ax$. Since the [[Ring, Field and Integral Domain#^8b4305|cancellation law holds in an integral domain]], $f$ is [[Relations and Functions#^042daf|injective]]. Because $R$ is finite, $f$ must also be surjective (ref. [[Relations and Functions#^9109dc|proposition]]). Therefore, there exists some $b \in R$ such that $ab = 1$, showing that every non-zero element has a multiplicative inverse. Hence, $R$ is a field. $\square$

## Ordered Field

>[!definition] Ordered Field
>An ordered field is a field $F$ along with a subset $P$ of $F$, called the positive subset, with the following properties:
>- if $a∈F$, then $a∈P$ or $a=0$ or $−a∈P$.
>- if $a∈P$, then $−a\notin P$.
>- if $a,b∈P$, then $a+b∈P$ and $ab∈P$.
>
> Equivalently, a field $F$ together with a [[Preorder, Partial Order and Posets#^a8688d|total order]] $\leq$ on $F$ is an ordered field if the order satisfies the following properties for all $a,b,c\in F$:
>- $a\leq b \implies a+c \leq b+c$.
>- $0\leq a,0\leq b \implies 0\leq ab$.
>$\quad$ ^43843e

> [!proposition]
> The positive subset $P$ is closed under multiplicative inverse. i.e. Suppose $F$ is an ordered field with positive subset $P$. Then $1∈P$ and $a^{-1}\in P$ for all $a\in F$.

