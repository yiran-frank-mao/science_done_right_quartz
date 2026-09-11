---
created: 2024-01-11
updated: 2024-10-03
---
In this note, we will discuss the basic concepts of number theory. In short, number theory is the study of $\Z$.

> [!definition] Division
> For two [[Number Systems#^25bad2|integers]] $a$ and $b$, we say *$a$ divides $b$*, written as $a\mid b$ if there exists [[Number Systems#^25bad2|integer]] $c$ such that $b=a\cdot c$.

> [!definition] Prime
> A *prime number* (or a *prime*) is a natural number greater than $1$ that is not a product of two smaller natural numbers. ^47f235

<b><u>e.g.</u></b> $2,3,5,7,11,13,17,19\cdots$ are prime numbers.

> [!lemma]
> For prime number $p$,  $p\nmid a \implies \gcd(p,a)=1$. ^4c2043

*Proof*  By definition of a prime, the only possible divisors of $p$ are $1$ and $p$. Since $p\nmid a$, we have $\gcd(p,a)=1$. $\square$

> [!theorem] Fundamental Theorem of Arithmetic
> Every integer greater than $1$ can either be prime or represented uniquely as a product of prime numbers. ^ff714c

*Proof*  Clearly $2$ is a prime. Assume all integers less than or equal to $n$ are primes or a product of prime numbers. Suppose $n+1$ is not prime. Then there exists $1<k\leq n$ that divides $n+1$. Thus $n+1$ is a product of primes. Therefore, by principle of induction, we have all integers are either prime or a product of prime numbers. $\square$

> [!corollary]
> There are infinitely many primes. ^1e1100

*Proof*  Assume there are only finitely many primes, say $p_{1},p_{2}\dots p_{n}$. Let $N=p_{1}p_{2}\dots p_{n}+1$. Clearly $N$ is not a member of $p_{1},p_{2}\dots p_{n}$ thus not prime. Hence $N$ is a product of primes. Therefore there exists prime $p_{j}$ such that $p_{j}\mid p_{1}p_{2}\dots p_{n}+1$, it follows that $p_{j}\mid 1$, yielding a contradiction. $\square$

## Greatest Common Divisor

> [!definition] Greatest Common Divisor
> The *greatest common divisor* of two or more [[Number Systems#^25bad2|integers]], which are not all zero, is the unique largest positive integer that divides each of the integers, denoted as $\gcd(x,y)$ in the two integers case. 
> In other words, it is the positive integer $d$ such that $d\mid x$, $d\mid y$ and $$c \mid x, c\mid y \implies c \mid d.$$ ^2ad3c0

*Proof*  The existence of $\gcd(x,y)$ is guaranteed by the Bézout’s identity below. The uniqueness of $\gcd(x,y)$ is guaranteed by the definition. $\square$

> [!theorem] Bézout’s Identity
> Let $a,b\in\Z$, not both zero. Then the set 
> $$ S=\{ ax+by \mid x,y\in \Z , ax+by>0\} $$
> has a least element $d$, and $d=\gcd(a,b)$. ^a2ecfb

> [!lemma] Euclid's Lemma
> Let $p$ be a prime number. If $p$ divides the product $ab$, then $p\mid a$ or $p\mid b$.

*Proof*  Suppose $p\nmid a$, then $\gcd(p,a)=1$ by [[Division and Prime#^4c2043|the lemma above]]. By [[Division and Prime#^a2ecfb|Bézout’s identity]], there exists $x,y\in\Z$ such that $px+ay=1$. Multiplying both sides by $b$, we have $pbx+aby=b$. Since $p\mid ab$, we have $p\mid b$. $\square$

> [!proposition]
> For integers $a,b,c\in \Z$ with $a\neq 0$, $a\gcd(b,c)=\gcd(ab, ac)$.
> 

*Proof*  We will show that $\gcd(ab, ac)$ divides $a\gcd(b,c)$ and vice versa. Let $d=\gcd(b,c)$, then $d\mid b$ and $d\mid c$. Thus $ad\mid ab$ and $ad\mid ac$, so $ad\mid \gcd(ab, ac)$. Conversely, let $e=\gcd(ab, ac)$, then $e\mid ab$ and $e\mid ac$. Note that by [[Division and Prime#^a2ecfb|Bézout’s identity]], there exists $x,y\in\Z$ such that $d=bx+cy$, so $ad=abx+acy$, thus $e\mid ad$. Therefore, we have $a\gcd(b,c)=\gcd(ab, ac)$. $\square$

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
> For every two integers $n,a$ that are coprime, then we have $a^{\varphi(n)} \equiv 1 \pmod{n}$, where $\varphi$ is the [[Arithmetic Functions#^d3f605|Euler's totient function]]. In particular, if $n = p$ is a [[Division and Prime#^47f235|prime number]] then $a^p ≡ a \pmod{p}$. ^5214dc

*Proof*  Let $n$ be a positive integer and $a$ be an integer coprime to $n$. Consider the set of integers $S_{n}=\{k_{1},k_{2},\cdots,k_{\varphi(n)}\}$ that are coprime to $n$. Multiplying each of these integers by $a$ modulo $n$ gives another set of integers that are also coprime to $n$. Since multiplication by $a$ is a bijection on the set of integers coprime to $n$, we have