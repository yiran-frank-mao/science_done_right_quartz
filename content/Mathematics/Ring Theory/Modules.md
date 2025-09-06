> Modules for rings are what vector spaces for fields.

> [!definition] Module
> Let $R$ be a (possibly non-commutative) ring. A (left) $R$-module is an abelian group $M$ with addition $+$ and scalar multiplication $R × M → M$, written $(r,m) \mapsto rm$ such that 
> - $1m=m$
> - $(r_1+r_2)m=r_1m+r_2m$
> - $r(m_1+m_2)=rm_1+rm_2$
> - $r_1(r_2 m)=(r_1r_2)m$
>
> for all $r,r_1,r_2 \in R$ and $m, m_1, m_2\in M$. 
> We say that $M$ is a right $R$-module if the last axiom is replaced by $r_2r_1(m)=(r_1 r_2)m$, equivalent to $(mr_1)r_2=m(r_1 r_2)$ under scalar multiplication  $M \times R → M$. ^697aa9

> [!proposition]
> Every (left) ideal in a ring $R$ is a (left) $R$-module.

**Prop**  Any abelian group $A$ is a $\Z$-module.
**Proof**  Suppose $(A,+)$ is an abelian group we can define for $n\in \Z$ and $a\in A$ that $$na := \begin{cases}\underbrace{a+\dots+a}_{n \text{ times}} \quad & n\geq0\\ -((-n)a) \quad &n<0\end{cases} $$This makes $A$ a $\Z$-module.

**Prop** Linear operators are related to $F[x]$-modules. Let $T : V → V$ be a linear operator on a finite dimensional vector space over field $F$ . Then $V$ is an $F [x ]$-module by setting $$\begin{aligned}f(x) \cdot v = (f(T))(v) =(a_{0} +a_{1}T+\dots+a_{n}T^{n})(v)\\ \text{for all }f(x)=a_0 +a_1x+\dots+a_nx^n \in F[x]\end{aligned}$$

> [!definition] Submodule
> Let $R$ be a ring and $M$ an $R$-module. A subgroup $N \leq M$ is a submodule of $M$ if $RN ⊂ N$. The quotient $M /N$ has a structure of an $R$-module, namely quotient module: $$r(m+N):=rm+N$$

<b><u>e.g.</u></b>  $\Z_n = \Z / n\Z$.

**Def**  <i><u>$R$-module Homomorphism</u></i>
Let $R$ be a ring and $M , N$ left $R$-modules. An $R$-module homomorphism $\varphi : M → N$ is a group homomorphism such that $φ(r m) = r φ(m)$ for all $r ∈ R$ and $m ∈ M$.

**Prop**  The kernel and image of an $R$-module homomorphism are submodules.

**Def**  <i><u>Canonical Map</u></i>
Let $R$ be a ring and $N$ a submodule of an $R$-module $M$. Then the canonical map $π:M →M/N,m\mapsto m+N$, is a surjective ring homomorphism with kernel $N$.

**Thrm**  <i><u>Mapping Property</u></i>
Let $R$ be a ring and $N$ a submodule of an $R$-module $M$. Let $φ : M → M^\prime$ be a homomorphism of $R$-modules with kernel $K$containing $N$. There is a unique homomorphism $\bar{\varphi}:M/N →M^\prime$ such that $\bar{\varphi}=φ◦π$, where $\pi$ is the canonical map.

**Thrm**  <i><u>First Isomorphism Theorem</u></i>
If $φ : M → M^\prime$ is a surjective homomorphism of $R$-modules with kernel $N$ then $\bar{\varphi}:M/N →M^\prime$ is an isomorphism.

**Thrm**  <i><u>Correspondence Theorem</u></i>

**Prop**  Let $R$ be a ring and $I$ an ideal. Let $M$ be an $R$-module. Then $I M$ is an $R$-submodule of $M$ and $M /I M$ is an $R/I$-modules.
**Proof**

**Def**  <i><u>Finitely Generated Module</u></i> and <i><u>Basis</u></i>
A module $M$ is finitely generated if there exists $m_1, \dots , m_k ∈ M$ such that every element of $M$ has the form $r_1m_1 +···+r_km_k$ for some $r_i ∈R$. elements $m_1,\dots,m_k ∈M$ are called independent if $r_1m_1+\dots+r_km_k =0$ implies that all $r_i=0$. An independent generating set is called a basis.

**Def**  <i><u>Cyclic Module</u></i>
An $R$-module $M$ is called cyclic if there exists $m ∈ M$ such that $M = Rm$.

## Free Modules

**Prop**  If $F$ is a field, we know that all modules are free and $F^n  \cong F^m$ iff $m = n$.

**Def**  <i><u>Invariant Base Number</u></i> and <i><u>Rank</u></i>
Rings $R$ with the property that $R^n \cong  R^m \iff n=m$ are called rings with invariant base number (IBN). The exponent in $R^n$ is called the rank of the free module.

**Prop**  Commutative rings are IBN.

**Def**  <i><u>Free Modules</u></i>
Let $R$ be a ring with IBN. An $R$-module $M$ is free of rank $n$ if $M  \cong  R^n$. If $\{ m_1,\dots,m_n \} \subset M$ is independent and generating then $M \cong R^n$. Indeed,$$
\varphi : (r_1,\dots,r_n) \mapsto
\sum_{i=1}^n r_im_i$$is an $R$-module isomorphism.

**Def**  <i><u>General Linear Map over Ring</u></i>
The general linear group over some ring $R$ is$$
\mathrm{GL}_n(R)= \{ 
A \in M_n(R) \mid \exists B \in M_n(R), AB=BA=I_n
 \}$$

**Prop**  Let $R$ be a non-zero (commutative unital) ring and $A \in M_n(R)$. The following are equivalent:
1. $A$ has right inverse
2. $A$ has left inverse
3. $A$ is invertible
4. $\det(A) \in R^{\times}$

**Prop**  Let $R$ be a commutative unital ring. Every $R$-module map $\varphi :R^n \to R^m$ is given by a multiplication with some matrix $A \in M_{m,n}(R)$.
**Proof**  Think of $R^m$ and $R^n$ as column vectors, let $A=[\varphi(e_1)\dots\varphi(e_n)]$, then $\phi(m)=Am$.