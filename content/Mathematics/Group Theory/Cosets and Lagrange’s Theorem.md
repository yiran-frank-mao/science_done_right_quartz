## Cosets

> [!definition] Coset
> Let $G$ be a group, $H \leq G$ a subgroup and $a \in G$. The following subsets are called *cosets* of $H$ in $G$: $$ \begin{aligned} a H &=\{a h\mid h\in H\}\quad({\mathrm{left~coset}}),\\ H a &=\{h a\mid h\in H\}\quad({\mathrm{right~coset}}). \end{aligned} $$ ^b825de

> [!proposition]
> Let $H$ be a subgroup of a group $G$. Then the left (or right) cosets form a partition of $G$. That is $G=\bigsqcup_{a \in G} a H$ and for $a,b \in G$ either $aH =bH$ or $aH \cap bH =\emptyset$.

*Proof*  If $aH \cap bH \neq \emptyset$, then we are allowed to pick some element $x\in aH \cap bH$, so that $x=ah_{1}=bh_{2}$. Then $a=bh_{2}h_{1}^{-1}\in bH$, so $aH\subset bH$, and similarly $bH\subset aH$, thus $aH=bH$. Moreover, any element $g\in G$ belongs to $gH$, so $G=\bigsqcup_{a \in G} a H$. $\square$

> [!theorem] Lagrange’s Theorem
> Let $H$ be a subgroup of a finite group $G$. Then $|H|$ divides $|G |$. ^add232

*Proof*  Let $a_1H,...,a_mH$ be the distinct cosets. Then $|G|=|a_1H|+···+|a_mH|=m|H|$. $\square$

> [!proposition]
> Let $G$ be a finite group and $a \in G$. Then $o(a) \mid |G|$. It follows that $x^{|G|} = e$ for all $x \in G$. In particular, if there exists $g\in G$ such that $o(g)=|G|$ then $G$ is [[Cyclic Groups#^c52ddd|cyclic]]. ^coro

*Proof*  Consider $\langle a \rangle$. By [Lagrange’s Theorem](Cosets%20and%20Lagrange’s%20Theorem.md#^add232), we have $|\langle a \rangle| \mid |G|$. Since $\langle a \rangle$ is cyclic, $|\langle a \rangle|=o(a)$, which implies that $o(a) \mid |G|$. Moreover, if $o(g)=|G|$, then $\langle g\rangle$ will have order $|G|$, which means $G=\langle g\rangle$. $\square$

> [!corollary]
>  A [[Groups, Order and Subgroups#^6e0960|group]] of [[Division and Prime#^47f235|prime]] order is cyclic. ^c1062e

*Proof*  Suppose group $G$ has prime order. Then for all subgroup $H\leq G$, by [proposition](Cosets%20and%20Lagrange’s%20Theorem.md#^coro), for all $a \in G$,we have $o(a) \mid |G|$, thus $o(a)=1$ or $o(a)=|G|$, indicating that $G$ is a cyclic group. $\square$ ^10a046

## Index

> [!definition] Index
> The *index* of a [[Groups, Order and Subgroups#^1ccb07|subgroup]] $H$ in a [[Groups, Order and Subgroups#^6e0960|group]] $G$, denoted $[G :H]$, is defined as the [[Cardinality#^1fd903|cardinality]] of the set of (left) cosets of $H$ in $G$.
> In particular, if $G$ is a finite group, then $[G :H]=|G|/|H|$. ^6fa811

> [!remark]-
> The "in particular" part is a direct consequence of [[Cosets and Lagrange’s Theorem#^add232|Lagrange's theorem]].
> 

> [!proposition]
> A [[Groups, Order and Subgroups#^1ccb07|subgroup]] of a finite group $G$ whose index is the smallest prime dividing the order of $G$ is [[Homomorphisms, Normal Subgroup & Conjugation#^normal|normal]]. In, particular, any subgroup of index 2 in $G$ is automatically normal.
> 

*Proof*  


Suppose $H\leq G$ such that $[G:H]=p$ is the smallest prime factor of $|G|$, and $|G|=pd$. Then $|H|=d$, is the largest divisor of $|G|$. Note that $|gH g^{-1}|=|H|=d$ for all $g\in G$, and $g Hg^{-1}\leq G$, so $|gHg^{-1}|$ divides $|G|$. 