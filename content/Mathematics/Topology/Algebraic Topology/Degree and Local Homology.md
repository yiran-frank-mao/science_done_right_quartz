---
created: 2025-10-02
updated: 2025-10-02
tags:
  - algebraic_topology
  - homology
completed: true
---
## Invariance of Domain

> [!theorem] Invariance of Domain
> Suppose $U \subset \mathbb{R}^{m}$ and $V \subset \mathbb{R}^{n}$ are nonempty open sets and are homeomorphic. Then $m=n$.

*Proof*  Suppose $f: U \to V$ is a homeomorphism. Pick any $x \in U$ and let $y = f(x)$. This homeomorphism induces a map of pairs $f: (U, U \setminus \{x\}) \to (V, V \setminus \{y\})$. This map in turn induces an isomorphism on the relative homology groups: $$f_*: H_k(U, U \setminus \{x\}) \xrightarrow{\cong} H_k(V, V \setminus \{y\})$$By the [[Exact Sequences and Relative Homology#^0c7a1e|Excision Theorem]], we can excise the complement of a neighborhood around $x$ (and $y$) to get: $$\begin{aligned}H_{k}(U, U \setminus \{x\}) \cong H_{k}(\mathbb{R}^{m}, \mathbb{R}^{m} \setminus \{x\})\\ H_k(V, V \setminus \{y\}) \cong H_k(\mathbb{R}^n, \mathbb{R}^n \setminus \{y\})\end{aligned}$$The long exact sequence for the pair $(\mathbb{R}^m, \mathbb{R}^m \setminus \{x\})$ and the fact that $\mathbb{R}^m$ is contractible shows that $H_k(\mathbb{R}^m, \mathbb{R}^m \setminus \{x\}) \cong \tilde{H}_{k-1}(S^{m-1})$. Thus, we have:$$\begin{aligned}H_k(U, U \setminus \{x\}) \cong \tilde{H}_{k-1}(S^{m-1}) \cong \begin{cases} \mathbb{Z} & k=m \\ 0 & k \neq m \end{cases} \\ H_k(V, V \setminus \{y\}) \cong \tilde{H}_{k-1}(S^{n-1}) \cong \begin{cases} \mathbb{Z} & k=n \\ 0 & k \neq n \end{cases}\end{aligned}$$Since these groups are isomorphic for all $k$, we must have $m=n$. $\square$

## The Degree of a Map

> [!definition] Degree
> The *degree* of a map $f\colon S^{n} \to S^{n}$ is the integer $d$ such that the induced map on the $n$-th homology group, $f_{*}\colon \tilde{H}_n(S^n) \to \tilde{H}_n(S^n)$, is multiplication by $d\in\Z$.
> 

> [!proposition] Properties of the Degree
> Let $f, g\colon S^{n} \to S^{n}$ be continuous maps.
> 1.  $\newcommand{\id}{\mathrm{id}}\deg(\id) = 1$.
> 2.  If $f$ is not surjective, then $\deg(f)=0$.
> 3.  If $f \simeq g$ (i.e., $f$ is homotopic to $g$), then $\deg(f) = \deg(g)$.
> 4.  $\deg(g \circ f) = \deg(g) \cdot \deg(f)$.
> 5.  If $r\colon S^n \to S^n$ is a reflection across a hyperplane through the origin, then $\deg(r) = -1$.
> 6.  The degree of the antipodal map, $-\id\colon x \mapsto -x$, is $\deg(-\id) = (-1)^{n+1}$.
> 7.  If $f$ has no fixed points, then $\deg(f) = (-1)^{n+1}$.
> $\quad$

*Proof Sketch*
* **(5)** Think of $S^n$ as two $n$-simplices, a northern hemisphere $\Delta^n_N$ and a southern hemisphere $\Delta^n_S$, glued along their common boundary (the equator). A generator for $H_n(S^n)$ is represented by the cycle $\Delta^n_N - \Delta^n_S$. A reflection $r$ across the equator maps $\Delta^n_N$ to $\Delta^n_S$ and vice versa. So, $r_*([\Delta^n_N - \Delta^n_S]) = [\Delta^n_S - \Delta^n_N] = -[\Delta^n_N - \Delta^n_S]$. Thus, $\deg(r)=-1$.
* **(6)** The antipodal map can be written as a composition of $n+1$ reflections. For example, in $\mathbb{R}^{n+1}$, $(x_0, \dots, x_n) \mapsto (-x_0, \dots, -x_n)$ is the composition of $r_i(x_0, \dots, x_i, \dots, x_n) = (x_0, \dots, -x_i, \dots, x_n)$ for $i=0, \dots, n$. Using properties (4) and (5), the result follows.
* **(7)** If $f(x) \neq x$ for all $x$, then the line segment from $f(x)$ to $-x$ does not pass through the origin. This allows us to construct a homotopy from $f$ to the antipodal map:
    $$f_t(x) = \frac{(1-t)f(x) - tx}{|(1-t)f(x) - tx|}$$
    So $f \simeq -\id$. By properties (3) and (6), $\deg(f) = \deg(-\id) = (-1)^{n+1}$. 

$\square$

## Applications

> [!theorem] Hairy Ball Theorem
> $S^n$ has a nowhere-vanishing continuous [[Vector Fields and Lie Algebra#^a87ff1|vector field]] if and only if $n$ is odd.

*Proof*  ($\Rightarrow$) Suppose $v\colon S^{n}\to \R^{n+1}$ is a nowhere-vanishing vector field on $S^n$. We can normalize it so $|v(x)|=1$ for all $x$. Since $v(x)$ is a vector in the tangent space at $x$, it is orthogonal to $x$. Consider the homotopy: $$f_t(x) = (\cos(\pi t))x + (\sin(\pi t))v(x)$$For $t=0$, $f_0(x) = x$, which is the identity map. For $t=1$, $f_1(x) = -x$, which is the antipodal map.
This shows that $\id \simeq -\id$. By the properties of degree, this implies $\deg(\id) = \deg(-\id)$. $$1 = (-1)^{n+1}$$This equality holds only if $n+1$ is even, which means $n$ must be odd.
($\Leftarrow$) If $n$ is odd, say $n=2k-1$, we can view $S^{2k-1}$ as the unit sphere in $\mathbb{C}^k$. For $x = (z_1, \dots, z_k) \in S^{2k-1}$, we can define a vector field $v(x) = ix = (iz_1, \dots, iz_k)$. This vector field is nowhere zero and is tangent to the sphere. $\square$

> [!theorem] Free Group Actions on Spheres
> If $n$ is even, the only nontrivial group (up to isomorphism) that can act freely on $S^n$ is $\mathbb{Z}/2\mathbb{Z}$.

*Proof*  Let $G$ be a group acting freely on $S^n$. This means for any $g \in G$ with $g \neq e$, the map $\phi_g\colon S^n \to S^n$ given by $\phi_g(x) = g \cdot x$ has no fixed points.
Consider the map $\lambda: G \to \{\pm 1\}$ given by $\lambda(g) = \deg(\phi_g)$. This is a group homomorphism.
Since the action is free, for any $g \neq e$, $\phi_g$ has no fixed points. By the properties of degree, this implies that $\deg(\phi_g) = (-1)^{n+1}$.
If $n$ is even, then $n+1$ is odd, so $\deg(\phi_g) = -1$ for all $g \neq e$.
The kernel of $\lambda$ is $\{g \in G \mid \lambda(g) = 1\}$. Since $\lambda(g) = -1$ for all $g \neq e$, the kernel is just $\{e\}$.
This means $\lambda$ is an injective group homomorphism. By the first isomorphism theorem, $G$ is isomorphic to a subgroup of $\{\pm 1\}$. The only nontrivial subgroup is $\{\pm 1\}$ itself, which is isomorphic to $\mathbb{Z}/2\mathbb{Z}$. $\square$

## Local Homology

> [!definition] Local Homology
> The *local homology* of a space $X$ at a point $x \in X$ is defined as:
> $$H_n(X|x) := H_n(X, X \setminus \{x\})$$
> By the Excision Theorem, for any open neighborhood $U$ of $x$, we have an isomorphism:
> $$H_n(U|x) \cong H_n(X|x)$$

<u><b>e.g.</b></u> The local homology of $\mathbb{R}^n$ at the origin is: $$H_{k}(\mathbb{R}^n|\vec{0}) \cong \begin{cases} \Z & \text{if } k=n \\ 0 & \text{if } k \neq n \end{cases}$$


### Induced Maps on Local Homology
**Question**: Suppose we have a map $f: X \to Y$ with $f(x) = y$. When does this induce a map on local homology groups, $f_*: H_n(X|x) \to H_n(Y|y)$?

**Answer**: For $f$ to be a map of pairs $(X, X \setminus \{x\}) \to (Y, Y \setminus \{y\})$, we need $f(X \setminus \{x\}) \subseteq Y \setminus \{y\}$. This is equivalent to the condition that $f^{-1}(y) = \{x\}$.

However, since local homology only depends on arbitrarily small neighborhoods, a less strict condition is sufficient. We only need there to exist some open neighborhood $U$ of $x$ such that $f$ maps $(U, U \setminus \{x\})$ to $(Y, Y \setminus \{y\})$. This requires $f(U \setminus \{x\}) \subseteq Y \setminus \{y\}$, which is equivalent to:
$$f^{-1}(y) \cap U = \{x\}$$
This means that $x$ is the *only* preimage of $y$ within the neighborhood $U$.

## The Local Degree

> [!definition] Local Degree
> Let $f\colon S^{n} \to S^{n}$ be a map. Suppose for a point $y \in S^{n}$, its preimage $f^{-1}(y)$ is a finite set of points $\{x_1, \dots, x_m\}$. For each $x_i$, we can find a small enough neighborhood $U_i$ such that $f^{-1}(y) \cap U_i = \{x_i\}$. This allows $f$ to induce a map on local homology:
> $$f_{*}\colon H_n(S^n|x_i) \cong \Z \to H_n(S^n|y) \cong \Z$$
> This map is multiplication by an integer called the *local degree* of $f$ at $x_i$, denoted $\deg(f|x_i)$.

> [!remark]
> If $f$ is a **local homeomorphism** at $x$, then the local degree $\deg(f|x)$ is either $+1$ or $-1$.
> - $\deg(f|x) = +1$ if $f$ is **orientation-preserving** at $x$.
> - $\deg(f|x) = -1$ if $f$ is **orientation-reversing** at $x$.

> [!theorem] Degree Formula
> Suppose $f: S^n \to S^n$ is a map such that for some $y \in S^n$, the preimage is a finite set $f^{-1}(y) = \{x_1, \dots, x_m\}$. Then the (global) degree of $f$ is the sum of the local degrees at these points:
> $$\deg(f) = \sum_{i=1}^m \deg(f|x_i).$$

*Proof*  Choose disjoint open neighborhoods $U_i$ of each $x_i$. Consider the following commutative diagram which involves maps from the long exact sequences of pairs: $$\begin{CD}H_n(S^n) @>j>> H_n(S^n, S^n \setminus \{x_1..x_m\}) \\@V{f_*}VV @VV{f_*}V \\H_n(S^n) @>j'>> H_n(S^n, S^n \setminus \{y\})\end{CD}$$By excision, $H_n(S^n, S^n \setminus \{x_1..x_m\}) \cong \bigoplus_i H_n(U_i, U_i \setminus \{x_i\})$. Let $e \in H_n(S^n)$ be a generator. The map $j$ sends $e \mapsto \sum e_i$, where $e_i$ is the corresponding generator for $H_n(S^n|x_i)$.
Following the diagram:
-   Going down then right: $j'(f_*(e)) = j'(\deg(f)e) = \deg(f) e_y$, where $e_y$ is the generator for $H_n(S^n|y)$.
-   Going right then down: $f_*(j(e)) = f_*(\sum e_i) = \sum f_*(e_i) = \sum (\deg(f|x_i) e_y)$.

By commutativity, the results must be equal. Thus, $\deg(f) = \sum_i \deg(f|x_i)$. $\square$

<u><b>e.g.</b></u> Constructing a map of any integer degree.
For any $n \ge 1$ and $d \in \Z$, we can construct a map $f: S^n \to S^n$ with $\deg(f)=d$.
Case $d \ge 0$:
    1.  Choose $d$ disjoint open disks $U_1, \dots, U_d$ in $S^n$.
    2.  Consider the quotient map that collapses the complement $S^n \setminus \bigcup U_i$ to a single point. This gives a map $S^n \to \bigvee_d S^n$.
    3.  Follow this with the "folding" map $\bigvee_d S^n \to S^n$ which is the identity on each sphere in the wedge.
    4.  Let the resulting map be $f$. If we choose a point $y$ (not the collapse point), its preimage will be $\{x_1, \dots, x_d\}$ where each $x_i \in U_i$.
    5.  At each $x_i$, the map is a local homeomorphism that preserves orientation, so $\deg(f|x_i) = 1$.
    6.  By the theorem, $\deg(f) = \sum_{i=1}^d 1 = d$. A constant map gives degree 0.

Case $d < 0$: First, construct a map $g$ of degree $|d|$ as above. Then compose it with a reflection $r: S^n \to S^n$, which has degree $-1$. The map $f = r \circ g$ will have $\deg(f) = \deg(r) \deg(g) = (-1)|d| = d$.

> [!proposition] Degree of a Suspension
> For any map $f: S^n \to S^n$, its suspension $Sf: S^{n+1} \to S^{n+1}$ has the same degree.
> $$\deg(Sf) = \deg(f).$$

*Proof*  The proof follows from the [[Naturality#^d73db0|naturality]] of the suspension isomorphism $\tilde{H}_{k+1}(SX) \cong \tilde{H}_k(X)$. The following diagram commutes: $$\begin{CD}\tilde{H}_{n+1}(S^{n+1}) @>{\cong}>> \tilde{H}_n(S^n) \\@V{(Sf)_*}VV @VV{f_*}V \\\tilde{H}_{n+1}(S^{n+1}) @>{\cong}>> \tilde{H}_n(S^n)\end{CD}$$Since the horizontal maps are isomorphisms and $f_*$ is multiplication by $\deg(f)$, it follows that $(Sf)_*$ must be multiplication by the same integer. $\square$

## The Splitting Lemma

> [!lemma] The Splitting Lemma
> For a short exact sequence of abelian groups (or modules):
> $$0 \rightarrow A \xrightarrow{i} B \xrightarrow{j} C \rightarrow 0$$
> The following are equivalent:
> 1. There exists a homomorphism $p\colon B \to A$ such that $\newcommand{\id}{\mathrm{id}}p \circ i = \id_A$. (This map $p$ is called a *retraction*).
> 2. There exists a homomorphism $s\colon C \to B$ such that $j \circ s = \id_C$. (This map $s$ is called a *section* or a *splitting*).
> 3. There is an isomorphism $\phi\colon B \to A \oplus C$ such that $B \cong A \oplus C$.
>
> If any of these conditions hold, the short exact sequence is said to *split*.

*Proof*  We will show that (1) and (2) are equivalent, and so are all three conditions. 
$(1)\implies (2)$: Given a retraction $p\colon B\to A$, notice that $\newcommand{\im}{\operatorname{im}}C\cong B/\im i$, we can define $s\colon B/\im i \to B$ by $b +\im i \mapsto b-i(p(b))$. This is well-defined because if $b + \im i = b' + \im i$, then $b - b' \in \im i$, so $b-b'=i(a)$ for some $a\in A$, therefore, $b-b'-i(p(b-b'))=b-b'-(b-b')=0$. Also, $j(s(b+\im i))=j(b-i(p(b)))=j(b)=b+\im i$, so $j\circ s=\id_{C}$.
$(2)\implies (1)$: Given a section $s\colon C\to B$, since $i$ is injective, $\im i\cong A$, define $p\colon B\to \im i$ by $p(b)=b - s(j(b))$. To show this is well-defined, we need to show $b - s(j(b))\in \im i$. By exactness, $\im i=\ker j$, and $j(b-sj(b))=j(b)-jsj(b)=j(b)-j(b)=0$. Also, $p(i(a))=i(a) - s(j(i(a)))=i(a)$, so $p\circ i=\id_{A}$. $\square$