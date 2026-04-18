---
created: 2024-03-31
updated: 2024-09-17
---
## Partial Order

> [!definition] Partial Order
> A partial order is a [[Relations and Functions#^759a11|homogeneous binary relation]] that is [[Relations and Functions#^1bdc5e|reflexive]], [[Relations and Functions#^cb363c|antisymmetric]], and [[Relations and Functions#^1f742d|transitive]]. That is 
> - $a\leq a$.
> - $a\leq b, b\leq a \implies a=b$.
> - $a\leq b, b\leq c \implies a\leq c$.
> 
> A *poset* is a set $A$ equipped with a partial order. ^fa7f22

<u><b>e.g.</b></u> The [[Number Systems#^5fea5c|real numbers]] $\R$ with their usual ordering $x ≤ y$ form a partially ordered set that is also linearly ordered: either $x ≤ y$ or $y ≤ x$ for any $x, y$.

>[!definition] Monotone Poset Function
>A function $m\colon A\to B$ with posets $(A,\leq_{A})$ and $(B,\leq_{B})$ is monotone if $$a\leq_Ab\implies m(a)\leq_{B}m(b).$$ ^893616

> [!definition] Total Order
> A total order or linear order is a partial order that is also [[Relations and Functions#^f0a2cd|connected]]. ^a8688d

> [!definition] Upper Bound
> Let $X$ be a nonempty partially ordered set and $A ⊂ X$ is a totally ordered subset. An upper bound for $A⊂X$ is an element $z ∈X$ such that $x ≤z$ for all $x ∈A$. 

**Def**  <i><u>Maximal Element</u></i>
A maximal element in a partially ordered set $X$ is an element $x ∈X$ such that $y ≥x$ for some $y ∈X$ implies $y = x$.

> [!theorem] Zorn's Lemma
> Let $X$ be a nonempty partially ordered set. If every totally ordered subset of $X$ has an upper bound in $X$, then $X$ has a maximal element. ^11e467



> [!remark]
> Zorn’s lemma is equivalent to the axiom of choice: for any collection of nonempty sets, it is possible to form a new set consisting of one element from each member of the collection.


