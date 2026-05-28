---
created: 2024-03-22
updated: 2024-09-26
---

>[!definition] Bounded Subset
>A subset $\newcommand{\R}{\mathbb{R}}\newcommand{\N}{\mathbb{N}}\newcommand{\S}{\mathbb{S}}\newcommand{\Z}{\mathbb{Z}}\newcommand{\C}{\mathbb{C}}\newcommand{\E}{\mathbb{E}}\newcommand{\Q}{\mathbb{Q}}\newcommand{\interior}{\operatorname{\text{int}}}\newcommand{\exterior}{\operatorname{\text{ext}}}\newcommand{\car}[1]{\overline{\overline{#1}}}S$ of $(X,d)$ is bounded if there exist $a\in X$ and $r>0$ such that $S\subset B(a,r)$. ^7012df

>[!definition] Open and Closed Subset
A subset $U$ of $(X,d)$ is open in $X$ if for every $x \in U$ there exists $\epsilon > 0$ such that $B(x,\epsilon)\subset U$. A subset $F$ of $(X,d)$ is closed if $X\setminus F$ is open. ^e112b1

<b><u>e.g.</u></b>   
- In $\R$ open intervals are open and closed intervals are closed.
- In any metric space $(X,d)$ both $X$ and $\emptyset$ are both open and closed.
- In a metric space with the discrete metric every point ${x}$ is open.
$\quad$

> [!theorem]
> In a metric space $(X,d)$, a subset $A$ is open iff $\interior(A)=A$ iff every $x ∈A$ has an open ball $B_{r}(x)$ such that $B_{r} (x) ⊂ A$.


**Lemma**  Open balls are open.
**Proof**  Suppose $B(a,r)$ is a open ball on metric space $(X, d)$. For all $x\in B(a,r)$, we have $d(a,x)<r$. Let $\epsilon=r-d(a,x)>0$, consider ball $B(x,\epsilon)$. For all $y\in B(x,\epsilon)$, we have $$
d(a,y)\leq d(a,x)+d(x,y)<d(a,x)+r-d(a,x)=r
$$ Thus $y\in B(a,r)$, it follows that $B(x,\epsilon)\subset B(a,r)$, hence $B(a,r)$ is open.

> [!theorem]
> Let $(X,d)$ be a metric space. For any set $A ⊂ X$, $\interior(A)$ and $\exterior(A)$ are open.

*Proof*  We have $$\begin{aligned}x\in \interior (A)&\implies ∃B_{r}(x) \text{ s.t. } B_{r}(x)⊂A \\ &\implies ∃B_{r} (x) \text{ s.t. } B_{r}(x) = \interior(B_{r}(x)) ⊂ \interior(A)\\ &\implies \interior(A) \text{ is open}\end{aligned}$$Since $\exterior(A) = \interior(A^{c})$ and $\interior(A^{c})$ is open, $\exterior(A)$ is also open. $\square$

**Lemma**  The intersection of finitely many open sets is open, that is if $U_1,\dots,U_n$ are open in $(X,d)$ then $\bigcap_{i=1}^{n}U_{i}$ is open in $(X,d)$.

**Proof**  For all $x\in\bigcap_{i=1}^{n}U_{i}$, since $U_1,\dots,U_n$ are open, exist $\epsilon_i$ such that $B(x,\epsilon_{i})\subset U_{i}$. Let $\epsilon=\min_{i=1,2,\dots,n}\epsilon_i>0$, then for all $y\in B(x,\epsilon)$, we have $$d(x,y)<\epsilon\leq\epsilon_{i}$$ Hence $y\in B(x,\epsilon_{i})$ for all $i$. Therefore $y\in U_i$ for all $i$ and thus $B(x,\epsilon)\subset\bigcap_{i=1}^{n}U_{i}$.

**Lemma**  The union of arbitrarily many open sets is open. 

> [!corollary] 
> The union of finitely many closed sets is closed, that is if $F_{1}, \dots , F_{n}$ are closed in $(X, d)$ then $\bigcup_{i=1}^n F_{i}$ is closed in $(X, d)$. And the intersection of arbitrarily many closed sets is closed.

*Proof*  We observe that $$X\setminus\bigcup_{i=1}^nF_i=\bigcap_{i=1}^n(X\setminus F_i)$$ Therefore by applying the above lemma we have $\bigcup_{i=1}^n F_{i}$ is closed. $\square$

> [!theorem] Structure of Open Sets in $\R$
> Every open sets in $\R$ is a countable union of disjoint open intervals.

*Proof*  Let $A$ be open in $\R$. For each $x∈A$ we can find $a<x<b$ such that $(a, b) ⊂ A$. Let $$a_x:=\inf\{a:(a,x]\subset A\},\quad b_x:=\sup\{b:[x,b)\subset A\}$$Then $x ∈I_x =(a_{x},b_{x})⊂A$. One can show, for any $x,y ∈A$ with $x\neq y$, either $I_{x} = I_{y}$ or $I_x ∩I_y = \emptyset$. This completes the proof. $\square$

**Thrm**  In a metric space a set $A$ is open iff $A^{c}$ is closed.

**Thrm**  Let $(X,d)$ be a metric space and $A ⊂ X$. Then $$A\text{ is closed} \iff A=\overline{A}$$
**Proof**  $A \text{ is closed} \iff  A^{c} \text{ is open} \iff A^{c}=\interior(A^{c})=\exterior(A)\iff A=\exterior(A)^{c}=\overline{A}$.

**Thrm**  Let $(X,d)$ be a metric space and $A ⊂ X$. Then $\overline{A}$ and $∂A$ are closed.

**Proof**  Recall that $A = \exterior(A)^{c}$ and $\exterior(A)$ is open. Thus $\overline{A}$ is closed. Recall also that $$\partial A = X \setminus (\interior(A)\cup \exterior(A))$$and both $\interior(A)$ and $\exterior(A)$ are open. Hence $∂A$ is closed.

**Thrm**  $\interior(A)$ is the largest open set contained in $A$. $\overline{A}$ is the smallest closed set containing $A$.

**Proof**  If $B$ is an open set contained in $A$, then $B = \interior(B) ⊂ \interior(A)$. If $B$ is a closed set containing $A$, then $\exterior(B) ⊂ \exterior(A)$ and hence $A=\exterior(A)^{c} ⊂\exterior(B)^{c}=\overline{B} =B$.