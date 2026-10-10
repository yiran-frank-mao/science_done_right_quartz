The $T_{n}$​ hierarchy is a way of classifying separation axioms in topology. They describe how well points and sets can be distinguished by open sets.

## Kolmogorov Space $(T_{0})$

> [!definition] Kolmogorov Space
> A [[Topological Spaces#^concept-39ce12df888c|topological space]] is called a *Kolmogorov space* or *$T_{0}$-space* if for any two distinct points in the space, there exists an open set that contains one of the points but not the other.

## Fréchet Space $(T_{1})$

> [!definition] $T_{1}$ Space
> A [[Topological Spaces#^concept-39ce12df888c|topological space]] is called *Fréchet* or *$T_{1}$-space* if for any two distinct points $x$, $y$ in the space, there exists open sets $U$, $V$ respectively such that $$x\in U, x\notin V, y\in V, y\notin U.$$

> [!theorem]
> The followings are equivalent:
> - A [[Mathematics/Topology/General Topology/Topological Spaces#^concept-39ce12df888c|topological space]] $X$ is $T_{1}$;
> - Every singleton set $\{x\}$ is closed for all $x\in X$;
> - For $A\subset X$, the intersection of all open sets containing $A$, is $A$.
> $\quad$

*Proof*  If $X$ is $T_{1}$, for any singleton set $\{x\}$, there are no [[Closure, Interior and Boundary#^11cf9f|limit points]], so the closure of $\{x\}$ is $\{x\}$, which is closed; Now assume every singleton set is closed, then for any point $y$ in the intersection of all open sets containing $A$, if $y\notin A$, since $\{y\}$ is closed, $X\setminus\{y\}$ is an open set containing $A$, but $y\notin X\setminus\{y\}$ which is a contradiction; Lastly, suppose the intersection of all open sets containing $A$ is $A$, and $x$, $y$ are two distinct points, then $X\setminus\{y\}$ and $X\setminus\{x\}$ serve as open sets containing $x$ and $y$ respectively, but not the other. $\square$

## Hausdorff Space $(T_{2})$

>[!definition] Hausdorff Space
> A topological space $X$ is called *Hausdorff* or $T_{2}$ if for any $x , y ∈ X$ with $x \neq y$ there exist [[Closure, Interior and Boundary#^eda962|open neighborhoods]] $U$ of $x$ and $V$ of $y$ such that $U ∩V = \emptyset$. ^f7bcc8

<u><b>e.g.</b></u>  It is clear that all metric spaces are Hausdorff. In fact, most of the spaces we will encounter is Hausdorff.

> [!proposition]
> Let $X$ be a Hausdorff space and $A\subset X$. A point $x∈X$ is a limit point of $A$ if and only if any neighborhood $U$ of $x$ contains infinitely many points of $A$.

>[!proposition] 
> In Hausdorff spaces, [[Closure, Interior and Boundary#^72dffe|limits]] of sequences are unique if they exist.

*Proof*  Assume a sequence $(x_{n})$ in a Hausdorff space has two distinct limits $x$ and $y$. Then there exist neighborhoods $U$ of $x$ and $V$ of $y$ such that $U ∩V = \emptyset$. However, since $x_{n} → x$ and $x_{n} → y$ , there exists an integer $N$ such that $x_{n} ∈ U$ and $x_{n} ∈V$ for $n≥N$. Thus $U∩V \neq \emptyset$, which is a contradiction. $\square$

> [!lemma] Super Hausdorff Lemma
> A [[Mathematics/Topology/General Topology/Topological Spaces#^concept-39ce12df888c|topological space]] $X$ is [[Mathematics/Topology/General Topology/Separation and Hausdorff Spaces#^f7bcc8|Hausdorff]] if and only if for any disjoint [[Mathematics/Topology/General Topology/Compactness of Topological Space#^da2511|compact]] sets $K_{1},K_{2}\subset X$, there are disjoint open sets $U_{1},U_{2}\subset X$ such that $K_{1}\subset U_{1}$ and $K_{2}\subset U_{2}$.
> 

*Proof*  $(\Leftarrow)$ direction is immediate because any singleton is compact. Conversely, suppose $X$ is Hausdorff, we first show that any compact set $K$ and singleton set $\{x\}$ can be separated by disjoint open neighborhoods. For any $y\in K$, we can pick an open neighbourhood $V_{y}$ of $y$ and an open neighborhood $U_{x}$ of $x$ such that $V_{y} \cap U_{y}=\emptyset$. Then $\{Y_{y}\}_{y\in K}$ forms an open cover of $K$, so it has a finite subcover $\{V_{y_{i}}\}_{i=1}^{n}$. Let $U:=\cap_{i=1}^{n} U_{y_{i}}$, then $U$ and $\cup_{i=1}^{n}V_{y_{i}}$ are disjoint open neighborhoods of $x$ and $K$. 
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/super_Hausdorff_lemma.svg" style="width:43%;"/>
Now for any two disjoint compact sets $K_{1}$ and $K_{2}$, for any $x\in K_{1}$, we can find open neighborhoods $U_{x}$ of $x$ and $V_{x}$ of $K_{2}$ such that $U_{x}\cap V_{x}=\emptyset$. Then similar to the previous case, $\{U_{x}\}_{x\in K_{1}}$ forms an open cover of $K_{1}$, so it has a finite subcover $\{U_{x_{i}}\}_{i=1}^{n}$. Let $U:=\cup_{i=1}^{n} U_{x_{i}}$, then $U$ and $\cap_{i=1}^{n}V_{x_{i}}$ are disjoint open neighborhoods of $K_{1}$ and $K_{2}$. $\square$

>[!proposition] 
> Every finite set in a [[Mathematics/Topology/General Topology/Separation and Hausdorff Spaces#^f7bcc8|Hausdorff space]] $X$ is [[Topological Spaces#^0849a0|closed]]. More generally, any [[Mathematics/Topology/General Topology/Compactness of Topological Space#^da2511|compact]] set in a Hausdorff space is closed.

*Proof*  It suffices to show for any $x\in X$ the set $\{x\}$ is closed. For any $z\in X\setminus \{x\}$, by the Hausdorff property we can find an open set $U_{z}$ containing $z$ but $x \notin U_{z}$. Thus $X \setminus\{x\} = \bigcup_{z∈X\setminus\{x\}} U_{z}$ and hence it is open. Consequently $\{x\}$ is closed. To show this is true for a compact set $K$, note that super Hausdorff lemma shows every $x\in K^{c}$ has an open neighborhood that is disjoint from $K$, so $K^{c}$ is open. $\square$

> [!corollary]
> Any [[Mathematics/Topology/General Topology/Compactness of Topological Space#^da2511|compact]] set $K$ in a [[Metric Spaces#^concept-e26011bc6f0a|metric space]] $X$ is closed and bounded.

*Proof*  Any metric space is Hausdorff, so $K$ is closed. Without loss of generality, we can assume that $K$ is nonempty, so we can fix some $x\in K$. Note that the open balls $\{B_{r}(x)\}_{r\in \mathbb{N}}$ forms an open cover of $X$ (thus an open cover of $K$), so it has a finite subcover $\{B_{r_{i}}(x)\}_{i=1}^{n}$. Let $R=\max\{r_{i}\mid i=1,\dots,n\}$, then $K\subset B_{R}(x)$, so $K$ is bounded. $\square$ 

>[!proposition] 
> Let $(X,\mathcal{T})$ be a Hausdorff space. If $\mathcal{T}^{\prime}$ is a [[Topological Spaces#^149286|finer]] topology on $X$, then $(X,\mathcal{T}^{\prime})$ is also a Hausdorff space.

*Proof*  Let $x,y\in X$ with $x\neq y$. Since $\mathcal{T}\subset \mathcal{T}^{\prime}$, the open sets in $\mathcal{T}$ are also open in $\mathcal{T}^{\prime}$. Thus there exist open sets $U,V\in \mathcal{T}\subset\mathcal{T}^{\prime}$ such that $x\in U$, $y\in V$ and $U\cap V=\emptyset$, that is $X$ is a Hausdorff space under $\mathcal{T}^{\prime}$. $\square$


> [!theorem]
> A [[Topological Spaces#^concept-39ce12df888c|topological space]] $X$ is Hausdorff if and only if the diagonal $\Delta = \{(x,x) \mid x \in X\}$ is closed in the [[Constructions on Topological Spaces#^fbf303|product space]] $X \times X$.
> 

*Proof*  Suppose $X$ is Hausdorff, then for every distinct $x,y\in X$, there are disjoint open neighborhoods $U$, $V$ of $x$ and $y$ respectively. Then $U\times V\subset \Delta^{c}$ is an open neighborhood of $(x,y)$, hence $X\setminus\Delta$ is open and $\Delta$ is closed. The converse is exactly the same argument in reverse. $\square$