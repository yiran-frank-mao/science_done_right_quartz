## Diagonalising Integral Matrices

**Thrm** _Smith Normal Form_

Let $A \in M_{m,n}(\Z)$. There exists invertible matrices $P\in\mathrm{GL}_m(\Z)$ and $Q \in \mathrm{GL}_n(\Z)$ such that $PAQ$ is diagonal with positive entries on the diagonal that $d_1 \mid d_2 \mid \dots \mid d_k$ with $k\leq m,n$. This form is unique.

## Presentation of Finitely Generated Modules

**Def** _Presentations of a Finitely Generated Module_

Let $R$ **be a ring and $φ :V →W$ **a map of finitely generated $R$-modules. Then $φ(V)$ is a submodule of $W$ **and we can form the quotient $W /φ(V )$. In particular, if $A ∈ M_{m,n} (R)$ is a matrix, it defines a map of free modules $A : R^n \to R^m$, $v \mapsto Av$ **and we can look at the quotient $V = R^m/AR^n$. We say that $V$ **is presented **by the matrix $A$.

**e.g.** $A=[4] : \Z \to \Z$ gives $\Z/4\Z$

**Thrm** Let $A:R^n\to R^m$ be in $M_{m,n}(R)$. Then the following matrices present the same quotient:

- $A^\prime = QAP$ in [Smith Normal Form](https://www.notion.so/Week-12-Presentation-of-Finitely-Generated-Modules-6b6964be24bb4fc9a31b21bc7e1c1525?pvs=21) with $Q\in \mathrm{GL}_{m}(R)$ and $P\in \mathrm{GL}_{m}(R)$
- $B$ obtained from $A$ by deleting a column of zeros
- $B$ obtained from $A$ by removing the $i$th row and $j$th column if the $j$th column is the standard basis element $e_i$

**Proof** Suppose we have $A\in M_{m,n}(R)$ and $A^\prime =QAP$ is in the Smith Normal Form. Then

$$ A^\prime R^n=QA(PR^n)=QA(R^n)=Q(AR^n)=AR^n $$

as $P$ and $Q$ are invertible, thus preserve the module.

**Corollary** Any presentation of a finitely generated module in the form of $R^m/AR^n$ can be written as $R^m/AR^n=R^m/A^\prime R^n = R/(d_1) \oplus R/(d_2) \oplus \dots\oplus R/(d_k) \oplus R^{m-k}$

**Thrm** Suppose $R$ is a principle integral domain(PID), then for all finitely generated $R$-module $V$, there exists $A\in M_{m,n}(R) \cong R^n \to R^m$ such that $V=R^m / AR^n$

## Noetherian Rings

**Def** _Noetherian Ring_

A ring is called noetherian if every ideal is finitely generated.

**Prop** Every PID is noetherian.

**Prop** Let $R$ be a ring, and $M\leq N$ be $R$-modules. Then if $M$ and $N/M$ are finitely generated so is $M$.

**Prop** Let $R$ be a noetherian ring. Every submodule of a finitely generated $R$-module $N$ is finitely generated.

**Prop** Let $R$ be a PID. A submodule $M$ of a finitely generated free module $N$ over a $R$ is free and $\operatorname{rank}(M ) ≤ \operatorname{rank}(N )$.

## Structure Theorem

**Thrm** _Structure of Finitely Generated Modules over PID_

Let $R$ be a PID and $M$ a finitely generated $R$-module. There exist $k,r ∈\N_0$ and $d_1 \mid d_2 \mid\dots\mid d_k$ all non-zero in $R$ such that

$$ M \cong R/(d_1)⊕\dots⊕R/(d_k)⊕R^r $$

Moreover, $m, k$ and the ideals $(d1) ⊃ \dots ⊃ (dk )$ are uniquely determined.

**Def** _Euclidean Ring_

A domain $R$ **is called euclidean if it is equipped with a map $δ : R \backslash \{0\} \to \N_0$, called a degree function, such that

1. $δ(f ) ≤ δ(f g)$ for all non-zero elements $f,g ∈ R$
2. For all $f , g ∈ R$ **with $f \neq 0$, there exist $q , r ∈ R$ **with $g = q f + r$, where either $r = 0$ or $δ(r) < δ(f )$.

**e.g.** $\Z$ with $δ(·) = | · |$, $F[x]$ with $δ = \deg$, and $\Z[i]$ with $δ(a +bi) = a^2 +b^2$, are all euclidean rings.

**Prop** Every euclidean ring is a PID.

**Thrm** _Structure Theorem for Finitely Generated Abelian Groups_

Let $G$ be a finitely generated abelian group. There exist $k,r ∈\N_0$ and positive integers $d_1 \mid d_2 \mid\dots\mid d_k$ such that

$$ G\cong \Z_{d_1} \times \Z_{d_2} \times \dots \times \Z_{d_k} \times \Z^r $$

**Corollary** _Structure of Linear Operators on Finite Dimensional Vector Spaces_

Let $T : V → V$ be an operator on an $n$-dimensional space over a field $F$. There exist monic polynomials $d_1(x) \mid d_2(x) \mid \dots \mid d_k (x)$ uniquely determined such that

$$ V=W_1 \oplus W_2 \oplus\dots \oplus W_k

$$

is a $T$-invariant decomposition with $W_i$ cyclic with $d_i(x)$ the characteristic polynomial of $T\big|_{W_i}$