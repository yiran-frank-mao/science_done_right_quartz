---
created: 2024-03-22
updated: 2025-05-03
---

>[!definition] Open and Closed Ball
>Let $\require{mhchem}\newcommand{\R}{\mathbb{R}}\newcommand{\interior}{\operatorname{\text{int}}}\newcommand{\exterior}{\operatorname{\text{ext}}}(X,d)$ be an arbitrary metric space. The open ball centered at $a \in X$ of radius $r\in\R^+$ is the set $$B_{r}(a)=B(a,r) = \{x\in X\mid d(x,a)<r\}$$ and the closed ball centered at $a \in X$ of radius $r\in\R^+$ is the set $$ \bar{B}(a,r) = \{x\in X\mid d(x,a)\leq r\}$$<b><u>e.g.</u></b>  If $X$ is any set and $d$ is the discrete metric then $$ B(x,r)=\begin{cases}\{x\}&r\leq1\\X&r>1&\end{cases} $$

>[!definition] Interior
>Let $(X,d)$ be a metric space, $A⊂X$ and $x ∈X$. $x$ is called an interior point of $A$ if there is $r >0$ such that $B(x,r)⊂A$. The set of all interior points of $A$ is called the interior of $A$, denoted by $\newcommand{\interior}{\operatorname{\text{int}}}\newcommand{\exterior}{\operatorname{\text{ext}}}\interior(A)$ or $A^\circ$. ^7741a2

>[!definition] 
>**Def**  <i><u>Exterior</u></i>
>Let $(X,d)$ be a metric space, $A⊂X$ and $x ∈X$. $x$ is called an exterior point of $A$ if there is $r>0$ such that $B(x,r)⊂A^{c} =X\setminus A$. The set of all exterior points of $A$ is called the exterior of $A$, denoted by $\exterior(A)$.

>[!definition] 
>**Def**  <i><u>Boundary</u></i>
>Let $(X,d)$ be a metric space, $A⊂X$ and $x ∈X$. $x$ is called a boundary point of $A$ if every ball $B(x,r)$ contains points of $A$ and points of $A^{c}$. The set of all boundary points of $A$ is called the boundary of $A$, denoted by $\partial A$.

>[!proposition] 
>**Prop**  By definition we can see immediately that
>- $\interior(A) ⊂ A$ and $\exterior(A) ⊂ A^{c}$.
>- $\exterior(A) = \interior(A^{c})$ and $\interior(A) = \exterior(A^{c})$.
>- int(A), $\exterior(A)$ and $∂A$ are mutually disjoint and $X = \interior(A)∪\exterior(A)∪∂A$.
>- If $A ⊂ B$, then $\interior(A) ⊂ \interior(B)$ and $\exterior(A) ⊃ \exterior(B)$.
>$\quad$

>[!proposition] 
>**Prop**  Let $(X,d)$ be a metric space, $x ∈X$ and $r >0$. Then
>- $\interior(B_{r}(x))=B_{r}(x)$.
>- $\exterior(B_{r}(x))⊃\{y∈X\mid d(y,x)>r\}$.
>- $\partial B_r(x)\subset\{y\in X\mid d(y,x)=r\}$.
>$\quad$

>[!corollary] 
>**Corollary**  Let $(X, \| \cdot \|)$ be a [[Normed Spaces#^345fd3|normed vector space]] and let $d$ be the induced metric. Then,
>- $\interior(B_r(x))=B_r(x)$.
>- $\exterior(B_r(x))=\{y\in{X}:d(y,x)>r\}$.
>- $\partial B_{r}(x)=\{y\in X:d(y,x)=r\}$.
>$\quad$