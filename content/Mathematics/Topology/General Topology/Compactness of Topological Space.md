---
created: 2024-01-06
updated: 2025-05-19
---
>[!definition] Cover and Subcover
>A *cover* of a set $A$ is collection $\mathcal{U}$ of sets whose union contains $A$: $$A\subset\bigcup_{U\in\mathcal{U}}U$$ A *subcover* of a cover $\mathcal{U}$ is a subset of $\mathcal{U}$ whose elements still cover $A$. A cover is *open* if all its elements are open. ^eb1952

<b><u>e.g.</u></b> $\{(n, n + 3) \mid n \in \Z\}$ is an open cover of $\R$; $\{(2k, 2k + 3) \mid k \in \Z\}$ is a subcover.

>[!definition] Compactness
>A topological space $T$ is *compact* if every open cover of $T$ has a finite subcover. A subset $S$ of $T$ is compact if every open cover of $S$ by subsets of $T$ has a finite subcover. This is the same as $S$ being compact with the subspace topology. ^da2511

<b><u>e.g.</u></b> $(0, 1)$ is not compact, $\{(0, a) \mid a ∈ (0, 1)\}$ is an open cover with no finite subcover; $\R$ is not compact, $\{(−\infty, a) : a ∈ \Z\}$ has no finite subcover.

> [!lemma]
> If $T$ is a topological space and $S \subset T$ then $S$ is compact in the $T$ if and only if $S$ is compact in the [[Mathematics/Topology/General Topology/Constructions on Topological Spaces#^a942da|subspace topology]] on $S$.

>[!theorem] 
> Let $X$ be a compact topological space and $K$ a closed [[Mathematics/Topology/General Topology/Constructions on Topological Spaces#^a942da|subspace]] of $X$. Then $K$ is compact. ^f5bb06

*Proof*  Let $K ⊂X$ be closed and let $\{U_{α}\}_{α∈\Lambda}$ be an open covering of $K$. Then $\{K^{c}\cup U_{α}\}_{α∈\Lambda}$ is an open covering of $X$. Since $X$ is compact, there exist $α_{1},\dots,α_{n} ∈ \Lambda$ such that $$X=K^{c}\bigcup\left(\bigcup_{i=1}^{n}U_{\alpha_i}\right)$$It follows that $K \subset \bigcup_{i=1}^{n}U_{\alpha_{i}}$, therefore $K$ is compact. $\square$

> [!corollary]
> Any intersection of a compact set with a closed set is compact.
> 

*Proof*  Suppose $C$ is closed and $K$ is compact. Then $C\cap K$ is closed in $K$ (w.r.t [[Mathematics/Topology/General Topology/Constructions on Topological Spaces#^a942da|subspace topology]]), and hence compact by the previous theorem and lemma. $\square$

> [!proposition]
> Any compact subset $K$ of a [[Separation and Hausdorff Spaces#^f7bcc8|Hausdorff space]] $X$ is closed.

*Proof*  For any $x\in K^{c}$, since $X$ is Hausdorff, we can find some 

## Tychonoff's Theorem

> [!theorem] Tychonoff's Theorem
> The product of any collection of compact topological spaces is compact with respect to the product topology.

## Lindelöf Spaces

There is a slightly weaker notion of compactness called Lindelöf spaces, which is defined as follows:

> [!definition] Lindelöf Space
> A topological space $X$ is called a *Lindelöf space* if every open cover of $X$ has a countable subcover. ^concept-871f5f6137af

> [!proposition]
> A [[Mathematics/Topology/General Topology/Countability Axioms and Nets#^concept-5144b7350d14|second-countable]] space is [[Mathematics/Topology/General Topology/Compactness of Topological Space#^concept-871f5f6137af|Lindelöf]].
> 

*Proof*  Let $\mathcal{B}$ be a countable basis for the topology of $X$. Let $\mathcal{U}=\{U_{\alpha}\}_{\alpha\in \Lambda}$ be an open cover of $X$. For each $x \in X$, there exists $U_x \in \mathcal{U}$ such that $x \in U_x$. Since $\mathcal{B}$ is a basis, there exists $B_x \in \mathcal{B}$ such that $x \in B_x \subseteq U_x$. The collection $\{B_{x} : x \in X\}$ is an open cover of $X$ consisting of elements from the countable basis $\mathcal{B}$. Since $\mathcal{B}$ is countable, $\{B_{x} : x \in X\}$ is countable. Now, for each $B_x$, we can choose the corresponding $U_x \in \mathcal{U}$ such that $B_x \subseteq U_x$. The collection $\{U_x : x \in X\}$ is a countable subcollection of $\mathcal{U}$ that covers $X$. Therefore, $X$ is Lindelöf. $\square$ ^40d004

> [!remark]
> The proof above utilized countable axiom of choice.

> [!lemma] Tube Lemma
> Let $X$ be any topological space and Y be a compact space. If x ∈X and U ⊂X ×Y is a nbhd of {x}×Y, then there is a nbhd V ⊂X of x so that V ×Y ⊂U.

## Sequential and Limit Point Compactness

> [!definition] Limit Point Compactness
> A topological space $X$ is called *limit point compact* if every infinite subset of $X$ has a limit point in $X$. ^concept-c564d7124948

> [!proposition]
> Every [[Compactness of Topological Space#^da2511|compact]] space is limit point compact.

*Proof*  Suppose $X$ is compact, and $A\subset X$ is infinite, and has no limit points. Then for each $x\in A$, there exists an open neighborhood $U_x$ of $x$ such that $U_{x}\cap A=\{x\}$, and for each $x\in X\setminus A$, there exists an open neighborhood $U_x$ of $x$ such that $U_{x}\cap A=\emptyset$. Then $\{U_{x}\}_{x\in X}$ is an open cover of $X$, but it does not have a finite subcover because every $U_{x}$ for $x\in A$ is needed to cover $A$. This contradicts the compactness of $X$. $\square$

>[!definition] Sequential Compactness
>Let $X$ be a topological space and $A\subset X$. We say that $A$ is *sequentially compact* if every sequence in $A$ has a subsequence converges to a point in $A$.


## References and Other Resources
- [Morphocular, The Concept So Much of Modern Math is Built On](https://www.youtube.com/watch?v=td7Nz9ATyWY)