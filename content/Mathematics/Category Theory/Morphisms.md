---
created: 2024-02-21
updated: 2024-09-17
---
## Monic and Epic

>[!definition] Monomorphism
>In any category $\mathbf{C}$, an morphism $f\colon A\to B$ is called a monomorphism (monic) if given any $g,h\colon C \to A$, $f\circ g = f\circ h$ implies $g = h$. We write $f \colon A\rightarrowtail B$ if $f$ is a monomorphism. ^4e0259

<u><b>e.g.</b></u>  A [[Relations and Functions#^862dba|function]] $f\colon A\to B$ is monic if and only if it is [[Relations and Functions#^042daf|injective]].

>[!definition] Epimorphisim
>In any category $\mathbf{C}$, an morphism $f\colon A\to B$ is called an epimorphism (epic) if given any $i, j \colon B \to D$, $i\circ f = j\circ f$ implies $i = j$. Write $f \colon A\twoheadrightarrow B$ if $f$ is a monomorphism.

<u><b>e.g.</b></u>  
- A [[Relations and Functions#^862dba|function]] $f\colon A\to B$ is epic if and only if it is [[Relations and Functions#^042daf|surjective]].
- In a fixed poset category $\mathbf{P}$, every morphism $p ≤ q$ is both monic and epic. Because for any $f\colon p\to q\in \mor\mathbf{P}$, we have unique $g\colon r\to p$ and $h\colon q\to s$. Thus monic and epic.
$\quad$

>[!proposition] 
>The composition of monomorphisms is a monomorphism.

*Proof*  Suppose  and $g\colon B\rightarrowtail C$. For all $i,j \colon X \to A$ with $gf\circ i = gf \circ j$, we have $g \circ (fi) = g \circ (fj)$, it follows that $fi=fj$, thus $i=j$, therefore $gf$ is also monic. $\square$

>[!proposition] 
> Given any monoid homomorphisms $f,g \colon (\Z,+,0) \to (M,*,u)$, if the restrictions to $\N$ are equal, $f \big|_{\N}= g \big|_{\N}$, then $f = g$.

*Proof*  Note that $$f(−n)=f((−1) +(−1)+\dots+(−1)) =f(−1) *f(−1) *\dots*f(−1)$$and similarly for $g$. Indeed, $$\begin{aligned}f(-1)&=f(-1)*u\\&=f(-1)*g(0)\\&=f(-1)*g(1-1)\\&=f(-1)*g(1)*g(-1)\\&=f(-1)*f(1)*g(-1)\\&=f(-1+1)*g(-1)\\&=f(0)*g(-1)\\&=u*g(-1)\\&=g(-1)\end{aligned}$$Hence $f = g$. $\square$

<u><b>e.g.</b></u> In the category $\mathbf{Mon}$ of monoids and monoid homomorphisms, there is a monic homomorphism $\N \rightarrowtail \Z$ where $\N$ is the additive monoid $(\N,+,0)$ of natural numbers, and $\Z$ is the additive monoid $(\Z, +, 0)$ of integers. This map, given by the inclusion $\N ⊂ \Z$ of sets, is also epic in $\mathbf{Mon}$.

## Isomorphisms

>[!definition] Isomorphism
>In any category $\mathbf{C}$, an arrow $f \colon A \to B$ is called an isomorphism if there is an arrow $g \colon B \to A$ in $\mathbf{C}$ such that$$f\circ g = 1_{A}\text{ and } g\circ f =1_{B}$$Since inverses are unique, we write $g = f^{-1}$. We say that $A$ is isomorphic to $B$, written $A\cong B$, if there exists an isomorphism between them.  ^8927b3

We shall check the inverse is unique. Suppose $g$ and $h$ are both inverse of $f$. Then we have:$$h = h\circ 1_{A}=h\circ(f\circ g)=(h\circ f)\circ g=1_{B} \circ g = g$$

>[!proposition] 
> Every isomorphism is both monic and epic. The converse is not true in general.

*Proof*  Suppose $f\colon A\to B$ is an isomorphism, then$$f\circ g = f\circ h\implies f^{-1}\circ f\circ g = f^{-1} \circ f\circ h\implies h=g$$Thus $f$ is monic. Similarly, it is also epic.  $\square$

>[!definition] Endomorphism & Automorphism
>An endomorphism is a morphism whose domain equals its codomain.
> An endomorphism that is an isomorphism is called an automorphism.

^9a350e

>[!definition] Groupoid
>A groupoid is a [[Structure of Categories#^2f5c3a|category]] in which every morphism is an isomorphism.

>[!proposition] 
> A group $G$ is a groupoid with one object $G$.

*Proof*  Clearly that singleton $G$ is a category $\mathbf{G}$. For all arrows $f_{x}\colon G\to G$, we have $$f_{x}\circ f_{x^{-1}}= 1_{G}$$$\square$

**Lemma**  Any category $\mathbf{C}$ contains a maximal groupoid, the subcategory containing all of the objects and only those morphisms that are isomorphisms.

## Cayley's Theorem

[[Homomorphisms, Normal Subgroup & Conjugation#^dcfefa|Cayley’s theorem]] in group theory says that any abstract group can be represented as a “concrete” one. The theorem can in fact be generalized to show that any category that is not “too big” can be represented as one that is “concrete”, i.e. a category of sets and functions.

>[!theorem] 
>Every category $\mathbf{C}$ with a set of arrows is isomorphic to one in which the objects are sets and the arrows are functions.

*Proof*  Define the Cayley representation $\bar{\mathbf{C}}$ of $\mathbf{C}$ to be the following concrete category with objects $\bar{A}=\{f\in \mor(\mathbf{C})\mid \cod f = A\}$ for all $A\in \obj (\mathbf{C})$. Morphisms are functions $\bar{g}\colon \bar{C}\to\bar{D}$ for any $g\colon C\to D$ in $\mathbf{C}$, defined by $\bar{g}(f)=g\circ f$. Indeed, they are isomorphic as functor $F\colon \mathbf{C} \to \mathbf{\bar{C}}, A\to\bar{A},g\to\bar{g}$ is invertible. $\square$

## Sections and Retractions

>[!proposition] 
>**Prop**  If an morphism $f\colon A\to B$ has a left inverse $g\colon B\to A$ such that $g\circ f=1_{A}$ then then $f$ must be monic and $g$ epic.
>**Proof**  Suppose $g\circ f=1_{A}$, then $f$ is monic as any $i,j\colon C\to A$ such that $f \circ i=f\circ j$ follows that $g\circ (f \circ i)=g\circ(f\circ j)$, implies that $i=j$. Similarly $g$ is epic.

**Def**  <i><u>Split Monomorphism</u></i>
A split monomorphism (epimorphism) is an arrow with a left (right) inverse. 
<u><b>e.g.</b></u>  In $\mathbf{Set}$, every monomorphism splits except those with domain $\emptyset$.

**Def**  <i><u>Section</u></i> and <i><u>Retraction</u></i>
Given arrows $e \colon X \to A$ and $s \colon A \to X$ such that $es = 1_{A}$, then $s$ is called a section or splitting of $e$, and e is called a retraction of $s$. The object $A$ is called a retract of $X$.

**Prop**  Functors also preserve split epimorphisms and split monomorphisms.
**Proof**  

**Def**  <i><u>Projective Objects</u></i>
An object $P$ is called projective if for any epimorphism $e\colon E\twoheadrightarrow X$ and morphism $f\colon P\to X$ there is some morphism $\bar{f}\colon P\to E$ such that $e\circ \bar{f}=f$:
![projobj|200](https://svgshare.com/i/13n_.svg)

**Prop**  In any category, any retract of a projective object is also projective.
**Proof**  Suppose arrows $e \colon P \to A$ and $s \colon A \to P$ such that $es = 1_{A}$ with projective $P$. For all epimorphism $e\colon E\to X$ and morphism $g\colon A\to X$, let $f=g\circ r\colon P\to X$. Since $P$ is projective, there exists $\bar{f}\colon P\to E$ such that $e\circ \bar{f}=f$. Let $\bar{g}=\bar{f}\circ s\colon A\to E$. Then $$e\circ\bar{g}=e\circ (\bar{f}\circ s)=(e\circ \bar{f})\circ s=f\circ s=g\circ r \circ s = g\circ 1_{A}=g$$Therefore $A$ is also projective.

## Hom-Set

>[!definition] Hom Set
>In any category $\mathbf{C}$, we call the following set of morphisms as hom-set:$$\mathrm{Hom}(A,B)=\{f\in\mor\mathbf{C}\mid f\colon A\to B\}$$And any any morphism $g \colon B \to B^{\prime}$ in $\mathbf{C}$ induces a function $\mathrm{Hom}(A,g)$:$$\mathrm{Hom}(A,g)\colon\mathrm{Hom}(A,B)\to\mathrm{Hom}(A,B^{\prime}),\quad f\mapsto g\circ f$$

**Def**  <i><u>Representable Functor</u></i>
The (covariant) representable functor of $A\in\obj \mathbf{C}$ is$$\mathrm{Hom}(A,\cdot)\colon\mathbf{C}\to\mathbf{Set}$$It is indeed a functor as $\mathrm{Hom}(A,1_{X})=1_{\mathrm{Hom}(A,X)}$ and $\mathrm{Hom}(A,g\circ f)=\mathrm{Hom}(A,g)\circ\mathrm{Hom}(A,f)$. ^6a1c64

>[!proposition] 
>**Prop**  A diagram of the form with object $P$:
>![|300](https://svgshare.com/i/13oy.svg)
>is a product for $A$ and $B$ iff for every object $X$, the canonical function $$\begin{aligned}\pi_{X}\colon\mathrm{Hom}(X,P)\to\mathrm{Hom}(X,A)\times\mathrm{Hom}(X,B),\quad x\mapsto(p_{1}\circ x, p_{2}\circ x) \\\pi_{X} =(\mathrm{Hom}(X,p_{1}),\mathrm{Hom}(X,p_{2}))\end{aligned}$$is an isomorphism.
>**Proof**  $P=A\times B$ by definition is equivalent to say that for all $(x_1,x_2)\in\mathrm{Hom}(X,A)\times\mathrm{Hom}(X,B)$, there is unique $u\in\mathrm{Hom}(X,P)$ such that $(p_{1},p_{2}) \circ u = (x_{1},x_{2})$, that is $\pi_{X}$ is bijective. ^69c772

>[!definition] Preserve Binary Products
>Let $\mathbf{C}$, $\mathbf{D}$ be categories with binary products. A functor $F \colon \mathbf{C} \to \mathbf{D}$ is said to preserve binary products if
>![presbprod|800](https://i.imgur.com/04Xt07Y.png)That is $\langle F(p_{1}),F(p_{2})\rangle\colon F(A\times B)\to F(A)\times F(B)$ is an isomorphism.

<u><b>e.g.</b></u>  The forgetful functor $U \colon\mathbf{Mon} \to \mathbf{Set}$ preserves binary products.

**Corollary**  For any object $X$ in a category $\mathbf{C}$ with products, the (covariant) representable functor $\mathrm{Hom}(X, \cdot) \colon C \to \mathbf{Set}$ preserves products.
**Proof**  For any $A,B ∈ \mathbf{C}$, the [[Objects and Elements#^69c772|proposition]] says that there is a canonical isomorphism $\pi_{X}$:$$\mathrm{Hom}(X,A\times B)\cong\mathrm{Hom}(X,A)\times\mathrm{Hom}(X,B)$$

**Def**  <i><u>Discrete Category</u></i>
A discrete category is a category $\mathbf{C}$ whose only morphisms are the identity morphisms: $$\Hom(X,X)=\{1_{X}\},\quad \Hom(X,Y)=\emptyset$$for all $X\neq Y$ be $\mathbf{C}$-objects.