>[!definition] Intersection
> Let $A$ and $B$ be two given sets. The intersection is the set:$$A\cap B=\{x:x\in A \wedge x\in B \}.$$ 
> More generally, we can intersect a collection of sets: $\bigcap_{i\in I} A_{i}$, where $I$ is some index set, and $A_{i}$ are sets. ^408460

>[!definition] Union
>The union of sets $A$ and $B$ is the set:$$A\cup B=\{x: x\in A \vee x\in B\}.$$
>More generally, we can union a collection of sets: $\bigcup_{i\in I} A_{i}$, where $I$ is some index set, and $A_{i}$ are sets. ^678b42

>[!definition] Disjoint Union
> The disjoint union of $A$ and $B$ is the set:$$A\sqcup B=\{(x,a):x\in A\}\cup\{(y,b):y\in B\}.$$ ^e08e6f

>[!definition] Difference and Complement
> The *difference* of $A$ from $B$ is the set $$A\setminus B=\{x:x\in A \wedge x \notin B\}$$
> In the circumstance that sets are considered within a fixed set $X$, for any subset $A$ of $X$ we write $X\setminus A$ as $A^{c}$ and call it the *complement* of $A$ in $X$.

> [!proposition]
> Let $A$, $B$, $C$ and $B_{i} (i ∈ I)$ be sets. The following properties hold:
> - Commutativity: $A\cap B=B\cap A$, $A\cup B=B\cup A$.
> - Associativity: $(A\cap B)\cap C=A\cap(B\cap C)$, $(A\cap B)\cap C=A\cap(B\cap C)$.
> - Distributivity: $A\cap\left(\bigcup_{i\in I}B_i\right)=\bigcup_{i\in I}(A\cap B_i)$, $A\cup\left(\bigcap_{i\in I}B_i\right)=\bigcap_{i\in I}(A\cup B_i)$.
> - de Morgan’s laws: $\left(\bigcap_{i\in I}B_i\right)^c=\bigcup_{i\in I}B_i^c$, $\left(\bigcup_{i\in I}B_i\right)^c=\bigcap_{i\in I}B_i^c$.
> $\quad$

*Proof*  These are direct consequences of the arithmetic of logical connectives. $\square$

## Cartesian Product

> [!definition] Cartesian Product
> Let $X_{1},\dots ,X_{n}$ be sets. The set$$\{(x_1,x_2,\dots,x_n):x_{1}\in X_{1},\dots,x_{n}\in X_{n}\}$$is called the *Cartesian product* of $X_{1},\dots,X_{n}$ and is written as$$X_1\times\dots\times X_{n}\quad \text{or} \quad \prod_{i=1}^{n}X_{i}$$where each $(x_1,\dots ,x_n)$ is an ordered $n$-tuple and the $x_{i}$ is called the $i$-th coordinate. ^bd02ce

> [!proposition]
> Suppose $\{X_{j}\}_{j\in J}$ and $\{Y_{k}\}_{k\in K}$ are families of sets for arbitrary index sets $J$ and $K$. Then
> $$\left(\bigcup_{j} X_{j}\right) \times \left(\bigcup_{k} Y_{k}\right)=\bigcup_{j,k} (X_{j} \times Y_{k}).$$ ^9d651c

*Proof*  For any element $(x_{l}, y_{r})\in \bigcup_{j,k} (X_{j} \times Y_{k})$, say $x_{l}\in X_{l}$ and $y_{r}\in Y_{r}$. Then $(x_{l},y_{r})\in (\bigcup_{j} X_{j}) \times (\bigcup_{k} Y_{k})$. The converse is similar. $\square$