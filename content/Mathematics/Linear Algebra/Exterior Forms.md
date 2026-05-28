## $k$-Forms

> [!definition] $k$-form 
> An exterior $k$-form on a [[Vector Spaces#^f4b63e|vector space]] $V$ is a skew-symmetric [[Tensors and Tensor Products#^da894d|multilinear map]] $\newcommand{\d}{\mathrm{d}}\newcommand{\Z}{\mathbb{Z}}\newcommand{\R}{\mathbb{R}}\newcommand{\D}{\mathrm{D}}\omega\colon V^{k}\to \R$. Skew-symmetric means that $\newcommand{\sgn}{\mathrm{sgn}}\omega(v_{1},\dots,v_{k})=\sgn(\sigma)\omega(v_{\sigma(1)},\dots,v_{\sigma(k)})$ for any [[Symmetric Group#^caba60|permutation]] $\sigma\in S_{k}$, where $\sgn(\sigma)$ is $1$ or $-1$, depending on whether the permutation is [[Symmetric Group#^c116d4|even]] or [[Symmetric Group#^c116d4|odd]]. 
> The set of all $k$-forms on $V$ is denoted by $\Lambda^{k}(V)$. ^794521

<u><b>e.g.</b></u>  
- In particular, a $1$-form is exactly a covector in the [[Mathematics/Linear Algebra/Duality#^6c7627|dual space]] $V^{*}$. 
- Suppose that we have chosen a linear coordinate system $(x^{1},x^{2},\dots,x^{n})$ on a vector space $V$, then each coordinate $x^{i}$ defines a $1$-form.
- If a uniform force field $\mathbf{F}$ is given on $\R^{3}$, its work $A$ along the displacement $\mathbf{r}$ is a $1$-form acting on $\mathbf{r}$.
- The oriented area of a parallelogram [[Vector Spaces#^ce69a9|spanned]] by two vectors $\mathbf{u}$ and $\mathbf{v}$ in $\R^{2}$ is given by the $2$-form $$S(\mathbf{u},\mathbf{v}) = \det( \begin{bmatrix}\mathbf{u} &\mathbf{v}\end{bmatrix} )$$
$\quad$

> [!corollary]
> Every $k$-form on $\R^{k}$ is either zero or the oriented volume of the parallelepiped spanned by $k$ vectors in $\R^{k}$.

> [!proposition]
> Suppose $\omega\in\Lambda^{k}(V)$. If $\{u_1,u_2,\dots,u_k\}$ are linearly dependent vectors in $V$, then $\omega(u_1,u_2,\dots,u_k)=0$.
> 

*Proof*  Since $\{u_1,u_2,\dots,u_k\}$ are linearly dependent, one can assume that $u_k=a_1 u_1+\cdots+a_{k-1}u_{k-1}$ for scalars $a_1,\dots,a_{k-1}$. Then, using the multilinearity of $\omega$, we have $$\begin{aligned}\omega(u_1,u_2,\dots,u_k) &= \omega(u_1,u_2,\dots,a_1 u_1+\cdots+a_{k-1}u_{k-1}) \\&= a_1\omega(u_1,u_2,\dots, u_1) + \cdots + a_{k-1}\omega(u_1,u_2,\dots,u_{k-1}).\end{aligned}$$By the skew-symmetry of $\omega$, $\omega(u_1,u_2,\dots, u_i)$ vanishes for all $i\leq k-1$, which shows $\omega(u_1,u_2,\dots,u_k)=0$ as desired. $\square$

> [!corollary]
> Any $k$-form on an $n$-dimensional vector space $V$ with $k>n$ is identically zero.

*Proof*  $k$ vectors in $V$ must be linearly dependent if $k>n$. $\square$

> [!attention] 
> We shall from now on, assume that a $k$-form on an $n$-dimensional vector space satisfies $k\leq n$ without further notice.

## The Exterior Product

> [!definition] Exterior (Wedge) Product
> The exterior product of a $k$-form $\omega\in\Lambda^{k}(V)$ and a $l$-form $\eta\in\Lambda^{l}(V)$ is defined as the $(k+l)$-form $\omega\wedge\eta$ given by: $$(\omega\wedge\eta)(v_{1},\dots,v_{k+l}):=\frac{1}{k!l!}\sum_{\sigma\in S_{k+l}} \sgn(\sigma)\omega(v_{\sigma(1)},\dots,v_{\sigma(k)})\eta(v_{\sigma(k+1)},\dots,v_{\sigma(k+l)}).$$Alternatively, we can also write $$(\omega\wedge\eta)(v_{1},\dots,v_{k+l})=\sum_{\substack{i_{1}<\cdots<i_{k},\\j_{1}<\cdots<j_{l}}} \sgn(i_{1},\dots,i_{k},j_{1},\dots,j_{l})\omega(v_{i_{1}},\dots,v_{1_{k}})\eta(v_{j_{1}},\dots,v_{j_{l}}).$$

The above two expressions are equivalent, because instead of summing over  all permutations of $k+l$ elements, we can sum over all possible partitions of $k$ and $l$ elements, and for each partition, we can permute the $k$ and $l$ elements separately. Notice that for each fixed partition $\{i_{1},\dots,i_{k}\}\cup\{j_{1},\dots,j_{l}\}$, assuming $i_{1}<\cdots<i_{k}$, $j_{1}<\cdots<j_{l}$,  and for each permutation $\tau\in S_{k}$, $\theta\in S_{l}$, suppose the resulting permutation of $k+l$ elements is $\sigma\in S_{k+l}$, i.e. $\sigma=i_{\tau(1)},\dots,i_{\tau(k)},j_{\theta(1)},\dots j_{\theta(l)}$, we have $$\sgn(\sigma) = \sgn(i_{1},\dots,i_{k},j_{1},\dots,j_{l}) \sgn(\tau)\sgn(\theta),$$as [[Symmetric Group#^8ed9de|it is a group homomorphism]]. Thus $\sgn(i_{1},\dots,i_{k},j_{1},\dots,j_{l})  =\sgn(\sigma) \sgn(\tau)\sgn(\theta)$, because the inverse of any element is itself in the group $\{\pm 1\}\cong \Z_{2}$.
Moreover, by skew-symmetry,$$\omega(v_{\sigma(1)},\dots,v_{\sigma(k)})=\sgn(\tau)\omega(v_{i_{1}},\dots,v_{i_{k}}),\quad \eta(v_{\sigma(k+1)},\dots,v_{\sigma(k+l)})=\sgn(\theta)\eta(v_{j_{1}},\dots,v_{j_{l}}).$$So finally we get $$ \begin{aligned}
(\omega\wedge\eta)(v_{1},\dots,v_{k+l}) &=\frac{1}{k!l!}\sum_{\sigma\in S_{k+l}} \sgn(\sigma)\omega(v_{\sigma(1)},\dots,v_{\sigma(k)})\eta(v_{\sigma(k+1)},\dots,v_{\sigma(k+l)})\\
&= \frac{1}{k!l!} \sum_{\substack{i_{1}<\cdots<i_{k},\\j_{1}<\cdots<j_{l}}} k!l!\cdot\sgn(i_{1},\dots,i_{k},j_{1},\dots,j_{l})\omega(v_{i_{1}},\dots,v_{1_{k}})\eta(v_{j_{1}},\dots,v_{j_{l}})\\
&= \sum_{\substack{i_{1}<\cdots<i_{k},\\j_{1}<\cdots<j_{l}}} \sgn(i_{1},\dots,i_{k},j_{1},\dots,j_{l})\omega(v_{i_{1}},\dots,v_{1_{k}})\eta(v_{j_{1}},\dots,v_{j_{l}}).
\end{aligned},$$where the second equality holds as there are $k!l!$ permutations for each fixed partition. $\square$

<u><b>e.g.</b></u>  Given two one forms $\omega,\eta\in \Lambda^{1}(V)$, their exterior product $\omega\wedge\eta$ is a two form that satisfies $$(\omega \wedge \eta) (v,u) = \omega(v)\eta(u)-\omega(u)\eta(v)=\det \left(  \begin{bmatrix}\omega(v) &\eta(v) \\ \omega(u) & \eta(u)\end{bmatrix} \right).$$

> [!proposition]
> Let $\{e_{i}\}_{i=1}^{n}$ be a basis for a vector space $V$ and $\{e_{i}^{*}\}_{i=1}^{n}$ be the dual basis. Then for any $l\leq m\leq n,$ $$(e_{l}^{*}\wedge e_{l+1}^{*}\wedge\cdots\wedge e_{m}^{*})(e_{l},e_{l+1},\dots,e_{m})=1.$$
> 

*Proof*  We will prove by induction on $m$. Clearly, the base case $l=m$ is true. Now assume it holds for all $q\leq k$, then $$\begin{aligned}\,&(e_{l}^{*}\wedge e_{l+1}^{*}\wedge\cdots\wedge e_{k}^{*}\wedge e_{k+1}^{*})(e_{l},e_{l+1},\dots,e_{k+1})\\=&\,\sum_{\sigma(l)<\cdots<\sigma(k)}\sgn(\sigma)(e_{l}^{*}\wedge e_{l+1}^{*}\wedge\cdots\wedge e_{k}^{*})(e_{\sigma(l)},e_{\sigma(l+1)},\dots e_{\sigma(k)})\cdot e_{k+1}^{*}(e_{\sigma(k+1)})\\=&\,(e_{l}^{*}\wedge e_{l+1}^{*}\wedge\cdots\wedge e_{k}^{*})(e_{l},e_{l+1},\dots e_{k})\cdot 1\\=&\, 1,\end{aligned}$$where the second equality holds because $e_{k+1}^{*}(e_{\sigma(k+1)})$ is nonzero only if $\sigma$ fixes $k+1$, and the last equality holds by the induction hypothesis. $\square$

> [!theorem]  
> The exterior multiplication of forms is skew-commutative, distributive, and associative:
> - $\omega\wedge\eta = (-1)^{kl} \eta\wedge\omega$ for any $k$-form $\omega$ and $l$-form $\eta$.
> - $(\lambda_{1}\omega_{1}+\lambda_{2}\omega_{2})\wedge \eta =\lambda_{1}\omega_{1}\wedge\eta+\lambda_{2}\omega_{2}\wedge\eta$ for any $k$-forms $\omega_{1}$, $\omega_{2}$ and $l$-form $\eta$.
> - $(\omega\wedge \eta) \wedge\beta = \omega \wedge (\eta\wedge\beta)$.
>$\quad$ ^f54177

<u><b>e.g.</b></u>  Let $e_{i}$ be a basis for a vector space $V$ with dual basis $e_{i}^{*}$. Then we can calculate $$\begin{aligned} &\,(e_{1}^{*}\wedge e_{2}^{*}+e_{2}^{*}\wedge e_{3}^{*})(e_{1}+e_{2},e_{3}+e_{1})\\=&\, (e_{1}^{*}\wedge e_{2}^{*}+e_{2}^{*}\wedge e_{3}^{*})(e_{1},e_{3}+e_{1}) + (e_{1}^{*}\wedge e_{2}^{*}+e_{2}^{*}\wedge e_{3}^{*})(e_{2},e_{3}+e_{1}) \\=&\, (e_{1}^{*}\wedge e_{2}^{*}+e_{2}^{*}\wedge e_{3}^{*})(e_{1},e_{3}) + (e_{1}^{*}\wedge e_{2}^{*}+e_{2}^{*}\wedge e_{3}^{*})(e_{2},e_{3}) + (e_{1}^{*}\wedge e_{2}^{*}+e_{2}^{*}\wedge e_{3}^{*})(e_{2},e_{1})\\=&\, (e_{1}^{*}\wedge e_{2}^{*})(e_{1},e_{3}) + (e_{2}^{*}\wedge e_{3}^{*})(e_{1},e_{3}) + (e_{1}^{*}\wedge e_{2}^{*})(e_{2},e_{3}) \\&\, + (e_{2}^{*}+e_{3}^{*}) (e_{2},e_{3}) + (e_{1}^{*}\wedge e_{2}^{*})(e_{2},e_{1})+(e_{2}^{*}\wedge e_{3}^{*})(e_{2},e_{1})\\=&\, 0+0+0+1-1+0=0\end{aligned}$$

> [!proposition]
> The space of $k$-forms on an $n$-dimensional vector space $V$ is a [[Vector Spaces#^f4b63e|vector space]] of dimension $\binom{n}{k}$, and the exterior product $\wedge$ gives the space of all forms $\Lambda(V):=\oplus_{k=1}^{n} \Lambda^{k}(V)$ the structure of a super-commutative [[Grading and Filtration#^9b78c3|graded algebra]] over the field $\R$. In particular, if $\{e_{j}^{*}\}_{j=1}^{n}$ forms a basis for the 1-forms, $\{e_{i_{1}}^{*}\wedge e_{i_{2}}^{*}\wedge\cdots\wedge e_{i_{k}}^{*}:i_{1}<\cdots<i_{k}\}$ forms a basis for the $k$-forms.
> 

*Proof*  We first show that the forms are linearly independent. Suppose $\eta\in\Lambda^{k}(V)$ is a linear combination of these forms, i.e. $$\eta=\sum_{i_{1}<\cdots<i_{k}} a_{i_{1},\cdots,i_{k}} e_{i_{1}}^{*}\wedge e_{i_{2}}^{*}\wedge\cdots\wedge e_{i_{k}}^{*}.$$We set $\eta$ to be identically $0$. Notice that since $(e_{i_{1}}^{*}\wedge\cdots\wedge e_{i_{k}}^{*})(e_{j_{1}},e_{j_{2}},\dots,e_{j_{k}})$ is nonzero only if $i=j$, $\eta(e_{j_{1}},e_{j_{2}},\dots,e_{j_{k}})=a_{j_{1},\dots,j_{k}}=0$ holds for all $j_{1}<\cdots<j_{k}$, thus the forms are linearly independent.
Now we show that every $k$-form can be expressed as a linear combination of these forms. Suppose $\omega\in\Lambda^{k}(V)$, then $$\omega=\sum_{i_{1}<\cdots<i_{k}} \omega(e_{i_{1}},e_{i_{2}},\dots,e_{i_{k}}) e_{i_{1}}^{*}\wedge e_{i_{2}}^{*}\wedge\cdots\wedge e_{i_{k}}^{*}.$$Finally, the exterior product gives $\Lambda(V)$ the structure of a super-commutative graded algebra because of [[Differential Forms#^f54177|the theorem]]. $\square$

## Pullback Invariance

> [!proposition] Pullback Preserves Exterior Product
> For a linear map $A\colon V\to W$, and $\omega\in\Lambda^{k}(W)$, $\eta\in\Lambda^{l}(W)$, there holds $$A^{*}(\omega\wedge \eta) = A^{*}(\omega)\wedge A^{*}(\eta).$$ ^bfacb5

*Proof*  For all $v_{1},\dots,v_{k+l}\in V$, we have $$\begin{aligned}(A^{*}(\omega)\wedge A^{*}(\eta))(v_{1},v_{2},\dots,v_{k+l})&=\frac{1}{k!l!}\sum_{\sigma\in S_{k+l}}\sgn(\sigma)\omega(Av_{\sigma(1)},\dots,Av_{\sigma(k)})\eta(Av_{\sigma(k+1)},\dots,Av_{\sigma(k+l)})\\&=(\omega\wedge\eta)(Av_{1},\dots ,Av_{k+l})\\&=A^{*}(\omega\wedge\eta)(v_{1},v_{2},\dots,v_{k+l})\end{aligned}$$$\square$

## Interior Product

> [!definition] Interior Product
> The interior product of a $k$-form $\omega\in\Lambda^{k}(V)$ and a vector $v\in V$ is defined as the $(k-1)$-form $i_{v}\omega$ given by: $$i_{v}\omega(v_{1},\dots,v_{k-1}):=\omega(v,v_{1},\dots,v_{k-1}).$$

> [!proposition]
> The interior product is a degree $-1$ superderivation in the sense that it defines a linear map from $k$-forms to $(k-1)$-forms, and satisfies $$i_{v}(\omega\wedge\eta) = i_{v}\omega\wedge\eta + (-1)^{\deg \omega}\omega\wedge i_{v}\eta.$$
> 

*Proof*  

> [!theorem]
> Let $\eta$ be the standard volume form on $\R^{3}$. Then $v\mapsto i_{v}\eta$ is an isomorohism from $\R^{3}$ to $\Lambda^{2}(\R^{3})$. Moreover, the following identities hold: $$\langle u\times v, w\rangle=\eta(u,v,w),\quad v^{*}\wedge w^{*}=i_{v\times w}\eta,\quad v^{*}\wedge i_{w}\eta=\langle v,w\rangle\eta.$$
> 
