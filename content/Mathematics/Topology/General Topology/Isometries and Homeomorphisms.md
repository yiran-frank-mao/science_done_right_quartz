---
created: 2023-12-11
updated: 2024-10-17
---
>[!definition] Isometry
> Suppose $X$ and $Y$ are metric spaces. Suppose that $f \colon X \to Y$ is a [[Relations and Functions#^042daf|bijection]] such that $$ d_Y(f(x),f(y))=d_X(x,y)\quad\text{ for all }x,y\in X$$Then $f$ is called an isometry between $X$ and $Y$. It preserves the distance between points. And we say that $X$ and $Y$ are isometric.

>[!definition] Homeomorphism
> Suppose $X$ and $Y$ are [[Topological Spaces#^65c94a|topological spaces]]. If $f \colon X \to Y$ is a [[Relations and Functions#^042daf|bijection]] and both $f$ and $f^{-1}$ are continuous we say that $f$ is a *homeomorphism* and that $X$ and $Y$ are *homeomorphic*. ^85034b
>

<u><b>e.g.</b></u>
- $[0,1]$ and $(0,1)$ are not homeomorphic because $[0,1]$ is compact but $(0,1)$ is not.
- $\R$ and $\R^{2}$ are not homeomorphic. Otherwise, if $f \colon \R → \R^{2}$ is a homeomorphism, then it also gives a homeomorphism from $R \setminus \{0\} → \R^{2} \setminus \{f (0)\}$. This is impossible, because $\R \setminus \{0\}$ is not connected while $\R^{2} \setminus \{f (0)\}$ is connected.
$\quad$

>[!proposition]
>If $f$ is a homeomorphism then $U$ is open in $X$ if and only if $f(U)$ is open in $Y$.

*Proof*  $U$ is open in $X$ implies that $f(U)$ is open in $Y$ as $f^{-1}$ is continuous; $V$ is open in $Y$ implies that $f^{-1}(V)$ is open in $X$ as $f$ is continuous.

>[!definition] Topological Property
>If some property $P$ of a metric space is such that if $(X,d)$ has property $P$ then so does every metric space that is homeomorphic to $(X,d)$ we say that $P$ is a topological property. More colloquially, these are properties that are only concerned with set-theoretic notions and/or open sets, rather than distances.

<b><u>e.g.</u></b>  Topological properties:
- $X$ is open in $X$.
- $X$ is finite; countably infinite; or uncountable.
- $X$ has a point such that $\{x\}$ is open in $X$ (an ‘isolated point’)
- every continuous real-valued function on $X$ is bounded.

Properties that are not topological:
- $X$ is bounded.
$\quad$

> [!proposition]
> If $f\colon X\to Y$ is a continuous bijection, and $X$ is compact, $Y$ is Hausdorff, then $f$ is a homeomorphism. 
> 
