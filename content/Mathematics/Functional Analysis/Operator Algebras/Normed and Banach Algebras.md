> [!definition] Submultiplicative Norm
> A [[Normed Spaces#^345fd3|norm]] over a [[Vector Spaces#^f4b63e|vector space]] $X$ is *submultiplicative* if $\|ab\|\leq \|a\| \|b\|$ for all $a,b\in X$.

> [!definition] Normed Algebra & Banach Algebra
> Let $\newcommand{\A}{\mathcal{A}}\A$ be an [[Noncommutative Rings#^2c3d07|algebra]] (over $\newcommand{\C}{\mathbb{C}}\C$) equipped with a submultiplicative norm, then $\A$ is called a *normed algebra*. 
> If $\A$ admits a unit $1_{\A}$ such that $\|1_{\A}\|=1$, then it is called a *unital normed algebra*.
> If it is also a [[Banach Spaces#^7196a5|Banach space]] (i.e. [[Complete Metric Space#^67b510|complete]]), then it is called a *Banach algebra*. ^040470

<u><b>e.g.</b></u>  Suppose $X$ is a Banach space, and $B(X)$ is the algebra of bounded linear operators on $X$ with operator norm $\|\cdot\|_{\infty}$. Then $(B(X), \|\cdot\|_{\infty})$ is a Banach algebra.

> [!theorem]
> Let $A$ be a Banach algebra, $I$ be a closed ideal in $A$, then $A/I$ is a Banach algebra, with the norm defined as $\|a+I\|=\inf_{i\in I}\|a+i\|$ for all $a\in A$.
> 

## Spectrum

Recall that the set of invertible elements in a algebra forms a group:

![[Ring, Field and Integral Domain#^c4d0ce]]

Here, for any unital algebra $A$, we denote the set of invertible elements in $\A$ as $\newcommand{\Inv}{\mathrm{Inv}}\Inv(\A):=\A^{\times}$.

> [!definition] Spectrum
> Suppose $A$ is a unital normed algebra. Then the *spectrum* of $a\in \A$ is the set $$\sigma_{\A}(a)=\{\lambda \in\C:a-\lambda \cdot 1_{\A} \text{ is not invertible}\}.$$ ^5f41ec

<u><b>e.g.</b></u>
- Suppose $\A=M_{n}(\C)$, the algebra of $n\times n$ complex matrices, then the spectrum of a matrix $B$ is the set of all eigenvalues of $B$.
- $\Omega$ is a compact [[Hilbert Spaces#^ae0212|Hilbert space]], then the spectrum of $f\in C(\Omega)$, for which $C(\Omega)$ is the algebra of all continuous maps $\Omega\to \C$, is the range of $f$. 
- Consider the algebra of polynomials $\C[z]$. The spectrum of $z$ is the whole $\C$.
$\quad$

> [!proposition]
> The [[Normed and Banach Algebras#^5f41ec|spectrum]] is a closed subset of $\C$.
> 

> [!theorem] Neumann Theorem
> Let $\A$ be a unital Banach algebra, and $a\in \A$ such that $\|a\|<1$. Then $(1-a)$ is invertible and $$(1-a)^{-1}=\sum_{n=0}^{\infty}a^{n}.$$
> 

> [!theorem]
> Let $\A$ be a unital Banach algebra, then $\Inv(\A)$ is open in $\A$, and the mapping $\Inv(\A)\to \A$, $a\mapsto a^{-1}$ is Fréchet differentiable.
> 

> [!lemma]
> If $a$ is an element of a unital Banach algebra $\A$, then the spectrum $\sigma(a)$ is a [[Topological Spaces#^0849a0|closed subset]] of $\C$ and $|\lambda|\leq \|a\|$ for any $\lambda\in\sigma(a)$.

*Proof*  We first prove that $|\lambda|\leq\|a\|$ by contradiction. Assume $|\lambda|>\|a\|$ for some $\lambda\in\sigma(a)$. Then, by the Neumann theorem, we have $(1-\frac{a}{\lambda})$ is invertible, hence $a-\lambda \cdot 1=(1-\frac{a}{\lambda})\cdot (-\lambda)$ is also invertible. This contradicts the definition of $\sigma(a)$.
Now we show that $\sigma(a)$ is closed. Define the map $\varphi\colon \C\to A$, $\lambda\mapsto a-\lambda\cdot 1$, which is [[Continuous Functions on Topological Spaces#^33ee5a|continuous]]. Then $\C\setminus\sigma(a)=\varphi^{-1}(\Inv(A))$. Since $\Inv(A)$ is open in $A$, it follows that $\sigma(a)$ is closed in $\C$. $\square$

> [!lemma]
> If $a$ is an element of a unital Banach algebra $\A$, then the map $F\colon \C\setminus\sigma(a) \to \A$, $\lambda\mapsto (a-\lambda\cdot 1)^{-1}$ is differentiable.

*Proof*  Observe that $F=(a\mapsto a^{-1})\circ(\lambda\mapsto a-\lambda\cdot 1)$, which is a composition of two differentiable maps, hence $F$ is differentiable. $\square$

> [!theorem] Gelfand Theorem
> If $a$ is an element of a unital Banach algebra $\A$, then the spectrum $\sigma(a)$ is nonempty.

*Proof*  Assume that $\sigma(a)=\emptyset$ (i.e. $a-\lambda\cdot 1$ is invertible for all $\lambda\in\C$) and we shall obtain a contradiction. For all $\lambda\in \C$ with $|\lambda|>2\|a\|$, we have $\|\lambda^{-1}a\|<\frac{1}{2}<1$, so Neumann theorem implies that $(1-\lambda^{-1}a)$ is invertible, and $$(1-\lambda^{-1}a)^{-1}=\sum^{\infty}_{n=0} (\lambda^{-1}a)^{n}.$$Therefore, $$\|(1-\lambda^{-1}a)^{-1}-1\|=\left\|\sum^{\infty}_{n=1} (\lambda^{-1}a)^{n}\right\|\leq \sum_{n=1}^{\infty}\|\lambda^{-1}a\|^{n}=\frac{\|\lambda^{-1}a\|}{1-\|\lambda^{-1}a\|}\leq 2\|\lambda^{-1}a\|<1,$$where the first inequality follows from the triangle inequality. Consequently, we have 
Moreover, from the above lemma, we know that $F\colon \C\setminus\sigma(a)\to A$, $\lambda\mapsto (a-\lambda\cdot 1)^{-1}$ is differentiable, so it is continuous on $\C\setminus\sigma(a)$.
Since $D=\{z\in\C:|z|\leq 2\|a\|\}$ is compact,  

> [!corollary] Gelfand-Mazur Theorem
> If $\A$ is a unital [[Normed and Banach Algebras#^040470|Banach algebra]] in which every nonzero element is invertible, then $\A=\C1_{\A}$.

> [!theorem] Beurling's Theorem (Gelfand's Formula)
> If $a$ is an element of a unital Banach algebra $\A$, then the spectral radius of $a$ is given by $$r(a)=\lim_{n\to\infty}\|a^{n}\|^{1/n}.$$
