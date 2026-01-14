## Cosets

> [!definition] Coset
> Let $G$ be a group, $H \leq G$ a subgroup and $a \in G$. The following subsets are called cosets of $H$ in $G$: $$ \begin{aligned} a H &=\{a h\mid h\in H\}\quad({\mathrm{left~coset}}),\\ H a &=\{h a\mid h\in H\}\quad({\mathrm{right~coset}}). \end{aligned} $$

> [!proposition]
> Let $H$ be a subgroup of a group $G$. Then the left (or right) cosets form a partition of $G$. That is $G=\coprod_{a \in G} a H$ and for $a,b \in G$ either $aH =bH$ or $aH ∩bH =\emptyset$.

> [!theorem] Lagrange’s Theorem
> Let $H$ be a subgroup of a finite group $G$. Then $|H|$ divides $|G |$. ^add232

*Proof*  Let $a_1H,...,a_mH$ be the distinct cosets. Then $|G|=|a_1H|+···+|a_mH|=m|H|$. $\square$

> [!corollary]
> Let $G$ be a finite group and $a \in G$. Then $o(a) \mid |G|$. It follows that $x^{|G|} = e$ for all $x \in G$. In particular, if there exists $g\in G$ such that $o(g)=|G|$ then $G$ is [[Cyclic Groups#^c52ddd|cyclic]]. ^coro

*Proof*  Consider $\langle a \rangle$. By [Lagrange’s Theorem](Cosets%20and%20Lagrange’s%20Theorem.md#^add232), we have $|\langle a \rangle| \mid |G|$. Since $\langle a \rangle$ is cyclic, $|\langle a \rangle|=o(a)$, which implies that $o(a) \mid |G|$. Moreover, if $o(g)=|G|$, then $\langle g\rangle$ will have order $|G|$, which means $G=\langle g\rangle$. $\square$

## Index

> [!definition] Index
> The *index* of a subgroup $H$ in a group $G$, denoted $[G :H]$, is defined as the [[Cardinality#^1fd903|cardinality]] of the set of (left) cosets of $H$ in $G$.
> In particular, if $G$ is a finite group, then $[G :H]=|G|/|H|$. ^6fa811

> [!corollary]
>  A group of prime order is cyclic. ^c1062e

*Proof*  Suppose group $G$ has prime order. Then for all subgroup $H\leq G$, by [corollary](Cosets%20and%20Lagrange’s%20Theorem.md#^coro), for all $a \in G$,we have $o(a) \mid |G|$, thus $o(a)=1$ or $o(a)=|G|$, indicating that $G$ is a cyclic group. $\square$ ^10a046

> [!proposition]
> A subgroup whose index is the smallest prime dividing the order of $G$ is [[Homomorphisms, Normal Subgroup & Conjugation#^normal|normal]]. In, particular, any subgroup of index 2 in $G$ is automatically normal.
> 
