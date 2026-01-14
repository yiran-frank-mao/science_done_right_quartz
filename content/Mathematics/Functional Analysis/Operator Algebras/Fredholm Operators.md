---
created: 2025-10-09
updated: 2025-10-09
tags:
  - functional-analysis
  - operator-theory
  - fredholm-operators
  - toeplitz-operators
  - winding-number
completed: true
---
## Fredholm Operators

> [!definition] Fredholm Operator
> Let $\newcommand{\H}{\mathcal{H}}\H$ be a [[Hilbert Spaces#^ae0212|Hilbert space]]. A [[Orthogonality and Bounded Linear Maps#^f95b62|bounded linear operator]] $T\colon \H \to \H$ is said to be *Fredholm* if:
> 1.  $\operatorname{im}(T)$ is a closed subspace of $\H$.
> 2.  $\ker(T) = \{x \in \H : Tx = 0\}$ is finite-dimensional.
> 3.  $\operatorname{coker}(T) = \H / \operatorname{im}(T)$ is finite-dimensional.
> $\quad$ ^def-fredholm

> [!definition] Index of a Fredholm Operator
> The *index* of a Fredholm operator $T$ is defined as the integer:
> $$ \text{ind}(T) = \dim(\ker T) - \dim(\text{coker} T). $$
> Since $\text{Ran}(T)$ is closed, we have $\H = \text{Ran}(T) \oplus (\text{Ran} T)^\perp$ and $(\text{Ran} T)^\perp = \ker(T^*)$. Thus, $\text{coker}(T) \cong \ker(T^*)$, and the index can be written as:
> $$ \text{ind}(T) = \dim(\ker T) - \dim(\ker T^*) $$ ^def-index

<u><b>e.g.</b></u>
* Let $S$ be the unilateral shift operator on $\ell^{2}(\mathbb{N})$. Then $S$ is Fredholm and $\text{ind}(S) = -1$.
* If an operator $T$ is invertible, then it is Fredholm and $\text{ind}(T) = 0$.
* If $K$ is a compact operator, then $I+K$ is a Fredholm operator.
$\quad$

> [!theorem] Atkinson's Lemma
> An operator $T \in B(\H)$ is Fredholm if and only if it is invertible modulo the compact operators. That is, there exist operators $L, R \in B(\H)$ such that:
> $$ LT = I + K_L \quad \text{and} \quad TR = I + K_R $$
> for some compact operators $K_L, K_R \in K(\H)$. ^atkinson-lemma

*Proof*
($\Leftarrow$) Suppose such $L$ and $R$ exist.
1.  **Range:** $\text{Ran}(T) \supset \text{Ran}(TR) = \text{Ran}(I+K_R)$. Since $I+K_R$ is Fredholm, its range is closed and has finite codimension. Therefore, $\text{Ran}(T)$ must also be closed and have finite codimension.
2.  **Kernel:** $\ker(T) \subset \ker(LT) = \ker(I+K_L)$. Since $K_L$ is compact, $\dim(\ker(I+K_L)) < \infty$, which implies $\ker(T)$ is finite-dimensional.

Thus, $T$ is Fredholm.
($\Rightarrow$) If $T$ is Fredholm, its restriction $T|_{(\ker T)^\perp}: (\ker T)^\perp \to \text{Ran}(T)$ is a continuous bijection , and thus has a continuous inverse $G: \text{Ran}(T) \to (\ker T)^\perp$. Extend $G$ to all of $H$ by defining it to be $0$ on $(\text{Ran} T)^\perp = \ker(T^*)$. One can then verify that $GT = I - P_{\ker T}$ and $TG = I - P_{\ker(T^*)}$. Since $\dim(\ker T) < \infty$ and $\dim(\ker T^*) < \infty$, the projection operators $P_{\ker T}$ and $P_{\ker(T^*)}$ are finite-rank and therefore compact. $\square$

## The Calkin Algebra

> [!definition] Calkin Algebra
> The set of all compact operators $K(\H)$ on a [[Hilbert Spaces#^ae0212|Hilbert space]] $\H$ forms a closed, two-sided $*$-ideal in the [[C*-Algebras#^e4fdc6|C*-algebra]] of bounded operators $B(H)$. The quotient algebra $B(\H) / K(\H)$ is called the *Calkin algebra*. We denote the canonical quotient map by $\pi\colon B(\H) \to B(\H) / K(\H)$.

> [!corollary]
> An operator $T \in B(\H)$ is Fredholm if and only if its image $\pi(T)$ is invertible in the Calkin algebra $B(\H)/K(\H)$.

## Properties of the Index

> [!theorem] Index of a Product
> If $S, T \in B(\H)$ are Fredholm operators, then the product $ST$ is also Fredholm, and its index is the sum of the indices:
> $$ \text{ind}(ST) = \text{ind}(S) + \text{ind}(T) $$ ^index-product

> [!proposition] Topological Properties
> The set of Fredholm operators $F(\H)$ is an open subset of $B(\H)$.
> The index map $\operatorname{ind}\colon F(H) \to \mathbb{Z}$ is continuous.

*Proof*  The Calkin algebra $B(\H)/K(\H)$ is a Banach algebra, so its group of invertible elements is open. Since $F(\H) = \pi^{-1}(\text{Inv}(B(\H)/K(\H)))$ and the quotient map $\pi$ is continuous, $F(\H)$ is the continuous preimage of an open set and is therefore open.
To show continuity of the index, we can show it is locally constant. For any $T \in F(\H)$, there exists a neighborhood where the index is constant. If $S$ is an inverse of $T$ modulo compacts, then for any $R$ with $\|T-R\| < \|S\|^{-1}$, the operator $SR$ is invertible. Since invertible operators have index 0, we get $\text{ind}(S) + \text{ind}(R) = \text{ind}(SR) = 0$, which implies $\text{ind}(R) = -\text{ind}(S) = \text{ind}(T)$. $\square$

> [!corollary] Invariance under Compact Perturbations
> If $T$ is a Fredholm operator and $K$ is a compact operator, then $T+K$ is also Fredholm and:
> $$ \operatorname{ind}(T+K) = \operatorname{ind}(T). $$ ^index-compact-perturbation

*Proof*  Consider the path $\alpha\colon [0, 1] \to \mathbb{Z}$ defined by $\alpha(t) = \text{ind}(T+tK)$. The map $t \mapsto T+tK$ is continuous, and the index map is continuous, so their composition $\alpha$ is continuous. Since $[0,1]$ is connected, its image $\alpha([0,1])$ must be a connected subset of $\mathbb{Z}$. The only connected subsets of $\mathbb{Z}$ are single points, so $\alpha$ must be a constant function. Therefore, $\text{ind}(T+K) = \alpha(1) = \alpha(0) = \text{ind}(T)$. $\square$

## Relationship with Toeplitz Operators

> [!proposition]
> A [[Toeplitz Operators#^04cb08|Toeplitz operator]] $T_{\varphi}$ with continuous symbol is Fredholm if and only if its symbol $\varphi \in C(S^{1})$ is invertible (i.e., $\varphi(z) \neq 0$ for all $z \in S^{1}$). ^fredholm-toeplitz

*Proof*  $T_\varphi$ is Fredholm iff $\pi(T_\varphi)$ is invertible in the Calkin algebra. There exists a $*$-isomorphism from $C(S^{1})$ onto a subalgebra of the Calkin algebra that maps $\varphi \mapsto \pi(T_\varphi)$. By spectral permanence, $\pi(T_\varphi)$ is invertible in the Calkin algebra iff it is invertible in this subalgebra , which is true iff $\varphi$ is invertible in $C(S^{1})$. $\square$

> [!lemma]
> If $\varphi \in C(S^{1})$ is an invertible function, then there exists a unique integer $n \in \mathbb{Z}$ such that $\varphi$ can be written in the form:
> $$ \varphi = e_n e^\psi $$
> where $e_n(z) = z^n$ and $\psi \in C(S^{1})$. Moreover, this $n$ is the [[The Argument Principle#^03d006|winding number]] $\operatorname{wn}(\varphi)$ of $\varphi$. ^winding-number-lemma

> [!theorem] Index of a Toeplitz Operator
> If $\varphi \in C(S^{1})$ is invertible, then the Toeplitz operator $T_\varphi$ is Fredholm and its index is given by the negative of the [[The Argument Principle#^03d006|winding number]] of its symbol:
> $$ \text{ind}(T_\varphi) = -\operatorname{wn}{wn}(\varphi) $$ ^index-toeplitz

*Proof*  First, one shows that if $\psi \in C(\mathbb{T})$ and $\varphi = e^\psi$, then $T_\varphi$ is invertible, which implies $\text{ind}(T_\varphi) = 0$.
Now, let $\varphi$ be any invertible symbol. By the [[#^winding-number-lemma|lemma]], we can write $\varphi = e_n e^\psi$, where $n = \text{wn}(\varphi)$.
The operator $T_\varphi - T_{e_n} T_{e^\psi}$ can be shown to be compact. By the [[#^index-compact-perturbation|invariance of index under compact perturbations]] and the [[#^index-product|index of a product property]], we have:
$$ \text{ind}(T_\varphi) = \text{ind}(T_{e_n} T_{e^\psi}) = \text{ind}(T_{e_n}) + \text{ind}(T_{e^\psi}) $$
Since $T_{e^\psi}$ is invertible, its index is 0. A direct calculation shows $\text{ind}(T_{e_n}) = -n$.
Therefore,
$$ \text{ind}(T_\varphi) = \text{ind}(T_{e_n}) + 0 = -n = -\text{wn}(\varphi) $$
$\square$

<u><b>e.g.</b></u>  Suppose $\varphi(z)=z^{-1}(z^{-1}+3)$. Note that $z\mapsto z^{-1}$ has winding number $-1$ and $z\mapsto z^{-1}+3$ has winding number $0$ (because it has a pole of order one at $0$, and a zero of order one at $-1/3$, so [[The Argument Principle#^9a9257|the argument principle]] applies). Thus, $\operatorname{wn}(\varphi)=-1+0=-1$, and the index of the Toeplitz operator $T_{\varphi}$ is $\text{ind}(T_{\varphi})=-\text{wn}(\varphi)=1$.
