---
created: 2024-05-22
updated: 2024-09-26
---
>[!definition] Continuous Function
> Let $(X,\tau_{X})$ and $(Y,\tau_Y)$ be [[Topological Spaces#^concept-39ce12df888c|topological spaces]] and $f \colon X \to Y$ a function. $f$ is called *continuous* if for every open set $V$ in $Y$, $f^{−1}(V)$ is open in $X$. 
>$f$ is called *continuous at $x \in X$* if, for any [[Closure, Interior and Boundary#^eda962|open neighborhood]] $V$ of $f(x)$ in $Y$, the set $f^{−1}(V)$ is a (not necessarily open) [[Closure, Interior and Boundary#^eda962| neighborhood]] of $x$ in $X$. ^33ee5a

<u><b>e.g.</b></u> 
- The identity map $\operatorname{id}_{X} \colon X → X$ is continuous;
- Any constant map is continuous;
- The composition of two continuous maps is always continuous.
$\quad$

>[!theorem] 
>Let $(X,τ_{X})$ and $(Y,τ_{Y})$ be topological spaces. Consider a function $f \colon X →Y$. The following are equivalent:
>1. $f$ is continuous on $X$;
>2. $f$ is continuous at every point in $X$;
>3. $f^{-1}(C)$ is closed in $X$ for every closed set $C$ in $Y$;
>4. $f^{-1}(B) \in \tau_{X}$ whenever $B \in \mathcal{B}$ for a [[Topological Spaces#^2fc468|basis]] $\mathcal{B}$ of $\tau_{Y}$;
>5. $f^{-1}(S)\in \tau_{X}$ whenever $S\in\mathcal{S}$ for a [[Topological Spaces#^02668a|subbasis]] $\mathcal{S}$ of $\tau_{Y}$;
>6. $f(\overline{A})\subset \overline{f(A)}$ for all $A\subset X$;
>$\quad$ ^30fe04

*Proof*  2 is obvious; 3 comes from definition of closed sets; 4 and 5 are because [[Relations and Functions#^f5be27|preimages preserve unions and intersections]]. We prove 6 here. Suppose $f$ is continuous. Since $\overline{f(A)}$ is closed, $f^{-1}(\overline{f(A)})$ is closed in $X$. Note that $f(A)\subset \overline{f(A)}$, so $A\subset f^{-1}(\overline{f(A)})$, hence $\overline{A}\subset f^{-1}(\overline{f(A)})$, thus $f(\overline{A})\subset \overline{f(A)}$. For the other direction, suppose $f(\overline{A})\subset \overline{f(A)}$ for all $A\subset X$. Let $C$ be a closed subset of $Y$. Then $f(\overline{f^{-1}(C)})\subset \overline{f(f^{-1}(C))}=\overline{C}=C$, thus $\overline{f^{-1}(C)}\subset f^{-1}(C)$, so $f^{-1}(C)$ is closed in $X$. Therefore, $f$ is continuous.  $\square$ 

>[!theorem] 
> Let $f \colon X → Y$ be a function between two topological spaces $X$ and $Y$. Assume that $X=\bigcup_{\alpha} U_{\alpha}$ ,where $U_{\alpha}$ is open in $X$ for each index $α$. Then $f$ is continuous if and only if $f \big|_{U_α}$ is continuous for every $\alpha$.

> [!definition] Open and Closed Map
> A map $f\colon X\to Y$ is *open* if for every open set $U\subset X$, $f(U)$ is open in $Y$. Similarly, it is *closed* if for every closed set $C\subset X$, $f(C)$ is closed in $Y$.
> ^cd295d

