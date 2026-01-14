---
created: 2024-01-11
updated: 2024-10-03
---
> [!definition] Division
> For two [[Number Systems#^b4eff7|natural numbers]] $a$ and $b$, we say $a$ divides $b$, written as $a\mid b$ if there exists [[Number Systems#^25bad2|integer]] $c$ such that $b=a\cdot c$.

> [!definition] Prime
> A prime number (or a prime) is a natural number greater than $1$ that is not a product of two smaller natural numbers. ^47f235

<b><u>e.g.</u></b> $2,3,5,7,11\dots$ are prime numbers.

> [!lemma] Euclidean's Lemma
> Let $p$ be a prime number. If $p$ divides the product $ab$, then $p\mid a$ or $p\mid b$.

> [!theorem] Fundamental Theorem of Arithmetic
> Every integer greater than $1$ can either be prime or represented uniquely as a product of prime numbers. ^ff714c

*Proof*  Clearly $2$ is a prime. Assume all integers less than or equal to $n$ are primes or a product of prime numbers. Suppose $n+1$ is not prime. Then there exists $1<k\leq n$ that divides $n+1$. Thus $n+1$ is a product of primes. Therefore, by principle of induction, we have all integers are either prime or a product of prime numbers. $\square$

> [!corollary]
> There are infinitely many primes.

*Proof*  Assume there are only finitely many primes, say $p_{1},p_{2}\dots p_{n}$. Let $N=p_{1}p_{2}\dots p_{n}+1$. Clearly $N$ is not a member of $p_{1},p_{2}\dots p_{n}$ thus not prime. Hence $N$ is a product of primes. Therefore there exists prime $p_{j}$ such that $p_{j}\mid p_{1}p_{2}\dots p_{n}+1$, it follows that $p_{j}\mid 1$, yielding a contradiction. $\square$

> [!definition] Greatest Common Divisor
> The greatest common divisor of two or more integers, which are not all zero, is the largest positive integer that divides each of the integers, denoted as $\gcd(x,y)$ in two integers case.

> [!lemma]
> For prime number $p$,  $p\nmid a \implies \gcd(p,a)=1$.

> [!algorithm] Euclidean Algorithm
> The Euclidean algorithm is an efficient method for computing the greatest common divisor of two integers $a$ and $b$.
> 1. Given two integers $a\geq b >0$.
> 2. Apply the division algorithm to obtain $a = bq_{1} + r_{1}$, where $0\leq r_{1} < b$.
> 3. If $r_{1} = 0$, then $\gcd(a,b) = b$. Otherwise, replace $a$ by $b$ and $b$ by $r_{1}$, and repeat step 2.
> $\quad$

<u><b>e.g.</b></u>  To compute $(56,12)$, we have the following steps:
1. $56 = 12 \cdot 4 + 8$;
2. $12 = 8 \cdot 1 + 4$;
3. $8 = 4 \cdot 2 + 0$.

Thus, $\gcd(56,12) = 4$.

> [!theorem] Fermat’s Little Theorem
> For every two integers $n,a$ that are coprime, then we have $a^{\varphi(n)} \equiv 1 \pmod{n}$, where $\varphi$ is the [[Arithmetic Functions#^d3f605|Euler's totient function]]. In particular if $n = p$ is a prime number then $a^p ≡ a \pmod{p}$. ^5214dc

*Proof*  