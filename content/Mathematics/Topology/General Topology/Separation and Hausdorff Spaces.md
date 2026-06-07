The $T_{n}$​ hierarchy is a way of classifying separation axioms in topology. They describe how well points and sets can be distinguished by open sets.

## Kolmogorov Space $(T_{0})$

> [!definition] Kolmogorov Space
> A [[Topological Spaces#^65c94a|topological space]] is called a *Kolmogorov space* or *$T_{0}$ space* if for any two distinct points in the space, there exists an open set that contains one of the points but not the other.

## Fréchet Space $(T_{1})$

> [!definition] $T_{1}$ Space
> A [[Topological Spaces#^65c94a|topological space]] is called *Fréchet* or *$T_{1}$ space* if for any two distinct points in the space, there exists an open set that contains one of the points but not the other, and vice versa.

> [!theorem]
> A topological space $X$ is a Fréchet space if and only if every singleton set $\{x\}$ is closed for all $x∈X$.
> 

## Hausdorff Space $(T_{2})$

>[!definition] Hausdorff Space
>A topological space $X$ is called *Hausdorff* if for any $x , y ∈ X$ with $x \neq y$ there exist [[Closure, Interior and Boundary#^eda962|open neighborhoods]] $U$ of $x$ and $V$ of $y$ such that $U ∩V = \emptyset$. ^f7bcc8

>[!theorem] 
> In Hausdorff spaces, [[Closure, Interior and Boundary#^72dffe|limits]] of sequences are unique if they exist.

*Proof*  Assume a sequence $(x_{n})$ in a Hausdorff space has two distinct limits $x$ and $y$. Then there exist neighborhoods $U$ of $x$ and $V$ of $y$ such that $U ∩V = \emptyset$. However, since $x_{n} → x$ and $x_{n} → y$ , there exists an integer $N$ such that $x_{n} ∈ U$ and $x_{n} ∈V$ for $n≥N$. Thus $U∩V \neq \emptyset$, which is a contradiction. $\square$

>[!theorem] 
> Every finite set in a Hausdorff topological space $(X,\tau)$ is closed.

*Proof*  It suffices to show for any $x∈X$ the set $\{x\}$ is closed. For any $z\in X\setminus \{x\}$, by the Hausdorff property we can find an open set $U_{z}$ containing $z$ but $x \notin U_{z}$. Thus $X \setminus\{x\} = \bigcup_{z∈X\setminus\{x\}} U_{z}$ and hence it is open. Consequently $\{x\}$ is closed. $\square$

>[!theorem] 
> Let $(X,\mathcal{T})$ be a Hausdorff space. If $\mathcal{T}^{\prime}$ is a [[Topological Spaces#^149286|finer]] topology on $X$, then $(X,\mathcal{T}^{\prime})$ is also a Hausdorff space.

*Proof*  Let $x,y\in X$ with $x\neq y$. Since $\mathcal{T}\subset \mathcal{T}^{\prime}$, the open sets in $\mathcal{T}$ are also open in $\mathcal{T}^{\prime}$. Thus there exist open sets $U,V\in \mathcal{T}\subset\mathcal{T}^{\prime}$ such that $x\in U$, $y\in V$ and $U\cap V=\emptyset$, that is $X$ is a Hausdorff space under $\mathcal{T}^{\prime}$. $\square$

**Thrm**  Let $X$ be a Hausdorff space and $A⊂X$. A point $x∈X$ is a limit point of $A$ if and only if any neighborhood $U$ of $x$ contains infinitely many points of $A$.