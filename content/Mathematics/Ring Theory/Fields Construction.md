## Adjoining Roots

> [!proposition]
> Any ring homomorphism between two fields is injective.
> 

*Proof*  Suppose that $\newcommand{\Z}{\mathbb{Z}}\phi: F \to K$ is a ring homomorphism between two fields $F$ and $K$ such that $\phi(a) = \phi(b)$ for some $a,b\in F$. Then, we have $\phi(a-b) = 0$, which implies that $a-b = 0$ since $F$ is a field. Thus, $a = b$, and hence $\phi$ is injective. $\square$

> [!lemma]
> Let $F$ be a field, and let $f$ be an irreducible polynomial in $F[x]$. Then the ring $K = F[x]/(f)$ is an extension field of $F$, and the residue $\bar{x}$ of $x$ is a root of $f(x)$ in $K$. ^f0d7bc

*Proof*  Since, the principle ideal $(f)$ in $F[x]$ is maximal if and only if $f$ is irreducible, we have that $K$ is a field. The residue $\bar{x}$ of $x$ in $K$ is the equivalence class of $x$ modulo $(f)$. By definition, $\bar{x}$ is a root of $f(x)$ in $K$. $\square$

> [!definition] Complete Splitting
> A polynomial $f(x)\in F[x]$ is said to be completely split over a field $F$ if it can be factored into linear factors in $F[x]$.

> [!proposition]
> Let $F$ be a field, and let $f(x)$ be a monic polynomial in $F[x]$ of positive degree. There exists a field extension $K$ of $F$ such that $f(x)$ splits completely in $K$. ^e95416

*Proof*  We use induction on the degree of $f(x)$. If $\deg(f) = 1$, then $f(x)$ is linear and has a root in $F$. Thus, we can take $K = F$. Now, suppose that the statement holds for all polynomials of degree less than $n$, and let $f(x)$ be a monic polynomial of degree $n$. By [[Fields Construction#^f0d7bc|the lemma]], there exists a field extension $F_{1}$ of $F$ such that $f(x)$ has a root $\alpha$ in $F_{1}$. Suppose that $f(x)$ can be factored as $f(x) = g(x)f_{1}(x)$, where $g(x)$ is a irreducible polynomial with $g(\alpha)=0$. By the induction hypothesis, there exists a field extension $F_{2}$ such that $g(x)$ splits completely in $F_{2}$, and a field extension $F_{3}$ of $F_{1}$ such that $f_{1}(x)$ splits completely in $F_{3}$. Then, the polynomial $f(x)$ splits completely in the field extension $F_{2}\cup F_{3}$. $\square$

> [!theorem] 
> Let $f$ and $g$ be polynomials with coefficients in a field $F$, with $f \ne 0$, and let $K$ be an extension field of $F$. Then the following statements hold:
> 1. Division with remainder of $g$ by $f$ gives the same answer, whether carried out in $F[x]$ or in $K[x]$.
> 2. $f$ divides $g$ in $K[x]$ if and only if $f$ divides $g$ in $F[x]$.
> 3. The (monic) greatest common divisor $d$ of $f$ and $g$ is the same, whether computed in $F[x]$ or in $K[x]$.
> 4. If $f$ and $g$ have a common root in $K$, they are not relatively prime in $F[x]$. If $f$ and $g$ are not relatively prime in $F[x]$, there exists an extension field in which they have a common root.
> 5. If $f$ is an irreducible element of $F[x]$ and if $f$ and $g$ have a common root in $K$, then $f$ divides $g$ in $F[x]$.
> $\quad$

*Proof*  We prove each statement one by one:
1. In $F[x]$, suppose we have $g=fq+r$, this is also true in $K[x]$ since $F\subset K$. Meanwhile, division with remainder is unique, so we have $g=fq+r$ in $K[x]$ as well. Thus, the statement holds. $\square$
2. Directly follows from (1). $\square$
3. Let $d$ and $d'$ be the (monic) greatest common divisor of $f$ and $g$ in $F[x]$ and $K[x]$ respectively. Then, by definition, $d\mid d'$. Note that there exist polynomials $a$ and $b$ in $F[x]$ such that $d = af + bg$, and $d'$ divides both $f$ and $g$ in $K[x]$. Thus, $d' \mid d$. So $d$ and $d'$ are [[Factorization#^d98fbf|associates]] in $K[x]$. Since $d$ is monic, we have $d = d'$. $\square$
4. Suppose that $f$ and $g$ are not relatively prime in $F[x]$. Then, there exists a non-zero greatest common divisor $d$ such that $d\mid f$ and $d\mid g$. By [[Fields Construction#^f0d7bc|the lemma]], there exists a field extension in which $d$ has a root, this will also be a root of $f$ and $g$. Conversely, if $f$ and $g$ have a common root $\alpha$ in $K$, then $x-\alpha$ is a common divisor of $f$ and $g$ in $K[x]$, so the greatest common divisor of $f$ and $g$ is not a unit in $F[x]$. Thus, $f$ and $g$ are not relatively prime in $F[x]$. $\square$
5. If $f$ is irreducible, its only monic divisors in $F [x]$ are $1$ and $f$. (4) tells us that the greatest common divisor of $f$ and g in $F[x]$ isn’t $1$. Therefore it is $f$. $\square$
$\quad$

## Multiple Roots of a Polynomial

> [!theorem]
> Let $f$ be a polynomial with coefficients in a field $F$. An element $\alpha$ in an extension field $K$ of $F$ is a *multiple (double) root*, meaning that $(x - \alpha)^2$ divides $f$, if and only if it is a root of $f$ and also a root of $f'$.
> 

*Proof*  Suppose that $\alpha$ is a root of $f$, say $f(x)=(x-\alpha)g(x)$. Then by the product rule of differentiation, we have $$f'(x)=(x-\alpha)g'(x)+g(x),$$hence $f'(\alpha)=0$ if and only if $g(\alpha)=0$. $\square$

> [!corollary]
> Let $f(x)$ be a polynomial with coefficients in $F$. There exists a field extension $K$ of $F$ in which $f$ has a multiple root if and only if $f$ and $f'$ are not relatively prime.

*Proof*  If $f$ has a multiple root in $K$, then $f$ and $f'$ have a common root in $K$, so they are not relatively prime in $K$ or $F$. Conversely, if $f$ and $f'$ are not relatively prime, then they have a common root in some field extension $K$, hence $f$ has a multiple root there. $\square$

> [!proposition] 
> Let $f$ be an irreducible polynomial in $F[x]$, where $F$ is a field. Then $f$ has no multiple root in any field extension of $F$ unless the derivative $f'$ is the zero polynomial.

*Proof*  We shall show that $f$ and $f'$ are relatively prime unless $f'$ is the zero polynomial. Since $f$ is irreducible, $f$ and $f'$ are not relatively prime if and only if $f\mid f'$. And unless $f'=0$, $f'$ should have degree no less than $\deg(f)$, however, $\deg(f')\leq \deg(f)$. Thus, $f'$ must be the zero polynomial. $\square$

> [!corollary]
> Let $f$ be an irreducible polynomial in $F[x]$, where $F$ is a field of characteristic zero, then $f$ has no multiple root in any field extension of $F$.
> 

*Proof*  In a field of characteristic zero, the derivative of a polynomial is never the zero polynomial. $\square$

## Primitive Elements

> [!definition] Primitive Element
> Let $K$ be a field extension of $F$. An element that generates $K$, i.e. $K=F[\alpha]$, is called a primitive element of $K$ over $F$.
> 

> [!lemma]
> Let $F$ be a field of characteristic $0$, and let $K$ be an extension field that is generated over $F$ by two elements $\alpha$ and $\beta$. For all but finitely many $c\in F$, the element $\alpha + c\beta$ is a primitive element of $K$ over $F$. ^f0d7bb

*Proof*  See Artin's Lemma 15.8.2. $\square$

> [!theorem] Primitive Element Theorem
> Let $K$ be a finite extension of a field $F$ of characteristic $0$. Then $K$ contains a primitive element $\alpha$ such that $K=F(\alpha)$. In other words, $K$ is a simple extension of $F$.
> 

*Proof*  Since $K$ is a finite extension, $K$ is generated by a finite set. In particular, a basis $\{\alpha_{1},\dots,\alpha_{k}\}$ will generate $K$ over $F$, say $K=F[\alpha_{1},\dots,\alpha_{k}]$. We apply induction on $k$. There is nothing to prove when $k=1$. For any $k>1$, assume the theorem holds for $k-1$, that is the extension field $L=F[\alpha_{1},\dots,\alpha_{k-1}]$. So $L$ is generated by a primitive element $\beta$, $L=F[\beta]$. Now, we have $K=F[\alpha_{1},\dots,\alpha_{k-1},\alpha_{k}]=F[\beta,\alpha_{k}]$. By [[Fields Construction#^f0d7bb|the lemma]], there exists a primitive element $\gamma$ such that $K=F[\gamma]$. Thus, the theorem holds. $\square$

## The Fundamental Theorem of Algebra

> [!definition] Algebraically Closed Field
> A field $F$ is said to be algebraically closed if every non-constant polynomial with coefficients in $F$ has a root in $F$. ^5b9555

> [!theorem] Fundamental Theorem of Algebra
> $\newcommand{\C}{\mathbb{C}}\C$ is an algebraically closed field. ^4e12b7

*Proof*  

> [!remark]
> There are other proofs as well. See [[The Argument Principle#^89d738|proof using Rouché's theorem]], [[The Fundamental Group#^dfc77e|proof using algebraic topology]].

> [!proposition]
>  Let $X$ be a finite set and $R = \mathrm{Func}(X,\R)$. Then $I \triangleleft R$ is maximal iff $I = I_x =\{ f ∈ R | f (x) = 0\}$ for some $x ∈ X$.
> 

> [!definition] Hilbert’s Nullstellensatz
> The maximal ideals in $\mathbb{C}[x_1, \dots , x_n ]$ are in bijection with points in $\mathbb{C}^n$.

> [!theorem]
> Let $I$ be an ideal of $\mathbb{C}[x_1,\dots,x_n]$ generated by $f_1,\dots,f_m ∈ \mathbb{C}[x_1,\dots,x_n]$, let $R=\mathbb{C}[x_1,\dots,x_n]/I$ and let vector space $V =V(f_1,\dots,f_m)$.Then points in $V$are in bijection with maximal ideals in $R$.
