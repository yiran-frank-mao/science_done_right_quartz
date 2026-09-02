## Suspension

> [!definition] Suspension
> The *suspension* of a [[Topological Spaces#^65c94a|topological space]] $X$ is the quotient of $X\times I$ obtained by collapsing $X\times\{0\}$ to a point and $X\times\{1\}$ to a point. The suspension is denoted by $SX$ or $\Sigma X$. ^a942da
> 

<u><b>e.g.</b></u>  Suspension of $S^{n}$ is $S^{n+1}$.

> [!proposition]
> Suspension is a [[Functoriality#^653948|functor]] from the [[Structure of Categories#^54ad73|category of topological spaces]] to itself.
> 

*Proof*  A continuous map $f\colon X\to Y$ suspends to $Sf\colon SX\to SY$, which is the quotient of $f\times \id_{I} \colon X \times I \to Y\times I$. Moreover $S(\id_{X})=\id_{SX}$, so $S$ is a functor. $\square$

## Wedge Sum

> [!definition] Wedge Sum
> The *wedge sum* of a family of pointed spaces $\{(X_{α},x_{α})\}_{α\in A}$ is the quotient of the disjoint union $\coprod_{α\in A} X_{α}$ obtained by identifying all the base points $x_{α}$ to a single point. The wedge sum is denoted by $\bigvee_{α\in A} X_{α}$. ^a942da
> 

## Join

> [!definition] Join
> The *join* of two spaces $X$ and $Y$ is the union $X*Y$ of all line segments joining points of $X$ to points of $Y$. This is a quotient.
