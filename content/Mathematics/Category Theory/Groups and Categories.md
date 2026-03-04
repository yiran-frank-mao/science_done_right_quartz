---
created: 2024-03-11
updated: 2024-09-17
---
## Groups in a Category

> [!definition] Group Object
> Let $\mathsf{C}$ be a [[Structure of Categories#^2f5c3a|category]] with finite products. A *group object* in $\mathsf{C}$ consists of objects and arrows as: 
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/groupinc.svg" alt="group_inc" style="width:40%;">
> satisfying the following conditions:
> - $m$ is associative, that is the following commutes: ![|350](https://svgshare.com/i/14CS.svg)
>   where $\cong$ is the canonical associativity isomorphism for products.
> - $u$ is a unit for $m$, that is both triangles in the following commute: ![|300](https://svgshare.com/i/14Bn.svg)
> - $i$ is an inverse with respect to $m$, that is both sides of this commute:
> 
> $\quad$^6ff745

> [!definition] Homomorphism
> A morphism $h \colon G → H$ of groups in $\mathbf{C}$ is called homomorphism if
> - $h$ preserves $m$
> - $h$ preserves $u$
> - $h$ preserves $i$

<u><b>e.g.</b></u> The idea of a group in a category captures the familiar notion of a group with additional structure:
 - A [[Groups, Order and Subgroups#^6e0960|group]] in the usual sense is a group in the category $\mathsf{Set}$.
 - A [[Topological Groups#^a4f93a|topological group]] is a group in $\mathsf{Top}$, the category of topological spaces.
$\quad$

## Category of Groups

**Prop**  If $N \triangleleft G$ is a [[Homomorphisms, Normal Subgroup & Conjugation#^normal|normal subgroup]] of $G$, then the following forms a [[Mathematics/Category Theory/Duality#^9b92cf|coequalizer]]: ![|330](https://svgshare.com/i/14Bc.svg)
**Proof**  

## Groups as Categories

**Prop**  A group is a category with one object, in which every arrow is an isomorphism.

**Def**  <i><u>Congruence</u></i>
A congruence on a category $\mathbf{C}$ is an [[Relations and Functions#^14741d|equivalence relation]] $\sim$ on morphisms such that:
- $f \sim g$ implies $\dom(f) = \dom(g)$ and $\cod(f) = \cod(g)$.
- $f \sim g$ implies $b\circ f\circ a \sim b\circ g\circ a$ for all morphisms $a \colon A \to X$ and $b \colon Y \to B$, where $\dom(f) = X = \dom(g)$ and $\cod(f) = Y = \cod(g)$.

**Prop** The intersection of a family of congruences is a congruence.

**Def**  <i><u>Congruence Category</u></i>
Let $\sim$ be a congruence on the category $\mathbf{C}$, and define the congruence category $\mathbf{C}^{\sim}$ by
- $\obj(\mathbf{C}^{\sim})=\obj\mathbf{C}$
- $\mor(\mathbf{C}^{\sim})=\{\langle f,g\rangle\mid f\sim g\}$
- $\tilde{1}_C=\langle1_C,1_C\rangle$
- $\langle f^{\prime},g^{\prime}\rangle\circ\langle f,g\rangle=\langle f^{\prime}f,g^{\prime}g\rangle$

**Def**  <i><u>Quotient Category</u></i>
We define the quotient category $\mathbf{C}/\mathord{\sim}$ as follows:
- $\obj\mathbf{(C/\mathord{\sim})}=\obj\mathbf{C}$.
- $\mor(\mathbf{C}/{\mathord{\sim}})=(\mor\mathbf{C})/{\sim}$.
- The morphisms have the form $[f]$ where $f ∈ \mor\mathbf{C}$.
- $1_{[C]} = [1_{C}]$, and $[g] \circ [f ] = [g \circ f ]$.

**Prop**  There is an evident quotient functor $π \colon \mathbf{C} \to \mathbf{C}/ \mathord{\sim}$. It then makes the following a coequalizer of categories:
![|330](https://svgshare.com/i/14Cp.svg)
**Proof**

**Def**  <i><u>Kernel of Functor</u></i>
Any functor $F \colon \mathbf{C} \to \mathbf{D}$ determines a congruence $\sim_{F}$ on $\mathbf{C}$ by setting$$f\sim g \iff \dom(f)=\dom(g),\cod(f)=\cod(g),F(f)=F(g)$$And we define $\ker(F) = \mathbf{C}^{\sim_{F}}$ as the kernel of $F$.

**Thrm**  For all functor $F \colon \mathbf{C} \to \mathbf{D}$, given any congruence $\sim$ on $\mathbf{C}$, one has: $$f\sim g\implies f\sim_{F}g$$if and only if there is a factorization $\tilde{F}\colon\mathbf{C}/\mathord{\sim}\to\mathbf{D}$ such that the following commutes:
![|200](https://svgshare.com/i/14AL.svg)
**Proof**

**Corollary**  Every functor $F \colon \mathbf{C} \to \mathbf{D}$ factors as $F = \tilde{F} \circ π$:
![|250](https://svgshare.com/i/14BG.svg)
where $π$ is bijective on objects and surjective on [[Objects and Elements#^6a1c64|Hom-sets]], and $\tilde{F}$ is injective
on [[Objects and Elements#^6a1c64|Hom-sets]].

## Finitely Presented Categories

<u><b>e.g.</b></u>  The category with two uniquely isomorphic objects is not free on any graph, since it’s finite, but has loops. But it is finitely presented with graph 
![|180](https://svgshare.com/i/14Cq.svg)
and relations $gf=1_A$ and $fg=1_B$.