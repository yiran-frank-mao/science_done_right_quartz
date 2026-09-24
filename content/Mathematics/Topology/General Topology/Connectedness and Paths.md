---
created: 2024-05-25
updated: 2024-09-26
---
>[!definition] Connectedness
>A [[Topological Spaces#^concept-39ce12df888c|topological space]] $X$ is called *connected* if there do not exist two disjoint nonempty open sets $U$ and $V$ such that $X = U \sqcup V$.  ^946cc4

<u><b>e.g.</b></u>  
- The set $\newcommand{\Q}{\mathbb{Q}}\newcommand{\R}{\mathbb{R}}\Q$ of [[Number Systems#^e8a24a|rational numbers]] in the standard Euclidean topology is not connected because $\Q = U \sqcup V$ with $U=\mathbb{Q}\cap(-\infty,\pi)$ and $V=\mathbb{Q}\cap(\pi,\infty)$. Note that this also means that a subspace of a connected space need not be connected.
- Let $\R$ be endowed with the standard Euclidean topology. A set $I ⊂ \R$ is connected if and only if $I$ is an [[Number Systems#^fd03c6|interval]].
$\quad$

>[!theorem] 
> Let $X$ and $Y$ be [[Topological Spaces#^concept-39ce12df888c|topological spaces]]. If $f \colon X → Y$ is continuous and $X$ is connected, then $f (X )$ is connected, i.e. the continuous image of a connected set is connected. ^affaf2

*Proof*  We prove the contrapositive. Suppose $f (X )$ is not connected, then there exist disjoint nonempty open sets $U$ and $V$ in $Y$ such that $f (X ) = U \sqcup V$. Then $f^{-1}(U)$ and $f^{-1}(V)$ are disjoint nonempty open sets in $X$ with $$X=f^{-1}(f(X))=f^{-1}(U\cup V)=f^{-1}(U)\cup f^{-1}(V)$$which shows that $X$ is not connected. $\square$

> [!corollary]
> Every continuous map $f \colon X \to Y$ from a connected topological space $X$ to a discrete topological space $Y$ is constant.

*Proof*  This is because the only connected subsets of a discrete space are the singletons. $\square$

> [!corollary] Intermediate Value Theorem
> Let $X$ be a connected topological space and $f \colon X → \R$ a continuous function, where $\R$ is endowed with the standard topology. If $f$ takes the values $a$ and $b$, then $f$ takes all the values between $a$ and $b$.

*Proof*  By the given conditions, $f (X )$ is connected and hence it is an interval. Since $a,b∈f(X)$, any value between $a$ and $b$ must be in $f(X)$. $\square$

> [!remark]-
> This is a generalization of the [[Real Continuous Functions#^f2dbe6|classical intermediate value theorem in real analysis]].
> 

>[!lemma]
> If $A\subset X$ is connected and $A\subset B\subset \overline{A}$, then $B$ is connected. In particular, the closure of a connected set is connected.

*Proof*  Since $A\subset B\subset \overline{A}$, we can write $B=A\cup C$ for for some $C\subset A'$ where $A'$ is the set of limit points of $A$. Without loss of generality, we assume that $A\neq B$, so $C\neq \emptyset$. Suppose $B=U\sqcup V$ for nonempty open sets $U,V\subset X$. Since $A$ is connected, either $A\subset U$ or $A\subset V$. Without loss of generality, assume $A\subset U$. Then $C\cap V$ is nonemty. Pick some $y\in C\cap V$, then $V$ is an open neighborhood of $y$, so it must intersect $A$, yielding a contradiction. Therefore, $B$ is connected. $\square$

> [!proposition]
> The only subset of a connected topological space which is both open and closed is the empty set and itself. ^7a08b9
>

*Proof*  Suppose $A\subset X$ is both open and closed. Then $A$ and $A^{c}$ are disjoint open sets with $X=A\sqcup A^{c}$, which implies that either $A$ or $A^{c}$ is empty. $\square$

## Path Connectedness

> [!definition] Path
> Let $X$ be a [[Topological Spaces#^concept-39ce12df888c|topological space]]. A *path* in $X$ joining two points $x,y ∈ X$ is a continuous function $f \colon [0,1]→X$ such that $f(0)=x$ and $f(1)=y$.
> If the start point and end point coincide, we call it a *loop*. ^1c51ed

> [!definition] Path Connectedness
> A topological space $X$ is called *path connected* if for every pair of points $x,y ∈ X$ can be joined by a path in $X$. ^630354

<u><b>e.g.</b></u>  Any convex set in a [[Topological Vector Spaces#^dd5802|topological vector space]] over $\R$ or $\C$ is path connected; $\R^{n}\setminus\{0\}$ is path connected for $n\geq 2$; The topologist's sine curve $\{(0,y)\mid y\in[-1,1]\}\cup\{(x, \sin(1/x))\mid x\in(0,\infty)\}\subset \R^{2}$ is connected but not path connected:
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/topologists_sine_curve.svg" style="width:50%;"/>

>[!theorem] 
> A path connected topological space is connected. In general, connected space is not necessarily path-connected.

*Proof*  If $X$ is not connected, then there exist disjoint nonempty open sets $U$,$V$ in $X$ with $X =U∪V$. Let $x ∈U$ and $y ∈V$. Since $X$ is path-connected, there is a path $f \colon [0,1]→X$ joining $x$ to $y$. By the continuity of $f$, $f^{−1}(U)$ and $f^{−1}(V)$ are disjoint nonempty open sets in $[0,1]$ with $$[0,1]=f^{-1}(X)=f^{-1}(U\cup V)=f^{-1}(U)\cup f^{-1}(V).$$Therefore $[0,1]$ is not connected, which is a contradiction. $\square$

<u><b>e.g.</b></u>  $\R^{n}\setminus\{0\}$ is path connected for $n\geq 2$; Any convex set in $\R^{n}$ is path connected; The topologist's sine curve is connected but not path connected.

> [!proposition]
> If $U$ is an open set in $\R^{n}$, then $U$ is [[Connectedness and Paths#^946cc4|connected]] if and only if $U$ is [[Connectedness and Paths#^630354|path connected]].

*Proof*  It suffices to show that if $U$ is nonempty connected, then it is path connected. Fix some $x\in U$, we define $V:=\{y\in U: \text{there is a path joining }x \text{ and } y\}$. Clearly $V\neq \emptyset$ because $x\in V$. By the [[Connectedness and Paths#^7a08b9|proposition]], it is enough to show that $V$ is both open and closed in $U$, which implies that $V=U$, hence $U$ is path connected. For any $y\in V$, since $U$ is open, there is a open ball $B_{r}(y)$ contained in $U$. Let $\gamma\colon [0,1]\to U$ be the path from $x$ to $y$. Note that for all $z\in B_{r}(y)$, we can define a path $\gamma_{z}\colon [0,1]\to U$ from $x$ to $z$ by $$\gamma_{z}(t)=\begin{cases} \gamma(2t),\quad& t\in[0,1/2],\\ (2t-1)z+(2-2t)y,\quad& t\in[1/2,1], \end{cases}$$connecting $x$ and $z$, so $z\in V$, which shows that $V$ is open in $U$.
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/connectedness_in_R%5En.svg" alt="connectedness_in_R^n" style="width:35%;"/>
Now we show that $V$ is closed in $U$. Let $\{y_{n}\}\subset V$ be a sequence converging to $y\in U$. As $U$ is open, there is some open ball $B_{\varepsilon}(y)\subset U$, and $y_{n}\in B_{\varepsilon}(y)$ for all sufficiently large $n$. Similarly by concatenation of paths, we can define a path joining $x$ to $y_{n}$ and then to $y$, hence $y\in V$. This shows that $V$ is closed in $U$. Therefore, $U$ is path connected. $\square$

> [!proposition]
> 1. Every quotient of a (path) connected space is (path) connected;
> 2. The union of a family of (path) connected subspaces of $X$ that have a point in common is (path) connected;
> 3. Any product of (path) connected spaces is (path) connected.
> 

*Proof*  (1) is immediate from [[Connectedness and Paths#^affaf2|the theorem]]; For (2), path connectedness is clear, and we will only prove that it is connected here. Suppose $\{A_{i}\}_{i\in I}$ is a family of connected subspaces of $X$ with a point $a\in \cap_{i\in I} A_{i}$. Suppose $U\sqcup V$ separates $\cup_{i\in I}A_{i}$, without loss of generality, we assume that $a\in U$, then $A_{i}\subset U$ for all $i\in I$, which implies that $\cup_{i\in I}A_{i}\subset U$, and $V=\emptyset$. 

## Components

> [!definition] Components
> A *(path) component* of a topological space $X$ is a maximal (path) connected subspace of $X$.
> 

> [!proposition]
> The following holds for a topological space $X$:
> 1. The (path) components form a partition of $X$;
> 2. Any (path) connected subset is contained in a unique (path) component;
> 3. Each path component is contained in a single component and each component is a disjoint union of path components.
> $\quad$

*Proof*

## Locally (Path) Connectedness

> [!definition] Locally Path Connected
> A topological space $Y$ is *locally path-connected* if for any point $y \in Y$ and any open neighborhood $U$ of $y$, there exists a path-connected open neighborhood $V \subseteq U$ containing $y$. ^ba4f32

<u><b>e.g.</b></u> Consider $I\times \Q\subset \R^{2}$. Clearly it is [[Connectedness and Paths#^946cc4|connected]] but not locally path-connected because for any point $(x,q)\in I\times \Q$, any open neighborhood $U$ of $(x,q)$ contains points of the form $(x,r)$ for $r\in I\setminus \Q$, which cannot be connected by a path in $I\times \Q$.

> [!proposition]
> If a topological space is both connected and locally path-connected, then it must be path-connected.
