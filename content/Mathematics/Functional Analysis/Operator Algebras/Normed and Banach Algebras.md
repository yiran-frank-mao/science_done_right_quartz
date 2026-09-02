> [!definition] Normed Algebra & Banach Algebra
> Let $\newcommand{\A}{A}\A$ be an [[Noncommutative Rings#^2c3d07|algebra]] (over $\newcommand{\C}{\mathbb{C}}\C$) equipped with a submultiplicative norm, that is, $\|ab\|\leq \|a\| \|b\|$ for all $a,b\in A$, then $\A$ is called a *normed algebra*. 
> If $\A$ admits a unit $1_{\A}$ such that $\|1_{\A}\|=1$, then it is called a *unital normed algebra*.
> If it is also a [[Banach Spaces#^7196a5|Banach space]] (i.e. [[Complete Metric Space#^67b510|complete]]), then it is called a *Banach algebra*. ^040470

<u><b>e.g.</b></u>  Suppose $X$ is a Banach space, and $B(X)$ is the algebra of bounded linear operators on $X$ with operator norm $\|\cdot\|_{\text{op}}$. Then $(B(X), \|\cdot\|_{\text{op}})$ is a Banach algebra with unit being the identity operator on $X$.

> [!proposition]
> Let $A$ be a Banach algebra, $I$ be a proper closed ideal in $A$, then $A/I$ is a Banach algebra, with the norm defined as $\|a+I\|:=\inf_{i\in I}\|a+i\|$ for all $a\in A$.
> 

*Proof*  We first check submultiplicativity of the norm on $A/I$ (we skip checking it is a norm here). For any $a+I$ and $b+I$, note that $aI+bI+I^{2}\subset I$ as $I$ is an ideal, we have $$\inf_{i\in I}\|ab+i\|\leq \inf_{i\in I, j\in I}\|ab+ai+bj+ij\| = \inf_{i\in I, j\in I}\|(a+i)(b+j)\|.$$By submultiplicativity of the norm in $A$, we have $\|(a+i)(b+j)\|\leq \|a+i\|\|b+j\|$. Taking infimum over $i,j\in I$, we get $\inf_{i\in I}\|ab+i\|\leq \inf_{i\in I}\|a+i\|\inf_{j\in I}\|b+j\|$. Hence, the norm is submultiplicative. The unit of $A/I$ has norm $1$ because on the one hand we have $\|1+I\|=\inf_{i\in I}\|1+i\|\leq \|1+0\|=1$, on the other hand, submultiplicativity implies $\|1+I\|^{2}\geq \|(1+I)(1+I)\| =\|1+I\|$, and $\|1+I\|\neq 0$ since $I\subsetneq A$ is proper, so $\|1+I\|=1$. To show completeness, we pick a Cauchy sequence $\{a_{n}+I\}_{n}$ in $A/I$, then one can pick a subsequence $\{a_{k_{n}}+I\}_{n}$ such that $\|a_{k_{n+1}}-a_{k_{n}}+ I\| < 2^{-n}$. Thus we can choose some $i_{n}\in I$, so that $\|a_{k_{n+1}}-a_{k_{n}}+ i_{n}\| < 2^{-n}$. Now define $a'_{1}:=a_{k_{1}}$, and $a'_{n+1}:=a_{k_{n+1}}+a'_{n}-a_{k_{n}}+i_{n}$. Note that $a'_{n+1}-a_{k_{n+1}}\in I$, so $a'_{n+1}+I=a_{k_{n+1}}+I$. Moreover, the sequence $\{a'_{n}\}_{n}$ is Cauchy in $A$ because $\|a'_{n+1}-a'_{n}\| = \|a_{k_{n+1}}-a_{k_{n}}+i_{n}\| < 2^{-n}$. Since $A$ is complete, there exists $a\in A$ such that $a'_{n}\to a$. Therefore, $a_{k_{n}}+I = a'_{n}+I\to a+I$ because the quotient map is a contraction. Since $\{a_{k_{n}}+I\}_{n}$ is a subsequence of the original Cauchy sequence $\{a_{n}+I\}_{n}$, we conclude that $\{a_{n}+I\}_{n}\to a+I$ (ref. [[Complete Metric Space#^80b2f4|proposition]]). Hence, $A/I$ is complete.  $\square$

> [!remark]-
> The topology induced from the norm on $A/I$ coincides with the [[Constructions on Topological Spaces#^d57887|quotient topology]] induced from the quotient map $q\colon A\to A/I$, $a\mapsto a+I$. In fact, we have $$q(B_{r}(a))=B_{r}(q(a)),\quad \forall a\in A, r>0.$$

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

> [!theorem] Neumann Theorem (Murphy, 1990, Theorem 1.2.2)
> Let $\A$ be a unital Banach algebra, and $a\in \A$ such that $\|a\|<1$. Then $(1-a)$ is invertible and $$(1-a)^{-1}=\sum_{n=0}^{\infty}a^{n}.$$ ^9e9db9

> [!theorem]
> Let $\A$ be a unital Banach algebra, then $\Inv(\A)$ is open in $\A$, and the mapping $\Inv(\A)\to \A$, $a\mapsto a^{-1}$ is Fréchet differentiable.
> 

> [!lemma]
> If $a$ is an element of a unital Banach algebra $\A$, then the spectrum $\sigma(a)$ is a [[Topological Spaces#^0849a0|closed subset]] of $\C$ and $|\lambda|\leq \|a\|$ for any $\lambda\in\sigma(a)$.

*Proof*  We first prove that $|\lambda|\leq\|a\|$ by contradiction. Assume $|\lambda|>\|a\|$ for some $\lambda\in\sigma(a)$. Then, by the Neumann theorem, we have $(1-\frac{a}{\lambda})$ is invertible, hence $a-\lambda \cdot 1=(1-\frac{a}{\lambda})\cdot (-\lambda)$ is also invertible. This contradicts the definition of $\sigma(a)$.
Now we show that $\sigma(a)$ is closed. Define the map $\varphi\colon \C\to A$, $\lambda\mapsto a-\lambda\cdot 1$, which is [[Continuous Maps on Topological Spaces#^33ee5a|continuous]]. Then $\C\setminus\sigma(a)=\varphi^{-1}(\Inv(A))$. Since $\Inv(A)$ is open in $A$, it follows that $\sigma(a)$ is closed in $\C$. $\square$

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
