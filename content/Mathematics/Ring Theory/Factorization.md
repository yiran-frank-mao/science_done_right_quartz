---
created: 2025-02-16
updated: 2025-02-16
tags:
  - algebra
completed: true
---
## Factoring and Euclidean Domain

We can extend the notion of factorization to rings (integral domains) other than $\newcommand{\Z}{\mathbb{Z}}\Z$:

> [!definition] Factorization & Division in Integral Domain
> Suppose $R$ is an [[Ring, Field and Integral Domain#^domain|integral domain]]. We have the following definitions:
> - $u\in R$ is a unit if $u$ is invertible in $R$.
> - $a$ divides $b$ if there exists $c\in R$ such that $b=ac$.
> - $a$ is a proper divisor of $b$ if $a$ divides $b$, say $b=ac$, with neither $a$ nor $c$ units.
> - $a$ and $b$ are associates if $a$ divides $b$ and $b$ divides $a$. i.e. $a=ub$ for some unit $u$.
> - $a$ is irreducible if $a$ is not a unit and it has no proper divisors, i.e. its only divisors are units and associates.
> - $p$ is prime if $p$ is not a unit and whenever $p$ divides $ab$, then $p$ divides $a$ or $p$ divides $b$.
>$\quad$ ^d98fbf

> [!definition] Size Function
> A size function on an [[Ring, Field and Integral Domain#^domain|integral domain]] $R$ can be any function $\sigma\colon R\setminus\{0\}\to \Z^{+}$ whose domain is the set of nonzero elements of $R$ and whose range is the set of nonnegative integers.

<u><b>e.g.</b></u> A multiplicative size function is especially useful, because it allows us to convert the factorization problem in an arbitrary integral domain to a factorization problem in $\Z$ (even $\N$). For example, consider $\Z[\sqrt{-5}]$. We can define a size function $\sigma$ on $\Z[\sqrt{-5}]$ such that $\sigma(z):=\|z\|^{2}$, where $\|\cdot \|$ denotes the [[Complex Numbers#^add791|complex modulus]]. Thus, it satisfies$$\sigma(zw)=\|zw\|^{2}=\|z\|^{2}\|w\|^{2}=\sigma(z)\sigma(w),$$which is multiplicative. Let's consider $1+\sqrt{-5}\in\Z[\sqrt{-5}]$, whose size is $6$. As $6$ can only be factored into $2\cdot 3$ in $\N$, but there is neither size $2$ nor size $3$ element in $\Z[\sqrt{-5}]$, hence we can conclude that $1+\sqrt{-5}$ is irreducible in $\Z[\sqrt{-5}]$.

> [!definition] Euclidean Domain
> An integral domain $R$ is an Euclidean domain if there exists a size function $\sigma$ on $R$ such that division with remainder is possible: for all $a,b\in R$ with $b\neq 0$, there exist $q,r\in R$ such that $a=qb+r$ with $r=0$ or $\sigma(r)<\sigma(b)$.

<u><b>e.g.</b></u>  
- $\Z$ is an Euclidean domain with size function be the absolute value.
- A polynomial ring $F[x]$ over a field $F$ is an Euclidean domain with size function be the degree of the polynomial. But for a non field ring $R$, $\deg$ will not make $R[x]$ a Euclidean domain. A simple example is in $\Z[x]$, $2x+1$ cannot divide $x^{2}$ with remainder, because $2\not\mid 1$ in $\Z$. Indeed, $\Z[x]$ is not even a PID.
- The ring of Gaussian integers ([[Complex Numbers#^a81924|complex numbers]] with both real and imaginary parts being integers) $\Z[i]$ is an Euclidean domain with size function being the [[Complex Numbers#^add791|complex norm]]. 
- In fact, if $m^{2}+1<4$, then the complex norm will make $\Z[\sqrt{-m}]$ a Euclidean domain. This is because if we want to divide $a$ by $d$, we can look at the complex number $a/d$. If it is in $\Z[\sqrt{-m}]$, then we are done, and the remainder $r=0$. Otherwise, we can pick the nearest integer to $a/d$ in $\Z[\sqrt{-m}]\subset\C$ as $q$, and let their difference be $s\in\C$, then we have $a/d=q+s$, so $a=qd+sd$. Note that $\sigma(sd)=\sigma(s)\sigma(d)\leq \sigma(d)$, because by our assumption, $m^{2}+1<4$, so $\sigma(s)<1$. Hence $\sigma(sd)<\sigma(d)$, and we can take $r=sd$ as the remainder. Geometrically, the condition $m^2 + 1 < 4$ means that every point in the parallelogram (or rectangle) of side lengths $1$ and $\sqrt{m}$ in the complex plane is within distance less than $1$ from some vertex.
$\quad$

> [!proposition]
> A Euclidean domain is a [[Principle Ideal Domains#^74559c|principal ideal domain]]. ^5f7518

*Proof*  We mimic the proof that [$\Z$ is a principle ideal domain](Principle%20Ideal%20Domains#%5E9b5851.md) once again. Let $R$ be an Euclidean domain with size function $\sigma$. Let $I\triangleleft R$ be a non trivial ideal. Pick $n\in I$ such that $\sigma(n)$ is minimal. We claim $I=(n)$. For any $m\in I$, by the remainder theorem, we have $m=qn+r$ for some $q,r\in R$ with $\sigma(r)<\sigma(n)$. Since $n,m\in I$, it follows that $r=m-qn\in I$. As $\sigma(n)$ is minimal, we must have $r=0$. Therefore $m=qn\in (n)$. $\square$

> [!definition] Greatest Common Divisor & Relatively Prime
> Let $a,b\in R$ be elements of an integral domain $R$. The greatest common divisor of $a$ and $b$ is an element $d\in R$ such that:
> - $d$ divides both $a$ and $b$.
> - If $e$ divides both $a$ and $b$, then $e$ divides $d$.
>
> We say $a$ and $b$ are relatively prime if their greatest common divisor is a unit.

> [!remark] GCD may not exist
> There will often be a common divisor $m$ that is maximal, meaning that $a/m$ and $b/m$ have no proper divisors in common. However, this element may fail to satisfy the second property. For instance in the ring $\Z[\sqrt{-5}]$, the elements $a=6$ and $b=2+2\sqrt{-5}$ are divisible by $2$ and $1+\sqrt{-5}$. These are maximal elements among common divisors, but neither one divides the other. 

> [!proposition]
> Any two greatest common divisors of $a$ and $b$ are associates. 

*Proof*  It is straightforward by the second property of the greatest common divisor. $\square$

> [!proposition]
> Let $R$ be a principle ideal domain, and let $a$ and $b$ be elements of $R$, which are not both zero. Then whatever element $d$ generates the ideal $(a,b)$ is a greatest common divisor of $a$ and $b$. And there are elements $x,y\in R$ such that $d=ax+by$.

*Proof*  Let $d\in (a,b)$ be an element that generates the ideal. Then $d$ divides both $a$ and $b$. Let $e$ be another common divisor of $a$ and $b$. Then $a,b\in (e)$, and so $(e)$ contains $(a,b)=(d)$, so $e$ divides $d$. Therefore $d$ is a greatest common divisor of $a$ and $b$. Moreover, existence of $x,y\in R$ such that $d=ax+by$ follows from the fact that $d\in(a,b)$. $\square$

## Unique Factorization Domains

> [!definition] Unique Factorization Domain
> An integral domain $R$ is a unique factorization domain if it has the following properties:
> - Factoring terminates.
> - The irreducible factorization of an element $a$ is unique, up to order and associates.

<u><b>e.g.</b></u>  Every field is vacuously a unique factorization domain. $\Z[\sqrt{5}]$ is not a unique factorization domain, because $4=(\sqrt{5}-1)(\sqrt{5}+1)=2\cdot 2= (3-\sqrt{5})(3+\sqrt{5})$.

> [!proposition]
> Let $R$ be an integral domain, then the following conditions are equivalent:
> - Factoring terminates.
> - $R$ does not contain an infinitely strictly increasing chain $(a_{1})\subsetneq(a_{2})\subsetneq(a_{3})\subsetneq\cdots$ of principle ideals.
>$\quad$

> [!proposition]
> In any [[Ring, Field and Integral Domain#^domain|integral domain]], every prime element is irreducible.

*Proof*  Let $p$ be a prime element in an integral domain $R$. Suppose $p=ab$ for some $a,b\in R$. Then $p$ divides $ab$. Since $p$ is prime, $p$ divides $a$ or $p$ divides $b$. Without loss of generality, suppose $p$ divides $a$. Then $a=pc$ for some $c\in R$. Substituting this back into $p=ab$, we have $p=pcb$, and since $R$ is an integral domain, we can cancel $p$ to get $1=cb$. Therefore $b$ is a unit, and $p$ is irreducible. $\square$

> [!remark] The converse is not true
> Consider $\Z[\sqrt{-5}]$. $2$ is irreducible, $2\mid (1+\sqrt{-5})(1-\sqrt{-5})$, but $2$ does not divide either of the factors.

> [!theorem]
> If $\newcommand{\Frac}{\operatorname{frac}}R$ is an integral domain, in which factoring terminates, then $R$ is a unique factorization domain if and only if every irreducible element is prime. ^94c6f6

*Proof*  Let $R$ be an integral domain where every irreducible element is prime. Suppose some element can be factored in two ways: $$a=p_{1}\cdots p_{n}=q_{1}\cdots q_{m}.$$Then $p_{1}$ divides $q_{1}\cdots q_{m}$, and since $p_{1}$ is prime, $p_{1}$ divides some $q_{i}$. Without loss of generality, suppose $p_{1}$ divides $q_{1}$. Then $q_{1}=p_{1}u$ for some unit $u$. Cancelling $p_{1}$ from both sides, we get $$p_{2}\cdots p_{n}=uq_{2}\cdots q_{m}.$$Repeating this process, we can show that $n=m$ and the $p_{i}$'s are associates of the $q_{i}$'s.
Conversely, suppose $R$ is a unique factorization domain. Let $p$ be an irreducible element, and suppose $p$ divides $ab$, say $ab=pc$. Assume $p$ divides neither $a$ nor $b$. Then $a$ and $b$ can be factored into irreducible elements, say $a=p_{1}\cdots p_{m}$ and $b=q_{1}\cdots q_{n}$. Then $p_{1}\cdots p_{m}q_{1}\cdots q_{n}=pc$. That are two inequivalent factorizations of $pc$, a contradiction. $\square$

<u><b>e.g.</b></u>  Consider a non-example of the ring of continuous functions $\R\to\R$. One can factor $$|x|=|x|^{1/2}\cdot|x|^{1/2}=|x|^{1/4}\cdot|x|^{1/4}\cdot |x|^{1/4}\cdot|x|^{1/4}=\cdots $$

> [!corollary]
> Every principal ideal domain is a unique factorization domain.
> 

*Proof*  To show any factorization stops, it suffices to show that a infinite factorization $$(a_{1})\subset(a_{2})\subset(a_{3})\subset \cdots,$$has all tailing terms equal from some point. Note that $I=\cup_{i=1}^{\infty}(a_{i})$ is an ideal, hence, principle, say $I=(a)$. Then $a\in (a_{k})$ for some $k$, and so $(a)\subset (a_{k})$. Since $(a)$ is the union of all $(a_{i})$, we must have $$(a)\subset(a_{k})\subset(a_{k+1})\subset\cdots\subset(a),$$that is the tailing terms are all equal to $(a)$, starting from $k$. $\square$

> [!proposition]
> A unique factorization domain is a principle ideal domain if and only if all nonzero [[Relations and Maximal Ideals#^da4561|prime ideals]] are [[Relations and Maximal Ideals#^ee0592|maximal]].
> 

> [!definition] Primitive Polynomial
> Suppose $R$ is a unique factorization domain. $f\in R[x]$ is primitive if one of (thus all) the following equivalent conditions hold:
> - the greatest common divisor of its coefficients is $1$ (thus any units). 
> - no prime in $R$ divides all the coefficients of $f$.
> - For any prime $p\in R$, the canonical map $\pi\colon R[x] \to (R/(p))[x]$ evaluated at $f$ is nonzero.
>
>$\quad$

If $f\in R[x]$ is not primitive, we can always uniquely write $f=d f_{0}$ where $d$ is the greatest common divisor of the coefficients of $f$ and $f_{0}$ is primitive. Similarly in $(\Frac R)[x]$, we can write $f=cf_{0}$ where $c$ is a fraction number and $f_{0}$ is primitive in $R[x]$.

> [!lemma] Gauss' Lemma
> The product of primitive polynomials is primitive. ^ad087a

*Proof*  By the third definition of primitive polynomial, it suffices to show that $(R/(p))[x]$ is an integral domain. Note that $R/(p)$ is an integral domain, and so is $(R/(p))[x]$. $\square$

> [!lemma]
> $f_{0}\in R[x]$ is primitive, suppose $g\in R[x]$, such that $f_{0}\mid g$ in $(\Frac R)[x]$. Then $f_{0}\mid g$ in $R[x]$. ^a09770

*Proof*  Suppose $g=f_{0}\cdot h$, so that $$g=d\cdot g_{0} = f_{0} \cdot (c\cdot h_{0})=c(f_{0}g_{0})$$By the [[Factorization#^ad087a|Gauss' lemma]], $f_{0}g_{0}$ is primitive, since there is only a unique way to express any polynomial as a product of an element in $R$ (up to a unit) and a primitive polynomial, we must have $c=d \cdot u$. $\square$

> [!lemma]
> A primitive $f\in R[x]$ factors non-trivially in $R[x]$ if and only if it factors non-trivially in $(\Frac R)[x]$.

*Proof*  

> [!corollary]
> Primitive $f\in R[x]$ is irreducible in $R[x]$ if and only if it is irreducible in $(\Frac R)[x]$. ^4f5a64

> [!proposition]
> $R$ is a unique factorization domain if and only if $R[x]$ is also a unique factorization domain.

*Proof*  By the [[Factorization#^94c6f6|the theorem]], it suffices to show that every irreducible element in $R[x]$ is prime. All irreducible elements in $R[x]$ are either a constant, or a non-constant. Since $R$ is a unique factorization domain, nothing need to be shown for constant irreducible elements. Let $f\in R[x]$ be a non-constant irreducible, $f$ has to be primitive and irreducible in $(\Frac R)[x]$. Suppose $f\mid ab$ in $R[x]$, then $f\mid ab$ in $(\Frac R)[x]$. So $f\mid a$ or $f\mid b$ in $(\Frac R)[x]$, and hence in $R[x]$ by [[Factorization#^a09770|the lemma]]. $\square$

<u><b>e.g.</b></u>  $\Q[x,y]\cong\Q[x][y]$ is a unique factorization domain, as $\Q[x]$ is a unique factorization domain.

## Factoring Polynomials in $\Z[x]$

By [[Factorization#^4f5a64|the corollary]], we can tell whether a polynomial is irreducible in $\Q[x]$ by checking its irreducibility in $\Z[x]$. Moreover, it is helpful to check its factorization in $\Z/(p)[x]=\Z_{p}[x]$ for some prime $p$. Because, there are only $p$ elements to check in $\Z_{p}$, and the factorization in $\Z_{p}[x]$ can be lifted back to $\Z[x]$.

<u><b>e.g.</b></u>  Consider $f(x)=x^{2}+x+2$. In $\Z_{3}[x]$, it is irreducible because $$f([0])=[2]\neq [0],\quad f([1])=[1]\neq [0],\quad f([2])=[2]\neq [0].$$So $f$ is irreducible in $\Z[x]$, thus in $\Q[x]$.

> [!proposition] Eisenstein's Criterion
> Let $f(x)=a_{n}x^{n}+\cdots+a_{0}\in\Z[x]$. Suppose there is a prime $p$ such that:
> - $p$ divides all $a_{i}$ except $a_{n}$.
> - $p^{2}$ does not divide $a_{0}$.
>
> Then $f(x)$ is irreducible in $\Q[x]$.

In fact, the Eisenstein's criterion holds for any unique factorization domain, not just $\Z$. We shall prove it in the following.

> [!theorem] Generalized Eisenstein's Criterion
> Let $f(x)=a_{n}x^{n}+\cdots+a_{0}\in R[x]$, where $R$ is a unique factorization domain. Suppose there is a prime $p\in R$ such that:
> - $p$ divides all $a_{i}$ except $a_{n}$.
> - $p^{2}$ does not divide $a_{0}$.
> 
> Then $f(x)$ is irreducible in $(\Frac R)[x]$.

*Proof*  Up to contradiction, suppose $f=gh$ in $(\Frac R)[x]$, where $g(x)=b_{m}x^{m}+\cdots + b_{0}$, and $h(x)=c_{r}x^{r}+\cdots + c_{0}$. The hypothesis implies that $f$ becomes $[a_{n}]x^{n}\neq 0$ in $(R/(p))[x]$, so in $(R/(p))[x]$, $g$ has to be $[b_{m}]x^{m}$ and $h$ has to be $[c_{r}]x^{r}$, which means $p$ divides all $b_{i}$,$c_{j}$ except $b_{m}$ and $c_{r}$. Therefore, $p^{2}$ divides $a_{0}=b_{0} c_{0}$, which is a contradiction. $\square$

> [!lemma]
> Let $f\in R[x]$, where $R$ is an integral domain. Then $f(x)$ is irreducible if and only if $f(x+n)$ is irreducible for all $n\in\Z$.

*Proof*  If $f(x)=g(x)\cdot h(x)$, then $f(x+1)=g(x+1)\cdot h(x+1)$. Conversely, if $f(x+1)=g(x+1)\cdot h(x+1)$, then $f(x)=g(x)\cdot h(x)$, if we let $x:=x-1$. $\square$

> [!theorem]
> The cyclotomic polynomial $$\Phi_{p}(x)=x^{p-1}+x^{p-2}+\cdots+x+1$$ is irreducible in $\Q[x]$ for any prime $p$.
> 

*Proof*  We know that $(x-1)\Phi_{p}(x)=x^{p}-1$, substituting $x:=y+1$ and we obtain, $$y\Phi_{p}(y+1)=(y+1)^{p}-1=y^{p}+\binom{p}{1}y^{p-1}+\cdots+\binom{p}{p-1}y+1-1,$$we cancel $y$, and get $$\Phi_{p}(y+1)=y^{p-1}+\binom{p}{1}y^{p-2}+\cdots+\binom{p}{p-1},$$for which the Eisenstein's criterion applies with $p$ as the prime. Hence, $\Phi_{p}(x)$ is irreducible in $\Q[x]$. $\square$

## Gauss Primes

We have seen that the ring $\Z[i]$ of Gauss integers is a Euclidean domain. In this section we describe the prime elements in $\Z[i]$, and their relation to prime elements in $\Z$.

> [!lemma]
> The following are true in $\Z[i]$:
> - A Gauss integer that is a real is an intger.
> - An integer $d$ divides a Gauss integer $a+bi$ in $\Z[i]$ if an only if $d$ divides both $a$ and $b$ in $\Z$.
>$\quad$

> [!lemma]
> Let $p$ be an prime integer, the followings are equivalent:
> - $p$ is a prime in $\Z[i]$.
> - the quotient $\Z[i]/(p)$ is a field.
> - $x^{2}+1$ is an irreducible element in $\newcommand{\F}{\mathbb{F}}\F_{p}[x]$.
>$\quad$

