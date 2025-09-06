>[!definition] Limit Point & Isolated Point
>Let $\newcommand{\R}{\mathbb{R}}\newcommand{\interior}{\operatorname{\text{int}}}\newcommand{\exterior}{\operatorname{\text{ext}}}(X,d)$ be a metric space and $A ⊂ X$. $x ∈ X$ is called a limit point of $A$ if every open ball $B_{r} (x)$ contains a point of $A$ other than $x$. 
>Conversely, $x ∈ A$ is called an isolated point of $A$ if there is an open ball $B_{r} (x)$ that contains no elements of $A$ other than $x$.

<u><b>e.g.</b></u>  
- Consider $A = (0, 1) ∪ \{2\}$ in $\R$ with Euclidean metric. Then $2$ is an isolated point of $A$, every point in $[0,1]$ is a limit point of $A$ and the closure of $A$ is $[0,1]∪\{2\}$.
- Let $(X, \|\cdot\|)$ be a [[Normed Spaces#^345fd3|normed vector space]] and $x ∈ X$. Then for any $r > 0$ we have $$\{\text{all limit points of }B_r(x)\}=\{y\in X:\|y-x\|\leq r\}$$

$\quad$

>[!definition] Closure
>The closure of $A$ is defined as $$\overline{A}=A\cup\{\text{all limit points of }A\}$$

>[!theorem] 
>Let $(X,d)$ be a metric space and $A ⊂ X$. If $x ∈ X$ is a limit point of $A$, then every open ball $B_{r} (x)$ contains infinitely many points of $A$.

*Proof*  

>[!theorem] 
>$x ∈ \overline{A}$ if and only if every $B_{r} (x)$ contains a point of $A$.

*Proof*  $x ∈\overline{A}$ implies $x ∈A$ or $x$ is a limit point of $A$. Thus every $B_{r}(x)$ contains a point of $A$. Suppose every $B_{r}(x)$ contains a point of $A$. If $x ∈A$, then $x ∈\overline{A}$. If $x \notin A$, then by the given condition, every $B_{r}(x)$ contains a point of $A$ other than $x$. Thus $x$ is a limit point of $A$ and hence $x∈\overline{A}$. $\square$

>[!theorem] 
>Let $(X,d)$ be a metric space and $A ⊂ X$, then $$\overline{A}=\exterior(A)^{c}=\interior(A)\cup\partial A=A\cup\partial A$$

*Proof*  we have$$\begin{aligned} x\in \overline{A} &\iff \text{every $B_{r}(x)$ contains a point of $A$} \\ &\iff x\notin \exterior(A) \\ &\iff x \in \exterior(A)^{c} \end{aligned}$$Therefore $\overline{A} = \exterior(A)^{c}$. Consequently, $$\overline{A}=X\setminus\mathrm{ext}(A)=\mathrm{int}(A)\cup\partial A$$This and $\interior(A)⊂A$ imply $\overline{A}⊂A∪∂A$. Since $A⊂\overline{A}$, we must have $A∪∂A⊂\overline{A}$ and thus $\overline{A}=A∪∂A$. $\square$
