---
created: 2024-04-16
updated: 2024-10-29
---
## Sequential Compactness

>[!theorem]
> Let $S$ be a subset in $\R^{k}$. Then $S$ is closed and [[Open and Closed Sets#^7012df|bounded]] iff every sequence in $S$ has a subsequence that converges to a point in $S$.

>[!definition] Sequential Compactness
>Let $(X , d )$ be a metric space. A set $S ⊂ X$ is called sequentially compact if every sequence in $S$ has a subsequence that converges to a point in $S$. ^f1fb8b

>[!theorem]
> In a metric space, every sequentially compact set is [[Open and Closed Sets#^7012df|bounded]] and closed.

> [!remark]+ The Converse is Not True in General
> However, the converse is not true in general. For example, consider the metric space $\Q$ with the standard metric inherited from $\R$. Let a subset $A:=[0,1]\cap\Q$. Clearly $A$ is closed as a intersection of closed sets, and bounded. However, $A$ is not sequentially compact since a subsequence of any sequence of rationals converging to $\sqrt{2}/2$ never converges to a point in $A$.
> 

>[!theorem]
> Let $(X , d )$ be a metric space. If $A ⊂ X$ is sequentially compact, then for any $x ∈ X$ there is $y ∈ A$ such that $$d(x,y)=d(x,A)$$This $y$ is called a nearest point in $A$ to $x$.

*Proof*  By the definition of $d(x,A)$, there is a sequence $(y_{n})$ in $A$ such that $d(x,y_{n}) → d(x,A)$. Since $A$ is sequentially compact, $(y_{n})$ has a convergent subsequence $(y_{n_k})$ with $y_{n_k} → y ∈ A$. Then $$d(x,A)=\lim_{k\to \infty}d(x,y_{n_k})$$

**Lemma**  Let $(X,d)$ be a metric space. If $A ⊂ X$ is sequentially compact, then for any $ε > 0$ there exists an integer $N$ and $N$ points $x_{1},\dots,x_{N}$ in $A$ such that $$A \subset \bigcup_{i=1}^N B_\varepsilon (x_{i}) $$

**Thrm**  Let $(X , d )$ be a metric space and let $A ⊂ X$ be sequentially compact. If $\mathcal{O} = \{U_{α} \}_{α∈I}$ is a family of open sets such that $$A\subset\bigcup_{\alpha\in I}U_\alpha$$then there exists finitely many open sets $U_{1},\dots ,U_{n}$ from $\mathcal{O}$ such that $$A\subset\bigcup_{i=1}^{n}U_\alpha$$**Proof**

## Covering and Compactness

>[!definition] Covering
>Let $(X,d)$ be a metric space and $A⊂X$. A collection of sets $\{U_α\}$ is called a covering of $A$ if $A⊂\bigcup_{\alpha\in I}U_\alpha$ . If in addition, each $U$ is open, then $\{U _\alpha\}$ is called an open covering of $A$.

>[!definition] Compactness
> Let $(X,d)$ be a metric space. A set $K ⊂ X$ is called compact if for every open covering $\{U_α\}$ of $K$ there exists a finite subcollection $\{U_{i}\}_{i=1}^{n}$ of $\{U_α\}$ such that $$K\subset\bigcup_{i=1}^nU_i$$ ^8c1327

>[!theorem]
> Let $(X,d)$ be a metric space. Then a set $K ⊂ X$ is compact iff it is sequentially compact.

*Proof*
