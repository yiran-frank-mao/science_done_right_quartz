---
created: 2024-01-06
updated: 2025-05-19
---
>[!definition] Cover and Subcover
>A cover of a set $A$ is collection $\mathcal{U}$ of sets whose union contains $A$: $$A\subset\bigcup_{U\in\mathcal{U}}U$$ A subcover of a cover $\mathcal{U}$ is a subset of $\mathcal{U}$ whose elements still cover $A$. A cover is open if all its elements are open. ^eb1952

<b><u>e.g.</u></b> $\{(n, n + 3) \mid n \in \Z\}$ is an open cover of $\R$; $\{(2k, 2k + 3) \mid k \in \Z\}$ is a subcover.

>[!definition] Compactness
>A topological space $T$ is compact if every open cover of $T$ has a finite subcover. A subset $S$ of $T$ is compact if every open cover of $S$ by subsets of $T$ has a finite subcover. This is the same as $S$ being compact with the subspace topology. ^da2511

<b><u>e.g.</u></b> $(0, 1)$ is not compact, $\{(0, a) \mid a ∈ (0, 1)\}$ is an open cover with no finite subcover; $\R$ is not compact, $\{(−\infty, a) : a ∈ \Z\}$ has no finite subcover.

>[!definition] Sequential Compactness
>Let $X$ be a topological space and $A⊂X$. We say that $A$ is sequentially compact if every sequence in $A$ has a subsequence converges to a point in $A$.

> [!lemma]
> If $T$ is a topological space and $S ⊂ T$ then $S$ is compact in the $T$ if and only if $(S,\mathcal{T}_S)$ is compact.

>[!theorem] 
> Let $X$ be a compact topological space and $K$ a closed [[Topological Spaces#^a942da|subspace]] of $X$. Then $K$ is compact.

^f5bb06

*Proof*  Let $K ⊂X$ be closed and let $\{U_{α}\}_{α∈\Lambda}$ be an open covering of $K$. Then $\{K^{c}\cup U_{α}\}_{α∈\Lambda}$ is an open covering of $X$. Since $X$ is compact, there exist $α_{1},\dots,α_{n} ∈ \Lambda$ such that $$X=K^{c}\bigcup\left(\bigcup_{i=1}^{n}U_{\alpha_i}\right)$$It follows that $K \subset \bigcup_{i=1}^{n}U_{\alpha_{i}}$, therefore $K$ is compact. $\square$

> [!proposition]
> Any compact subset $K$ of a [[Hausdorff Space#^f7bcc8|Hausdorff space]] $T$ is closed.

## Tikhonov Theorem

**Def**  <i><u>Product of Sets</u></i>
Let $\{X_α\}_{α∈A}$ be a family of sets. We define $∏_{α∈A} X_{α}$ to be the collection of all
functions $x \colon A → \bigcup_{\alpha\in A} X_{\alpha}$ such that $x(α)∈X_{\alpha}$ for each $α ∈A$.

**Def**  <i><u>Projection</u></i>






## References and Other Resources
- [Morphocular, The Concept So Much of Modern Math is Built On](https://www.youtube.com/watch?v=td7Nz9ATyWY)