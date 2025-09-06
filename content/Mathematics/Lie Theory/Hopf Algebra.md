---
updated: 2025-09-05
---
The notion of Hopf algebra is an abstraction of the properties of

> [!definition] Coalgebra
> A *coalgebra* is just like a unital algebra, but with all the structure maps reversed. Precisely, a coalgebra $A$ is a [[Vector Spaces#^f4b63e|vector space]] over a [[Ring, Field and Integral Domain#^575174|field]] $F$, equipped with a comultiplication $\Delta\colon A\otimes A \to A$ and a counit $e\colon A \to F$, satisfying the following left/right co-unitality laws
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/coalgebra_counitality.svg" alt="coalgebra_counitality" style="width:80%;"/>
> and co-associativity laws
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/coalgebra_coassociativity.svg" alt="coalgebra_coassociativity" style="width:30%;"/>
> where $\otimes$ is the [[Tensors and Tensor Products#^732917|tensor product]], $\lambda$ and $\rho$ are the left and right unit isomorphisms of the monoidal category of vector spaces.

> [!definition] Hopf Algebra
> An $F$-bialgebra  $(A,m,i,\Delta,e)$ with multiplication $m$, comultiplication $\Delta$, unit $i\colon F\to A$ and counit $e\colon A\to F$ is called a *Hopf algebra* if there exists a linear map $s\colon A\to A$, called the *antipode* or *coinverse*, such that $\newcommand{\id}{\mathrm{id}}m\circ (\id \otimes s ) \circ \Delta = m\circ (s\otimes \id ) \circ \Delta$.
> Moreover, if the antipode is an anti-involution, i.e. $s\circ s = \id$, then $A$ is called an *involutive Hopf algebra* or *Hopf \*-algebra*.
> 

> [!remark]+
> Just like an inverse in most cases is unique, the antipode is also unique when it exists.

> [!definition] Group-like & Lie-like Elements
> A *group-like* element in a Hopf algebra $A$ is a non-zero element $x\in A$ such that $\Delta(x)=x\otimes x$. 
> An element $y\in A$ is called *Lie-like* or *primitive* if $\Delta(y)=y\otimes 1 + 1 \otimes y$.

> [!theorem] Milnor–Moore Theorem
> Given a [[Connectedness and Paths#^946cc4|connected]], [[Grading and Filtration#^9b78c3|graded]], cocommutative Hopf algebra $A$ over a field of characteristic $0$, $A$ is isomorphic to the universal enveloping algebra of its Lie algebra of primitive elements.
