---
created: 2024-10-25
updated: 2024-11-13
completed: true
---
## First and Second Steps of Riemann Mapping Theorem

> [!lemma]
> If $\newcommand{\C}{\mathbb{C}}D ⊂\C$ is a [[The Fundamental Group#^3b18ee|simply connected]] domain and $0 \notin D$, then there exists $k∈H(D)$ such that $k(z)^{2}= z$ for all $z ∈D$. Such a map $k$ is [[Relations and Functions#^042daf|injective]], and if $w∈k(D)$ then $−w \notin k(D)$. ^b2c9c6

*Proof*  Since $D$ is simply connected and $0\notin D$, we may choose a [[Integration and Primitives#^f2c63f|primitive]] $F\in H(D)$ of the function $\frac{1}{z}\in H(D)$. By the proposition, $F$ is a branch of the logarithm up to a constant. Define $k(z)=e^{F(z)/2}$. Then $k(z)^{2}=e^{F(z)}=z$ for all $z\in D$. Assume that $k(z_{1})=k(z_{2})$ for some $z_{1}, z_{2}\in D$. Then $z_{1}=k(z_{1})^{2}=k(z_{2})^{2}=z_{2}$, so $k$ is injective. Now if $k(z_{1})=-k(z_{2})$, then $z_{1}=k(z_{1})^{2}=k(z_{2})^{2}=z_{2}$, so $k(z_{1})=k(z_{2})$, that is $k(z_{1})=0$, and thus $z_{1}=0$, yielding a contradiction. $\square$

>[!lemma] First Step of Riemann Mapping Theorem
> Let $D\subsetneq \C$ be a [[The Fundamental Group#^3b18ee|simply connected]] domain. Let $z_{0}\in D$, and define $$\mathcal{F}=\{ f\in H(D) \mid f(z_{0})=0, f(D)\subset\Delta, f \text{ is injective} \}$$Then $\mathcal{F}$ is non-empty. ^52e695

*Proof*  Since $D\neq\C$, we may choose $a\in\C$, $a\notin D$. Let $D'$ be the translated domain $D-a$, so that $0\notin D'$. By the above lemma, there exists injective $k\in H(D')$ such that $k(z)^{2}=z$ for all $z\in D'$, and if $w\in k(D')$ then $−w \notin k(D')$. Fix some $w_{0}\in k(D')$. Since $k$ is injective, it is not constant, the [[The Open Mapping Theorem#^6df1f8|open mapping theorem]] implies that $k(D')$ is open. Thus, there exists $r>0$ such that $\Delta(w_{0},r)\subset k(D')$ and $\Delta(−w_{0},r)\cap k(D')=\emptyset$. That is, for all $z\in D'$, $|k(z)+w_{0}|\geq r$, which is equivalent to $|k(z-a)+w_{0}|\geq r$ for all $z\in D$. Hence $$\left|\frac1{k(z-a)+w_0}\right|\leq\frac1r$$so that $z\mapsto \frac1{k(z-a)+w_0}$ is an injective, bounded holomorphic function on $D$. And so $$z\mapsto \epsilon\left(\frac1{k(z-a)+w_0}-\frac1{k(z_0-a)+w_0}\right)$$is injective and vanishes at $z_{0}$, and can be bounded into $\Delta$ by choosing $\epsilon$ small enough. $\square$

> [!lemma] Converse Schwarz lemma
> Let $D'\subsetneq \Delta$ be a [[The Fundamental Group#^3b18ee|simply connected]] domain and suppose $0\in D'$. Then there exist an injective $h\in H(D')$ such that $h(0)=0$, $h(D')\subset \Delta$ and $|h'(0)|>1$. ^da28e9

*Proof*  We choose $w_{0}\in \Delta \setminus D'$. Let $D'':=\alpha_{w_{0}}(D')$ and note that $D''\subset \Delta$ and $0\notin D''$. By the [[Riemann Mapping Theorem#^b2c9c6|lemma]], we can pick injective $k\in H(D'')$ such that $k(z)^{2}=z$ for all $z\in D''$. Note that $|k(x)|=|z|^{1/2}<1$, so $k(D'')\subset \Delta$. Let $h:=\alpha_{w_{1}}\circ k\circ\alpha_{w_{0}}$, where $w_{1}:=k(\alpha_{w_{0}}(0))$, so that $h(0)=0$. Since $k$ is injective, $h$ is also injective. Since $k$ is holomorphic, $h$ is holomorphic. Since $k(D'')\subset \Delta$, we have $h(D)\subset \Delta$.
Now let $\tilde{h}\colon \Delta\to\Delta$ be the following one-sided inverse of $h$: $$\tilde{h}=\alpha ^{-1}_{w_{0}} \circ (z\mapsto z^{2}) \circ \alpha_{w_{1}}^{-1}$$Then $\tilde{h}\in H(\Delta)$, and for all $z\in D'$, we have $$\tilde{h}(h(z))=\alpha_{w_0}^{-1}(\alpha_{w_1}^{-1}(\alpha_{w_1}(k(\alpha_{w_0}(z))^2)=\alpha_{w_0}^{-1}(k(\alpha_{w_0}(z))^2)=\alpha_{w_0}^{-1}(\alpha_{w_0}(z))=z$$Since $h(0)=0$, we conclude that $\tilde{h}(0)=0$, and by differentiating, we have $$\tilde{h}^{\prime}(h(z))h^{\prime}(z)=1$$Evaluating at $0$ and taking modulus, we have $|\tilde{h}^{\prime}(0)||h^{\prime}(0)|=1$. By the [[Conformal Transformations of The Disk#^5147f4|Schwarz lemma]], we have $|\tilde{h}^{\prime}(0)|\leq 1$. But $\tilde{h}$ is not injective since $\alpha_{w_{1}}^{-1}$ contains both $\frac{1}{2}$ and $-\frac{1}{2}$, so $\tilde{h}$ cannot be a rotation, therefore $|\tilde{h}^{\prime}(0)|<1$. Hence $|h^{\prime}(0)|>1$. $\square$

> [!remark]+ Converse to the Schwarz lemma
> This lemma is a sort of converse to the Schwarz lemma, because the Schwarz lemma says that the statement of the lemma is false when $D'= ∆$.

>[!lemma] Second Step of Riemann Mapping Theorem
> Let $D\subsetneq \C$ be a [[The Homotopy Invariance Theorem#^708d4a|simply connected domain]]. Let $z_{0}\in D$, and define $$\mathcal{F}=\{ f\in H(D) \mid f(z_{0})=0, f(D)\subset\Delta, f \text{ is injective} \}$$Then if $f\in\mathcal{F}$ and $|f^{\prime}(z_0)|\geq|g^{\prime}(z_0)|$ for all $g\in\mathcal{F}$, then $f(D)=\Delta$. ^03db60

*Proof*  We will show the contrapositive. Suppose that $f\in\mathcal{F}$ and $f(D)\subsetneq \Delta$. Let $D'=f(D)$, and then choose $h$ as in the [[Riemann Mapping Theorem#^da28e9|lemma]], and set $g:=h\circ f$. Then $g(z_{0})=h(0)=0$, $g(D)=h(f(D))=h(D')\subset\Delta$, and $g$ is injective as a composition of injective functions, so $g\in\mathcal{F}$. But $$|g'(z_0)|=|h'(f(z_0))f'(z_0)|=|h'(0)||f'(z_0)|>|f'(z_0)|$$as required. $\square$

## Hurwitz’s Theorem

> [!theorem] Hurwitz’s Theorem
> Let $D$ be a domain, and let $f_{n},f ∈H(D)$ with $f\neq 0$. Suppose that $f_{n} →f$ normally on $D$ and that $f(z_{0}) = 0$ for some $z_{0}  ∈D$. Then for all $r>0$, there is some $N >0$ such that whenever $n≥N$ we have $K_{f_n,\Delta(z_0,r)}\geq1$. ^8f6710

*Proof*  Since $f\neq 0$, the [[Series Expansion of Holomorphic Functions#^b5768d|uniqueness theorem]] implies that there is some $r_{0}>0$ such that $f$ has no zeroes in $\overline{\Delta(z_{0 },r)}\setminus \{ z_{0} \}$ (if no such $r$ existed, we could construct a sequence of zeroes converging to $z_{0}$, and $f$ would be e identically zero). Let $r<r_{0}$, and $\epsilon:=\min_{|z-z_{0}|=r}|f(z)|>0$. Choose $N$ such that $n\geq N$ implies that $|f_{n}(z)-f(z)|<\epsilon$ for all $z\in \partial \Delta(z_{0},r)$. This is allowed by the [[Normal Convergence of Holomorphisms#^f32fe1|theorem]], and $\partial\Delta(z_{0},r)$ is [[Compactness of Metric Space#^f1fb8b|compact]].
We now apply [[The Argument Principle#^fc2a0d|Rouche’s theorem]] to $f_{n}=f+(f_n-f)$. When $n\geq N$, we have for all $z\in\partial\Delta(z_{0},r)$, $$|f_n(z)-f(z)|<\epsilon\leq|f(z)|$$So we have $$K_{f_n,\Delta(z_0,r)}=K_{f,\Delta(z_0,r)}\geq1$$$\square$

>[!remark]+
> This theorem says that $f$ can only have a zero if eventually the functions $f_{n}$ have a zero nearby; that is, a zero cannot just appear in the limit. This is false in the context of real analysis. Consider the functions $f_{n}(x)=x^{2}+\frac{1}{n}$ on the interval $(−1,1)$. None of the functions $f_{n}$ has any zeroes, but the limit $f(x) = x^{2}$ has a zero at $x= 0$.

> [!lemma] Part (a), Third Step of Riemann Mapping Theorem
> Let $D\subsetneq \C$ be a [[The Homotopy Invariance Theorem#^708d4a|simply connected domain]]. Let $z_{0}\in D$, and define $$\mathcal{F}=\{ f\in H(D) \mid f(z_{0})=0, f(D)\subset\Delta, f \text{ is injective} \}$$ If $f_{n} ∈\mathcal{F}$ and $f_{n} →f$ normally on $D$, then either $f =0$ or $f ∈\mathcal{F}$. ^2f96e4

*Proof*  Clearly, we have $f(z_{0})=\lim_{n\to \infty} f_{n}(z_{0})=0$. Since $f_{n}(D)\subset \Delta$, $|f_{n}(z)|<1$ for all $z\in D$. So taking the limit as $n\to\infty$, we have $|f(z)|\leq 1$ for all $z\in D$. Suppose $|f(z)|=1$ for some $z\in D$. Then $z$ is a maximum point of $|f|$ on $D$, so $f$ is constant by the [[The Open Mapping Theorem#^5a8a82|strong maximum principle]]. Since $f(z_{0})=0$, we must have $f=0$. Otherwise, $|f(z)|<1$ for all $z\in D$.
Now we verify the third condition. Suppose $f\neq 0$, and to a contradiction that $f(z_{1})=f(z_{2})$ for some $z_{1},z_{2}\in D$ with $z_{1}\neq z_{2}$. Choose $r>0$ such that $z_{1}\notin \Delta(z_{2},r)$. Let $g_{n}(z):=f_{n}(z)-f_{n}(z_{1})$ and $g(z)=f(z)-f(z_{1})$, then $g_{n}\to g$ normally on $D$, and $g(z_{2})=0$. By the [[Riemann Mapping Theorem#^8f6710|Hurwitz's theorem]], there exists $N$ such that $K_{g_{n},\Delta(z_{2},r)}\geq1$ for all $n\geq N$. Thus there exists $z_{3}\in\Delta(z_{2},r)$ such that $$0=g_{N}(z_{3})=f_{N}(z_{3})-f_{N}(z_{1})$$Hence $f_{N}(z_{3})=f_{N}(z_{1})$. But $z_{1}\notin \Delta(z_{2},r)$, so $z_{1}\neq z_{3}$ and thus $f_{N}$ is not injective, a contradiction.
Therefore, $f$ is injective, and $f\in\mathcal{F}$. $\square$

## Montel's Theorem

> [!lemma]
> Let $D$ be a domain and let $\mathcal{F}⊂H(D)$. Assume that for every compact $K ⊂D$ there exists an $M >0$ such that $|f(z)|≤M$ for all $f ∈\mathcal{F}$ and $z ∈K$. Let $$\mathcal{F}_K=\{f|_K: f\in\mathcal{F}\}\subset C(K)$$Then every sequence in $\mathcal{F}_{K}$ has a subsequence that [[Convergence of Functions#^a59a2d|converges uniformly]] on $K$.

*Proof*  We will prove by [[Convergence of Functions#^5cb1ea|Arzelà-Ascoli theorem]], showing that
1. $\mathcal{F}_{K}$ is bounded: for all $z ∈K$, there is a $M >0$ such that $|f(z)|≤M$ for all $f ∈\mathcal{F}_K$
2. $\mathcal{F}_{K}$ is uniformly equicontinuous: for all $\varepsilon>0$, there exists a $\delta>0$ such that $|z_{1}-z_{2}|<\delta$ implies $|f(z_{1})-f(z_{2})|<\varepsilon$ for all $f\in\mathcal{F}_K$.

Each singleton set $\{z\}\subset D$ is compact, so by assumption, each $f(z)$ is bounded. So $\mathcal{F}_{K}$ is bounded. Let $\varepsilon>0$, for $r>0$, let $$K^{r}:=\{ z\in\C : d(z,K)\leq r \}$$Since $K^{r}$ is compact, we may choose $r>0$ such that $K^{r}\subset D$. By assumption, there is $M>0$ such that $|f(z)|\leq M$ for all $f\in\mathcal{F}$ and $z\in K^{r}$. Choose $\delta>0$ such that $\delta<r$ and $\delta<\frac{r}{2M}\varepsilon$. We will show that if $|z-z'|<\delta$, then $|f(z)-f(z')|<\varepsilon$ for all $f\in\mathcal{F}_K$. Fix $z\in K$, Define $g\in H(\Delta)$ by $g(w)=\frac{f(z+rw)-f(z)}{2M}$. Since $|w|<1$, we have $z,z+rw\in\Delta(z,r)\subset K^r$, so by the triangle inequality, we have $$|f(z+rw)-f(z)|\leq2M$$so $|g(w)|\leq 1$ for all $w\in\Delta$. By construction we have $g(0)=0$, so we invoke the [[Conformal Transformations of The Disk#^5147f4|Schwarz lemma]] to conclude that $|g(w)|\leq |w|$ for all $w\in\Delta$. Now suppose further that $z'\in K$ and $|z-z'|<\delta$. Set $w=\frac{z-z'}{r}$, and since $\delta<r$ we have $|w|<1$. Thus $$\frac{\left|f(z+r\frac{z'-z}r)-f(z)\right|}{2M}=\left|g(w)\right|\leq\left|w\right|=\frac{\left|z'-z\right|}r$$It follows that $$|f(z')-f(z)|\leq\frac{2M}r|z-z'|<\frac{2M}r\delta<\varepsilon$$This completes the proof of uniform equicontinuity, so by the [[Convergence of Functions#^5cb1ea|Arzelà-Ascoli theorem]], every sequence in $\mathcal{F}_{K}$ has a subsequence that converges uniformly on $K$. $\square$

> [!theorem] Montel’s Theorem
> Let $D$ be a domain and let $\mathcal{F}⊂H(D)$. Assume that for every compact $K ⊂D$ there exists an $M >0$ such that $|f(z)|≤M$ for all $f ∈\mathcal{F}$ and $z ∈K$. Then every sequence in $\mathcal{F}$ has a [[Normal Convergence of Holomorphisms#^dd2ac8|normally convergent]] subsequence. ^d891b2

*Proof*  Let $(f_{n}) \subset \mathcal{F}$ be a sequence, $K_{j}:=\left\{z\in D: |z|\leq j,d(z,\partial D)\geq\frac{1}{j}\right\} \subset D$. Clearly each $K_{j}$ is compact and $\bigcup_{j=1}^{\infty} K_{j}=D$, since each $z\in D$ lies in some $K_{j}$, and every compact $K\subset D$ is a subset of some $K_{j}$. By the above lemma, we may choose a subsequence $f_{1,n}$ of $f_{n}$ that converges uniformly on $K_{1}$, a subsequence $f_{2,n}$ of $f_{1,n}$ converges uniformly on $K_{2}$, and so on. We then have a family of subsequences $f_{j,n}$ that converges uniformly on $K_{j}$ for all $j\in\mathbb{N}$. Now let $g_{n}:=f_{n,n}$, a subsequence of $f_{n}$. Indeed, this is a subsequence of every $f_{j,n}$ eventually after omitting at most finitely many (less than $j$) terms. $$\begin{array}{}f_{1,1}&f_{1,2}&f_{1,3}&\dots \\f_{2,1}&f_{2,2}&f_{2,3}&\dots \\f_{3,1}&f_{3,2}&f_{3,3}&\dots \\\vdots&\vdots&\vdots&\ddots\end{array}$$Since every compact $K\subset D$ is contained in some $K_{j}$, the sequence $(g_{n})$ converges uniformly on every compact $K\subset D$, which is to say that $g_{n}$ converges normally on $D$. $\square$

> [!lemma] Part (b), Third Step of Riemann Mapping Theorem
> Let $D$ be a domain and let $\mathcal{F}⊂H(D)$. Assume that for every compact $K ⊂D$ there exists an $M >0$ such that $|f(z)|≤M$ for all $f ∈\mathcal{F}$ and $z ∈K$. Let $$\mathcal{F}_K=\{f|_K\mid f\in\mathcal{F}\}\subset C(K)$$Then every sequence in $\mathcal{F}_{K}$ has a subsequence that converges uniformly on $K$. ^9ae797

*Proof*  This is a direct application of [[Riemann Mapping Theorem#^d891b2|Montel's theorem]]. $\square$

## Riemann Mapping Theorem

> [!theorem] Riemann Mapping Theorem
> Let $D\subsetneq \C$ be a [[The Homotopy Invariance Theorem#^708d4a|simply connected domain]]. Let $z_{0}\in D$. Then there exists a [[Holomorphic and Conformal Maps#^3dad2a|biholomorphic map]] $f\colon D\to \Delta$ such that $f(z_{0})=0$. ^1da8e6

*Proof*  Given such a simply connected domain $D$, let $$\mathcal{F}_{D}:=\{f\in H(D):f(z_{0})=0,f(D)\subset\Delta, f \text{ is injective}\}$$Let $Q=\sup_{g\in\mathcal{F}}|g'(z_{0})|$. Choose a sequence $(g_{n})\subset \mathcal{F}$ such that $\lim_{n\to \infty}|g_{n}'(z_{0})|=Q$ (this required [[Riemann Mapping Theorem#^52e695|step 1]], that $\mathcal{F}\neq\emptyset$). By [[Riemann Mapping Theorem#^9ae797|step 3(b)]], we can find a subsequence $(g_{k_{n}})$ that converges normally on $D$ to some $f\in H(D)$. Then $|f'(z_{0 })|=\lim_{n\to \infty}|g'_{k_{n}}(z_{0})|=Q$. Since each $g_{n}$ is injective, by the [[The Open Mapping Theorem#^bf7ce8|corollary]], $g_{n}'(z_{0})\neq 0$, in particular, $Q\neq 0$. So $f'(z_{0})\neq 0$, therefore $f$ is not identically zero. By [[Riemann Mapping Theorem#^2f96e4|step 3(a)]] we have $f\in\mathcal{F}$, $f$ is injective. Now by [[Riemann Mapping Theorem#^03db60|step 2]], we have $f(D)=\Delta$. And so $f$ is the desired biholomorphic map by the [[The Open Mapping Theorem#^2ea31f|theorem]]. $\square$

> [!corollary] Riemann Uniformization Theorem
> Every simply connected domain $D\subseteq \hat{\C}$ is conformally equivalent to one and only one of the $\Delta$, $\C$ and $\hat{\C}$. ^558348

*Proof*  If $\hat{\C}\setminus D$ contains at least two points, then $D$ is conformally equivalent to $\Delta$ by the [[Riemann Mapping Theorem#^1da8e6|Riemann mapping theorem]]. If $\hat{\C}\setminus D$ contains only one point, we apply a Möbius transformation that maps this point to $\infty$. Such a transformation is biholomorphic between $D$ and $\C$. Finally, if $\hat{\C}\setminus D=\emptyset$, then $D=\hat{\C}$. 
It remains to show that $\Delta$, $\C$ and $\hat{\C}$ are not conformally equivalent with each other. First of all, $\Delta$ and $\C$ are non-compact, whereas $\hat{\C}$ is compact. Secondly, if $f\colon \C\to\Delta$ is a biholomorphic map, then $f$ is entire and bounded, and by the [[Series Expansion of Holomorphic Functions#^a2323b||Liouville's theorem]], $f$ is constant, which is a contradiction. $\square$

> [!proposition]
> Every conformal transformation of $\C$ has the form $f(z)=az+b$ with $a,b\in \C$.

