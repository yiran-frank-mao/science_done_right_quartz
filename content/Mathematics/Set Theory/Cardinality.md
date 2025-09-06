## Cardinality and Properties

>[!definition] Cardinality
>With every set A we associate a symbol $\overline{\overline{A}}$, called the cardinality or cardinal number of A, which obeys the following rules:
>- If two sets $A$ and $B$ are equinumerous, then $\overline{\overline{A}} = \overline{\overline{B}}$.
>- For the empty set $\emptyset$ we set $\overline{\overline{\emptyset}}=0$.
>- For any $n∈\N$ we set $\overline{\overline{\{1,\dots,n\}}}=n$.
>- We set $\car{\N} = d$ and $\car{\R} = c$.
>- For two sets $A$ and $B$, if $A$ is equinumerous to a subset of $B$, then $\car{A}\leq\car{B}$.
>- If $\car{A}\leq\car{B}$ and $\car{A}\neq\car{B}$, we write $\car{A}<\car{B}$.
> $\quad$^1fd903

> [!proposition]
> $\car{A}\leq\car{B}$ if and only if there exists injection $f\colon A\to B$.
>

*Proof*  $g\colon A\to f(A), x \mapsto f(x)$ forms a bijection, $A \sim f(A)\subseteq B$. $\square$

> [!corollary] Pigeonhole Principle
> There does not exist an injective function whose codomain is smaller than its domain.

> [!proposition]
> The following properties hold:
> 1.  $0<1<2<\dots<d <c$.
> 2. For any infinite set $A$ there holds $\car{A}\geq d$.
> 3. $\car{A} \leq \car{B}$ and $\car{B} \leq \car{C}$ implies $\car{A} \leq \car{C}$.
> $\quad$

*Proof*  $n<n+1$ is obvious. We have $n<d$ as [[Equinumerous and Countability#^39892f|any denumerable set is infinite]]. And since [[Equinumerous and Countability#^818a9f|the set of real numbers is denumerable]] we have $d < c$. The second statement is a direct result of [[Equinumerous and Countability#^5d2bac|any infinite set has a denumerable subset]]. Since $\car{A}≤\car{B}$ and $\car{B} ≤\car{C}$, there exist injections $f \colon A\to B$ and $g\colon B \to C$. Thus $g\circ f \colon A→C$ is an injection. This means $\car{A}≤\car{C}$. $\square$

> [!definition] Disjoint Sets
> Given two sets $A$ and $B$, if $A∩B = \emptyset$, then $A$ and $B$ are called disjoint. For a family of sets $\{A_{i}\}_{i∈I}$, if $A_{i} ∩A_{j} =\emptyset$ for any two distinct indices $i,j ∈I$, then $\{A_{i}\}_{i∈I}$ is called mutually disjoint.

**Lemma**  Let $\{A_{i}\}_{i∈I}$ and $\{A_{i}\}_{i∈I}$ be two families of mutually disjoint sets over the same index set $I$. If $A_{i} \sim B_{i}$ for all $i ∈I$, then $$\bigcup_{i\in I}A_{i}\sim\bigcup_{i\in I}B_{i}$$
**Thrm**  <i><u>Schröder-Bernstein Theorem</u></i>
Let $A$ and $B$ be two sets. If $\car{A}\leq \car{B}$ and $\car{B}\leq \car{A}$, then $\car{A}=\car{B}$.
<u><b>e.g.</b></u>  Recall that $(0,1) \sim \R$. Since $(0,1) ⊂ [0,1]$, we have $\car{[0,1]} ≥ \car{(0,1)} = c$. Since $[0, 1] ⊂ \R$, we also have $\car{[0, 1]} ≤ \R = c$ . By the theorem, $\car{[0,1]}= c$.

**Thrm**  Any subset of a countable set is countable.
**Proof**  Let $X$ be countable and $A ⊂ X$ . If $A$ is finite, nothing needs to be proved. If $A$ is infinite, it follows from  that $\car{A} ≥ d$. On the other hand, since $A ⊂ X$ and $X$ is countable, we have $\car{A} ≤ X ≤ d$. By Schroder-Bernstein Theorem, we have $\car{A} = d$. ^aee7c6

**Thrm**  A countable union of countable sets is countable. ^7d624e

**Corollary**  If $A_{1},\dots,A_{n}$ are countable sets, then $\bigcup_{i=1}^{n}A_{i}$ is also a countable set. 
**Proof**  We define $A_{n+1} = A_{n+2} = \dots = \emptyset$. Then $\bigcup_{i=1}^nA_i=\bigcup_{i=1}^\infty A_i$ and the latter is countable by the above theorem. ^b77fc5

**Corollary**  Let $A$ and $B$ be two sets. If $\car{ A ∪ B} = c$, show that either $\car{A} = c$ or $\car{B} = c$.
**Proof**  Assume that $\car{A} < c$ and $\car{B} < c$. Since $\car{A∪B}=c$, there is a bijection $f\colon A∪B\to \R^2$. Let $U=f(A)$ and $V =f(B)$. Then $$\overline{\overline{U}}=\overline{\overline{A}}<c,\quad\overline{\overline{V}}=\overline{\overline{B}}<c,\quad\mathbb{R}^2=f(A\cup B)=f(A)\cup f(B)=U\cup V$$Let $X=\{(x,0):x\in\mathbb{R}\}$ and $Y=\{(0,y):y\in\mathbb{R}\}$. Then both $X$ and $Y$ have cardinality $c$. Let $p_1$ and $p_2$ denote the projections of $\R^2$ onto $X$ and $Y$ respectively. We claim that $p_1(U)\neq X$ and $p_{2}(V)\neq Y$. If $p_1(U) = X$, since $p_1$ is a surjection, this means that $X$ is equinumerous to a subset of $U$ and hence $\car{U} ≥ \car{X} = c$, contradicting $\car{U} < c$. By a similar argument we can obtain $p_2(V ) \neq Y$. Therefore, there exists $x^*, y^* ∈ \R$ such that $(x^*, y) \notin U$ for all $y∈\R$ and $(x,y^{*})\notin V$ for all $x∈\R$. Thus $(x^{*},y^{*)}\notin U∪V =\R^2$, yielding a contradiction.

**Thrm**  The set $\Q$ of rational numbers is denumerable.
**Proof**  By definition, we have$$\Q=\bigcup_{n=1}^{\infty} A_{n},\quad A_{n}\colon=\left\{\frac mn:m\in\mathbb{Z}\right\}$$Indeed $A_{n}\sim \Z\sim\N$ by mapping $\frac{m}{n}\mapsto m$. Hence $\car{Q}\leq d$ by [[Cardinality#^7d624e|theorem]]. As $\N\subset \Q$, $\car{Q}\geq d$. Therefore $\car{\Q}=d$.

> [!theorem]
> Let $A$ be an infinite set and $B$ a countable set. Then $\car{A∪B} = \car{A}$. ^5f56a0

*Proof*  Since $A$ is infinite, by proposition we can pick a denumerable subset $A_{1} ⊂ A$. Since $B$ is countable, by [[Cardinality#^aee7c6|theorem]] $B \setminus A$ is also countable. It then follows from [[Cardinality#^b77fc5|corollary]] that $A_{1} ∪(B \setminus A)$ is countable, that is $\car{A_{1} ∪(B \setminus A)}≤ d$. Note that $\car{A_{1} ∪ (B \setminus A)} ≥ A_{1} = d$ . By the Schroder-Bernstein Theorem we have $\car{A_{1} ∪(B \setminus A)} = d$, thus $A_{1} \sim A_{1} ∪(B \setminus A)$. Therefore, we may use lemma to obtain$$A=(A\setminus A_1)\cup A_1\sim(A\setminus A_1)\cup(A_1\cup(B\setminus A))=A\cup B$$as required. 


**Corollary**  The set of irrational numbers has cardinality $c$, that is $\R\setminus\Q \sim \R$.
**Proof**  Note that $(\R \setminus \Q) ∪ \Q = \R$. Recall that $\Q$ is denumerable. If $\R \setminus \Q$ is finite, then the [[Cardinality#^b77fc5|corollary]] would imply $\R$ is countable, contradicting the fact $\car{\R} = c > d$. Thus $\R \setminus \Q$ must be infinite. It then follows from [[Cardinality#^5f56a0|theorem]] that $\car{\R \setminus \Q} = \car{\R}$.

**Thrm**  If $A_{1},\dots ,A_{n}$ are countable, then $A_{1} \times\dots\times A_{n}$ is also countable.
**Proof**  The result holds trivially for $n = 1$. Assume the result is true for $n = k$, that is the product of any $k$ countable sets is countable. The consider $n = k +1$. Let $A_{1},\dots,A_{k},A_{k+1}$ be $k +1$ countable sets. Since $A_{k+1}$ is countable, we may write $A_{k+1}=\{x_1,x_2,\dots\}$. Let $B_{i} =A_{1}\times\dots\times A_{k}\times\{x_{i}\}$ for each $i$. Then $B_{i}\sim A_{i}\times\dots A_{k}$ by simply $(a_{1},a_{2},\dots,a_{k},x_{i})\mapsto(a_{1},a_{2},\dots,a_{k})$. Hence each $B_{i}$ is countable by inductive hypothesis. Therefore, $$A_{1} \times\dots\times A_{k+1}=\bigcup_{i}B_{i}$$is countable as [[Cardinality#^7d624e|countable union of countable sets is countable]].

**Thrm**  Let $\R^{\infty}$ denote the set of all sequences consisting of real numbers, that is $$\R^{\infty}=\{(x_{1},x_{2},x_{3},\dots) \mid x_{i}\in\R \text{ for all } i=1,2,3,\dots\}$$Then $\car{\R}=c$.

**Corollary**  For any $n\in \N$ there holds $\car{\R^{n}}=c$.

**Corollary**  Let $A_{1},\dots ,A_{n}$ be nonempty sets with $\car{A_{i}}≤ c$ for each $i$ and at least one of them has cardinality $c$. Then $A_{1} \times\dots\times A_{n}$ has cardinality $c$. ^f185f1

**Thrm**  Let $\{A_{i}\}_{i∈I}$ be a family of sets with $1≤\car{I} ≤c$ and $\car{A_{i}} ≤c$ for all $i ∈I$. If one of $\{A_{i}\}_{i∈I}$ has cardinality $c$, then $$\car{\bigcup_{i\in I}A_{i}}=c$$**Proof**  According to [[Cardinality#^f185f1|corollary]] we have $\car{I \times \R}=c$. Since $\car{A_{i}}≤c$, there exists an injection $f_{i}\colon A_{i}\to \R$ for each $i\in I$. Consider the function $f\colon \bigcup_{i\in I}A_{i} \to I \times \R$ such that $x \mapsto (j, f_{j}(x))$ for all $x\in A_{j}$. Observe that $f$ is injective, therefore $$\car{\bigcup_{i\in I}A_i}\leq\car{I\times\mathbb{R}}=c$$On the other hand, since there is $i_{0}∈I$ such that $\car{A_{i_{0}}}=c$ and $A_{i_{0}}  ⊂\bigcup_{i\in I}A_i$, we have$$\car{\bigcup A_i}\geq\car{A_{i_0}}=c$$Hence $\car{\bigcup_{i\in I}A_{i}}=c$.

## Power Sets

**Def**  <i><u>Power Set</u></i>
Given a set $A$, the set consisting of all subsets of $A$ is called the power set of $A$, denoted as $P(A)$.
<u><b>e.g.</b></u>  For $A = \{1,2,3\}$ we have $P(A)=\{\emptyset,\{1\},\{2\},\{3\},\{1,2\},\{1,3\},\{2,3\},\{1,2,3\}\}$

**Thrm**  For any set $A$ there holds $\car{A} < \car{P(A)}$.
**Proof**  Note that the function $\varphi \colon A → P(A)$ defined by $φ(x)=\{x\}$ for all $x ∈A$ is an injection. Therefore $\car{A} ≤ \car{P(A)}$. If $A = P(A)$, then there exists a bijection $f \colon A→P(A)$. Define $$Y=\{x\in A:x\notin f(x)\}$$which is a subset of $A$ and hence is contained in $P(A)$. Thus there exists $y ∈ A$ such that $Y=f(y)$. We have either $y∈Y$ or $y \neq Y$. If $y∈Y$,then as an element in $Y$ we must have $y\neq f(y)=Y$ which is a contradiction; if $y \notin Y$, then $y \notin f(y)$, by definition of $Y$ we must have $y ∈ Y$ , a contradiction again. This shows $\car{A} \neq \car{P (A)}$. Consequently $\car{A} < \car{P(A)}$.

**Corollary**  There is no maximal cardinality.
**Proof**  A direct consequence of the above theorem.

**Thrm**  $\car{P(\N)} = c$.

**Hypo**  <i><u>Continuum Hypothesis</u></i>
There does not exist a set $A$ with $d < \car{A} < c$.

**Thrm**  The continuum hypothesis is consistent while independent with the accepted axioms of set theory. Therefore, the continuum hypothesis is undecidable within the existing axioms of set theory.
