## Closed Subspaces and Orthogonality

> [!proposition]
> In any finite dimensional inner product space, every subspace is closed.
> 

*Proof*  Suppose $V$ is a finite dimensional inner product space and $W$ is a subspace of $V$. Then $W$ is finite dimensional. Since every finite dimensional normed space is complete, it follows that $W$ is closed in $V$. $\square$

> [!remark]
> However, this is not true in general for infinite dimensional spaces. For example, in an infinite dimensional Hilbert space with basis $\{e_{i}\}_{i=1}^{\infty}$, the subspace $\newcommand{\span}{\mathrm{span}}\span\{e_{1},e_{2},\dots\}$, which is the space of all finite linear combinations of the basis vectors, is not closed. To see this, consider the sequence $f_{n}=\sum_{i=1}^{n}e_{i}$, which converges to $f=\sum_{i=1}^{\infty}e_{i}$, which is not in $\span\{e_{1},e_{2},\dots\}$.
> 

> [!lemma]
> Suppose $\renewcommand{\S}{\mathcal{S}} \S\subset \H$ is a closed subspace of a Hilbert space $\H$, and $f\in \H$. Then
>  - There exists a unique element $g\in \S$ which is closest to $f$, in the sense that $\|f-g\|=\inf_{h\in \S}\|f-h\|$.
>  - $f-g$ is perpendicular to $\S$. i.e. $\langle f-g,h\rangle=0$ for all $h\in \S$.
> 
> $\quad$

> [!proposition]
> If $\S$ is a closed subspace of a Hilbert space $\newcommand{\H}{\mathcal{H}}\H$, then $\H$ is a [[Direct Sum#^2700ee|direct sum]] of $\S$ and its orthogonal: $$\H=\S\oplus\S^{\perp}.$$

> [!proposition]
> Suppose $U\subset V$ is a subspace of an (possibly infinite dimensional) [[Inner Products#^f0c22c|inner product space]], then $U^{\perp}$ is always [[Open and Closed Sets#^e112b1|closed]], and $(U^{\perp})^{\perp}=\bar{U}$, where $\bar{U}$ denotes the [[Closure, Interior and Boundary#^cf4e59|closure]] of $U$.

*Proof*  For all $\{f_{n}\}\subset U^{\perp}$ that converges to $f$, we claim that $f\in U^{\perp}$. Note that for all $g\in U$ and some $n\in\N$, we have $$|\langle f_{n},g\rangle-\langle f,g\rangle|=|\langle f_{n}-f,g\rangle|\leq \|f_{n}-f\|\cdot \|g\|,$$so $\{\langle f_{n},g\rangle\}_{n=1}^{\infty}$ converges to $\langle f,g\rangle$. Note that since each $\langle f_{n},g\rangle=0$, it converges to $0\in\C$. Hence, $\langle f,g\rangle=0$ for all $g\in U$. This shows that $f\in U^{\perp}$. So $U^{\perp}$ is closed.
Thus $(U^{\perp})^{\perp}$ is closed, and $\bar{U}\subset (U^{\perp})^{\perp}$. Now for any $h\in (U^{\perp})^{\perp}$, since $\bar{U}$ is closed, $\H=\bar{U}\oplus\bar{U}^{\perp}$, so we can write $h=h_{1}+h_{2}$, where $h_{1}\in \bar{U}$ and $h_{2}\in \bar{U}^{\perp}$. For any $g\in \bar{U}^{\perp}\subset U^\perp$, there holds $$0=\langle h,g\rangle=\langle h_{1},g\rangle+\langle h_{2},g\rangle.$$As $h_{1}\in \bar{U}$, $\langle h_{1},g\rangle=0$. So $\langle h_{2},g\rangle=0$ for all $g\in \bar{U}^{\perp}$, which implies $\langle h_{2},h_{2}\rangle=0$, hence $h_{2}=0$. Therefore, $h=h_{1}\in \bar{U}$, which implies that $(U^{\perp})^{\perp}=\bar{U}$. $\square$

> [!corollary]
> Suppose $U\subset V$ is a subspace of an (infinite dimensional) inner product space, then $U$ is [[Closure, Interior and Boundary#^b560bf|dense]] in $V$ iff $U^{\perp}=\{0\}$. ^6ac7cd

*Proof*  This is straightforward from the previous proposition. $\square$

<u><b>e.g.</b></u>  Consider the Hilbert space $L^{2}(S^{1})$, has an orthonormal basis $\{e^{in\theta}\}_{n\in \Z}$, where 

## Bounded Linear Operators

> [!definition] Bounded Linear Operator
> Suppose $V$ and $W$ are [[Normed Spaces#^345fd3|normed spaces]], then a linear operator $T\colon V\to W$ is bounded if there exists $M>0$ such that $$\|T(v)\|_{W}\leq M \|v\|_{V},\quad \text{for all }v\in V.$$In such case, the operator norm of $T$ is defined as $$\newcommand{\op}{\text{op}}\|T\|_{\op}:=\sup_{\|f\|_{V}= 1}\|T(f)\|_{W}.$$ ^f95b62

> [!lemma]
> For any bounded linear map $T\colon \H_{1}\to\H_{2}$ between two Hilbert spaces, we have $$\|T\|_{\op} = \sup_{\|f\|=1,\|g\|=1}|\langle Tf,g\rangle|.$$ ^f6c4d5

*Proof*  By Cauchy-Schwarz inequality, for all $g\in\H_{2}$ with $\|g\|=1$, we have $$|\langle Tf,g \rangle|\leq \|Tf\| \|g\|=\|Tf\|\leq\|T\|,$$ and so $\|T\|\geq \sup_{\|f\|=1,\|g\|=1}|\langle Tf,g\rangle|$. Conversely, $$\|Tf\|=\left\langle Tf,\frac{Tf}{\|Tf\|}\right\rangle\leq\sup_{\|f\|=1,\|g\|=1}|\langle Tf,g\rangle|,$$hence, we have $\|T\|\leq \sup_{\|f\|=1,\|g\|=1}|\langle Tf,g\rangle|$, which implies that $\|T\| = \sup_{\|f\|=1,\|g\|=1}|\langle Tf,g\rangle|$. $\square$

> [!proposition]
> A linear operator $T\colon\H_{1}\to\H_{2}$ is bounded if and only if it is [[Continuity of Functions#^f56121|continuous]] w.r.t the norm topology.
> 

*Proof*  If $T$ is bounded, then for all $\{f_{n}\}_{n=1}^{\infty}$ in $\H_{1}$, we have $\|T(f_{n})-T(f)\|\leq M\|f_{n}-f\|$ for all $n$. Taking the limit as $n\to\infty$, we have $\|T(f_{n})-T(f)\|\to 0$ as $n\to\infty$, so $T$ is continuous. Conversely, if $T$ is continuous, assume that $T$ is unbounded. Then for each $n>0$, there exists some $g_{n}$ such that $\|T(g_{n})\|> n \|g_{n}\|$. Let $h_{n}:=g_{n}/(n\|g_{n}\|)$, then $\|h_{n}\|=1/n$, so $h_{n}\to 0$. Since $T$ is continuous at $0$, we have $T(h_{n})\to 0$, however, $\|T(h_{n})\|>1$, which is a contradiction. Therefore, $T$ must be bounded. $\square$

> [!remark]+
>  There are many types of continuity. In fact, we have the following chain of implications: $$\|T_{n}-T\|_{\op}\to 0 \implies \forall f, T_{n}f\to Tf \implies \forall g, \langle T_{n}f,g\rangle \to \langle Tf,g\rangle.$$

