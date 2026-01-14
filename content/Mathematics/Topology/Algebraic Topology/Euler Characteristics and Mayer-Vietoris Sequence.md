## Euler Characteristic Revisited

> [!definition] Rank of a Group
> The *rank* of a finitely generated [[Groups, Order and Subgroups#^6d511a|abelian group]] is the number of $\newcommand{\Z}{\mathbb{Z}}\Z$ summands in its decomposition.

 <u><b>e.g.</b></u>  $\text{rank}(\Z \oplus \Z \oplus \Z/69\Z) = 2$.

> [!theorem] Homological Euler Characteristic
> The [[CW Complexes#^ddd7c6|Euler characteristic]] of a finite CW complex $X$ can be computed from its homology groups:
> $$\chi(X) = \sum_{n \ge 0} (-1)^n \text{rank}(H_n(X)).$$
> > [!corollary]
> > The Euler characteristic $\chi(X)$ is a topological invariant and does not depend on the specific CW structure chosen for $X$.

*Proof*  Let $C_{n} = C_{n}^{\mathrm{CW}}(X)$, $Z_n = \ker(d_n)$, and $B_n = \text{im}(d_{n+1})$. These groups are related by two short exact sequences for each $n$:$$\begin{aligned}0 \to Z_n \to C_n \to B_{n-1} \to 0\\0 \to B_n \to Z_n \to H_n \to 0\end{aligned}$$From a lemma on short exact sequences of finitely generated abelian groups, we know that ranks are additive. Thus:
1. $\text{rank}(C_n) = \text{rank}(Z_n) + \text{rank}(B_{n-1})$
2. $\text{rank}(Z_n) = \text{rank}(B_n) + \text{rank}(H_n)$

Now, we compute $\chi(X)$: $$\begin{aligned}\chi(X) &= \sum_{n} (-1)^n \text{rank}(C_n) \\&= \sum_{n} (-1)^n (\text{rank}(Z_n) + \text{rank}(B_{n-1})) \\&= \sum_{n} (-1)^n \text{rank}(Z_n) + \sum_{n} (-1)^n \text{rank}(B_{n-1}) \\&= \sum_{n} (-1)^n (\text{rank}(B_n) + \text{rank}(H_n)) + \sum_{n} (-1)^n \text{rank}(B_{n-1}) \\&= \sum_{n} (-1)^n \text{rank}(H_n) + \sum_{n} (-1)^n \text{rank}(B_n) + \sum_{n} (-1)^n \text{rank}(B_{n-1}).\end{aligned}$$The last two sums cancel each other out via a change of index. Therefore, we are left with the desired result: $$\chi(X) = \sum_n (-1)^n \text{rank}(H_n(X)) $$$\square$

<u><b>e.g.</b></u>
- Sphere: $\chi(S^n) = \begin{cases} 2 & n \text{ even} \\ 0 & n \text{ odd} \end{cases}$.
- Real Projective Space: $\newcommand{\RP}{\mathbb{R}\mathrm{P}}\chi(\RP^n) = \begin{cases} 1 & n \text{ even} \\ 0 & n \text{ odd} \end{cases}$.
- Klein Bottle: $\chi(K) = 0$.
- Genus $g$ Surface: $\chi(M_g) = 2 - 2g$.
- Complex Projective Space: $\newcommand{\CP}{\mathbb{C}\mathrm{P}}\chi(\CP^n) = n+1$.
$\quad$

## Mayer-Vietoris Sequence

> [!theorem] Mayer-Vietoris Sequence
> Suppose a [[Topological Spaces#^65c94a|space]] $X$ is the union of the interiors of two subspaces $A$ and $B$, i.e., $X = \text{int}(A) \cup \text{int}(B)$. Then there is a [[Abelian Categories#^0c5eb9|long exact sequence]] in homology:
> $$\cdots \to H_n(A \cap B) \to H_n(A) \oplus H_n(B) \to H_n(X) \xrightarrow{\partial_*} H_{n-1}(A \cap B) \to \cdots$$ 

*Proof*  This sequence arises from the short exact sequence of chain complexes: $$0 \to C_n(A \cap B) \xrightarrow{x \mapsto (x, -x)} C_n(A) \oplus C_n(B) \xrightarrow{(x, y) \mapsto x+y} C_n(A+B) \to 0$$ Here $C_n(A+B)$ represents chains in $A \cup B$, and by the Excision Theorem, its homology is $H_n(X)$. $\square$

<u><b>e.g.</b></u>  The suspension $SX$ of a space $X$ is given by $SX = C_+X \cup_X C_-X$, where $C_+X$ and $C_-X$ are two cones on $X$ joined at their base.
Let $A = C_+X$ and $B=C_-X$. Then $A \cap B = X$ and $A \cup B = SX$. Both $A$ and $B$ are contractible, so their reduced homology groups are zero, i.e., $\tilde{H}_k(C_{\pm}X) = 0$ for all $k$. The reduced Mayer-Vietoris sequence contains the segment: $$\dots \to \tilde{H}_n(C_+X) \oplus \tilde{H}_n(C_-X) \to \tilde{H}_n(SX) \xrightarrow{\partial_*} \tilde{H}_{n-1}(X) \to \tilde{H}_{n-1}(C_+X) \oplus \tilde{H}_{n-1}(C_-X) \to \dots$$Since the cone homology groups are zero, this simplifies to:$$\dots \to 0 \to \tilde{H}_n(SX) \xrightarrow{\partial_*} \tilde{H}_{n-1}(X) \to 0 \to \dots$$This shows that the connecting homomorphism $\partial_*$ is an isomorphism: $$\tilde{H}_n(SX) \cong \tilde{H}_{n-1}(X).$$ 