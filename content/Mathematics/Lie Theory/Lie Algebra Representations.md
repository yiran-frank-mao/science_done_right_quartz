> [!definition] Representation of Lie Algebras
> Let $\newcommand{\g}{\mathfrak{g}}\g$ be a Lie algebra over a field $F$. A representation of $\g$ on a [[Vector Spaces#^f4b63e|vector space]] $V$ is a Lie algebra homomorphism $\newcommand{\gl}{\mathfrak{gl}}\rho\colon \g\to \gl(V)$ where $\gl(V)$ is the [Lie algebra of all linear endomorphisms on $V$](Lie%20Algebra#^d72504). ^df3ff7

## Weights and Maximal Vectors

> [!definition] Weight
> Let $(\pi, V)$ be a representation of a Lie algebra $\g$ over a field $F$. Then a vector $v\in V$ is said to have *weight* $\lambda$ if

## Classification of Representations

> [!proposition]
> The [[Lie Algebra#^5007ba|Lie algebra]] $\newcommand{\sl}{\mathfrak{sl}}\sl_{2}(\C)$ has precisely one irreducible representation of dimension $m$ for every $m ∈ \N$. ^566e35

*Proof*  Let us use the standard basis of $\sl_{2}(\C)$: $$[h,x]=2x, \quad [h,y]=-2y, \quad [x,y]=h.$$Suppose $\newcommand{\End}{\operatorname{End}}\rho\colon \sl_{2}(\C)\to \End(V)$ is an irreducible representation. The commutation relation above immediately implies that $\ad_{h}$ is diagonalisable, so by [[Jordan-Chevalley Decomposition#^cd64a6|theorem]], $\rho(h)$ is always diagonalizable. Hence $V$ is a direct sum of weight spaces: $$V=\bigoplus_{\lambda}V_{\lambda}.$$Note that the commutation relations imply that $\rho(x)$ raises weights by 2, while $\rho(y)$ lowers weights by 2. $V$ is finite dimensional, so only finitely many $V_{\lambda}$ can be nontrivial. Let $\mu$ be the highest weight such that $V_{\mu}\neq0$ but $V_{\mu+2}=\{0\}$. Let $v_{0}$ be the highest weight vector, $v_{-1}=0$ and $v_{j}=\frac{1}{j!}\rho(y)^{j}(v_{0})$. Then we observe the following:
- $\rho(h)v_{i} = (\mu-2j) v_{j}$
- $\rho(y)v_{j} = (j+1)v_{j+1}$
- $\rho(x)v_{j} = (\mu - j + 1)v_{j-1}$

Now let $m$ be the smallest integer such that $v_{m}\neq 0$ but $v_{m+1}=0$. Consider $$W_{m}:=\operatorname{span}\{v_{0},\dots,v_{m}\}\subset V.$$Then $(\rho, W_{m})$ is a subrepresentation of $(\rho, V)$. Since $(\rho, V)$ is irreducible, $W=V$. Thus, $\{v_{0},\dots,v_{m}\}$ forms a basis of $V$, and $\dim V = m+1$. $\square$

<u><b>e.g.</b></u>  Here are some concrete examples:
- $\dim V=1$. The trivial representation with $\rho$ being the zero map.
- $\dim V=2$. The standard representation on $V=\C^{2}$ given by inclusion $\rho\colon\sl_{2}(\C)\hookrightarrow \gl_{2}(\C)$.
- $\dim V=3$. This is isomorphic to the adjoint representation $\ad\colon \sl_{2}(\C)\to \gl(\sl_{2}(\C))$.
$\quad$

> [!theorem] Weyl's Theorem
> Let $\g$ be a [[Ideals, Simple and Semisimple Lie Algebras#^476cc0|semisimple]] Lie algebra over $\mathbb{C}$, with a finite dimensional representation $(\rho, V)$. Then $V$ is expressable as a direct sum of irreducible representations $V=V_{1} \oplus \cdots \oplus V_{k}$. 
> That is, the category of representations of semisimple Lie algebras is a semisimple category.
> 
