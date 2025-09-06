>[!definition] Category
>A category is an algebraic structure consisting of 
>- Objects: $A,B,C\dots$
>- Morphisms (arrows): $f,g,h,\dots$
>
>such that 
>- Each morphism has specified domain and codomain objects: $f \colon X \to Y$ signifies that $f$ is a morphism with domain $X$ and codomain $Y$.
>- Each object has a designated identity morphism $1_{X} \colon X \to X$.
>- For any pair of morphisms $f$, $g$ with the codomain of $f$ equal to the domain of $g$, there exists a specified composite morphism $g \circ f$ whose domain is equal to the domain of $f$ and whose codomain is equal to the codomain of $g$.
>The composition law is subject to the following axioms:
>- Unital with identity morphisms: For any $f \colon X \to Y$, the composites $1_{Y}\circ f$ and $f\circ 1_{X}$ are both equal to $f$.
>- Associativity: $h\circ(g\circ f)=(h\circ g) \circ f$.
>$\quad$ ^2f5c3a

<u><b>e.g.</b></u> 
- The [[Number Systems#^5fea5c|real numbers]] $\R$ and continuous functions $\R \to \R$.
- [[Topological Spaces#^65c94a|Topological spaces]] and [[Continuous Functions on Topological Spaces#^33ee5a|continuous mappings]].
- [[Manifolds and Atlases#^6ef2ef|Smooth manifolds]] and [[Smooth Functions and Maps#^4fb5f6|smooth mappings]].
$\quad$ 

>[!definition] Commutative Diagram
>A commutative diagram is a diagram such that all directed paths in the diagram with the same start and endpoints lead to the same result. A commutative diagram often consists of three parts:
>- objects (also known as vertices)
>- morphisms (also known as arrows or edges)
>- paths or composites
>$\quad$

>[!definition] Subcategory
>A subcategory $\mathbf{D}$ of a category $\mathbf{C}$ is defined by restricting to a subcollection of objects and subcollection of morphisms subject to the requirements that the subcategory $\mathbf{D}$ contains the domain and codomain of any morphism in $\mathbf{D}$, the identity morphism of any object in $\mathbf{D}$, and the composite of any composable pair of morphisms in $\mathbf{D}$.

## Foundations, Large and Small

>[!definition] Small and Large
>A category $\require{mhchem}\newcommand{\obj}{\operatorname{\textbf{obj}}}\newcommand{\mor}{\operatorname{\textbf{mor}}}\newcommand{\Hom}{\mathrm{Hom}}\mathbf{C}$ is called small if both the collection $\obj(\mathbf{C})$ of objects of $\mathbf{C}$ and the collection $\mor(\mathbf{C})$ of arrows of $\mathbf{C}$ are sets. Otherwise, $\mathbf{C}$ is called large. ^20e64e

<u><b>e.g.</b></u>  All finite categories are clearly small, the category $\mathbf{Group}$ of groups, and the category $\mathbf{Set}$ of sets are all large. 

>[!definition] Locally-Small
>A category $\mathbf{C}$ is called locally small if for any objects $X, Y$ in $\mathbf{C}$, the collection $\text{Hom}_\mathbf{C} (X,Y)=\{f\in\mor(\mathbf{C})\mid f\colon X\to Y \}$ is a set (called a hom-set).

<u><b>e.g.</b></u>  Many of the large categories we want to consider are in fact locally small. $\mathbf{Set}$ is locally small since $\text{Hom}_\mathbf{Set} (X,Y)=Y^{X}$, the set of all functions from $X$ to $Y$. Similarly, $\mathbf{Pos}$, $\mathbf{Top}$, and $\mathbf{Group}$ are all locally small.

>[!proposition] 
> Any small category is locally small.