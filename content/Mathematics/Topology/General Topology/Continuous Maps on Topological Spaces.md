---
created: 2024-05-22
updated: 2024-09-26
---
>[!definition] Continuous Function
> Let $(X,τ_{X})$ and $(Y,τ_Y)$ be [[Topological Spaces#^65c94a|topological spaces]] and $f \colon X \to Y$ a function. $f$ is called *continuous* if for every open set $V$ in $Y$, $f^{−1}(V)$ is open in $X$. 
>$f$ is called *continuous at $x \in X$* if, for any [[Closure, Interior and Boundary#^eda962|open neighborhood]] $V$ of $f(x)$ in $Y$, the set $f^{−1}(V)$ is a [[Closure, Interior and Boundary#^eda962| neighborhood]] of $x$ in $X$. ^33ee5a

<u><b>e.g.</b></u> 
- The identity map $\operatorname{id}_{X} \colon X → X$ is continuous;
- Any constant map is continuous;
- The composition of two continuous maps is continuous;
$\quad$

>[!theorem] 
>Let $(X,τ_{X})$ and $(Y,τ_{Y})$ be topological spaces. Consider a function $f \colon X →Y$. The following are equivalent:
>1. $f$ is continuous on $X$;
>2. $f$ is continuous at every point in $X$;
>3. $f^{-1}(C)$ is closed in $X$ for every closed set $C$ in $Y$;
>4. $f^{-1}(B) \in \tau_{X}$ whenever $B \in \mathcal{B}$ for a [[Topological Spaces#^2fc468|basis]] $\mathcal{B}$ of $\tau_{Y}$;
>5. $f^{-1}(S)\in \tau_{X}$ whenever $S\in\mathcal{S}$ for a [[Topological Spaces#^02668a|subbasis]] $\mathcal{S}$ of $\tau_{Y}$;
>6. $f(\overline{A})\subset \overline{f(A)}$ for all $A\subset X$;
>$\quad$

*Proof*  2 is obvious; 3 comes from definition of closed sets; 4 and 5 are because [[Relations and Functions#^f5be27|preimages preserve unions and intersections]]. We prove 6 here. Suppose $f$ is continuous. Since $\overline{f(A)}$ is closed, $f^{-1}(\overline{f(A)})$ is closed in $X$. Note that $f(A)\subset \overline{f(A)}$, so $A\subset f^{-1}(\overline{f(A)})$, hence $\overline{A}\subset f^{-1}(\overline{f(A)})$, thus $f(\overline{A})\subset \overline{f(A)}$. For the other direction, suppose $f(\overline{A})\subset \overline{f(A)}$ for all $A\subset X$. Let $C$ be a closed subset of $Y$. Then $f(\overline{f^{-1}(C)})\subset \overline{f(f^{-1}(C))}=\overline{C}=C$, thus $\overline{f^{-1}(C)}\subset f^{-1}(C)$, so $f^{-1}(C)$ is closed in $X$. Therefore, $f$ is continuous.  $\square$ 

>[!theorem] 
> Let $f \colon X → Y$ be a function between two topological spaces $X$ and $Y$. Assume that $X=\bigcup_{\alpha} U_{\alpha}$ ,where $U_{\alpha}$ is open in $X$ for each index $α$. Then $f$ is continuous if and only if $f \big|_{U_α}$ is continuous for every $\alpha$.

> [!definition] Open and Closed Map
> A map $f\colon X\to Y$ is *open* if for every open set $U\subset X$, $f(U)$ is open in $Y$. Similarly, it is *closed* if for every closed set $C\subset X$, $f(C)$ is closed in $Y$.
> ^cd295d

>[!definition] Projection Map
>Define the following function as projection maps: $$\begin{aligned}\pi_{1}\colon X \times Y \to X, \quad (x,y) \mapsto x \\\pi_{2}\colon X \times Y \to Y, \quad (x,y) \mapsto y\end{aligned}$$

**Thrm**  Let $A$, $X$ and $Y$ be topological spaces. A function $f \colon A → X × Y$ is continuous if and only if the components $f_{1} = π_{1} \circ f$ and $f_{2} = π_{2} \circ f$ are continuous.
**Proof**  Recall that $f$ is continuous iff $f ^{−1}(S)$ is open in $A$ for any $S ∈ \mathcal{S}$ . Since $$\begin{aligned}f^{-1}(U\times Y)=f^{-1}(\pi_1^{-1}(U))=(\pi_1\circ f)^{-1}(U)=f_1^{-1}(U)\\f^{-1}(X\times V)=f^{-1}(\pi_2^{-1}(V))=(\pi_2\circ f)^{-1}(V)=f_2^{-1}(V)\end{aligned}$$we complete the proof. ^30fe04

**Corollary**  The product topology on $X × Y$ is the coarsest topology for which both $π_{1}$ and $π_{2}$ are continuous.

## Compactness and Continuous Functions

> [!theorem] Continuous Image of a Compact Set is Compact
> Let $X$ and $Y$ be topological spaces. If $K\subseteq X$ is compact and $f \colon X → Y$ is [[Continuous Maps on Topological Spaces#^33ee5a|continuous]], then $f (K )$ is compact.

> [!proposition]
> The inverse of a bijective continuous function $f\colon X\to Y$, with $Y$ compact, is continuous, so it is a homeomorphism. ^3626d1

*Proof*  Suppose $f\colon X\to Y$ is a continuous bijection. Consider the inverse function $f^{-1}\colon Y\to X$. Let $V\subset X$ be open, then $f(V)$ is open in $Y$ because $f$ is continuous. Since $Y$ is compact, $f(V)$ is compact. Since $f$ is a bijection, $f(V)$ is also a bijection. Therefore, $f(V)$ is closed. Hence, $f^{-1}$ is continuous.^33ee5a





**Corollary**  Let $X$ be a compact topological space and $f \colon X → \R$ continuous, where $\R$ is endowed with the standard topology. Then $f$ achieves its maximum and minimum value on $X$.

**Lemma**  Let $X$ and $Y$ be topological spaces and let $X × Y$ be endowed with the [[Constructions on Topological Spaces#^fbf303|product topology]]. Assume that $Y$ is compact. For $p ∈ X$, if $N ⊂ X ×Y$ is open with $\{p\}×Y ⊂ N$, then there is an [[Closure, Interior and Boundary#^eda962|open neighborhood]] $U$ of $p$ such that $U ×Y ⊂ N$.

**Thrm**  If $X$ and $Y$ are compact topological spaces, then $X × Y$ is also compact in the product topology.

> [!theorem] Heine–Borel Theorem
> Any closed interval $[a,b]$ is a compact subset of $\R$. More generally, a subset of  $\R^n$ is compact if and only if, it is bounded and is a close subset of  $\R^𝑛$. ^6e5465

*Proof*  
