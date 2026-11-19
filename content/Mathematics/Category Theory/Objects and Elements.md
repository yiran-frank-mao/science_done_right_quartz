## Initial and Terminal

>[!definition] Initial and Terminal Objects
> In a category $\mathsf{C}$, an object $0$ is *initial* or *coterminal* if there is a unique morphism $0\to C$ for all $C\in \mathsf{C}_{0}$. An object $1$ is *terminal* if there is a unique morphism $C\to 1$ for all $C\in \mathsf{C}_{0}$.
> If an object is both initial and terminal, it is called a *zero object* or *null object*. A *pointed category* is one with a zero object, or more generally, isomorphic initial and terminal objects. ^a7dd74

<u><b>e.g.</b></u>   
- In $\mathsf{Set}$ the empty set $\emptyset$ is initial, and any singleton set $\{*\}$ is terminal. 
- In $\mathsf{Cat}$ the category $\mathsf{0}$ (no objects and no arrows) is initial, and the category $\mathsf{1}$ (one object and identity arrow) is terminal.
- In $\mathsf{Group}$, the one element group is both initial and terminal, hence a zero object.
- In $\mathsf{UnitalRing}$, $\Z$ is the initial object, and the trivial ring $\{0\}$ is the terminal object.
- In $\mathbf{P}$, an object is initial iff it is the least element, and terminal iff it is the greatest element.
- For any category $\mathsf{C}$ and any object $X \in \mathsf{C}_{0}$, the identity arrow $1_X \colon X\to X$ is a terminal object in $\mathsf{C}/X$ and an initial object in $X/\mathsf{C}$.
$\quad$

>[!proposition] 
> Initial and terminal objects are unique up to isomorphism if exists.

*Proof*  Suppose $A,B\in\obj \mathbf{C}$ are initial. Then there's unique $f\colon A\to B$ and $g\colon B\to A$. Hence $g\circ f\circ g = g$, this implies $g\circ f=1_{A}$. Similarly $f\circ g=1_{B}$, thus $A\cong B$. Similarly we have $A\cong B$ if $A,B\in\obj \mathbf{C}$ are terminal. $\square$

>[!definition] Strict Initial Object
>A strict initial object $I$ is one for which every morphism into $I$ is an isomorphism.

## Pointed Category

> [!definition] Zero Morphism
> Suppose $\mathsf{C}$ is a pointed category with a zero object $0$ (up to isomorphism). For any objects $A,B\in\mathsf{C}_{0}$, we can define a zero morphism $0_{A,B}\colon A\to B$ as the composition $A\to 0 \to B$. ^concept-119c48c6824e

> [!proposition]
> In a pointed category, composition of a morphism with a zero morphism is always a zero morphism.
> 

*Proof*  The following diagram commutes:
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/composition_with_zero_morphism.svg" style="width:70%;"/>
$\square$

In a pointed category, we can define the notion of kernel and cokernel:

> [!definition] Kernel & Cokernel
> In a category with a zero object, a *kernel* of a morphism $f\colon A \to B$ is a morphism $k\colon K \to A$ that is an [[Mathematics/Category Theory/Equalizers and Coequalizers#^concept-a1eefc7bba8b|equalizer]] of $f$ and $0_{A,B}\colon A\to B$. That is, the following diagram commutes:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/abelian_category_kernel.svg" style="width:40%;"/>
> Dually, *cokernel* of $f$ is a morphism $c\colon B \to C$ that is a [[Mathematics/Category Theory/Equalizers and Coequalizers#^9b92cf|coequalizer]] of $f$ and $0_{A,B}\colon A\to B$.

^74fe30

## Generalized Elements

In a broad, non-technical sense, an “element” is a “component” or “basic part” of a more substantial whole. Ordinary or global elements of a set are simply the points of that set, and hence sufficiently capture this broad notion of “element” in $\mathsf{Set}$, since by definition sets are no more than collections of points. However, in general, knowing about the points of an object is insufficient to count as knowing its elements (construed broadly).

>[!definition] Global Element
>In any category $\mathsf{C}$ with a terminal object $1$, the morphisms $1\to A$ are called *global elements*, *points* or *constants* of $A$.

>[!definition] Generalized Element
>The morphism $x\colon X\to A\in\mor\mathbf{C}$ is called a *generalized element* or $X$-valued point of $A$, with stage of definition given by $X$.

<u><b>e.g.</b></u>  In $\mathsf{Set}$, every element of a set $A$ can be depicted as a morphism $x \colon \{*\} \to A$.

> [!proposition]
> In any category $\mathsf{C}$, and for any morphisms $f,g \colon C \to C^{\prime}$, we always have $f=g$ if and only if for all $x\colon D\to C$, it holds that $fx=gx$.

*Proof*  