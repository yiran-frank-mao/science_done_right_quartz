## Engel's Theorem

> [!definition] ad-Nilpotent
> An element $\newcommand{\g}{\mathfrak{g}}x \in \g$ is *ad-nilpotent* if the map $\newcommand{\ad}{\operatorname{ad}}\ad_{x} \in \mathfrak{gl}(\g)$ is a nilpotent endomorphism, i.e., $(\ad_x)^k = 0$ for some $k$.

> [!lemma]
> If $x \in \mathfrak{gl}(V)$ is a nilpotent endomorphism, then $\ad_x \in \mathfrak{gl}(\mathfrak{gl}(V))$ is also nilpotent. ^818119

*Proof*  Let $\lambda_x, \rho_x$ be the left and right multiplication maps by $x$. Then $\ad_x = \lambda_x - \rho_x$. Since $\lambda_x$ and $\rho_x$ commute, we can use the binomial expansion: $\ad_x^n = (\lambda_x - \rho_x)^n = \sum_{i=0}^n \binom{n}{i} \lambda_x^i (-\rho_x)^{n-i}$. If $x^k=0$, then for $n=2k-1$, in each term of the sum either $i \ge k$ or $n-i \ge k$, so either $\lambda_x^i=0$ or $\rho_x^{n-i}=0$. Thus $\ad_x^{2k-1}=0$.  $\square$

> [!theorem] Engel's Theorem
> A finite-dimensional Lie algebra $\g$ is [[Ideals, Simple and Semisimple Lie Algebras#^f7e0b3|nilpotent]] if and only if every element $x \in \g$ is ad-nilpotent. ^3a3f00

A key lemma in the proof is another form of the theorem:

> [!theorem] Engel's Theorem (Alternative Form)
> Let $V$ be a non-zero finite-dimensional [[Vector Spaces#^f4b63e|vector space]]. If $\g \leq \mathfrak{gl}(V)$ is a Lie subalgebra consisting entirely of nilpotent endomorphisms, then there exists a non-zero vector $v \in V$ such that $x \cdot v = 0$ for all $x \in \g$. ^f3a13a

## Lie's Theorem

> [!definition] Full Flag
> Let $V$ be a finite dimensional [[Vector Spaces#^f4b63e|vector space]] over a field $F$, and let $\newcommand{\dim}{\operatorname{dim}}n=\dim V$. A *full flag* in $V$ is a sequence of subspaces $$(0)=V_{0} \subsetneq V_{1} \subsetneq V_{2} \subsetneq \cdots \subsetneq V_{n}=V,$$ where $\dim V_{i}=i$.

<u><b>e.g.</b></u>  If $V=F^{n}$ with a basis $\{e_{1}, e_{2}, \ldots, e_{n}\}$, then the standard full flag is given by $V_{i}=\mathrm{span}\{e_{1}, e_{2}, \ldots, e_{i}\}$ for $1 \leq i \leq n$.

> [!theorem] Lie's Theorem
> Let $\g$ be a [[Ideals, Simple and Semisimple Lie Algebras#^b49788|solvable]] Lie algebra over an [[Fields Construction#^5b9555|algebraically closed]] [[Ring, Field and Integral Domain#^575174|field]] $F$ of [[Fields and Field Extensions#^2bfbd8|characteristic]] $0$. Let $V$ be a finite-dimensional [[Vector Spaces#^f4b63e|vector space]] over $F$. If $\varphi\colon \g \to \mathfrak{gl}(V)$ is a [[Lie Algebra Representations#^df3ff7|representation]], then there exists a non-zero vector $v \in V$ which is a common eigenvector for all $x \in \g$. ^d489ea

*Proof*  We proceed by induction on $\dim(\mathfrak{g})$. For the base case, if $\dim(\mathfrak{g})=1$, then $\mathfrak{g}=F a$ for $a \in \mathfrak{g l}(V)$. Since $F$ is algebraically closed, $a$ has at least one eigenvalue, and therefore at least one eigenvector in $V$. That is, there exists some nonzero $v \in V$ such that $a \cdot v=\lambda v$. It follows that $\mathfrak{g} \cdot v \subset F v$. Now, assume $\dim(\mathfrak{g})>1$, and assume the theorem holds for all Lie algebras $\mathfrak{h}$ such that $\dim(\mathfrak{h})<\dim(\mathfrak{g})$. The proof follows the following steps:
1. Find an ideal $\mathfrak{h} \triangleleft \mathfrak{g}$ with $\operatorname{codim}(\mathfrak{h})=1$ (i.e. $\dim(\mathfrak{g} / \mathfrak{h})=1$ ).
2. Find a common eigenvector for $\mathfrak{h}$.
3. Show that $\mathfrak{g} \cdot W \subset W$, where $W$ is the subspace of common eigenvectors for $\mathfrak{h}$.
4. Show that $\mathfrak{g}=\mathfrak{h}+F z$ for $z \in \mathfrak{g} \backslash \mathfrak{h}$ and find a nonzero eigenvector $w \in W$ for $z$.

Step 1. By assumption $\mathfrak{g}$ is solvable, so $[\mathfrak{g}, \mathfrak{g}]$ is a proper subspace of $\mathfrak{g}$ (otherwise $D^{n}(\mathfrak{g})=\mathfrak{g}$ for every $n$, and so can never terminate). Then $\overline{\mathfrak{g}}=\mathfrak{g} /[\mathfrak{g}, \mathfrak{g}]$ is abelian, meaning every subspace is an ideal. Let $\overline{\mathfrak{h}}$ be a co-dimension one subspace, and hence an ideal, in $\overline{\mathfrak{g}}$. By the correspondence theorem, there exists an ideal $\pi^{-1}(\overline{\mathfrak{h}})=\mathfrak{h} \triangleleft \mathfrak{g}$ with $[\mathfrak{g}, \mathfrak{g}] \subset \mathfrak{h}$. Then $\overline{\mathfrak{g}} / \overline{\mathfrak{h}} \cong \mathfrak{g} / \mathfrak{h}$, and $\dim(\mathfrak{g} / \mathfrak{h})=1$.
Step 2. By the inductive hypothesis, there exists some $0 \neq v_{0} \in V$ such that $x \cdot v_{0}=\lambda(x) v_{0}$ for every $x \in \mathfrak{h}$. It is easy to check that $\lambda: \mathfrak{h} \rightarrow F$ is a linear functional. So, $v_{0}$ is a common eigenvector for $\mathfrak{h}$.
Step 3. Let $$W:=\{v \in V \mid \exists y \in \mathfrak{h} \text { s.t. } y \cdot v=\lambda(y) v\}$$We note that $W \neq(0)$ by Step 2. We claim that $\mathfrak{g} \cdot W \subseteq W$. To show this, let $w \in W$, $x \in \mathfrak{g}$. We want to show that $x \cdot w \in W$ - that is, for every $y \in \mathfrak{h}, y \cdot(x \cdot w)=\lambda(y)(x \cdot w)$. Since $\mathfrak{h}$ is an ideal, $[x, y] \in \mathfrak{h}$, and then $$\begin{aligned}y \cdot(x \cdot w) & =x \cdot(y \cdot w)-[x, y] \cdot w \\& =x \cdot(\lambda(y) w)-\lambda([x, y]) w \\& =\lambda(y)(x \cdot w)-\lambda([x, y]) w\end{aligned}$$It is therefore sufficient to show that $\lambda([x, y])=0$. Let $n>0$ be the largest integer such that $w, x w, \ldots, x^{n-1} w$ are all linearly independent. Let $W_{i}=\operatorname{Span}_{\mathbb{C}}\left\{w, x w, \ldots, x^{i-1} w\right\}$ for $i \geq 1$. By definition, $\dim\left(W_{i}\right)=i$ for $1 \leq i \leq n$, and $W_{i}=W_{n}$ for all $i>n$. It follows that $x\left(W_{n}\right) \subseteq W_{n}$, namely, $x$ restricts to an endomorphism of $W_{n}$. We now show that, for all $y \in \mathfrak{h}$, we have $y\left(W_{i}\right) \subseteq W_{i}$ for every $i$. It is sufficient to show $y \cdot\left(x^{j} w\right) \in W_{i}$ for every $0 \leq j \leq i-1$. We proceed by induction: if $i=1$ then $y \cdot w=\lambda(y) w \in W_{1}$. Now, assume $y\left(W_{j}\right) \subseteq W_{j}$ for every $j<i$. Then, $y \cdot\left(x^{j} w\right) \in W_{j} \subset W_{i}$ for any $0 \leq j<i-1$. It only remains to check $x^{i-1} w$ : $$y \cdot\left(x^{i-1} w\right)=x^{i-1} \cdot(y w)-\left[x^{i-1}, y\right] w=\lambda(y)\left(x^{i-1} w\right)-\lambda\left(\left[x^{i-1}, y\right]\right) w$$since $\left[x^{i-1}, y\right] \in \mathfrak{h}$ as it is an ideal. So, $y \cdot\left(x^{i-1} w\right) \in \operatorname{Span}_{F}\left\{w, x w, \ldots, x^{i-1} w\right\}=W_{i}$, meaning $y\left(W_{i}\right) \subseteq W_{i}$. If we let $B=\left\{w, x w, \ldots, x^{n-1} w\right\}$, then the matrix of $y$ with respect to $B$ is upper triangular: $$[y]_{B}=\left[\begin{array}{cccc}* & \cdots & \cdots & * \\0 & \ddots & & \vdots \\\vdots & \ddots & \ddots & \vdots \\0 & \cdots & \cdots & *\end{array}\right]$$since $y$ preserves $W_{i}$ for each $i$. But recall that when $y$ is applied to $x^{i-1} w$, the coefficient of $x^{i-1} w$ in the result is exactly $\lambda(y)$. So, this tells us that$$[y]_{B}=\left[\begin{array}{cccc}\lambda(y) & \cdots & \cdots & * \\0 & \ddots & & \vdots \\\vdots & \ddots & \ddots & \vdots \\0 & \cdots & \cdots & \lambda(y)\end{array}\right]$$This applies to every $y \in \mathfrak{h}$, in particular to $[x, y] \in \mathfrak{h}$, hence$$\operatorname{tr}([x, y])=\operatorname{tr}\left([x, y]_{B}\right)=n \lambda([x, y])$$But as the trace of a commutator is zero, and the field has characteristic zero, the latter equation implies that $\lambda([x, y])=0$. It follows that for any $w \in W, x \in \mathfrak{g}, y \in \mathfrak{h}$, we have $y \cdot(x \cdot w)=\lambda(y)(x \cdot w)$, meaning $\mathfrak{g} \cdot W \subseteq W$.
Step 4. Since $\operatorname{codim}(\mathfrak{h})=1$, we have that $\mathfrak{g}=\mathfrak{h} \oplus F z$ for any $z \in \mathfrak{g} \backslash \mathfrak{h}$. Fix such a $z$; by Step 3 , we know that $z \cdot W \subseteq W$. Since $F$ is algebraically closed, $z_{\mid W}$ has an eigenvector in $W$. That is, there exists some nonzero $w_{0} \in W$ such that $z \cdot w_{0}=\alpha w_{0}$. Thus, $\mathfrak{h} \cdot w_{0}=\lambda(\mathfrak{h}) w_{0} \subseteq F w_{0}$, and $F z \cdot w_{0}=F\left(\alpha w_{0}\right)=F w_{0}$. So, $\mathfrak{g} \cdot w_{0}=(\mathfrak{h} \oplus F z) \cdot w_{0} \subseteq F w_{0}$. $\square$

<u><b>e.g.</b></u>  
- Consider the Lie algebra $\mathfrak{b}_{n}(\C)$ of all upper triangular $n \times n$ complex matrices: $$\mathfrak{b}_{n}(\mathbb{C}) \cdot\begin{pmatrix} 1 \\0 \\\vdots \\0\end{pmatrix}=\mathbb{C}\begin{pmatrix}1 \\0 \\\vdots \\0\end{pmatrix}$$
- This theorem is not true if the field is not algebraically closed. Consider $$\left\{\begin{pmatrix}a & b \\-b & a\end{pmatrix} : a, b \in \mathbb{R}\right\} \subset \mathrm{M}_{2}(\mathbb{R}) \cong \mathfrak{g l}(\mathbb{R}^{2}).$$Then for any arbitrary matrix $A=\begin{pmatrix}a & b \\-b & a\end{pmatrix}$ such that $b \neq 0$, the characteristic polynomial is $p_{A}(t)=(t-a)^{2}+b^{2}$, which has no real roots. Thus, there are no eigenvectors in $\mathbb{R}^{2}$ for such matrices.
$\quad$

> [!corollary]
> Let $\mathfrak{g} \subset \mathfrak{g l}(V)$ be a solvable Lie algebra, over an [[Fields Construction#^5b9555|algebraically closed]] field $F$ of characteristic $0$. Then, $\mathfrak{g}$ stabilises a full flag $\left(V_{i}\right)_{i=0}^{n}$, i.e., $\mathfrak{g} \cdot V_{i} \subset V_{i}$ for all $0 \leq i \leq n$. ^e9c4ad

*Proof*  We'll prove this inductively on the dimension $n$ of $V$. In the base case where $\dim V=$ 0 , then $(\{0\})$ is a full flag. Trivially, $\mathfrak{g} \cdot\{0\} \subset\{0\}$, so the statement is true for dimension $n=0$.
Suppose that the statement were true over all vector spaces of dimension $n-1$. Then in $V$ of dimension $n$, from the above theorem we conclude that there exists some $v \in V$ such that $\mathfrak{g} \cdot v \subset F v$; that is, $\mathfrak{g} \cdot(F v) \subset F v$.
So both $V$ and $F v$ are $\mathfrak{g}$-modules, so $V / F v$ is also a $\mathfrak{g}$-module. $V / F v$ has dimension $n-1$, so there exists a flag $\left(U_{i}\right)_{i=0}^{n-1}$ in $V / F v$ that is stabilised by $\mathfrak{g}$. By the correspondence theorem, we deduce that each $U_{i}=V_{i+1} / F v$ for some subalgebra $V_{i} \subset V$, with $V_{n}=V$, and each $V_{i}$ stabilised by $\mathfrak{g}$.
Defining $V_{0}=\{0\}$, then $\left(V_{i}\right)_{i=0}^{n}$ is a full flag that is stabilised by $\mathfrak{g}$, as required. $\square$

There exists a similar result for nilpotent Lie algebras:

> [!corollary]
> Let $\mathfrak{g} \subset \mathfrak{g l}(V)$ be a nilpotent Lie algebra, over an [[Fields Construction#^5b9555|algebraically closed]] field $F$ of characteristic $0$. Then, $\mathfrak{g} \cdot V_{i} \subset V_{i-1}$ for all $0 \leq i \leq n$. ^121a6c

## Characterizations of Solvable Lie Algebras

> [!corollary]
> Let $\mathfrak{g}$ be a Lie algebra over an [[Fields Construction#^5b9555|algebraically closed]] field $F$ of characteristic $0$. Then the following are equivalent:
> 1. $\mathfrak{g}$ is solvable.
> 2. There exists a chain of ideals $$\mathfrak{g}=\mathfrak{a}_{1} \supset \mathfrak{a}_{2} \supset \cdots \supset \mathfrak{a}_{n}=(0)$$ such that $\mathfrak{a}_{i} / \mathfrak{a}_{i+1}$ is abelian.
> 3. $[\mathfrak{g}, \mathfrak{g}]$ is [[Ideals, Simple and Semisimple Lie Algebras#^f7e0b3|nilpotent]].
> 4. $\ad(\mathfrak{g}) \subset \operatorname{End}(\mathfrak{g})$ is solvable.
> $\quad$

^58b6d6

*Proof*  $(1)\implies (2)$:
Suppose $\g$ is soluble. Then there exists $n$ such that $D^{n}(\g)=(0)$. Let $\newcommand{\a}{\mathfrak{a}}\a_{j}=D^{j}(\g)$. Then we get a chain of ideals $$\g=\a{1} \supset \a{2} \supset \cdots \supset \a_{n}=(0),$$and each $\a_{i} / \a_{i+1}$ is abelian because by definition $\a_{i+1}=\left[\a_{i}, \a_{i}\right]$ is the commutator.
$(2)\implies(4)$:
Suppose $\g=\a \supset \a_{1} \supset \cdots \supset \a_{n}=(0)$ is a chain of ideals and each $\a_{i} / \a_{i +1}$ is abelian, then $\left[\a_{i}, \a_{i}\right]<\a_{i +1}$. So $\operatorname{ad}_{x}\left(\a_{i}\right)<\a_{i +1}$ for all $x \in \a_{i}$, that is, $\operatorname{ad}\left(\a_{i}\right)<\a_{i+1}$. Since $\ad$ is a representation preserving the Lie brackets, we have $$\left[\operatorname{ad}\left(\a_{i}\right), \operatorname{ad}\left(\a_{i}\right)\right]=\operatorname{ad}\left(\left[\a_{i}, \a_{i}\right]\right) < \operatorname{ad}\left(\a_{i+1}\right)$$Hence by induction using the infusion above, $$D^{k}\left(\operatorname{ad}(\g)\right) < \operatorname{ad}\left(\a_{k+1}\right) \text { for all } n-1 \geq k\geq 1.$$In particular, $D^{n-1}\left(\operatorname{ad}(\g)\right) < \operatorname{ad}\left(\a_{n}\right)=0$, so $\ad(g)$ is solvable.
$(4)\implies (3)$:
Suppose $\ad (g)< \gl (\g)$ is solvable. By [[Engel's Theorem#^3a3f00|Engel's theorem]], to show $[g, g]$ is nilpotent, it suffices to show $\ad_{z}$ is nilpotent for all $z \in[\g, \g]$. Since $[\g, \g]$ is spanned by $[x, y]$ for $x,y \in \g$, it is enough to check $\ad_{[x,y]}$ is nilpotent for all $x,y \in \g$.
Let $V_{0}=\g$. By [[Engel's Theorem#^d489ea|Lie's theorem]], there exists a common eigenvector $v_{0}\in V$ for all endomorphisms in $\ad(\g)$. Suppose $\operatorname{ad}_{x} v_{0}=\lambda v_{0}$, $\operatorname{ad}_{y} v_{0}=\eta v_{0}$, then $$\operatorname{ad}_{[x,y]}(v_{0})=\operatorname{ad}_{x} \operatorname{ad}_{y} v_{0}-\operatorname{ad}_{y} \operatorname{ad}_{x}v_{0}=\lambda\eta v_{0} -\eta\lambda v_{0} =0.$$Therefore $\dim(\ker \operatorname{ad}_{[x,y]}) \geq 1$.
Now let $V_{1}=V_{0} / \ker \ad_{[x,y]}$, which is of dimension strictly less than $\operatorname{dim} V_{0}$. We can invoke Lie's theorem again to get another vector space $V_{2}=V_{1}/\ker\ad_{[x,y]}^{2}$.
Since $V_{0}=\g$ is finite dimensional, repeating the above process will finally terminate at some $V_{m}=(0)$. That is, $\ad(g)$ is the zero map. Thus $\ad_{[x,y]}$ is nilpotent.
$(3)\implies(1)$:
Since $[g, g]$ is nilpotent, $[g, g]$ is soluble, $D^{m}\left([\g, \g]\right)=0$ for some $m \geq 1$. Thus $D^{m+1}(\g)=D^{m}\left([\g, \g]\right)=0$, so $\g$ is solvable. $\square$