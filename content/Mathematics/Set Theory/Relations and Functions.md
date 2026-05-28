---
created: 2024-02-23
updated: 2024-10-29
completed: true
---
## Relations

>[!definition] Binary Relation
>A binary relation $R$ over sets $X$ and $Y$ is a set of ordered pairs of elements from $X$ and $Y$:$$R ⊆ \{ (x,y) \mid x\in X, y\in Y \}$$The statement $(x,y) ∈ R$ reads "$x$ is $R$-related to $y$" and is written as $xRy$. ^d801dc

> [!definition] Homogeneous Relation
> A homogeneous relation on a set $X$ is a binary relation between $X$ and itself, i.e. it is a subset of $X\times X$. ^759a11

> [!definition] Reflexivity
> A homogeneous relation $R$ on a set $X$ is reflexive if it relates every element of $X$ to itself. That is $(x,x) \in R$. ^1bdc5e
>

> [!definition] Symmetry
> A homogeneous relation $R$ on a set $X$ is symmetric if $aRb \implies bRa$.

> [!definition] Antisymmetry
> A homogeneous relation $R$ on a set $X$ is antisymmetric if there is no pair of distinct elements of $X$ each of which is related by $R$ to the other. Formally, $R$ is antisymmetric if for all $a, b \in X$,$$(a,b)\in R \text{ and } a\neq b \implies (b,a)\notin R$$ Equivalently, $$aRb, bRa \implies a=b$$^cb363c

> [!definition] Transitivity
> A homogeneous relation $R$ on a set $X$ is transitive if, for all elements $a, b, c$ in $X$, whenever $R$ relates $a$ to $b$ and $b$ to $c$, then $R$ also relates $a$ to $c$. ^1f742d

> [!definition] Connectedness
> A homogeneous relation $R$ on a set $X$ is connected if for all $x,y\in X$: $$x\neq y \implies xRy \text{ or } yRx$$It is called strongly connected if $xRy$ or $yRx$ for all $x,y\in X$ no matter if they are equal. ^f0a2cd

> [!definition] Univalent
> For all $x ∈ X$ and $y_{1},y_{2}\in Y$ with relation $R$, if $xRy_{1}$ and $xRy_{2}$ implies $y_1 = y_2$, we say $R$ is univalent. ^70f956

> [!definition] Serial
> We say $R$ defined on $X$ and $Y$ is serial or total if for all $x ∈ X$, there exists some $y ∈ Y$ such that $xRy$. ^d97ac1

## Equivalence Relation

>[!definition] Equivalence Relation
>An equivalence relation is a relation on a set, generally denoted by $∼$, that is reflexive, symmetric, and transitive for everything in the set.
>- Reflexivity: $a ∼ a$
>- Symmetry: $a∼b \implies b∼a$
>- Transitivity: $a∼b \text{ and } b∼c \implies a∼c$
>$\quad$ ^14741d

<u><b>e.g.</b></u>  The relation “is equal to”, denoted $=$, is an equivalence relation on the set $\mathbb{R}$.

> [!definition] Equivalence Class
> Given an equivalence relation $\sim$ defined on set $X$, the equivalence class $[x]$ of an element $x ∈ X$ is defined by $$[x]:=\{y\in X \mid x\sim y\}$$ ^973688

> [!proposition]
> Suppose some equivalence relation $\sim$ is defined on set $X$, then every element $z\in X$ is exactly in one of the equivalence classes.

*Proof*  Suppose $z\in [x_1]$ and $z\in [x_2]$. Then we have $z\sim x_1$ and $z\sim x_2$, it follows that $x_{1}\sim x_{2}$, hence $x_{1}\in[x_{2}]$, yielding that $[x_{1}]=[x_{2}]$.

> [!definition] Quotient
> The set of all equivalence classes in $X$ with $\sim$, is called the quotient of $X$ by $\sim$: $$X / \mathord{\sim}:=\{[x]\mid x\in X\}$$

## Function and Associated Sets

>[!definition] Function
>Let $X$ and $Y$ be two sets. A function $f \colon X \to Y$ is a relation that is [[Relations and Functions#^70f956|univalent]] and [[Relations and Functions#^d97ac1|serial]] defined over $X$ and $Y$. The sets $X$ and $Y$ are called the domain and codomain of $f$ respectively. ^862dba

> [!definition] Range
> For some function $f\colon X\to Y$, the range is the set$$f(X)=\{y\in Y:y=f(x)\text{ for some }x\in X\}$$ ^eb7c36

> [!definition] Graph
> The following set is called the graph of a function $f$:$$\Gamma(f)=\{(x,y):x ∈X,y ∈Y \text{ and } y =f(x)\}$$ ^bd51b5

>[!definition] Image
>Given a subset $A\subset X$, its image under $f\colon X\to Y$ is defined by$$f(A)=\{y\in Y:y=f(x) \text{ for some }x\in A\}$$^8f2f00

> [!definition] Preimage
> Given a subset $B ⊂ Y$ , its inverse image or preimage under $f$ is defined by$$f^{-1}(B)=\{x\in X:f(x)\in B\}$$

> [!proposition]
> Let $f \colon X \to Y$ be a function. For any set $A⊂X$ and $B ⊂Y$ there hold$$A\subset f^{-1}(f(A)), \quad f(f^{-1}(B))\subset B$$

*Proof*  For any $x\in A$, $f(x)\in f(A)$, thus $x\in f^{-1}(f(A))$. For any $y\in f(f^{-1}(B))$, $y=f(x)$ for some $x\in f^{-1}(B)$, thus $y=f(x)\in B$.  $\square$

> [!proposition]
> Suppose $f\colon X \to Y$. For any family of sets $\{A_{i}\}_{i\in I}$ in $X$ there hold$$f\left(\bigcup_{i\in I}A_i\right)=\bigcup_{i\in I}f(A_i),\quad f\left(\bigcap_{i\in I}A_i\right)\subset\bigcap_{i\in I}f(A_i)$$

*Proof*  By definition, for all $y\in f\left(\bigcup_{i\in I}A_{i}\right)$, $y=f(a)$ for some $a \in \bigcup_{i\in I}A_{i}$. Thus $a\in A_{k}$ for some $k\in I$. It follows that $y=f(a)\in \bigcup_{i\in I}f(A_i)$. All statements above are reversible, thus we have equality holds: $f\left(\bigcup_{i\in I}A_i\right)=\bigcup_{i\in I}f(A_i)$. Consider any $y\in f\left(\bigcap_{i\in I}A_{i}\right)$, then $y=f(a)$ for some $a\in \bigcap_{i\in I}A_{i}$. It follows that $a\in A_{i}$ for all $i\in I$, hence $y=f(a)\in f(A_{i})$ for all $i\in I$. Thus $y\in \bigcap_{i\in I}f(A_{i})$. $\square$

> [!proposition]
> Suppose $f\colon X \to Y$. For any family of sets $\{B_{i}\}_{i∈I}$ in $Y$ there hold$$f^{-1}\left(\bigcup_{i\in I}B_i\right)=\bigcup_{i\in I}f^{-1}(B_i),\quad f^{-1}\left(\bigcap_{i\in I}B_i\right)=\bigcap_{i\in I}f^{-1}(B_i)$$

*Proof*  For any $x\in f^{-1}\left(\bigcup_{i\in I}B_i\right)$, $f(x)\in \bigcup_{i\in I}B_i$, thus $f(x)\in B_{k}$ for some $k\in I$. It follows that $x\in f^{-1}(B_{k})$ and hence $x\in \bigcup_{i\in I}f^{-1}(B_i)$. All statements above are reversible, thus we have equality holds: $f^{-1}\left(\bigcup_{i\in I}B_i\right)=\bigcup_{i\in I}f^{-1}(B_i)$. Consider any $x\in f^{-1}\left(\bigcap_{i\in I}B_i\right)$, then $f(x)\in \bigcap_{i\in I}B_i$, it follows that $f(x)\in B_{i}$ for all $i\in I$. Thus $x\in f^{-1}(B_{i})$ for all $i\in I$, hence $x\in \bigcap_{i\in I}f^{-1}(B_{i})$. Conversely, for any $x\in \bigcap_{i\in I}f^{-1}(B_{i})$, $x\in f^{-1}(B_{i})$ for all $i\in I$, thus $f(x)\in B_{i}$ for all $i\in I$, hence $f(x)\in \bigcap_{i\in I}B_{i}$. That is $x\in f^{-1}\left(\bigcap_{i\in I}B_{i}\right)$. $\square$

## Composition and Inverse

>[!definition] Composition
>Let $f \colon X \to Y$ and $g\colon Y \to Z$ be two functions. Then the function $g\circ f \colon X \to Z$ defined by$$(g\circ f)(x)=g(f(x)),\quad\text{ for all }x\in X$$is called the composition of $f$ and $g$.

>[!definition] Injection, Surjection and Bijection
>Let $f \colon X \to Y$ be a function,
>- $f$ is called injective or one-one if $f (x_{1}) = f (x_{2})$ implies $x_{1} = x_{2}$.
>- $f$ is called surjective or onto if $f(X)=Y$, i.e. for every $y ∈Y$ there is $x ∈X$ such that $y = f (x)$.
>- $f$ is called bijective if $f$ is both injective and surjective.
>$\quad$ ^042daf

> [!proposition]
> If a set $X$ is finite, then a function $f \colon X \to X$ is injective if and only if it is [[Relations and Functions#^042daf|surjective]]. ^9109dc

*Proof*  Suppose $f\colon X\to X$ is injective. Assume $f$ is not surjective, then there exists $y\in X$ such that $y\notin f(X)$. Because $X$ is finite, by the pigeonhole  $\square$

>[!definition] Invertible Function
>A function $f \colon X \to Y$ is invertible if there is a function $g \colon Y \to X$ such that$$g(f(x))=x, \text{ and } f(g(y))=y \text{ for all } x\in X, y\in Y$$We will call $g$ the inverse of $f$ and denote it as $f ^{−1}$.

>[!theorem]
>A function $f \colon X \to Y$ is invertible if and only if it is bijective.

*Proof*  Assume $f \colon X \to Y$ is invertible and $f^{−1} \colon Y \to X$ denotes its inverse function. If $f (x_{1}) = f (x_{2})$, then $$x_1=f^{-1}(f(x_1))=f^{-1}(f(x_2))=x_2$$which shows that f is injective. Next, for any $y ∈ Y$ , we have $y = f (f ^{−1}(y))$ which means $f$ is surjective. Thus $f$ is bijective. Conversely, if $f$ is bijective, then for any $y$ there is one and only one $x ∈ X$ such that $y = f (x)$. Define $g \colon Y \to X$ by $g(y) = x$ which is well-defined. Moreover $g(f(x))=g(y)=x$ and $f(g(y))=f(x)=y$ which shows that f is invertible and $f ^{−1} = g$. $\square$
