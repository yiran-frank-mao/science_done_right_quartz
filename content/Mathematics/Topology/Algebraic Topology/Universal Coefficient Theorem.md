---
completed: true
updated: 2025-10-23
created: 2025-10-23
---
In [[Projective Resolution of Modules]], we've introduced enough homological algebras. Now we can state and prove the Universal Coefficient Theorem, which relates homology and cohomology via the $\operatorname{Ext}$ and $\operatorname{Hom}$ functors.

> [!theorem] Universal Coefficient Theorem
> Let $C$ be a chain complex of free abelian groups  and $G$ be an [[Groups, Order and Subgroups#^6d511a|abelian group]]. Then for each $n$, there is a [[Abelian Categories#^0c5eb9|short exact sequence]]:
> $$\newcommand{\Ext}{\operatorname{Ext}}\newcommand{\Hom}{\operatorname{Hom}} 0 \to \Ext(H_{n-1}(C,\Z), G) \to H^n(C;G) \to \Hom(H_{n}(C,\Z), G) \to 0$$
> This sequence splits, but the splitting is not natural. ^2162f3

*Proof Sketch*
1.  For the chain complex $C = \{C_n, d_n\}$, we have the cycles $Z_n = \ker d_n$ and boundaries $B_n = \text{im } d_{n+1}$. By definition, the homology is $H_n = Z_n / B_n$.
2.  These groups fit into two short exact sequences for each $n$:
    -   $0 \rightarrow B_n \rightarrow Z_n \rightarrow H_n \rightarrow 0$ (from the definition of homology)
    -   $0 \rightarrow Z_n \rightarrow C_n \rightarrow B_{n-1} \rightarrow 0$ (from the definition of cycles and boundaries)
3.  Since $C_n$ is a free abelian group, its subgroup $B_{n-1}$ must also be free. Because $B_{n-1}$ is a free (and thus projective) module, the second sequence $0 \rightarrow Z_n \rightarrow C_n \rightarrow B_{n-1} \rightarrow 0$ splits.
4.  Applying the functor $\Hom(-, G)$ is contravariant and left-exact. Applying it to the split sequence from step 3 gives a split short exact sequence of cochain complexes: $$0 \longleftarrow \Hom(Z_n, G) \longleftarrow \Hom(C_n, G) \longleftarrow \Hom(B_{n-1}, G) \longleftarrow 0$$
5.  A short exact sequence of cochain complexes induces a long exact sequence in cohomology. This gives: $$\dots \rightarrow H^{n-1}(\Hom(B,G)) \rightarrow H^n(\Hom(Z,G)) \rightarrow H^n(C;G) \rightarrow H^n(\Hom(B,G)) \rightarrow \dots$$
6.  By analyzing the differentials and applying the long exact sequence for Ext derived from the sequence $0 \rightarrow B_n \rightarrow Z_n \rightarrow H_n \rightarrow 0$, one can identify the terms in the long exact sequence from step 5. This process yields the short exact sequence stated in the theorem.
7.  To show the sequence splits, one constructs a splitting map $\alpha\colon \Hom(H_n(C), G) \to H^n(C;G)$. This is done by choosing a splitting $s_{n}\colon C_n \to Z_n$ of the sequence in step 3. For any homomorphism $\varphi\colon H_{n}(C) \to G$, the composition $\varphi \circ q \circ s_n: C_n \to G$ (where $q\colon Z_n \to H_n(C)$ is the quotient map) defines a cocycle whose cohomology class gives the desired splitting.

$\square$

> [!remark]+
> For finitely generated abelian groups, $\operatorname{Hom}(-,\mathbb{Z})$ detects only the free part, while $\operatorname{Ext}(A,\mathbb{Z})$ is naturally isomorphic to the torsion subgroup of $A$. Thus,
> $$H^{n}(X;\mathbb{Z})\cong\big(\text{free part of }H_{n}(X;\mathbb{Z})\big)\oplus\big(\text{torsion part of }H_{n-1}(X;\mathbb{Z})\big)$$
> In other words, going from homology to  cohomology moves the torsion up one dimension, the opposite is true when going from cohomology to homology.

## Properties of the Ext Functor

> [!lemma]
> The [[Projective Resolution of Modules#^4c2101|Ext functor]] has the following properties:
> 1. $\Ext(M_1 \oplus M_2, N) \cong \Ext(M_1, N) \oplus \Ext(M_2, N)$
> 2. $\Ext(M, N_1 \oplus N_2) \cong \Ext(M, N_1) \oplus \Ext(M, N_2)$
> 3. $\Ext(\mathbb{Z}, N) = 0$ for any [[Groups, Order and Subgroups#^6d511a|abelian group]] $N$.
> 4. $\Ext(\mathbb{Z}/n\mathbb{Z}, N) \cong N/nN$.
> 5. $\Ext(\Z/n, \Z/m)\cong \Z/\gcd(m,n)$
> $\quad$

<u><b>e.g.</b></u>  We compute the cohomology groups $\newcommand{\RP}{\mathbb{R}\mathrm{P}}H^{n}(\RP^5; \Z/2)$ using the Universal Coefficient Theorem. Since the sequence splits, $H^n(\RP^5; \mathbb{Z}_2) \cong \Ext(H_{n-1}(\RP^5), \mathbb{Z}_2) \oplus \Hom(H_n(\RP^5), \mathbb{Z}_2)$. We compute the two terms for each $n$. The calculation is summarized in the following table:

| $n$ |  $H_n(\RP^5)$  | $\Hom(H_n, \mathbb{Z}/2)$ |           $\Ext(H_{n-1}, \mathbb{Z}/2)$           | $H^n(\RP^5; \mathbb{Z}/2)$ |
| :-: | :------------: | :-----------------------: | :-----------------------------------------------: | :------------------------: |
|  0  |  $\mathbb{Z}$  |      $\mathbb{Z}/2$       |                         0                         |       $\mathbb{Z}/2$       |
|  1  | $\mathbb{Z}/2$ |      $\mathbb{Z}/2$       |       $\Ext(\mathbb{Z}, \mathbb{Z}/2) = 0$        |       $\mathbb{Z}/2$       |
|  2  |      $0$       |            $0$            | $\Ext(\mathbb{Z}/2, \mathbb{Z}/2) = \mathbb{Z}/2$ |       $\mathbb{Z}/2$       |
|  3  | $\mathbb{Z}/2$ |      $\mathbb{Z}/2$       |            $\Ext(0, \mathbb{Z}/2) = 0$            |       $\mathbb{Z}/2$       |
|  4  |      $0$       |            $0$            | $\Ext(\mathbb{Z}/2, \mathbb{Z}/2) = \mathbb{Z}/2$ |       $\mathbb{Z}/2$       |
|  5  |  $\mathbb{Z}$  |      $\mathbb{Z}/2$       |            $\Ext(0, \mathbb{Z}/2) = 0$            |       $\mathbb{Z}/2$       |

## Universal Coefficient Theorem for Homology

Similarly, we also have the universal coefficient theorem for homology, which relates homology with different coefficients:

> [!theorem] Universal Coefficient Theorem for Homology
> Let $C$ be a chain complex of free abelian groups  and $G$ be an [[Groups, Order and Subgroups#^6d511a|abelian group]]. Then the following short exact sequence splits:
> $$0 \to H_{n}(C;\mathbb{Z})\otimes G \to H_{n}(C;G) \to \operatorname{Tor}_1^{\mathbb{Z}}(H_{n-1}(C;\mathbb{Z}),G)\to 0.$$
