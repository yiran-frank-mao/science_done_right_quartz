---
created: 2024-05-25
updated: 2024-09-26
---
>[!definition] Connectedness
>A [[Topological Spaces#^65c94a|topological space]] $X$ is called *connected* if there do not exist two disjoint nonempty open sets $U$ and $V$ such that $X = U ∪V$.  ^946cc4

<u><b>e.g.</b></u>  The set $\newcommand{\Q}{\mathbb{Q}}\newcommand{\R}{\mathbb{R}}\Q$ of [[Number Systems#^e8a24a|rational numbers]] in the standard Euclidean topology is not connected because $\Q = U ∪V$ with $$U=\mathbb{Q}\cap(-\infty,\pi)\quad\text{ and }\quad V=\mathbb{Q}\cap(\pi,\infty)$$

>[!proposition] 
> Let $\R$ be endowed with the standard Euclidean topology. A set $I ⊂ \R$ is connected if and only if $I$ is an [[Number Systems#^fd03c6|interval]].

>[!theorem] 
> Let $X$ and $Y$ be [[Topological Spaces#^65c94a|topological spaces]]. If $f \colon X → Y$ is continuous and $X$ is connected, then $f (X )$ is connected, i.e. the continuous image of a connected set is connected.

> [!corollary] 
> Let $X$ be a connected topological space and $f \colon X → \R$ a continuous function, where $\R$ is endowed with the standard topology. If $f$ takes the values $a$ and $b$, then $f$ takes all the values between $a$ and $b$.

*Proof*  By the given conditions, $f (X )$ is connected and hence it is an interval. Since $a,b∈f(X)$, any value between $a$ and $b$ must be in $f(X)$.

> [!proposition]
> The only subset of a connected topological space which is both open and closed is the empty set and itself. ^7a08b9
>

*Proof*  

## Path Connectedness

> [!definition] Path
> Let $X$ be a [[Topological Spaces#^65c94a|topological space]]. A *path* in $X$ joining two points $x,y ∈ X$ is a continuous function $f \colon [0,1]→X$ such that $f(0)=x$ and $f(1)=y$.
> If the start point and end point coincide, we call it a *loop*. ^1c51ed

> [!definition] Path Connectedness
> A topological space $X$ is called path connected if for every pair of points $x,y ∈ X$ can be joined by a path in $X$. ^630354

>[!theorem] 
> A path connected topological space is connected. In general, connected space is not necessarily path-connected.

*Proof*  If $X$ is not connected, then there exist disjoint nonempty open sets $U$,$V$ in $X$ with $X =U∪V$. Let $x ∈U$ and $y ∈V$. Since $X$ is path-connected, there is a path $f \colon [0,1]→X$ joining $x$ to $y$. By the continuity of $f$, $f^{−1}(U)$ and $f^{−1}(V)$ are disjoint nonempty open sets in $[0,1]$ with $$[0,1]=f^{-1}(X)=f^{-1}(U\cup V)=f^{-1}(U)\cup f^{-1}(V)$$Therefore $[0,1]$ is not connected, which is a contradiction. $\square$

> [!proposition]
> If $U$ is an open set in $\R^{n}$, then $U$ is connected if and only if $U$ is path connected.

*Proof*  It suffices to show that if $U$ is nonempty connected, then it is path connected. Fix some $x\in U$, we define $V:=\{y\in U: \text{there is a path joining }x \text{ and } y\}$. Clearly $V\neq \emptyset$ because $x\in V$. By the [[Connectedness and Paths#^7a08b9|proposition]], it is enough to show that $V$ is both open and closed in $U$, which implies that $V=U$, hence $U$ is path connected. For any $y\in V$, since $U$ is open, there is a open ball $B_{r}(y)$ contained in $U$. Let $\gamma\colon [0,1]\to U$ be the path from $x$ to $y$. Note that for all $z\in B_{r}(y)$, we can define a path $\gamma_{z}\colon [0,1]\to U$ from $x$ to $z$ by $$\gamma_{z}(t)=\begin{cases} \gamma(2t),\quad& t\in[0,1/2],\\ (2t-1)z+(2-2t)y,\quad& t\in[1/2,1], \end{cases}$$connecting $x$ and $z$, so $z\in V$, which shows that $V$ is open in $U$.
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/connectedness_in_R%5En.svg" alt="connectedness_in_R^n" style="width:35%;"/>
Now we show that $V$ is closed in $U$. Let $\{y_{n}\}\subset V$ be a sequence converging to $y\in U$. As $U$ is open, there is some open ball $B_{\varepsilon}(y)\subset U$, and $y_{n}\in B_{\varepsilon}(y)$ for all sufficiently large $n$. Similarly by concatenation of paths, we can define a path joining $x$ to $y_{n}$ and then to $y$, hence $y\in V$. This shows that $V$ is closed in $U$. Therefore, $U$ is path connected. $\square$

> [!definition] Locally Path Connected
> A topological space $Y$ is *locally path-connected* if for any point $y \in Y$ and any open neighborhood $U$ of $y$, there exists a path-connected open neighborhood $V \subseteq U$ containing $y$. ^ba4f32

<u><b>e.g.</b></u> Consider $I\times \Q\subset \R^{2}$. Clearly it is [[Connectedness and Paths#^946cc4|connected]] but not locally path-connected because for any point $(x,q)\in I\times \Q$, any open neighborhood $U$ of $(x,q)$ contains points of the form $(x,r)$ for $r\in I\setminus \Q$, which cannot be connected by a path in $I\times \Q$.

> [!proposition]
> If a topological space is both connected and locally path-connected, then it must be path-connected.
