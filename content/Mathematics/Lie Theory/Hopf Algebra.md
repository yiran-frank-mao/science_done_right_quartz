---
updated: 2025-09-05
---
## Coalgebras, Bialgebras and Hopf Algebras

> [!definition] Coalgebra
> A *coalgebra* is just like a [[Noncommutative Rings#^2c3d07|unital algebra]], but with all the structure maps reversed. Precisely, a coalgebra $A$ is a [[Vector Spaces#^f4b63e|vector space]] over a [[Ring, Field and Integral Domain#^575174|field]] $F$, equipped with a comultiplication $\Delta\colon A\to A\otimes A$ and a counit $e\colon A \to F$, satisfying the following left/right co-unitality laws
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/coalgebra_counitality.svg" alt="coalgebra_counitality" style="width:80%;"/>
> and co-associativity laws
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/coalgebra_coassociativity.svg" alt="https://q.uiver.app/#q=WzAsNCxbMCwwLCJBIl0sWzIsMCwiQVxcb3RpbWVzIEEiXSxbMCwxLCJBXFxvdGltZXMgQSJdLFsyLDEsIkFcXG90aW1lcyBBXFxvdGltZXMgQSJdLFswLDEsIlxcRGVsdGEiXSxbMCwyLCJcXERlbHRhIiwyXSxbMiwzLCJcXG1hdGhybXtpZH1cXG90aW1lcyBcXERlbHRhIl0sWzEsMywiXFxEZWx0YVxcb3RpbWVzIFxcbWF0aHJte2lkfSJdXQ==" style="width:30%;"/>
> where $\otimes$ is the [[Tensors and Tensor Products#^732917|tensor product]], $\lambda$ and $\rho$ are the left and right unit isomorphisms of the monoidal category of vector spaces.

> [!definition] Hopf Algebra
> An $F$-bialgebra  $(A,m,i,\Delta,e)$ with multiplication $m$, comultiplication $\Delta$, unit $i\colon F\to A$ and counit $e\colon A\to F$ is called a *Hopf algebra* if there exists a linear map $s\colon A\to A$, called the *antipode* or *coinverse*, such that $\newcommand{\id}{\mathrm{id}}m\circ (\id \otimes s ) \circ \Delta = m\circ (s\otimes \id ) \circ \Delta$.
> Moreover, if the antipode is an anti-involution, i.e. $s\circ s = \id$, then $A$ is called an *involutive Hopf algebra* or *Hopf $\ast$-algebra*. ^ad39af

<u><b>e.g.</b></u>  
- The [[Noncommutative Rings#^a15722|group algebra]] $F[G]$ of a [[Groups, Order and Subgroups#^6e0960|group]] $G$ is a Hopf algebra with comultiplication defined by $\Delta(g) = g\otimes g$ for all $g\in G$, counit defined by $e(g)=1$ for all $g\in G$, and antipode defined by $s(g)=g^{-1}$ for all $g\in G$.
- Any [[Universal Enveloping Algebra#^3bf4c7|universal enveloping algebra]] of a [[Lie Algebra#^5007ba|Lie algebra]] is a Hopf algebra, as shown [[Universal Enveloping Algebra#^966336|here]].
$\quad$

> [!remark]+
> Just like an inverse in most cases is unique, the antipode is also unique when it exists.

> [!definition] Hopf Algebra Morphism
> A Hopf algebra morphism between two Hopf algebras $(A,m_{A},i_{A},\Delta_{A},e_{A},s_{A})$ and $(B,m_{B},i_{B},\Delta_{B},e_{B},s_{B})$ is a linear map $f\colon A\to B$ that is both an algebra homomorphism and a coalgebra homomorphism, and is compatible with the antipodes, i.e., $f\circ s_{A} = s_{B}\circ f$.
> 

## The Theorem of Milnor—Moore

> [!definition] Group-like & Lie-like Elements
> A *group-like* element in a Hopf algebra $A$ is a non-zero element $x\in A$ such that $\Delta(x)=x\otimes x$. 
> An element $y\in A$ is called *Lie-like* or *primitive* if $\Delta(y)=y\otimes 1 + 1 \otimes y$. ^ced771

> [!proposition]
> The set of all Lie-like elements in a Hopf algebra $A$, denoted $P(A)$, forms a Lie algebra under the commutator bracket $[x,y]=xy - yx$.
> 

*Proof*  First, we verify that $P(A)$ is a vector space. For any $x,y\in P(A)$ and $\lambda\in F$, we have $$\Delta(x+\lambda y) = \Delta(x) + \lambda \Delta(y) = (x\otimes 1 + 1 \otimes x) + \lambda(y\otimes 1 + 1 \otimes y) = (x+\lambda y)\otimes 1 + 1 \otimes (x+\lambda y),$$so $x+\lambda y\in P(A)$. Next, we check that the commutator bracket is closed in $P(A)$. For any $x,y\in P(A)$, we have $$\begin{aligned} \Delta([x,y]) &= \Delta(xy - yx) \\ &= \Delta(x)\Delta(y) - \Delta(y)\Delta(x) \\ &= (x\otimes 1 + 1 \otimes x)(y\otimes 1 + 1 \otimes y) - (y\otimes 1 + 1 \otimes y)(x\otimes 1 + 1 \otimes x) \\ &= xy \otimes 1 + x \otimes y + y \otimes x + 1 \otimes xy - (yx \otimes 1 + y \otimes x + x \otimes y + 1 \otimes yx) \\ &= (xy - yx) \otimes 1 + 1 \otimes (xy - yx) \\ &= [x,y] \otimes 1 + 1 \otimes [x,y], \end{aligned}$$so $[x,y]\in P(A)$. Finally, the commutator bracket satisfies bilinearity, antisymmetry, and the Jacobi identity, making $P(A)$ a Lie algebra. $\square$

We've already showed in [[Universal Enveloping Algebra#^966336|here]] that the universal enveloping algebra of a Lie algebra is a Hopf algebra. The Milnor–Moore theorem states that, under certain conditions, the converse is also true:

> [!theorem] Milnor–Moore Theorem
> Given a [[Grading and Filtration#^9b78c3|graded]], cocommutative Hopf algebra $A=\bigoplus_{n=0}^{\infty} A_{n}$ that is connected over a [[Ring, Field and Integral Domain#^575174|field]] of [[Fields and Field Extensions#^2bfbd8|characteristic]] $0$ (i.e., $A_{0}$ is the ground field), suppose $\dim A_{n}<\infty$ for all $n$, then $A$ is isomorphic to the [[Universal Enveloping Algebra#^3bf4c7|universal enveloping algebra]] of its Lie algebra of [[Hopf Algebra#^ced771|Lie-like]] elements.

Although it is beyond the scope of this article to provide a full proof, we outline the ideas for a much weaker version of the theorem, where we assume $A$ is generated by its Lie-like elements (then $A$ is automatically connected).
Let $i\colon P(A)\hookrightarrow A$ be the inclusion. By the universal property of universal enveloping algebra, $i$ extends uniquely to a Hopf map $\tilde{i}\colon U(P(A))\to A$. Since $A$ is generated by its Lie-like elements, then any element $x\in A$ can be written as a linear combination of monomials in $P(A)$, so $\tilde{i}$ is surjective by the [[Universal Enveloping Algebra#^28e157|Poincaré–Birkhoff–Witt Theorem]]. To show that $\tilde{i}$ is an isomorphism, it suffices to prove that it is injective.
For this, we use the filtration structure. Recall that $U(P(A))$ has a standard filtration $$U_{0}\subseteq U_{1}\subseteq U_{2} \subseteq \cdots$$where $U_{n}$ is the subspace spanned by monomials of length at most $n$ in $P(A)$. Let $K=\ker \tilde{i}$ with induced filtration $K_{n}=K\cap U_{n}$. Assume $K\neq\{0\}$, then there exists a smallest $m$ such that $K_{m}\neq \{0\}$. Take any non-zero $x\in K_{m}$, then its image in the associated graded algebra $\mathrm{gr}(U(P(A)))$ is non-zero. Pick a nonzero element $\xi\in K_{m}$. Observe that $m$ cannot be zero or one. $U_{0}$ is the ground field $F$, $\tilde{i}$ acts as identity on it; $U_{1}=F\oplus P(A)$, and $\tilde{i}$ restricted to $P(A)$ is just the inclusion. So $m\geq 2$.
Let $\eta=\Delta(\xi)-(\xi\otimes 1 + 1\otimes \xi)$. Suppose $\xi=x_{1}\dots x_{m}$, then $$\Delta(\xi)=\Delta(x_{1})\cdots \Delta(x_{m})=(x_{1}\otimes 1+1\otimes x_{1})\cdots(x_{m}\otimes 1 + 1\otimes x_{m})\in \bigoplus_{l+r=m} U_{l}\otimes U_{r},$$so $\xi\otimes 1$ is the unique term in $U_{m}\otimes U_{0}$ coming from picking the first part of every $(x_{j}\otimes 1+1\otimes x_{j})$. Similarly, $1\otimes \xi$ is also the unique term in $U_{0}\otimes U_{m}$. Therefore, $\eta\in \bigoplus_{l+r<m} U_{l}\otimes U_{r}\subset U_{m-1}\otimes U_{m-1}$. 
Since $\tilde{i}$ is a Hopf map, we have $0=\Delta(\tilde{i}(\xi))=\tilde{i}\otimes \tilde{i}(\Delta(\xi))=\tilde{i}\otimes \tilde{i}(\eta)$. So $\eta\in \ker \tilde{i}\otimes \tilde{i}=(K\otimes U(P(A)) + U(P(A)) \otimes K )$. 
Combing the above inclusions, we get $$\eta\in (K\cap U_{m-1})\otimes U_{m-1} + U_{m-1}\otimes (K\cap U_{m-1})=K_{m-1}\otimes U_{m-1} + U_{m-1}\otimes K_{m-1}=\{0\},$$where the last equality follows from the minimality of $m$. Thus, $\Delta(\xi)=\xi\otimes 1 + 1\otimes \xi$, i.e., $\xi$ is Lie-like, $\xi\in P(U(P(A)))=P(A)$, which means $\xi$ has degree $1$, contradicting $m\geq 2$. Therefore, $K=\{0\}$, and $\tilde{i}$ is an isomorphism. $\square$