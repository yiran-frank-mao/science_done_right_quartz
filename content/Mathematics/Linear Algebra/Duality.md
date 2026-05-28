---
updated: 2025-09-03
---
> [!definition] Dual Space & Covector
> The dual space of a [[Vector Spaces#^f4b63e|vector space]] $V$, denoted as $V^{*}$, is the set of all linear maps from $V$ to $\R$. i.e. $V^{*} = \Hom(V,\R)$. And elements of $V^{*}$ are called covectors or dual vectors. ^6c7627

> [!proposition]
> The dual space is a [[Vector Spaces#^f4b63e|vector space]].

*Proof*  It is clear enough to show that both associativity, commutativity hold. We identify the constant function $v \mapsto 0$ as the additive identity. $\square$

> [!proposition]
> Suppose $v_{1},v_{2},\dots, v_{n}$ is a basis for $V$. Then $\varphi_{1}, \varphi_{2}, \dots , \varphi_{n}$ defined by $$\varphi_{i}(v_{j})=\delta_{ij}$$forms a basis for $V^{*}$.

*Proof*  

> [!corollary]
> For any [[Vector Spaces#^f4b63e|vector space]] $V$, $\dim V = \dim V^{*}$, and further $V^{*} \cong V$.
> 

*Proof*  This a consequence of the above proposition, because $v_{i}\mapsto \varphi_{i}$ is a linear isomorphism. $\square$

**Thrm**  In a inner product space $(V, \langle\cdot, \cdot \rangle)$, for any $\varphi \in V^{*}$, there is a unique $w\in V$ such that $\varphi=\langle w, \cdot \rangle$.
**Proof**  We identify any $\varphi \in V^{*}$ by identifying its values on the basis vectors. Suppose $v_{1},v_{2}, \dots v_{n}$ form a basis for $V$. Then we have 

> [!proposition]
> There is a [[Functoriality and Naturality#^b8c1fd|natural isomorphism]] between $V$ and $(V^{*})^{*}$. That is, the double dual functor is naturally isomorphic to the identity functor on the category of vector spaces.
> 

*Proof*  Define the [[Functoriality and Naturality#^d73db0|natural transformation]] $\newcommand{\id}{\mathrm{id}}\newcommand{\Vect}{\mathbf{Vect}}\eta\colon \id \Rightarrow (-)^{**}$ by $$\eta_{V}(v)(\alpha):=\alpha(v),\quad\text{for all }\alpha\in V^{*}, v\in V, V\in \Vect_{0}$$We shall check the following diagram commutes for any $V,W\in \Vect_{0}$:
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/natural_iso_double_dual.svg" alt="natural_iso_double_dual" style="width:20%;"/>
For any $v\in V$ and $\alpha\in W^{*}$, there holds $$\begin{aligned}(f^{**}\circ \eta_{V})(v)(\alpha)=f^{**}( \eta_{V}v) (\alpha)&= (\eta_{V}v \circ f^{*})(\alpha)=\eta_{V}v(f^{*}\alpha)=\eta_{V}v(\alpha\circ f)=\alpha(fv),\\ (\eta_{W}\circ f)(v)(\alpha)&=\eta_{W}(fv)(\alpha)= \alpha(fv).\end{aligned}$$Thus the diagram commutes, and $\eta$ is a natural transformation. Moreover, $\eta_{V}$ is an isomorphism for any $V\in \Vect_{0}$, thus $\eta$ is a natural isomorphism. $\square$

> [!remark]+ Geometric Interpretation
> Geometrically, this definition uses no bases or coordinates—it is **intrinsically defined** by the structure of vector spaces. That's why "natural" is often equated with **basis-independence** or **coordinate-free** definition in geometry. Concretely, if one identify $f$ as the coordinate, then the above commutative diagram basically means coordinate free.