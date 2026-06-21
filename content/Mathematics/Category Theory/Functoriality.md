## Functoriality

>[!definition] Functor
>A *(covariant) functor* between [[Structure of Categories#^2f5c3a|categories]] $\mathsf{C}$ and $\mathsf{D}$ is a mapping of objects to objects and morphisms to morphisms such that for all $\mathsf{C}$-objects $A$ and $B$:
>- $F(f \colon A\to B)=F(f)\colon F(A)\to F(B)$
>- $F(g\circ f)=F(g)\circ F(f)$
>- $F(1_{A})=1_{F(A)}$
> 
> A contravariant functor is a similar mapping $\mathsf{C}\to\mathsf{D}$, but reverses the direction of morphisms:
> - $F(f \colon A\to B)=F(f)\colon F(B)\to F(A)$,
> - $F(g\circ f)=F(f)\circ F(g)$,
> - $F(1_{A})=1_{F(A)}$.
> 
> Equivalently, a contravariant functor is a (covariant) functor from the opposite category $\mathsf{C}^{\text{op}}$ to $\mathsf{D}$. ^653948

<u><b>e.g.</b></u>  
- Every category $\mathsf{C}$ has an identity functor $1_{\mathsf{C}} \colon \mathsf{C} \to \mathsf{C}$. 
- The mapping sends any [[Vector Spaces#^f4b63e|vector space]] $V$ to its [[Mathematics/Linear Algebra/Duality#^6c7627|dual space]] $V^{*}$, and any linear map $f \colon V \to W$ to its dual map (i.e. the pullback) $f^{*} \colon W^{*} \to V^{*}$ is a contravariant functor from the category of vector spaces to itself.
- The functor that sends each finite set to its power set and each function to the corresponding function on the power sets is a contravariant functor.
$\quad$

> [!remark]+ The Category of Small Categories
> We now have another example of a category, namely $\mathsf{Cat}$, the category of all [[Structure of Categories#^20e64e|small categories]] and corresponding functors.
> 

>[!definition] Injective & Surjective on Objects
>A functor $\newcommand{\obj}{\operatorname{\textbf{obj}}}\newcommand{\mor}{\operatorname{\textbf{mor}}}\newcommand{\Hom}{\mathrm{Hom}} F \colon \mathsf{C} → \mathsf{D}$ is said to be *injective on objects* if the object part $F_0 \colon \obj\mathsf{C} → \obj\mathsf{D}$ is injective, it is surjective on objects if $F_{0}$ is surjective. Similarly, $F$ is injective or surjective on morphisms if the morphism part $F_{1} \colon \mor\mathsf{C} → \mor\mathsf{D}$ is injective or surjective.

>[!definition] Faithful & Full Functor
> Suppose $\mathsf{C}$, $\mathsf{D}$ are [[Structure of Categories#^d0fa66|locally-small]] categories. A functor $F\colon \mathsf{C}\to \mathsf{D}$ is *faithful* if for all $A,B ∈ \obj\mathsf{C}$, the map $$F_{A,B}\colon\Hom_\mathsf{C}(A,B)\to \Hom_\mathsf{D}(F(A),F(B)),\quad f\mapsto F(f)$$is [[Relations and Functions#^042daf|injective]]. It is *full* if $F_{A,B}$ is [[Relations and Functions#^042daf|surjective]].

>[!definition] Embedding
>A functor $F \colon \mathsf{C} \to \mathsf{D}$ is called an *embedding* if it is full, faithful, and injective on objects.

>[!definition] Full Subcategory
>A *full subcategory* $\mathsf{U}\rightarrowtail\mathsf{C}$ consists of some objects of $\mathsf{C}$ and all of the morphisms between them.

## Representable Structure

>[!definition] Representable Functor
>Let $\mathsf{C}$ be a [[Structure of Categories#^d0fa66|locally-small]] category, we have the *representable functors*: $$\Hom_\mathsf{C}(C,-)\colon \mathsf{C} \to \mathsf{Set}$$for all objects $C \in \mathsf{C}_{0}$.

>[!definition] Generator
>A *generator* for category $\mathsf{C}$ is an object $C$ has the property that for any objects $X$ and $Y$ and morphisms $f,g \colon X \to Y$, if $f \neq g$ then there is an arrow $x \colon C → X$ such that $fx\neq gx$. That is, the arrows in the category are distinguished by their effect on generalized elements based at $C$.

>[!definition] Contravariant Representable Functors
>Let $\mathsf{C}$ be a locally small category, we have the contravariant representable functors: $$\Hom_\mathsf{C}(-,C)\colon \mathsf{C}^\text{op} \to \mathsf{Set}$$taking $f \colon A → B$ to $f^{*} \colon \Hom_\mathsf{C}(B,C) → \Hom_\mathsf{C}(A,C)$ by $f^{*}(h) = h\circ f$ for $h \colon B → C$.

## Equivalence of Categories

>[!definition] Equivalent Categories
> An *equivalence of categories* consists of a pair of functors $E\colon \mathsf{C}\to\mathsf{D}$ and $F\colon \mathsf{D}\to\mathsf{C}$ and a pair of natural isomorphisms $$\alpha\colon 1_\mathsf{C} \to F \circ E, \quad \beta\colon1_\mathsf{D}\to E\circ F$$
> In this situation, the functor $F$ is called a *pseudo-inverse* of $E$. The categories $\mathsf{C}$ and $\mathsf{D}$ are then said to be *equivalent*, written $\mathsf{C} ≃ \mathsf{D}$.

>[!proposition] 
> The following conditions on a functor $F \colon \mathsf{C} → \mathsf{D}$ are equivalent:
>- $F$ is part of an equivalence of categories.
>- $F$ is full and faithful and “essentially surjective” on objects: for every $D ∈ \obj \mathsf{D}$ there is some $C ∈\obj \mathsf{C}$ such that $F(C)\cong D$.
>$\quad$