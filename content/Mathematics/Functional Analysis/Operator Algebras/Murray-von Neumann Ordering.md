
Recall that 

![[Positive Elements and Ideals in C*-Algebras#^28c050]]

Projections are self-adjoint, so they are partially ordered by the order on self-adjoint elements. Under this usual ordering $\leq$, we have

> [!lemma]
> Suppose $p,q \in M$ are projections, then $p\leq p$ iff $pq=p$.
> 

However, there is a more refined notion of ordering for projections in von Neumann algebras, known as the Murray-von Neumann ordering.

> [!definition] Murray-von Neumann Ordering
> Suppose $M$ is a von Neumann algebra. We define a [[Mathematics/Set Theory/Preorder, Partial Order and Posets#^fa7f22|preorder]] $\lesssim$ on the set of projections in $M$ by declaring $p \lesssim q$ if there exists a partial isometry $v \in M$ such that $v^{*} v = p$ and $vv^{*} \leq q$. 
> Consider the equivalence relation $\approx$ induced by this preorder, the corresponding equivalence classes are called *Murray-von Neumann equivalence classes*. The order type of the quotient poset $M/\approx$ is called the *Murray-von Neumann order type* of $M$. ^concept-4f75ac3e2ead

> [!definition]
> A projection $p \in M$ is said to be *infinite* if $p \approx q$ for some  $q < p$ (that is, $q$ such that $q \leq p$ but $q\neq p$). Otherwise, we say $p$ is *finite*.
> A [[Mathematics/Functional Analysis/Operator Algebras/von Neumann Bicommutant Theorem#^concept-4a6a80d096e9|von Neumann algebra]] $M$ is said to be *finite* if its identity $1$ is a finite projection, and *infinite* otherwise. ^ac7c0d

