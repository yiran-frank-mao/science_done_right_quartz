In this page, we will deal with the standard $\sigma$-algebra $\mathcal{B}$ making $\R^{d}$ (in particular $\R$) a [[Measurable Spaces and Functions#^60a516|measurable space]], as well as measurable functions that has $(\R,\mathcal{B})$ as its codomain. We will not assume any conditions more than a measurable space on the domain of $f$.

## Borel Sets

Recall the definition of a measurable space:

![[Measurable Spaces and Functions#^60a516|measurable space]]

> [!definition] Borel $\sigma$-Algebra
> The *Borel $\sigma$-algebra* on $\R^{d}$, denoted as $\mathcal{B}_{\R^{d}}$, is the smallest [[Measurable Spaces and Functions#^60a516|$\sigma$-algebra]] containing all [[Open and Closed Sets in Metric Spaces#^e112b1|open sets]]. The term “smallest” means that if $\mathcal{S}$ is any $\sigma$-algebra that contains all open sets in $\R^{d}$, then necessarily $\mathcal{B}_{\R^{d}}\subset \mathcal{S}$. Elements of the Borel $\sigma$-algebra are called *Borel sets*. ^47dc88

<u><b>e.g.</b></u>  
- Every closed subset of $\R$ is a Borel set because every closed subset of $\R$ is the complement of an open subset of $\R$.
- Every half-open interval $[a, b)$ (where $a, b \in \R$) is a Borel set because $[a, b) =  \bigcap_{k=1}^{\infty} (a − 1/k , b)$.
$\quad$

## Measurable Functions

Recall the definition of measurable functions:

![[Measurable Spaces and Functions#^11c83a]]

<u><b>e.g.</b></u>  If $\mathcal{S}=\{\emptyset, X\}$, then the only $\mathcal{S}$-measurable functions from $X$ to $\R$ are the constant functions.

> [!definition] Characteristic Function
> The *characteristic function* of a set $E\subset X$ is a function defined by $$\chi_{E}(x)=\begin{cases}1,\quad & \text{if }x\in E, \\ 0, \quad & \text{if }x\notin E.\end{cases}$$

As its name indicates, we observe that

> [!proposition]
> $\chi_{E}$ is $\mathcal{S}$-measurable if and only if $E\in \mathcal{S}$.

*Proof*  This is obvious once we have written out preimage: for any Borel set $B$, $$\begin{aligned}\chi_E^{-1}(B)&=\begin{cases}E&\mathrm{~if~}0\notin B\mathrm{~and~}1\in B,\\X\setminus E&\mathrm{~if~}0\in B\mathrm{~and~}1\notin B,\\X&\mathrm{~if~}0\in B\mathrm{~and~}1\in B,\\\emptyset&\mathrm{~if~}0\notin B\mathrm{~and~}1\notin B.&\end{cases}\end{aligned}$$ $\square$

> [!proposition]
> Suppose $(X,\mathcal{S})$ is a measurable space. A function $f\colon x\to \R$ is  $\mathcal{S}$-measurable, if and only if, $f^{-1}((-\infty,a])$ or $f^{-1}([a,\infty))$ or $f^{-1}((-\infty,a))$ or $f^{-1}((a,\infty))$ is $\mathcal{S}$-measurable for all $a\in \R$. 
> 

*Proof*  It suffices to prove $f^{-1}((a,\infty))\in\mathcal{S}$ for all $a\in\R$ implies measurability of $f$. Suppose $f^{-1}((a,\infty))\in\mathcal{S}$ for all $a\in\R$. Consider $\mathcal{S}'=\{A\subseteq \R \mid f^{-1}(A)\in\mathcal{S} \}$. We claim that the Borel $\sigma$-algebra is a subset of $\mathcal{S}'$. To show this, we show that $\mathcal{S}'$ contains every open subset, and is indeed a $\sigma$-algebra. Clearly, $\emptyset\in\mathcal{S}'$ because $f^{-1}(\emptyset)=\emptyset$. Suppose $A\in \mathcal{S}'$, then $f^{-1}(A)\in \mathcal{S}$, and thus $f^{-1}(A^{c})= f^{-1}(A)^{c}\in\mathcal{S}$, so $A^{c}\in \mathcal{S}'$. If $A_{1}, A_{2}, \dots\in \mathcal{S}'$, then $f^{-1}(A_{i})\in \mathcal{S}$ for all $i$, and thus $f^{-1}(\bigcup_{i=1}^{\infty} A_{i})=\bigcup_{i=1}^{\infty} f^{-1}(A_{i})\in \mathcal{S}$, so $\bigcup_{i=1}^{\infty} A_{i}\in \mathcal{S}'$. Therefore, $\mathcal{S}'$ is a $\sigma$-algebra. Finally, we show that every open subset of $\R$ is in $\mathcal{S}'$. It suffices to show that every open interval $(a,b)$ is in $\mathcal{S}'$. But we have $(a,b)=\bigcup_{n=1}^{\infty} (a,b-1/n]$, and $(a,b-1/n]=(a,\infty)\cap(b-1/n,\infty)^c$, and thus $(a,b)\in \mathcal{S}'$. Therefore, the Borel $\sigma$-algebra is a subset of $\mathcal{S}'$, and thus $f$ is measurable. $\square$

> [!proposition]
> Suppose $(X, \mathcal{S})$ is a measurable space and $f, g \colon X \to \R$ are $\mathcal{S}$-measurable. Then
> - $f + g$, $f − g$, and $f g$ are $\mathcal{S}$-measurable functions;
> - if $g(x)\neq 0$ for all $x\in X$, then $f/g$ is an $\mathcal{S}$-measurable function.
> $\quad$
> 

> [!proposition]
> Suppose $(X, \mathcal{S})$ is a measurable space and $f_{1}, f_{2}, \dots$ is a sequence of  $\mathcal{S}$-measurable functions from $X$ to $\mathbb{R}$. Suppose $\lim_{k\to \infty} f_{k}(x)$ exists for each  $x \in X$. Define $f\colon X \to \mathbb{R}$ by $f(x):=\lim_{k\to \infty} f_{k}(x)$, then $f$ is $\mathcal{S}$-measurable.

*Proof*  Fix some $a\in\R$. We claim that $$f^{-1}((a,\infty))=\bigcup_{j=1}^\infty\bigcup_{m=1}^\infty\bigcap_{k=m}^\infty f_k^{-1}\left(\left(a+\frac1j,\infty\right)\right).$$For any $x\in f^{-1}((a,\infty))$, we have $f(x)=\lim_{k\to \infty} f_{k}(x)>a$. Choose $j$ such that $1/j<f(x)-a$, say $1/j=(f(x)-a)/2$, then there exists some $m$ such that $f_{k}(x)>a+1/j$ for all $k\geq m$. This proves that $x$ is in the RHS.
For the other direction, picks some $x\in \bigcup_{j=1}^\infty\bigcup_{m=1}^\infty\bigcap_{k=m}^\infty f_k^{-1}\left(\left(a+\frac1j,\infty\right)\right)$, then there exists some $j$ and $m$, such that $f_{k}(x)>a+1/j$ for all $k\geq m$. Note that $f(x)=\lim_{k\to \infty}f_{k}(x)$, so $f(x)\geq a+1/j>a$, and thus $x\in f^{-1}((a,\infty))$. Therefore, the claim holds, and $f$ is $\mathcal{S}$-measurable. $\square$

## Extended Real-Valued Measurable Functions

> [!definition] Extended Reals
> We define the *extended reals* $[-\infty,\infty]:=\R\cup\{\infty\}\cup\{-\infty\}$. It is a measurable space with $\sigma$-algebra defined by $$\mathcal{B}_{[-\infty,\infty]}:=\{B\subset [-\infty,\infty]\mid B\cap \R \in \mathcal{B}_{\R}\}.$$
> This is (also) called the *Borel $\sigma$-algebra* on $[-\infty,\infty]$.
> In other words, a set $A \subset [−∞, ∞]$ is a Borel set if and only if there exists a Borel set $B ⊆ \R$ such that $A = B$ or $A= B ∪ {∞}$ or $A = B ∪ \{−∞\}$ or  $A = B ∪ \{∞, −∞\}$.

Similarly, a function $f \colon X → [−∞, ∞]$ is *measurable* if and only if $f^{-1}(B)$ is measurable for every Borel set $B ⊆ [−∞, ∞]$, and we have analogous conditions for a function to be measurable:

> [!proposition]
> Suppose $(X, \mathcal{S})$ is a measurable space and $f \colon X \to [−∞, ∞]$, then $f$ is $\mathcal{S}$-measurable if and only if $f^{-1}([a, ∞))$ or $f^{-1}([−∞, a))$ is $\mathcal{S}$-measurable for all $a \in \R$.
> 

> [!proposition]
> Suppose $(X,\mathcal{S})$ is a [[Measurable Spaces and Functions#^60a516|measurable space]], and $\{f_{n}\}_{n=1}^{\infty}$ is a sequence of $\mathcal{S}$-measurable functions from $X$ to $[-\infty, \infty]$. Then $$x\mapsto\sup_{n}f_{n}(x), \quad x\mapsto\inf_{n} f_{n}(x),\quad x\mapsto\limsup_{n\to \infty} f_{n}(x),\quad x\mapsto\liminf_{n\to \infty}f_{n}(x)$$are $\mathcal{S}$-measurable. In particular, if $\lim_{n\to \infty} f_{n}$ exists a.e., it is measurable.

*Proof*  Let $a\in \R$. Note that $\{\sup_{n} f_{n}>a\}=\bigcup_{n}\{f_{n}>a\}$, and $\{\limsup_{n} f_{n}>a\}=\bigcap_{N}\bigcup_{n\geq N}\{f_{n}>a\}$, and other cases are similar. $\square$

> [!remark]
> The above is NOT true if we have an uncountable family of measurable functions. For example, consider $X=\R$ with the [[Measurable Spaces and Functions#^401f01|countable-cocountable $\sigma$-algebra]]. Then $$f_{r}(x)=\begin{cases}1,&\text{if }x=r,\\0,&\text{otherwise}\end{cases}$$is measurable for each $r\in \R$, but $\sup_{r\in [0,1]}f_{r}(x)=\chi_{[0,1]}(x)$ is not measurable.
> 

> [!definition] Simple Function, Step Function
> A simple function is a function that can be expressed as a finite linear combination of characteristic functions of measurable sets with finite measure: $$f=\sum_{k=1}^{N}a_{k}\chi_{E_{k}}$$where $a_{k}$ are constants. In particular, if each $E_{k}$ is a rectangle, then $f$ is called a step function. ^ad60a2