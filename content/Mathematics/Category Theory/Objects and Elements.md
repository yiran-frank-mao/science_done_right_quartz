## Initial and Terminal

>[!definition] Initial and Terminal Objects
>In any category $\mathbf{C}$, an object $0$ is initial (coterminal) if there is a unique morphism $0\to C$ for all $C\in\obj \mathbf{C}$. An object $1$ is terminal if there is unique morphism $C\to 1$ for all $C\in\obj \mathbf{C}$. ^a7dd74

<u><b>e.g.</b></u>   
- In $\mathbf{Sets}$ the empty set is initial, and any singleton set is terminal. 
- In $\mathbf{Cat}$ the category $\mathbf{0}$ (no objects and no arrows) is initial, and the category $\mathbf{1}$ (one object and identity arrow) is terminal.
- In $\mathbf{Groups}$, the one element group is both initial and terminal. 
- In $\mathbf{P}$, an object is initial iff it is the least element, and terminal iff it is the greatest element.
- For any category $\mathbf{C}$ and any object $X ∈ \obj\mathbf{C}$, the identity arrow $1_X \colon X\to X$ is a terminal object in $\mathbf{C}/X$ and an initial object in $X/\mathbf{C}$.
$\quad$

>[!proposition] 
> Initial and terminal objects are unique up to isomorphism if exists.

*Proof*  Suppose $A,B\in\obj \mathbf{C}$ are initial. Then there's unique $f\colon A\to B$ and $g\colon B\to A$. Hence $g\circ f\circ g = g$, this implies $g\circ f=1_{A}$. Similarly $f\circ g=1_{B}$, thus $A\cong B$. Similarly we have $A\cong B$ if $A,B\in\obj \mathbf{C}$ are terminal.

>[!definition] Zero Object
>If an object is both initial and terminal, it is called a zero object or null object.

>[!definition] Pointed Category
>A pointed category is one with a zero object.

>[!definition] Strict Initial Object
>A strict initial object $I$ is one for which every morphism into $I$ is an isomorphism.

## Generalized Elements

>[!example] Comment
>In a broad, non-technical sense, an “element” is a “component” or “basic part” of a more substantial whole. Ordinary or global elements of a set are simply the points of that set, and hence sufficiently capture this broad notion of “element” in $\mathbf{Sets}$, since by definition sets are no more than collections of points. However, in general, knowing about the points of an object is insufficient to count as knowing its elements (construed broadly).

>[!definition] Global Element
>In any category $\mathbf{C}$ with a terminal object $1$, the morphisms $1\to A$ are called global elements, points or constants of $A$.

>[!definition] 
>**Def**  <i><u>Generalized Element</u></i>
>The morphism $x\colon X\to A\in\mor\mathbf{C}$ is called a generalized element or $X$-valued point of $A$, with stage of definition given by $X$.

<u><b>e.g.</b></u>  In $\mathbf{Sets}$, every element of a set $A$ can be depicted as a morphism $x \colon \{1\} \to A$.

**Prop**  In any category $\mathbf{C}$, and for any morphisms $f,g \colon C \to C^{\prime}$, we always have $f=g$ if and only if for all $x\colon D\to C$, it holds that $fx=gx$.
**Proof**