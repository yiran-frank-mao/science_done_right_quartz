---
created: 2024-01-06
updated: 2025-05-19
---
>[!definition] Cover and Subcover
>A *cover* of a set $A$ is collection $\mathcal{U}$ of sets whose union contains $A$: $$A\subset\bigcup_{U\in\mathcal{U}}U$$ A *subcover* of a cover $\mathcal{U}$ is a subset of $\mathcal{U}$ whose elements still cover $A$. A cover is *open* if all its elements are open. ^eb1952

<b><u>e.g.</u></b> $\{(n, n + 3) \mid n \in \Z\}$ is an open cover of $\R$; $\{(2k, 2k + 3) \mid k \in \Z\}$ is a subcover.

>[!definition] Compactness
>A topological space $T$ is *compact* if every open cover of $T$ has a finite subcover. A subset $S$ of $T$ is compact if every open cover of $S$ by subsets of $T$ has a finite subcover. This is the same as $S$ being compact with the subspace topology. ^da2511

<b><u>e.g.</u></b> 
- $(0, 1)$ is not compact, $\{(0, a) \mid a ∈ (0, 1)\}$ is an open cover with no finite subcover; 
- $\R$ is not compact, $\{(−\infty, a) : a ∈ \Z\}$ has no finite subcover;
- $[0,1]^\mathbb{N}$ with the box topology is not compact. In fact, any discrete infinite space is not compact, since the cover of singletons has no finite subcover.
$\quad$

> [!lemma]
> If $T$ is a topological space and $S \subset T$ then $S$ is compact in the $T$ if and only if $S$ is compact in the [[Mathematics/Topology/General Topology/Constructions on Topological Spaces#^a942da|subspace topology]] on $S$.

> [!theorem] Continuous Image of a Compact Set is Compact
> Let $X$ and $Y$ be topological spaces. If $K\subseteq X$ is compact and $f \colon X → Y$ is [[Continuous Maps on Topological Spaces#^33ee5a|continuous]], then $f (K )$ is compact. ^1075ec

> [!corollary] Extreme Value Theorem
> Let $X$ be a compact topological space and $f \colon X \to \R$ continuous, where $\R$ is endowed with the standard topology. Then $f$ achieves its maximum and minimum value on $X$.
> 

> [!theorem] Heine–Borel Theorem
> Any closed interval $[a,b]$ is a compact subset of $\R$. More generally, a subset of  $\R^{n}$ is compact if and only if, it is bounded and closed. ^6e5465

*Proof*  

>[!theorem] 
> Let $X$ be a compact topological space and $K$ a closed [[Mathematics/Topology/General Topology/Constructions on Topological Spaces#^a942da|subspace]] of $X$. Then $K$ is compact. ^f5bb06

*Proof*  Let $K ⊂X$ be closed and let $\{U_{α}\}_{α∈\Lambda}$ be an open covering of $K$. Then $\{K^{c}\cup U_{α}\}_{α∈\Lambda}$ is an open covering of $X$. Since $X$ is compact, there exist $α_{1},\dots,α_{n} ∈ \Lambda$ such that $$X=K^{c}\bigcup\left(\bigcup_{i=1}^{n}U_{\alpha_i}\right)$$It follows that $K \subset \bigcup_{i=1}^{n}U_{\alpha_{i}}$, therefore $K$ is compact. $\square$

> [!corollary]
> Any intersection of a compact set with a closed set is compact.
> 

*Proof*  Suppose $C$ is closed and $K$ is compact. Then $C\cap K$ is closed in $K$ (w.r.t [[Mathematics/Topology/General Topology/Constructions on Topological Spaces#^a942da|subspace topology]]), and hence compact by the previous theorem and lemma. $\square$

> [!lemma] Tube Lemma
> Let $X$ be any [[Mathematics/Topology/General Topology/Topological Spaces#^concept-39ce12df888c|topological space]] and $Y$ be a [[Mathematics/Topology/General Topology/Compactness of Topological Space#^da2511|compact space]]. If $x\in X$ and $U \subset X \times Y$ is an open set containing $\{x\}\times Y$, then there is an open neighborhood $V ⊂X$ of $x$ so that $V \times Y \subset U$.
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/tube_lemma.svg" style="width:45%;"/>

*Proof*  $U$ is an open neighborhood of any $(x,y)\in \{x\}\times Y$, so $U$ contains some $V_{(x,y)}\times W_{(x,y)}$ with $V_{(x,y)}$ an open neighborhood of $x$ in $X$ and $W_{(x,y)}$ an open neighborhood of $y$ in $Y$. Then $\{W_{(x,y)}\}_{y\in Y}$ forms an open cover of $Y$, since $Y$ is compact, we can take a finite subcover $\{W_{y_{1}},\dots,W_{y_{n}}\}$ of $Y$. Then $V=\bigcap_{i=1}^{n}V_{(x,y_{i})}$ is an open neighborhood of $x$ in $X$ and $$V\times Y=V\times\left(\bigcup_{i=1}^{n}W_{y_{i}}\right)=\bigcup_{i=1}^{n}\left(V\times W_{y_{i}}\right)\subset U.$$ $\square$

> [!corollary]
> Any finite disjoint union, quotient, or finite product of [[Mathematics/Topology/General Topology/Compactness of Topological Space#^da2511|compact spaces]] is compact.

*Proof*  Finite disjoint unions of compact spaces are compact since any open cover of the union is an open cover of each component; The quotient of a compact space is compact since [[Compactness of Topological Space#^1075ec|the continuous image of any compact space is compact]]; To show finite product of compact spaces is compact, it suffices to only consider the product of two compact spaces, say $X\times Y$. Suppose $\{U_{i}\}_{i\in I}$ is an open cover of $X\times Y$, then for any $x\in X$, there is a subcover $\{U_{i}\}_{i\in I_{x}}$ that covers $\{x\}\times Y$, which is compact. So we can pick a finite subcover, $\{U_{i}\}_{i\in J_{x}}$ where $J_{x}\subset I_{x}$ is a finite index set. By the tube lemma, we can enlarge $\{x\}\times Y$ to a tube $V_{x}\times Y$ that is also covered by $\{U_{i}\}_{i\in J_{x}}$. Now $\{V_{x}\}_{x\in X}$ is an open cover of $X$, so we can pick a finite subcover $\{V_{x_{i}}\}_{i=1}^{n}$, then $\{U_{i}\mid i\in \cup_{k=1}^{n} J_{x_{k}}\}$ is a finite subcover of $X\times Y$. $\square$

## Tychonoff's Theorem

We have just showed that any finite product of compact spaces is compact. However, this is true even for infinite products if we assume the axiom of choice. This is known as *Tychonoff's theorem*.

> [!theorem] Tychonoff's Theorem
> The product of any collection of compact topological spaces is compact with respect to the product topology.

To prove this theorem, we need an alternative characterization of compactness in terms of closed sets:

> [!definition] Finite Intersection Property
> A collection of subsets of a set $X$ is said to have the *finite intersection property (FIP)* if the intersection of any finite subcollection is nonempty.
> 

> [!proposition]
> A [[Mathematics/Topology/General Topology/Topological Spaces#^concept-39ce12df888c|topological space]] $X$ is [[Mathematics/Topology/General Topology/Compactness of Topological Space#^da2511|compact]] if and only if every collection of closed subsets of $X$ with the finite intersection property has a nonempty intersection.

*Proof*  We prove that $X$ is compact iff any collection of closed sets with empty intersection has a finite subcollection with empty intersection. Note that if $\{U_{i}\}_{i\in I}$ is an open cover of $X$, then it has a finite subcover if and only if $\{U_{i}^{c}\}_{i\in I}$ has a finite subcollection with empty intersection. This finishes the proof. $\square$

## Lindelöf Spaces

There is a slightly weaker notion of compactness called Lindelöf spaces, which is defined as follows:

> [!definition] Lindelöf Space
> A topological space $X$ is called a *Lindelöf space* if every open cover of $X$ has a countable subcover. ^concept-871f5f6137af

> [!proposition]
> A [[Mathematics/Topology/General Topology/Countability Axioms and Nets#^concept-5144b7350d14|second-countable]] space is [[Mathematics/Topology/General Topology/Compactness of Topological Space#^concept-871f5f6137af|Lindelöf]].
> 

*Proof*  Let $\mathcal{B}$ be a countable basis for the topology of $X$. Let $\mathcal{U}=\{U_{\alpha}\}_{\alpha\in \Lambda}$ be an open cover of $X$. For each $x \in X$, there exists $U_x \in \mathcal{U}$ such that $x \in U_x$. Since $\mathcal{B}$ is a basis, there exists $B_x \in \mathcal{B}$ such that $x \in B_x \subseteq U_x$. The collection $\{B_{x} : x \in X\}$ is an open cover of $X$ consisting of elements from the countable basis $\mathcal{B}$. Since $\mathcal{B}$ is countable, $\{B_{x} : x \in X\}$ is countable. Now, for each $B_x$, we can choose the corresponding $U_x \in \mathcal{U}$ such that $B_x \subseteq U_x$. The collection $\{U_x : x \in X\}$ is a countable subcollection of $\mathcal{U}$ that covers $X$. Therefore, $X$ is Lindelöf. $\square$ ^40d004

> [!remark]
> The proof above utilized countable axiom of choice.

## Sequential and Limit Point Compactness

> [!definition] Limit Point Compactness
> A topological space $X$ is called *limit point compact* if every infinite subset of $X$ has a limit point in $X$. ^concept-c564d7124948

> [!lemma]
> Every [[Compactness of Topological Space#^da2511|compact]] space is limit point compact.

*Proof*  Suppose $X$ is compact, and $A\subset X$ is infinite, and has no limit points. Then for each $x\in A$, there exists an open neighborhood $U_x$ of $x$ such that $U_{x}\cap A=\{x\}$, and for each $x\in X\setminus A$, there exists an open neighborhood $U_x$ of $x$ such that $U_{x}\cap A=\emptyset$. Then $\{U_{x}\}_{x\in X}$ is an open cover of $X$, but it does not have a finite subcover because every $U_{x}$ for $x\in A$ is needed to cover $A$. This contradicts the compactness of $X$. $\square$

>[!definition] Sequential Compactness
>Let $X$ be a topological space and $A\subset X$. We say that $A$ is *sequentially compact* if every sequence in $A$ has a subsequence converges to a point in $A$.

> [!lemma]
> Suppose $X$ is limit point compact, first-countable and [[Mathematics/Topology/General Topology/Separation and Hausdorff Spaces#^f7bcc8|Hausdorff]], then $X$ is sequentially compact.
> 

*Proof*  

> [!lemma]
> If $X$ is sequentially compact, and second-countable, then $X$ is compact.
> 

*Proof*  Since $X$ is second-countable, it is Lindelöf, so it suffices to show that any countable open cover $\{U_{i}\}_{i\in\mathbb{N}}$ of $X$ admits a finite cover. For the sake of contradiction, suppose $X$ is not compact, then any finite subcollection does not cover the whole space, so we can pick $x_{i}\in X\setminus \bigcup_{j=1}^{i}U_{j}$ for each $i$, and $(x_{i})_{i=1}^{\infty}$ is a sequence in $X$, which has convergent subsequence, say, $x_{k_{i}} \to x$ as $i\to \infty$. Suppose $x\in U_{m}$ for some $m\in \mathbb{N}$, then there exists an integer $N$ such that $x_{k_{i}}\in U_{m}$ for all $i\geq N$. However, for sufficiently large $i$ such that $k_{i}>m$, we have $x_{k_{i}}\in X\setminus U_{m}$, which is a contradiction. $\square$

> [!theorem]
> Compactness, limit point compactness, and sequential compactness are equivalent for metric spaces and second-countable Hausdorff spaces.
> 


## References and Other Resources
- [Morphocular, The Concept So Much of Modern Math is Built On](https://www.youtube.com/watch?v=td7Nz9ATyWY)