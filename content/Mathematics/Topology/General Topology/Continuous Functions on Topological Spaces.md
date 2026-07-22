---
created: 2024-05-22
updated: 2024-09-26
---
>[!definition] Continuous Function
> Let $(X,τ_{X})$ and $(Y,τ_Y)$ be [[Topological Spaces#^65c94a|topological spaces]] and $f \colon X \to Y$ a function. $f$ is called *continuous* if for every open set $V$ in $Y$, $f^{−1}(V)$ is open in $X$. 
>$f$ is called *continuous at $x \in X$* if, for any [[Closure, Interior and Boundary#^eda962|neighborhood]] $V$ of $f (x)$ in $Y$, the set $f^{−1}(V)$ is a neighborhood of $x$ in $X$. ^33ee5a

>[!theorem] 
>Let $(X,τ_{X})$ and $(Y,τ_{Y})$ be topological spaces. Consider a function $f \colon X →Y$. The following are equivalent:
>- $f$ is continuous at every point in $X$.
>- $f$ is continuous on $X$.
>- $f^{-1}(C)$ is closed in $X$ for every closed set $C$ in $Y$.
>- $f^{-1}(B) \in \tau_{X}$ whenever $B \in \mathcal{B}$ for a [[Topological Spaces#^2fc468|basis]] $\mathcal{B}$ of $\tau_{Y}$.
>- $f^{-1}(S)\in \tau_{X}$ whenever $S\in\mathcal{S}$ for a [[Topological Spaces#^02668a|subbasis]] $\mathcal{S}$ of $\tau_{Y}$.
>$\quad$

>[!theorem] 
>**Thrm**  Let $f \colon X → Y$ be a function between two topological spaces $X$ and $Y$. Assume that $X=\bigcup_{\alpha} U_{\alpha}$ ,where $U_{\alpha}$ is open in $X$ for each index $α$. Then $f$ is continuous if and only if $f \big|_{U_α}$ is continuous.

>[!definition] 
>**Def**  <i><u>Projection Map</u></i>
>Define the following function as projection maps: $$\begin{aligned}\pi_{1}\colon X \times Y \to X, \quad (x,y) \mapsto x \\\pi_{2}\colon X \times Y \to Y, \quad (x,y) \mapsto y\end{aligned}$$

**Thrm**  Let $A$, $X$ and $Y$ be topological spaces. A function $f \colon A → X × Y$ is continuous if and only if the components $f_{1} = π_{1} \circ f$ and $f_{2} = π_{2} \circ f$ are continuous.
**Proof**  Recall that $f$ is continuous iff $f ^{−1}(S)$ is open in $A$ for any $S ∈ \mathcal{S}$ . Since $$\begin{aligned}f^{-1}(U\times Y)=f^{-1}(\pi_1^{-1}(U))=(\pi_1\circ f)^{-1}(U)=f_1^{-1}(U)\\f^{-1}(X\times V)=f^{-1}(\pi_2^{-1}(V))=(\pi_2\circ f)^{-1}(V)=f_2^{-1}(V)\end{aligned}$$we complete the proof. ^30fe04

**Corollary**  The product topology on $X × Y$ is the coarsest topology for which both $π_{1}$ and $π_{2}$ are continuous.

## Compactness and Continuous Functions

**Thrm**  Let $X$ and $Y$ be topological spaces. If $K\subseteq X$ is compact and $f \colon X → Y$ is [[Continuous Functions on Topological Spaces#^33ee5a|continuous]], then $f (K )$ is compact.

**Thrm**  If $f\colon X\to Y$ is 

> [!proposition]
> The inverse of a bijective continuous function $f\colon X\to Y$, with $Y$ compact, is continuous. ^3626d1

*Proof*  Suppose $f\colon X\to Y$ is a continuous bijection. Consider the inverse function $f^{-1}\colon Y\to X$. Let $V\subset X$ be open, then $f(V)$ is open in $Y$ because $f$ is continuous. Since $Y$ is compact, $f(V)$ is compact. Since $f$ is a bijection, $f(V)$ is also a bijection. Therefore, $f(V)$ is closed. Hence, $f^{-1}$ is continuous.^33ee5a


**Corollary**  Let $X$ be a compact topological space and $f \colon X → \R$ continuous, where $\R$ is endowed with the standard topology. Then $f$ achieves its maximum and minimum value on $X$.

**Lemma**  Let $X$ and $Y$ be topological spaces and let $X × Y$ be endowed with the [[Constructions on Topological Spaces#^fbf303|product topology]]. Assume that $Y$ is compact. For $p ∈ X$, if $N ⊂ X ×Y$ is open with $\{p\}×Y ⊂ N$, then there is an [[Closure, Interior and Boundary#^eda962|open neighborhood]] $U$ of $p$ such that $U ×Y ⊂ N$.

**Thrm**  If $X$ and $Y$ are compact topological spaces, then $X × Y$ is also compact in the product topology.

> [!theorem] Heine–Borel Theorem
> Any closed interval $[a,b]$ is a compact subset of $\R$. More generally, a subset of  $\R^n$ is compact if and only if, it is bounded and is a close subset of  $\R^𝑛$. ^6e5465

*Proof*  
