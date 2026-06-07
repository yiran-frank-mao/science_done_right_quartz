---
created: 2024-02-23
updated: 2025-02-09
---
## Equinumerous Sets

> [!definition] Equinumerous
> Let $A$ and $B$ be two sets. If there exists a bijection $f \colon A\to B$, then we say $A$ is *equinumerous* or *equivalent* to $B$ and write $A \sim B$.

<u><b>e.g.</b></u> 
- We have $\newcommand{\N}{\mathbb{N}}\newcommand{\Z}{\mathbb{Z}}\N\sim\Z$ because the function $f \colon \N\to\Z$ defined by $$f(n)=\begin{cases}k \quad &\text{if } n=2k \\-k \quad &\text{if } n=2k+1\end{cases}$$is a bijection.
- $[0,1)\sim(0,1)$ because we can take a sequence $\{a_{n}\}$ with distinct elements in $(0,1)$, say $a_{n} = \frac{1}{3^{n}}$ for $n = 1,2,\cdots$. Define $f \colon [0,1) → (0,1)$ as follows: $$f(x)=\left\{\begin{array}{ll}1/3&\quad\text{if $x=0$,}\\1/3^{n+1}&\quad\text{if $x=1/3^n$ for }n\geq1,\\x&\quad\text{otherwise}\end{array}\right.$$Then $f$ is a bijection and thus $[0, 1) ∼ (0, 1)$.
$\quad$

> [!proposition]
> The equinumerous relation is an [[Relations and Functions#^14741d|equivalence relation]].

 *Proof*  The identity function is a bijection $A \to A$, thus it is reflexive. If $A ∼ B$, then there is a bijection $f \colon A \to B$. The inverse function $f^{−1} \colon B \to A$ is also a bijection. Thus $B ∼A$, therefore it is symmetric. If $A∼B$ and $B ∼C$, then there exist bijection $f \colon A\to B$ and $g \colon B \to C$. Since the composition $g\circ f \colon A\to C$ is a bijection, we have $A∼C$, thus it is transitive. $\square$

> [!theorem] Cantor-Schröder-Bernstein Theorem
> If both $f\colon A\to B$ and $g\colon B\to A$ are [[Relations and Functions#^042daf|injective]], then $A\sim B$.


## Countability of Sets

> [!definition] Finite Set
> A set is called finite if it is either empty or it is equinumerous to $\{1,\dots,n\}$ for some $n ∈ \N$. If a set is not finite, then it is called infinite.

> [!definition] Denumerability & Countability
> A set is called denumerable if it is equinumerous to $\N$. 
> A set is called countable if it is either finite or denumerable. 
> A set that is not countable is called uncountable. ^79eb6c

> [!theorem]
> Any denumerable set is infinite. ^39892f

*Proof*  Assume a nonempty denumerable set $A$ is finite. Then for some $n\in \N$ we have $A\sim\{1,\dots,n\}$. By definition of denumerability, we have $\N\sim A$. By transitivity, $\N\sim\{1,\dots,n\}$, yielding a contradiction. $\square$ 

> [!proposition]
> The difference between any infinite set and finite set is still infinite.

*Proof*  Suppose set $A$ is infinite and set $B$ is finite. Assume $A\setminus B$ is finite, and $A\setminus B \sim \{1,\dots,k\}$.

> [!theorem]
> Any infinite set contains a denumerable subset. ^5d2bac

*Proof*  Suppose $A$ is a infinite set. Then $A\neq \emptyset$, and pick $a_{1}\in A$. Since $A$ is infinite, $A\setminus\{a_{1}\}\neq\emptyset$. Thus we can pick $a_{2} ∈ A\setminus\{a_1\}$. We have $a_{2} ∈A$ and $a_{2} \neq a_{1}$. We can repeat this procedure. If the procedure ended up in finite many steps, we would get a set $\{a_{1},\dots ,a_{n}\}$ for some $n ∈ \N$ such that $A\setminus \{a_{1},\dots ,a_{n}\} = \emptyset$ which means $A = \{a_1 , \dots , a_{n} \}$, contradicting the assumption that $A$ is infinite. Therefore, the above procedure does not end up in finite many steps. It then produces an infinite sequence $\{a_1,a_2,\dots\}$ contained in $A$ with distinct elements. $\square$

> [!proposition]
> The set $\R$ of real numbers is uncountable. ^818a9f

*Proof*  Assume exists $f\colon \N\to\R$ be some bijection. Then the range of $f$ is $\{f(k)\mid k\in\N\}$, which is  

