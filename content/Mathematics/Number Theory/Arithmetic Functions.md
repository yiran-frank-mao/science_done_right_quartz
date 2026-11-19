**Def**  <i><u>Arithmetic Function</u></i>
An arithmetic function is generally any function $f:\Z^{+}\to\C$.

**Def**  <i><u>Additivity</u></i>
An arithmetic function $f$ is completely additive if $f(mn) = f(m) + f(n)$ for all natural numbers $m$ and $n$; It is additive if $f(mn) = f(m) + f(n)$ for all coprime natural numbers $m$ and $n$.

**Def**  <i><u>Multiplicativity</u></i>
An arithmetic function $f$ is completely multiplicative if $f(mn) = f(m)f(n)$ for all natural numbers $m$ and $n$; It is multiplicative if $f(mn) = f(m)f(n)$ for all coprime natural numbers $m$ and $n$.

> [!definition] Euler Totient Function
> The Euler totient function $\varphi(q):\Z^{+}\to\N$ is mapping to the number of positive integers not greater than $q$ that are coprime to $q$: $$\varphi(q)=n\prod_{p\mid q}\left(1-\frac1p\right)$$^d3f605

**Prop**  The Euler totient function is multiplicative. 

**Def**  <i><u>Dirichlet Character</u></i>
A complex-valued arithmetic function $\chi:\mathbb{Z}\to\mathbb{C}$ is a Dirichlet character of modulus $q$ if for all integers $a$ and $b$:
- $\chi(ab)=\chi(a)\chi(b)$ i.e. $\chi$ is completely multiplicative.
- $\chi(a)=0$ for all $\gcd(a,q)>1$
- $\chi(a)\neq0$ for all $\gcd(a,q)=1$
- $\chi(a+q)=\chi(a)$
We call trivial character the principle character, denoted as $$\chi_0(a)=\begin{cases}0\quad \gcd(a,q)>1\\1\quad \text{otherwise}\end{cases}$$