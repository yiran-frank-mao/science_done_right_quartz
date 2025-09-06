## Hardy-Littlewood Maximal Function

> [!lemma] Vitali's Covering Lemma
> Suppose $\mathcal{B} = \{B_1, B_2, \ldots, B_N\}$ is a finite collection of open balls in some [[Metric Spaces#^0eacc7|metric space]] $(X,d)$. Then there exists a disjoint sub-collection $B_{i_1}, B_{i_2}, \ldots, B_{i_k}$ of $\mathcal{B}$ such that the $3$-times expansions $\hat{B}_{i_{1}}, \hat{B}_{i_{2}}, \ldots, \hat{B}_{i_{k}}$ of $B_{i_1}, B_{i_2}, \ldots, B_{i_k}$ satisfy
> $$\bigcup_{n=1}^{k} \hat{B}_{i_{n}} \supset \bigcup_{i=1}^{N} B_{i}.$$

> [!corollary]
> Suppose $\mathcal{B} = \{B_1, B_2, \ldots, B_N\}$ is a finite collection of open balls in $\R^d$. Then there exists a disjoint sub-collection $B_{i_1}, B_{i_2}, \ldots, B_{i_k}$ of $\mathcal{B}$ that satisfies  
> $$m\left(\bigcup_{\ell = 1}^{N} B_{\ell}\right) \leq 3^d \sum_{j=1}^{k} m(B_{i_j}).$$

> [!definition] Hardy-Littlewood Maximal Function
> Suppose $f\colon \R^d \to \R$ is [[Lebesgue Integration#^f4d3e6|integrable]], we define its Hardy-Littlewood maximal function $f^{*}\colon\R^{d}\to[0,\infty]$ by $$f^{*}(x):=\sup_{B\supset\{x\}}\frac{1}{m(B)}\int_{B} |f(y)|\dd y.$$In other words, $f^{*}$ is the supremum over all balls $B$ containing $x$ of the average value of $|f|$ over $B$.

<u><b>e.g.</b></u>  Hardy-Littlewood maximal function of the characteristic function of the interval $[0, 1]$ is $$\chi_{[0,1]}^{*}(x)=\begin{cases}\frac{1}{2(1-x)} \quad&\text{if }x\leq 0, \\ 1 \quad &\text{if } 0<x<1, \\ \frac{1}{2x} \quad& \text{if }x\geq 1.\end{cases}$$

> [!theorem]
> Suppose $f\colon \R^{d}\to \R$ is integrable. Then the Hardy-Littlewood maximal function $f^{*}$ is Lebesgue measurable and $f^{*}(x)<\infty$ for almost every $x\in\R^{d}$.
> 

> [!theorem]
> Suppose $f\colon \R^{d}\to \R$ is integrable. Then there holds $$m\left(\{x\in\R^{d}:f^{*}(x)>\alpha\}\right)\leq\frac{3^{d}}{\alpha}\|f\|_{1},$$
> for all $\alpha>0$.

> [!remark]
> Broadly speaking, this means $f^{*}$ is not much larger than $|f|$.
> 

## Lebesgue Differentiation Theorem

> [!definition] Locally Integrable Function
> A measurable function $f\colon \R^{d}\to \R$ is locally integrable if for every ball $B$, the function $f(x)\chi_{B}(x)$ is integrable.

> [!proposition]
> Clearly, if $f$ is integrable, then $f$ is locally integrable.

> [!theorem] Lebesgue Differentiation Theorem
> If $f$ is locally integrable on $\R^{d}$, then $$\lim_{\substack{m(B)\to0\\B\supset\{x\}}}\frac{1}{m(B)}\int_{B}f(y) \dd y=f(x),\quad\text{for almost all } x\in\R^{d}.$$ ^35dec0

## Density

> [!definition] Lebesgue Density
> Suppose $E\subset \R^{d}$. The density of $E$ at $x\in\R^{d}$ is defined as $$\newcommand{\dens}{\operatorname{dens}}\dens(E,x):=\lim_{\substack{m(B)\to0\\B\supset\{x\}}}\frac{m(E\cap B)}{m(B)},$$ if the limit exists. If the limit does not exist, we say that the density of $E$ at $x$ is undefined.

<u><b>e.g.</b></u>  This definition captures the notion of the proportion of a set in small intervals centered at a number $x$. For example, the density of $[0,1]$ is $$\dens([0,1],x)=\begin{cases} 1\quad &\text{if } x\in(0,1),\\\frac{1}{2} \quad&\text{if }x=0 \text{ or }1,\\ 0,\quad&\text{otherwise.}\end{cases}$$

> [!corollary] Lebesgue Density Theorem
> Suppose $E$ is a measurable subset of $\R^{d}$, then the density of $E$ is $1$ at almost every point of $E$ and $0$ at almost every point of $\R^{d}\setminus E$.

*Proof*  This is a direct consequence of the [[Lebesgue Differentiation Theorem#^35dec0|Lebesgue Differentiation Theorem]]. To see this, note that if $E$ is measurable, then $\chi_{E}$ is integrable. Thus, by the Lebesgue Differentiation Theorem, we have $$\lim_{\substack{m(B)\to0\\B\supset\{x\}}}\frac{1}{m(B)}\int_{B}\chi_{E}(y) \dd y=\chi_{E}(x),\quad\text{for almost all } x\in\R^{d}.$$ This implies that $$\lim_{\substack{m(B)\to0\\B\supset\{x\}}}\frac{m(E\cap B)}{m(B)}=\chi_{E}(x),$$ for almost all $x\in \R^{d}$. $\square$

> [!definition] Lebesgue Points
> Suppose $f$ is locally integrable on $\R^{d}$. A point $x\in\R^{d}$ is called a Lebesgue point of $f$ if $f(x)$ is finite and $$\lim_{\substack{m(B)\to0\\B\supset\{x\}}}\frac{1}{m(B)}\int_{B}|f(y)-f(x)| \dd y=0.$$We call the set of Lebesgue points of $f$ the Lebesgue set of $f$.

> [!proposition]
> If $f$ is locally integrable on $\R^{d}$, then $x\in\R^{d}$ is a Lebesgue point of $f$ if and only if $f$ is continuous at $x$.
> 

> [!corollary]
> If $f$ is locally integrable on $\R^{d}$, then almost every point of $\R^{d}$ is a Lebesgue point of $f$.

> [!definition] Shrink Regularity
> A collection of sets $\{U_{\alpha}\}_{\alpha\in A}$ is said to shrink regularly to $x$ if there is a constant $c>0$ such that for each $U_{\alpha}$, there is a ball $B$ such that $$x\in B, u_{\alpha}\subset B, \text{ and } m(U_{\alpha})\geq cm(B).$$

<u><b>e.g.</b></u>  In $\R^{d}$ with $d>2$, the collection of all open rectangles containing $x$ does not shrink regularly to $x$. This can be seen if we consider very thin rectangles.

> [!proposition]
> 

## Good Kernels and Approximations to the Identity