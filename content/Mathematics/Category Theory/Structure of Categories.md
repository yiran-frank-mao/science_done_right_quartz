>[!definition] Category
> A *category* is an algebraic structure consisting of 
>- *Objects*: $A,B,C\dots$
>- *Morphisms (arrows)*: $f,g,h,\dots$
>
>such that 
>- Each morphism has specified *domain* and *codomain* objects: $f \colon X \to Y$ signifies that $f$ is a morphism with domain $X$ and codomain $Y$.
>- Each object has a designated identity morphism $1_{X} \colon X \to X$.
>- For any pair of morphisms $f$, $g$ with the codomain of $f$ equal to the domain of $g$, there exists a specified composite morphism $g \circ f$ whose domain is equal to the domain of $f$ and whose codomain is equal to the codomain of $g$.
>
>The composition law is subject to the following axioms:
>- Unital with identity morphisms: For any $f \colon X \to Y$, the composites $1_{Y}\circ f$ and $f\circ 1_{X}$ are both equal to $f$.
>- Associativity: $h\circ(g\circ f)=(h\circ g) \circ f$.
>
> We shall denote the collection of objects as $\newcommand{\obj}{\operatorname{obj}}\obj \mathsf{C}$ or $\mathsf{C}_{0}$, and the collection of morphisms as $\newcommand{\mor}{\operatorname{mor}} \mor\mathsf{C}$ or $\mathsf{C}_{1}$. ^2f5c3a

<u><b>e.g.</b></u> 
- The [[Number Systems#^5fea5c|real numbers]] $\R$ and continuous functions $\R \to \R$ is a category of a single object. More generally, [[Topological Spaces#^65c94a|topological spaces]] and [[Continuous Functions on Topological Spaces#^33ee5a|continuous mappings]] form a category $\mathsf{Top}$.
- [[Manifolds, Atlases and Smooth Structures#^6ef2ef|Smooth manifolds]] and [[Smooth Functions and Maps#^4fb5f6|smooth mappings]] form a category $\mathsf{Man}$.
- [[Groups, Order and Subgroups#^6e0960|Groups]] and [[Homomorphisms, Normal Subgroup & Conjugation#^homo|group homomorphisms]] form a category $\mathsf{Group}$.
- Any set $S$ can be regarded as a category with objects being the elements of $S$ and only identity morphisms. This is usually called a *discrete category*. In particular, the empty set $\emptyset$ gives the empty category, and any singleton set $\{*\}$ gives a category $\mathsf{1}$ with one object and one morphism.
$\quad$ ^008eea

> [!remark]- Why $\mathsf{C}_{0}$ and $\mathsf{C}_{1}$?
> There is a reason why objects are denoted $\mathsf{C}_{0}$ and morphisms are denoted $\mathsf{C}_{1}$. We will have a unified way to treat objects and morphisms where they are called *cells*. Specifically, objects are $0$-cells, and morphisms are $1$-cells, and "potential" morphisms between morphisms will be called  as $2$-cells. This will be discussed in detail in [[Category Theory#^f2a96d|higher categories]].
> 

>[!definition] Commutative Diagram
>A commutative diagram is a diagram such that all directed paths in the diagram with the same start and endpoints lead to the same result. A commutative diagram often consists of three parts:
>- objects (also known as vertices)
>- morphisms (also known as arrows or edges)
>- paths or composites
>$\quad$

>[!definition] Subcategory
>A subcategory $\mathsf{D}$ of a category $\mathsf{C}$ is defined by restricting to a subcollection of objects and subcollection of morphisms subject to the requirements that the subcategory $\mathsf{D}$ contains the domain and codomain of any morphism in $\mathsf{D}$, the identity morphism of any object in $\mathsf{D}$, and the composite of any composable pair of morphisms in $\mathsf{D}$.

## Foundations, Large and Small

>[!definition] Small and Large
>A category $\mathsf{C}$ is called small if both the collection $\obj(\mathsf{C})$ of objects of $\mathsf{C}$ and the collection $\mor(\mathsf{C})$ of arrows of $\mathsf{C}$ are sets. Otherwise, $\mathsf{C}$ is called large. ^20e64e

<u><b>e.g.</b></u>  All finite categories are clearly small, the category $\mathsf{Group}$ of groups, and the category $\mathsf{Set}$ of sets are all large. 

>[!definition] Locally-Small
>A category $\mathsf{C}$ is called *locally small* if for any objects $X, Y$ in $\mathsf{C}$, the collection $\newcommand{\Hom}{\operatorname{Hom}} \Hom_\mathsf{C} (X,Y)=\{f\in\mor(\mathsf{C})\mid f\colon X\to Y \}$ is a set (called a hom-set).
> In other words, it is [[Monoidal Categories#^5e1a68|$\mathsf{Set}$-enriched]]. ^d0fa66

<u><b>e.g.</b></u>  Many of the large categories we want to consider are in fact locally small. $\mathsf{Set}$ is locally small since $\text{Hom}_\mathsf{Set} (X,Y)=Y^{X}$, the set of all functions from $X$ to $Y$. Similarly, $\mathsf{Pos}$, $\mathsf{Top}$, and $\mathsf{Group}$ are all locally small.

>[!proposition] 
> Any small category is locally small.