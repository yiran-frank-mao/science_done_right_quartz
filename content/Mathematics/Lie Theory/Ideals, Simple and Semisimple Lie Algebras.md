---
tags:
  - lie-algebra
  - algebra
updated: 2025-09-28
completed: true
---
## Lie Algebra Ideals

> [!definition] Lie Algebra Ideal and Quotients
> A subspace $\newcommand{\a}{\mathfrak{a}}\a$ of a [[Lie Algebra#^5007ba|Lie algebra]] $\newcommand{\g}{\mathfrak{g}}\g$ is an *ideal*, denoted $\a \triangleleft \g$, if $[\g, \a] \subseteq \a$. That is, for any $x \in \g$ and $y \in \a$, we have $[x, y] \in \a$.
> If $\a\triangleleft\g$, then the quotient $\g/\a$ is well-defined, and $[x+\a,y+\a]:=[x,y]+\a$.

<u><b>e.g.</b></u>
1. For any homomorphism $\varphi\colon \g_1 \to \g_2$, the kernel $\ker(\varphi)$ is an ideal of $\g_1$.
2. The [[Central Extensions of Lie Algebras#^e35973|center]] of $\g$, $Z(\g) = \{x \in \g \mid [x, y] = 0 \text{ for all } y \in \g\}$, is an ideal.
3. The centralizer of a subset $S \subseteq \g$, $C_{\g}(S) = \{x \in \g \mid [x, s] = 0 \text{ for all } s \in S\}$, is an ideal if $S$ is an ideal. (This is sufficient but not necessary)
4. The commutator algebra of $\g$, $[\g, \g] = \text{span}\{[x, y] \mid x, y \in \g\}$, is an ideal.
5. For ideals $\newcommand{\b}{\mathfrak{b}}\a, \b \triangleleft \g$, their sum $\a + \mathfrak{b} = \{x + y \mid x \in \a, y \in \mathfrak{b}\}$, and their Lie bracket $[\a, \mathfrak{b}] = \text{span}\{[x, y] \mid x \in \a, y \in \mathfrak{b}\}$ are also ideals.
$\quad$

> [!definition] Simple Lie Algebras
> A [[Lie Algebra#^5007ba|Lie algebra]] $\g$ is *simple* if it has no non-trivial ideals.
> 

<u><b>e.g.</b></u>  The Lie algebra $\mathfrak{sl}_2(F) = \text{span}_F\{h, x, y\}$ with brackets $[h,x]=2x$, $[h,y]=-2y$, $[x,y]=h$ is simple provided $\text{char}(F) \neq 2$.
*Proof*  Let $\a \triangleleft \mathfrak{sl}_2(F)$ be a non-zero ideal. By the commutation relation, we know that the adjoint map $\newcommand{\ad}{\operatorname{ad}}\ad_{h}$ is diagonalizable with eigenvalues $2, 0, -2$ corresponding to eigenvectors $x, h, y$. Take any non-zero element $u = ax + by + ch \in \a$.
If $b \neq 0$, apply $\ad_x$ twice: $\ad_x(u) = bh - 2cy$ and $\ad_x^2(u) = -2bx$. Since $\text{char}(F) \neq 2$ and $b \neq 0$, this implies $x \in \a$.
Similarly, if $a \neq 0$, applying $\ad_y$ twice gives $\ad_{y}^{2}(u)=2ay$, showing $y \in \a$.
Once $x$ or $y$ is in $\a$, we have $[x,y]=h \in \a$. Then $[h,x]=2x$ and $[h,y]=-2y$ show that if one of $x, y$ is in $\a$, the other must be as well.
If $a=b=0$, then $u=ch$ with $c \neq 0$, so $0\notin\a$, yielding a contradiction. $\square$

> [!theorem] Isomorphism Theorems for Lie Algebras
> The following isomorphism theorems hold for Lie algebras, similar to those for groups and rings:
> - Suppose $\newcommand{\h}{\mathfrak{h}}\varphi\colon \g \to \h$ is a Lie algebra homomorphism, then $\newcommand{\im}{\mathrm{im}\,}\g/\ker{\varphi}\cong \im\varphi$.
> - If $\a ,\b\triangleleft \g$ and $\a \subseteq \b$ are ideals, then $(\g/\a)/(\b/\a)\cong \g/\b$.
> - If $\a ,\b\triangleleft \g$, then $\b/(\a\cap \b)\cong (\a+\b)/\a$.
> $\quad$

> [!proposition]
> If $\a\triangleleft \g$ is an ideal, then $[\a,\a]\triangleleft [\g,\g]$, and $[\g,\g]/[\a,\a]\cong [\g/\a,\g/\a]$. ^d5396d

*Proof*  Suppose $x,y\in\g$ and $z,w\in\a$, let $u=[x,y]\in[\g,\g]$, then $$[u,[z,w]]+[z,[w,u]]+[w,[u,z]]=0.$$So $[u,[z,w]]\in\a$, hence $[\a,\a]\triangleleft[\g,\g]$. Now consider the quotient map $\pi\colon \g \twoheadrightarrow \g/\a$. We have $\pi([\g,\g]) = [\g/\a,\g/\a]$ and $\pi([\a,\a]) = \{0\}$. Thus, by the first isomorphism theorem, $[\g,\g]/[\a,\a] \cong [\g/\a,\g/\a]$. $\square$

## Solvability and Semi-Simplicity

> [!definition] Derived Series and Solvability
> The *derived series* of a Lie algebra $\g$ is a sequence of ideals defined recursively as follows:
> $$ D^{0}(\g) = \g, \quad D^{k+1}(\g) = [D^{k}(\g), D^{k}(\g)]. $$
> A Lie algebra $\g$ is *solvable* if $D^N(\g) = \{0\}$ for some integer $N$. ^b49788

<u><b>e.g.</b></u>  The Borel subalgebra $\b_{n}(F)$ of $\mathfrak{gl}_n(F)$, consisting of all upper triangular matrices, is solvable.

> [!definition] Semi-Simple Lie Algebras
> A Lie algebra $\g$ is *semi-simple* if its only solvable ideal is $\{0\}$. ^476cc0

> [!proposition] Properties of Solvable Lie Algebras
> Let $\g$ be a Lie algebra.
> 1.  If $\g$ is solvable, so are its subalgebras and homomorphic images.
> 2.  If $\a \triangleleft \g$ is a solvable ideal and the quotient $\g/\a$ is solvable, then $\g$ is solvable.
> 3.  If $\a, \mathfrak{b} \triangleleft \g$ are solvable ideals, then their sum $\a+\mathfrak{b}$ is also a solvable ideal.
> $\quad$

*Proof*  
1. Suppose $\h < \g$ is a subalgebra. Then $D^k(\h) \subseteq D^k(\g)$ for all $k$. If $\g$ is solvable, then $D^N(\g) = \{0\}$ for some $N$, so $D^N(\h) \subseteq D^N(\g) = \{0\}$, hence $\h$ is solvable. If $\varphi\colon \g \to \mathfrak{k}$ is a homomorphism, then $\varphi(D^k(\g)) = D^k(\varphi(\g))$ for all $k$. If $\g$ is solvable, then $D^N(\g) = \{0\}$ for some $N$, so $D^N(\varphi(\g)) = \varphi(D^N(\g)) = \{0\}$, hence $\varphi(\g)$ is solvable.
2. Consider the quotient map $\pi\colon \g \twoheadrightarrow \g/\a$. We have $\pi(D^k(\g)) = D^k(\g/\a)$ for all $k$. If $\a$ and $\g/\a$ are solvable, then $D^M(\a) = \{0\}$ and $D^N(\g/\a) = \{0\}$ for some $M, N$. From the [[Ideals, Simple and Semisimple Lie Algebras#^d5396d|proposition]], we know that $D^{M+N}(\g)/D^{M+N}(\a) \cong D^{M+N}(\g/\a) = \{0\}$, so $D^{M+N}(\g) = D^{M+N}(\a) = \{0\}$, $\g$ is solvable.
3. We note that $\a\hookrightarrow\a+\b \twoheadrightarrow (\a+\b)/\a \cong\b/(\a\cap\b)$, so by part 2, $\a+\b$ is solvable. 

$\square$

This implies there exists a unique maximal solvable ideal in $\g$:

> [!corollary] Radical of a Lie Algebra
> For any Lie algebra $\g$, there exists a unique maximal solvable ideal in $\g$, called the *radical* of $\g$, denoted $\newcommand{\Rad}{\mathrm{Rad}}\Rad(\g)$. The quotient algebra $\g/\Rad(\g)$ is semi-simple.

## Nilpotent Lie Algebras

> [!definition] Lower Central Series and Nilpotency
> The *lower central series* of a Lie algebra $\g$ is defined recursively:
> $$ C^0(\g) = \g, \quad C^{k+1}(\g) = [\g, C^k(\g)] $$
> A Lie algebra $\g$ is *nilpotent* if $C^N(\g) = \{0\}$ for some integer $N$. ^f7e0b3

<u><b>e.g.</b></u>
- The Lie algebra of strictly upper triangular matrices is nilpotent. However, the Borel subalgebra of all upper triangular matrices is solvable but not nilpotent.
- The affine Lie algebra $\mathfrak{aff}_{1}=\operatorname{span}\{H,X\}$ with $[H,X]=X$ is solvable but not nilpotent.
$\quad$

> [!proposition]
> Nilpotency implies solvability.

*Proof:* $D^k(\g) \subseteq C^k(\g)$ for all $k \ge 1$.  $\square$

> [!proposition] Properties of Nilpotent Lie Algebras
> Let $\g$ be a Lie algebra.
> 1. Subalgebras and homomorphic images of a nilpotent Lie algebra are nilpotent.
> 2. If $\g/Z(\g)$ is nilpotent, then $\g$ is nilpotent.
> 3. If $\g$ is nilpotent and non-zero, then its center $Z(\g)$ is non-zero.
> $\quad$

*Proof*  (1) is clear, we will show (2) and (3).
(2) Let $\pi\colon \g \twoheadrightarrow \g/Z(\g)$ be the quotient map. Suppose $C^{n}(\g/Z(\g))=(0)$. Then $\pi(C^{n}(\g))=C^{n}(\g/Z(\g))=(0)$. So $C^{n}(\g) \subseteq Z(\g)$. Thus, $C^{n+1}(\g)=[\g,C^{n}(\g)] \subseteq [\g,Z(\g)]=\{0\}$. Hence, $\g$ is nilpotent.
(3) Suppose $\g$ is nilpotent, non-zero and $Z(\g) = \{0\}$. Assume that $C^{n}(\g)=(0)$. This means $C^{n-1}(\g)\subseteq Z(\g)$, so $C^{n-1}(\g)=(0)$. Repeating this argument, we get $\g=C^{0}(\g)=(0)$, a contradiction. Hence, $Z(\g)\neq\{0\}$. $\square$