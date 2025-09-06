---
completed: true
updated: 2025-07-28
---
## Size of Finite Fields

> [!lemma]
> The [[Fields and Field Extensions#^2bfbd8|characteristic]] of any field is either zero or a prime.

*Proof*  Assume a field $F$ has characteristic neither zero nor a prime, say $n$. Then $n\cdot 1_{F} = 0_{F}$, where $1_{F}$ is the multiplicative identity of $F$ and $0_{F}$ is the additive identity of $F$. Let $p$ be the smallest prime divisor of $n$. Then, we have $p\cdot 1_{F} = 0_{F}$, which contradicts the assumption that the characteristic of $F$ is neither zero nor a prime. $\square$

> [!lemma]
> A finite field must have characteristic $p$ for some prime $p$ and its order is $p^{r}$ for some $r\in \N$.
> 

*Proof*  Let $F$ be a finite field. The characteristic of a finite field cannot be zero, so it must be a prime $p$. Hence, $F$ contains the finite subfield $\newcommand{\F}{\mathbb{F}}\F_{p}$. Note that $F$ is finite, thus a finite-dimensional vector space over $\mathbb{F}_{p}$. Let $r$ be the dimension of $F$ as a vector space over $\mathbb{F}_{p}$. Then, the order of $F$ is $p^{r}$. $\square$

<u><b>e.g.</b></u>  Consider $\F_{4}\cong \F_{2}[x]/(x^{2}+x+1)=:K$. Suppose $\alpha$ is a root of $x^{2}+x+1$ in $\F_{4}$. Then, we have $\F_{4}=\{0, 1, \alpha, \alpha+1\}$. And $\alpha+1$ is also a root of $x^{2}+x+1$.

> [!warning]
> Do not confuse the field $\newcommand{\F}{\mathbb{F}}\F_{4}$ with the ring $\Z/4\Z$, which isn’t a field. Indeed, $\Z/n\Z$ is a field if and only if $n$ is prime. (See [[Ring, Field and Integral Domain#^9aa68f|proposition]])
> 

## Properties of Finite Fields & The Frobenius Automorphism

> [!definition] Frobenius Automorphism
> The Frobenius automorphism of a field $F$ of characteristic $p$ is the map $\phi: F \to F$ defined by $\phi(x) = x^{p}$ for all $x \in F$.

Note that this is NOT a well-defined homomorphism for rings. But it is a well-defined homomorphism for finite fields, which we will show next.

*Proof*  First, we show that $\phi$ is a homomorphism. Let $x,y\in F$, then we have $$\phi(x+y)= (x+y)^{p} = x^{p}+y^{p}=\phi(x)+\phi(y),$$where the second equality follows from the binomial theorem, all coefficients in the middle are divisible by $p$, thus vanish. Multiplication is preserved trivially: $$\phi(xy)=(xy)^{p}=x^{p}y^{p}=\phi(x)\phi(y).$$Thus, $\phi$ is a homomorphism. Next, we show that $\phi$ is bijective. Since $\phi$ is a homomorphism, it is injective, thus automatically surjective by [[Relations and Functions#^9109dc|the proposition]]. $\square$

> [!theorem]
> Let $p$ be a prime integer, and let $q = p^{r}$ be a positive power of $p$. Then
> 1. The elements of a order $q$ field $K$ are exactly fixed points of $\phi^{r}$, where $\phi$ is the corresponding Frobenius automorphism. In other words, $r$ is the smallest integer such that $\newcommand{\id}{\mathrm{id}}\phi^{r}=\id$.
> 2. Any finite field of order $q$ is isomorphic to $\F_{p}[x]/(f)$ for some polynomial $f\in \F_{p}[x]$. Equivalently, $K$ is a finite extension of $\F_{p}$, and we can write $K = \F_{p}[\alpha]$, where $\alpha$ is a root of an irreducible polynomial $f\in \F_{p}[x]$ of degree $r$.
> 3. Let $K$ be a field of order $q$. The multiplicative group $K^\times$ of nonzero elements of $K$ is a cyclic group of order $q - 1$.
> 4. There exists a field of order $q$, and all fields of order $q$ are isomorphic.
> 5. If $F$ is a field of order $p^{r}$ and $K$ is a field of order $p^{s}$, then there is a homomorphism $F \to K$ if and only if $r\mid s$. In this case, it is an isomorphism if and only if $r = s$.
>$\quad$

*Proof*  We shall prove each statement one by one:
1. Let $K$ be a field of order $q$. Note that the group $K^{\times}$ has order $q-1$. Therefore the order of any element $x\in K^{\times}$ divides $q-1$ by [[Cosets and Lagrange’s Theorem#^coro|the Lagrange's Theorem]], so $x^{q-1}=1$, which means $x^{q}=x$. Observe that $0$ is also a fixed point of $\phi^{r}$, so we have $\phi^{r}(x)=x$ for all $x\in K$. We shall show the "in other words" part in (3). $\square$
2. 
3. Since $K^{\times}$ is a finite Abelian group, by [[Cyclic Groups#^2a69ea|the structure theorem]], we can write $$K^{\times}\cong \Z_{d_{1}}\times \Z_{d_{2}} \times \cdots \times \Z_{d_{k}}$$where $q-1=d_{1}d_{2}\cdots d_{k}$ and $d_{1}\mid d_{2}\mid \cdots\mid d_{k}$. So $d_{k}$ is the exponent of $K^\times$ (i.e. the smallest positive integer $e$ such that $x^{e}=1$), and $x^{d_{k}}=1$ for all $x\in K^{\times}$. That is, the polynomial $x^{d_{k}}-1$ has $q-1$ roots in $K$, so its degree, $d_{k}$ has to be greater than or equal to $q-1$. On the other hand, by (1), we know that $x^{q-1}=1$ for all $x\in K^{\times}$, so $d_{k} \mid q-1$ (since $d_{k}$ is the exponent), which means $d_{k}\leq q-1$, thus $d_{k}=q-1$. Therefore, $K^{\times}\cong \Z_{q-1}$ is cyclic. $\square$
4. We know that the elements of a field of order $q$ will be roots of the polynomial $x^{q}-x$. There exists a field extension $L$ of $\F_{p}$ in which this polynomial splits completely by [[Fields Construction#^e95416|the proposition]]. We claim that the set of all its roots in $L$ is a field of order $q$. To see this, we need to check that $x^{q}-x$ has no multiple roots, as well as this set is indeed a field. Note that the derivative of $x^{q}-x$ is $q x^{q-1}-1=-1$ in a field of characteristic $p$. Thus, the polynomial $x^{q}-x$ has no multiple roots. Moreover, clearly, $0$ and $1$ are roots of $x^{q}-x$. Let $\alpha$ and $\beta$ be the roots of $x^{q}-x$, then we have $$\alpha+\beta=\alpha^{q}+\beta^{q}=(\alpha+\beta)^{q}$$which means $\alpha+\beta$ is also a root of $x^{q}-x$. So the set of roots of $x^{q}-x$ is closed under addition. The same holds for multiplication clearly, so the set of roots of $x^{q}-x$ is indeed a field.
   We now show that two fields $K_{1}$ and $K_{2}$ of order $q$ must be isomorphic. Let $K_{1}= \F_{p}[\alpha]$ and $K_{2}= \F_{p}[\beta]$, where $\alpha$ and $\beta$ are roots of some irreducible polynomials $f,g\in \F_{p}[x]$ of degree $r$ respectively. We may assume that $\alpha\neq \beta$ and both $f$ and $g$ are not linear, otherwise $K_{1}=K_{2}$ naturally. Note that $\alpha$ is also a root of $x^{q}-x$, so $f\mid x^{q}-x$. Since $x^{q}-x$ splits completely in $K_{2}$, there is some element $\theta\in K_{2}$ that is also a root of $f$, so the map that $\alpha\mapsto\theta$ will be an injective homomorphism. Thus it is an isomorphism since $K_{1}$ and $K_{2}$ are finite fields of the same size. $\square$
5. Based on (4), we can assume without loss of generality that $F\supset \F_{p}$ and $K\supset \F_{p}$ are field extensions of $\F_{p}$, and it suffices to show that $F$ is a subfield of $K$ iff $r\mid s$. If $F\subset K$ is a subfield, then by [[Fields and Field Extensions#^ff28a3|multiplicative property]], we have $[K:F][F:\F_{p}]=[K:\F_{p}]$, so $[k:F]r=s$, which means $r\mid s$. Conversely, if $r\mid s$, then we can write $s=qr$ for some integer $q$. For any element $a\in F$, $a$ is a root of $x^{p^{r}}-x$ in $F$, so it satisfies $a^{p^{s}}-a=a^{(p^{r})^{q}}-a=aa^{(p^{r})^{q-1}}-a=a^{p^{r}}-a=0$, thus $a\in K$. Therefore, $F\subset K$. $\square$
$\quad$