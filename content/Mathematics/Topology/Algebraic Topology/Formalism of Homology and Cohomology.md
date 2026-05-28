---
created: 2025-10-07
updated: 2025-10-22
tags:
  - algebraic-topology
  - homology
  - category-theory
  - cohomology
  - functors
completed: true
---
## Homology with Coefficients

> [!definition] Chain Complex with Coefficients
> Let $X$ be a [[Topological Spaces#^65c94a|topological space]] and $G$ be an [[Groups, Order and Subgroups#^6d511a|abelian group]], which we call the *coefficient group*. The *singular chain group of $X$ with coefficients in $G$* is defined as the free $G$-module with basis as the set of singular $n$-simplices in $X$.
> $$C_n(X; G) := G\{\sigma: \Delta^n \to X\}$$
> An element of $C_n(X; G)$ is a finite formal sum of the form $\sum_{i} g_i \sigma_i$, where $g_i \in G$ and $\sigma_i: \Delta^n \to X$ are singular $n$-simplices.
> The usual boundary map $d_{n}\colon C_n(X) \to C_{n-1}(X)$ extends $G$-linearly to a boundary map $d_{n}\colon C_n(X; G) \to C_{n-1}(X; G)$ by defining:
> $$\partial\left(\sum_i g_i \sigma_i\right) = \sum_i g_i (\partial\sigma_i).$$
> Since $d^{2} = 0$ still holds, $(C_*(X;G), \partial)$ forms a chain complex.

> [!definition] Homology with Coefficients
> The *$n$-th homology group of $X$ with coefficients in $G$*, denoted $H_n(X; G)$, is the $n$-th homology group of the chain complex $(C_*(X;G), d)$:
> $$H_n(X; G) = \frac{\ker(d_{n}\colon C_n(X;G) \to C_{n-1}(X;G))}{\mathrm{im}(d_{n+1}\colon C_{n+1}(X;G) \to C_n(X;G))}$$

<u><b>e.g.</b></u>
- The "usual" singular homology is simply homology with integer coefficients. $H_n(X) = H_n(X; \mathbb{Z})$.
- The reduced homology of the $n$-sphere with coefficients in $G$ is: $$\tilde{H}_k(S^n; G) \cong  \begin{cases} G & k=n \\ 0 & k \neq n  \end{cases}$$
- Using the cellular chain complex for $\newcommand{\RP}{\mathbb{R}\mathrm{P}}\RP^n$ with coefficients in $\mathbb{Z}/2\mathbb{Z}$, we find: $$ H_{k}(\RP^{n}; \mathbb{Z}/2\mathbb{Z}) \cong \begin{cases}\mathbb{Z}/2\mathbb{Z} & 0 \le k \le n \\ 0 & \text{else} \end{cases}$$
- Popular choices for the coefficient group $G$ include:
	- $\mathbb{Z}/p\mathbb{Z}$ for a prime $p$.
    * The field of rational numbers $\mathbb{Q}$.
    * The $p$-adic integers $\mathbb{Z}_p$.
$\quad$

## Naturality and Splitting

> [!proposition]
> The connecting homomorphism $\partial_{n}\colon H_n(X, A) \to H_{n-1}(A)$ in the long exact sequence of a pair is a natural transformation between the functors $H_n(-, -)$ and $H_{n-1}(-)$ from the category of pairs of spaces $\mathsf{Pair}$ to the category of abelian groups $\mathsf{Ab}$.

> [!proposition] Splitting via Retraction
> If $(X, A)$ is a pair and there exists a retraction $r: X \to A$ (i.e., a map such that $r \circ i = \text{id}_A$ where $i: A \hookrightarrow X$ is the inclusion), then the long exact sequence of the pair splits.
> The map $i_*\colon H_n(A) \to H_n(X)$ is injective, and we have a split short exact sequence for each $n$:
> $$0 \to H_n(A) \to H_n(X) \to H_n(X,A) \to 0$$
> This implies that the homology of $X$ decomposes into a direct sum:
> $$H_n(X) \cong H_n(A) \oplus H_n(X, A)$$

## Axiomatic Approach

The properties of singular homology can be distilled into a set of axioms, known as the *Eilenberg-Steenrod axioms*.

> [!definition] Homology Theory
> A *homology theory* $H$ is a sequence of [[Functoriality and Naturality#^653948|functors]] $H_{n}\colon \mathsf{Pair} \to \mathsf{Ab}$ for $n \in \mathbb{Z}$, equipped with [[Functoriality and Naturality#^d73db0|natural transformations]] $\partial_{n}\colon H_{n}(X,A) \to H_{n-1}(A)$, satisfying the following axioms:
> 1.  Homotopy Invariance: If $f \simeq g: (X, A) \to (Y, B)$, then $H_{n}(f) = H_{n}(g)$.
> 2.  Excision: For any $U \subset A$ such that $\bar{U} \subset \text{int}(A)$, the inclusion $i\colon (X \setminus U, A \setminus U) \to (X,A)$ induces an isomorphism $H_{n}(i)\colon H_{n}(X \setminus U, A \setminus U) \cong H_{n}(X, A)$.
> 3.  Long Exact Sequence: For any pair $(X, A)$, there is a [[Abelian Categories#^0c5eb9|long exact sequence]]:
>    $$ \cdots \to H_{n}(A) \to H_{n}(X) \to H_{n}(X,A) \xrightarrow{\partial_n} H_{n-1}(A) \to \cdots $$
> 4.  Additivity: If $X$ is a disjoint union $X = \coprod_\alpha X_\alpha$, then the inclusion maps $i_\alpha\colon X_\alpha \to X$ induce an isomorphism $\bigoplus_\alpha H_{n}(i_\alpha): \bigoplus_\alpha H_{n}(X_\alpha) \cong H_{n}(X)$.
>
> If, in addition, the theory satisfies the Dimension Axiom:
> $$H_{n}(\{*\}) \cong \begin{cases} G & n=0 \\ 0 & n \neq 0 \end{cases}$$ for some abelian group $G$, then it is called an *ordinary homology theory*.

> [!remark]+
> $H_{n}(X)$ abbreviates $H_{n}(X, \emptyset)$.
>

> [!theorem] Uniqueness of Homology
> If $H'$ is an ordinary homology theory with $H'_{0}(\{*\}) \cong G$, then there is a natural isomorphism $H_{n}'(X, A) \cong H_n(X, A; G)$ for any CW pair $(X, A)$.

*Proof Sketch*: The proof relies on showing that the axioms uniquely determine the homology of CW complexes. One shows that singular homology $H_*( - ; G)$ satisfies the axioms. Then, for any other theory $h_*$ satisfying the axioms, one builds a natural isomorphism to $H_*( - ; G)$ inductively over the skeletal filtration of a CW complex, using the Five Lemma at each step.

## Cohomology

The central idea of cohomology is to "dualize" the constructions of homology by applying a $\mathrm{Hom}$ functor, which flips the direction of most of the maps involved.
To make this precise, we first recall the notion of an opposite category:

![[Constructions on Categories#^a77bf6]]

> [!definition] Cohomology Theory
> A *cohomology theory* consists of a sequence of [[Functoriality and Naturality#^653948|functors]] $H^{n}\colon \mathsf{Pairs} \to \mathsf{Ab}$ for each $n \in \mathbb{Z}$ , and a sequence of [[Functoriality and Naturality#^d73db0|natural transformations]] $\partial^{n}\colon H^n(A) \to H^{n+1}(X,A)$ called the *connecting homomorphisms*, satisfying the following axioms:
> 1.  Homotopy Invariance: If $f \simeq g$, then the induced maps are equal, $f^* = g^*$.
> 2.  Excision: The inclusion $(X \setminus U, A \setminus U) \hookrightarrow (X,A)$ induces an isomorphism in cohomology.
> 3.  Additivity: For a disjoint union of spaces, $H^{n}(\coprod_{\alpha} X_{\alpha}) = \bigoplus_\alpha H^{n}(X_{\alpha})$.
> 4.  Long Exact Sequence: For any pair $(X,A)$, there is a long exact sequence in cohomology:
> $$\dots \to H^{n}(X,A) \to H^n(X) \to H^{n}(A) \xrightarrow{\partial^{n}} H^{n+1}(X,A) \to \dots$$
> $\quad$

> [!remark] Why study cohomology?
> - It is another algebraic invariant of topological spaces, which sometimes contains different information than homology.
> - The direct sum of cohomology groups, $H^*(X) = \bigoplus_i H^i(X)$, can be given the structure of a graded ring via the cup product: $H^i(X) \times H^j(X) \to H^{i+j}(X)$. A continuous map $f: X \to Y$ induces a ring homomorphism $f^*: H^*(Y) \to H^*(X)$.
> - Poincaré Duality, a deep result for manifolds, relates the homology of a space to its cohomology.