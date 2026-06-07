---
completed: true
tags:
  - fundamental-group
  - algebraic-topology
---
## Group Structure on Loops

> [!definition] Fundamental Group
> The *fundamental group* $\newcommand{\Z}{\mathbb{Z}}\pi_{1}(X,x_{0})$ of a [[Topological Spaces#^65c94a|topological space]] $X$ at a base point $x_{0}$ is the group of [[Homotopy Types#^76ea93|(path) homotopy]] [[Relations and Functions#^973688|classes]] of [[Connectedness and Paths#^1c51ed|loops]] based at $x_{0}$, with the multiplication of concatenation of loops, inverse being the reversed loop, and identity being the constant loop at $x_{0}$. ^74adbc

> [!lemma]
> In [$\newcommand{\R}{\mathbb{R}}\R$](Number%20Systems#^5fea5c), any two paths are homotopic if and only if they have the same endpoints.

*Proof*  For any two paths $f$ and $g$ with same endpoints, $H(t,s)=t \cdot f(s)+(1-t)\cdot g(s)$ gives a valid homotopy.  $\square$

> [!proposition]
> $\pi_{1}(S^{1},1)\cong \Z$.
> 

*Proof*  The ideal is that $S^{1}$ looks locally like $\R$. Define $p\colon \R\to S^{1}$, $x\mapsto e^{2\pi i x}$, paths $w_{n}\colon I\to S^{1}$, $s\mapsto e^{2\pi i n s}$, and $\tilde{w}_{n}\colon I\to\R$, $s\mapsto ns$. Note that $p\circ \tilde{w}_{n}=w_{n}$. We claim that $\Phi\colon \Z\to \pi_{1}(S^{1},1)$ sending integer $n$ to the homotopy class of $w_{n}$ forms the desired isomorphism. First show that it is a group homomorphism, i.e. $w_{m+n}\simeq w_{m} \cdot w_{n}$. Define $\tau_{m}\colon \R\to \R$, $x\mapsto x+m$. Observe that $$(p\circ (\tau_{m}\circ \tilde{w}_{n}))(x)=e^{2\pi i (nx+m)}=e^{2\pi i n x}=w_{n}(x),$$so $p\circ (\tau_{m}\circ \tilde{w}_{n})=w_{n}$. Note that both $\tilde{w}_{m+n}$ and $\tilde{w}_{m}\cdot (\tau_{m}\circ \tilde{w}_{n})$ are paths in $\R$ from $0$ to $m+n$, hence there exists a homotopy $\tilde{f}_{t}$ from $\tilde{w}_{m}\cdot (\tau_{m}\circ \tilde{w}_{n})$ to $\tilde{w}_{m+n}$. Now let $f_{t}:=p\circ \tilde{f}_{t}$, then $f_{t}$ is a homotopy from $p\circ (\tilde{w}_{m}\cdot (\tau_{m}\circ \tilde{w}_{n}))=w_{m}\cdot w_{n}$ to $p\circ \tilde{w}_{m+n}=w_{m+n}$. This shows that $\Phi$ is a homomorphism.
Now we show the surjectivity. Fixing some loop $f\colon I\to S^{1}$. Define $S_{+}:=S^{1}\setminus\{1\}$ and $S_{-}:=S^{1}\setminus\{-1\}$. We can partition the preimage of $p$ as following: $$\begin{align} p^{-1}(S_{+})=\bigsqcup_{n\in\Z}\tilde{V}_{n},&\quad \tilde{V}_{n}=(n,n+1), \\ p^{-1}(S_{-})=\bigsqcup_{n\in\Z}\tilde{U}_{n},&\quad \tilde{U}_{n}=(n-1/2,n+1/2). \end{align}$$Then the restrictions of $p$, say $p|_{\tilde{U}_{n}}\colon \tilde{U}_{n} \to S_{-}$ and $p|_{\tilde{V}_{n}}\colon \tilde{V}_{n}\to S_{+}$ are homeomorphism, with inverses $\alpha_{n}\colon S_{-}\to \tilde{U}_{n}$ and $\beta_{n}\colon S_{+}\to \tilde{V}_{n}$ respectively. There is a partition of $I$, $0=s_{0}<s_{1}<\cdots<s_{k}=1$ with each $f([s_{j-1},s_{j}])$ either a subset of $S_{+}$ or a subset of $S_{-}$. Now define $\tilde{f}\colon I\to \R$ satisfying $\tilde{f}(0)=0$, and then inductively on $[s_{j-1},s_{j}]$ by $$\tilde{f}|_{[s_{j-1},s_{j}]}:=\begin{cases}\alpha_{n} \circ f|_{[s_{j-1},s_{j}]},\quad \text{if } f([s_{j-1},j])\subset S_{-}, \\ \beta_{l} \circ f|_{[s_{j-1},s_{j}]},\quad \text{if } f([s_{j-1},j])\subset S_{+},  \end{cases} $$where $n$ and $l$ are the unique integer for which $\tilde{f}(s_{j-1})\in \tilde{U}_{n}$ or $\tilde{f}(s_{j-1})\in\tilde{V}_{l}$. This gives a path $\tilde{f}\colon I\to\R$ starting at $0$ and ending at some $k\in p^{-1}(1)=\Z$. Thus $\tilde{f}\simeq \tilde{w}_{k}$, hence, $f\simeq w_{k}$ by applying $p$ to the both sides, and so $\Phi(k)=[f]$.
Finally, we show that $\Phi$ is injective. Suppose $\Phi(n)=\Phi(m)$, then $w_{n}\simeq w_{m}$, there exists a homotopy $H\colon I\times I\to S^{1}$ from $w_{n}$ to $w_{m}$. Similarly, there exists a partition of $I\times I$, $0=s_{0}<s_{1}<\cdots<s_{a}=1$ and $0=t_{0}<t_{1}<\cdots<t_{b}=1$, such that $H([s_{j-1},s_{j}]\times [t_{k-1},t_{k}])$ is either a subset of $S_{+}$ or a subset of $S_{-}$. Now define $\tilde{H}\colon I\times I\to \R$ similarly as above, which gives a homotopy from $\tilde{w}_{n}$ to $\tilde{w}_{m}$, hence $\Phi(n)=\Phi(m)$ implies $n=m$. Thus $\Phi$ is injective. $\square$ ^6ff1bb

> [!remark]+
> In fact, the distributive law holds in general: Suppose $\varphi\colon X\to Y$ is continuous, and $f,g\colon I\to X$ are paths, then $$\varphi\circ (f\cdot g)=(\varphi\circ f)\cdot(\varphi \circ g).$$

## Change of Basepoints

> [!proposition] 
> Suppose $h\colon I\to X$ is a path from $x_{0}$ to $x_{1}$, then the map $\beta_{h}\colon\pi_{1}(X,x_{1})\to\pi_{1}(X,x_{0})$ defined by $\beta_{h}([f]):=[h\cdot f\cdot h^{-1}]$ is an [[Homomorphisms, Normal Subgroup & Conjugation#^c32ca8|isomorphism]].

*Proof*  We first check that it is well-defined. Suppose $f_{0}\simeq f_{1}$ are homotopic paths of $[f]\in\pi_1(X,x_1)$ with homotopy $f_{t}$. Then $h\cdot f_{0}\cdot h^{-1}\simeq h\cdot f_{1}\cdot h^{-1}$ via $h\cdot f_{t}\cdot h^{-1}$.
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/change_of_basepoints.svg" alt="change_of_basepoints" style="width:22%;"/>
Secondly, it is a homomorphism because $$\beta_{h}([f][g])=\beta_{h}([f\cdot g])=[h\cdot f\cdot g\cdot h^{-1}]=[h\cdot f\cdot h^{-1}\cdot h\cdot g\cdot h^{-1}]=\beta_{h}([f])\beta_{h}([g]).$$Moreover, $\beta_{h^{-1}}$ is a inverse of $\beta_{h}$ (here $h^{-1}$ means the [[Homotopy Types#^2b9913|reversed path]]), thus $\beta_{h}$ is an isomorphism. $\square$

> [!remark]+
> Note that there is no ambiguity when we defined $\beta_{h}([f]):=[h\cdot f\cdot h^{-1}]$. Because actually $(h\cdot f)\cdot h^{-1}\simeq h\cdot (f\cdot h^{-1})$.

Fundamental groups are powerful in many (other) realms of mathematics. 
- It can even be used to prove the [[Fields Construction#^4e12b7|fundamental theorem of algebra]]: 
  *Proof*   For the sake of contradiction, suppose some non-constant polynomial $p(z)=z^{n}+a_{n-1}z^{n-1}+\cdots+a_{0}$ has no roots. Then for each $r\geq 0$, $$f_{r}(s)=\frac{p(re^{2\pi is})/p(r)}{|p(re^{2\pi is})|/|p(r)|}$$is a loop in $S^{1}$ based at $1$. Now fix some large $R>\max(1,|a_{0}|+\cdots+|a_{n-1}|)$. Then $f_{r}$ is a homotopy from $f_{0}=w_{0}$ to $f_{R}$. Let $p_{t}(z)=z^{n}+(1-t)(a_{n-1}z^{n-1}+\cdots+a_{0})$. Define $$g_{t}(s):=\frac{p_{t}(Re^{2\pi is})/p_{t}(R)}{|p_{t}(Re^{2\pi is})|/|p_{t}(R)|}.$$Note that since $R$ is sufficiently large $p_{t}(Re^{2\pi is})$ is never zero, $g_{t}$ is a valid homotopy from $f_{R}$ to $w_{n}$. Therefore, $$w_{0}=f_{0}\simeq f_{R}=g_{0}\simeq g_{1}=w_{n},$$which implies $n=0$ since $\pi_{1}(S^{1},1)\cong \Z$. This contradicts the assumption that $p$ is non-constant. $\square$ ^dfc77e
- We can also show the 2-dimensional Brouwer's fixed-point theorem by the fundamental group. It states that any continuous $h\colon D^{2}\to D^{2}$ has a fixed point, where $D^{2}$ is the closed disk in $\C$.
  *Proof*  Suppose $h$ has no fixed points. Then we can define $r\colon D^{2}\to S^{1}$ by sending $x\in D^{2}$ to the intersect point of $S^{1}$ and the ray from $h(x)$ to $x$. Note that $r(x)=x$ for $x\in S^{1}$. Consider the inclusion $i\colon S^{1}\hookrightarrow D^{2}$, we have $i\circ w_{1}\simeq c_{1}$ via some homotopy $f_{t}$. Then $w_{1}=r\circ i \circ w_{1} \simeq c_{1}$ via $r\circ f_{t}$, yielding a contradiction. $\square$
$\quad$ ^01b5b9

> [!proposition]
> Suppose $X$ and $Y$ are topological spaces, then the fundamental group $\pi_{1}(X\times Y,x_{0}\times y_{0})$ is isomorphic to $\pi_{1}(X,x_{0})\times \pi_{1}(Y,y_{0})$.
> 

*Proof*  This is simply because the universal property of product spaces implies that there is a one-to-one correspondence between the loops at $(x_{0},y_{0})$ in $X\times Y$ and the pairs of loops $(f,g)$ in $X$ and $Y$ at $(x_{0},y_{0})$. Then taking homotopy classes for the both sets gives the two groups. $\square$

<u><b>e.g.</b></u>  We can directly deduce that the fundamental group of a torus $\pi_{1}(S^{1}\times S^{1},(1,1))\cong \Z\times \Z$.

> [!proposition]
> Suppose $x_{0}\in A\subset X$. If $X$ retracts onto $A$, then the inclusion induced $i_{*}\colon \pi_{1}(A,x_{0})\to \pi_{1}(X,x_{0})$ is [[Relations and Functions#^042daf|injective]].
> Moreover, if $X$ [[Homotopy Types#^05414e|deformation retracts]] to $A$, then $i_{*}$ is an isomorphism.

*Proof*  Suppose $r\colon X\to A$ is the retraction and $i\colon A\to X$ is the inclusion, then $r\circ i=\id_{A}$, so $(r_{*}\circ i_{*})([f])=[r\circ i\circ f]=[f]$, which means $r_{*}\circ i_{*}=\id_{\pi_{1}(A,x_{0})}$, hence $i_{*}$ has to be [[Relations and Functions#^042daf|injective]]. Moreover, if $r\circ i \simeq \id_{X}$ through the homotopy $r_{t}$, then for any $[f]\in\pi_{1}(X,x_{0})$, pick a representative $f\colon I\to X$, let $f_{t}:=r_{t}\circ f$, then $f_{t}$ is a homotopy from $f=\id_{X}\circ f$ to $i\circ r\circ f$, so $[f]=[i\circ r\circ f]=i_{*}([r\circ f])$. Thus $i_{*}$ is [[Relations and Functions#^042daf|surjective]], hence an isomorphism. $\square$ 

> [!theorem]
> Suppose $\varphi\colon X\to Y$ is a homotopy equivalence. Then $\varphi_{*}\colon \pi_{1}(X,x_{0})\to \pi_{1}(Y,\varphi(x_{0}))$ is an [[Homomorphisms, Normal Subgroup & Conjugation#^c32ca8|isomorphism]].
> 
 
*Proof*


> [!definition] Simple Connectedness
> A [[Topological Spaces#^65c94a|topological space]] is simply-connected if it is [[Connectedness and Paths#^630354|path-connected]] and its fundamental group is trivial. ^3b18ee

