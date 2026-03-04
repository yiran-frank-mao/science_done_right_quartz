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
- Every category $\mathbf{C}$ has an identity functor $1_{\mathbf{C}} \colon \mathbf{C} \to \mathbf{C}$. 
- The mapping sends any [[Vector Spaces#^f4b63e|vector space]] $V$ to its [[Mathematics/Linear Algebra/Duality#^6c7627|dual space]] $V^{*}$, and any linear map $f \colon V \to W$ to its dual map (i.e. the pullback) $f^{*} \colon W^{*} \to V^{*}$ is a contravariant functor from the category of vector spaces to itself.
- Let $\mathbf{C}$ be the category of finite sets, and $\mathbf{D}$ be the category of commutative The functor $F \colon \mathbf{C} \to \mathbf{D}$ that sends each finite set to its power set and each function to the corresponding function on the power sets is a contravariant functor.
$\quad$

> [!remark]+ The Category of Small Categories
> We have another example of a category, namely $\mathbf{Cat}$, the category of all [[Structure of Categories#^20e64e|small categories]] and corresponding functors.
> 

>[!definition] Injective  and Surjective Functor
>A functor $\newcommand{\obj}{\operatorname{\textbf{obj}}}\newcommand{\mor}{\operatorname{\textbf{mor}}}\newcommand{\Hom}{\mathrm{Hom}} F \colon \mathbf{C} → \mathbf{D}$ is said to be injective on objects if the object part $F_0 \colon \obj\mathbf{C} → \obj\mathbf{D}$ is injective, it is surjective on objects if $F_{0}$ is surjective. Similarly, $F$ is injective or surjective on morphisms if the morphism part $F_{1} \colon \mor\mathbf{C} → \mor\mathbf{D}$ is injective or surjective.

>[!definition] Faithful Functor
>Functor $F$ is faithful if for all $A,B ∈ \obj\mathbf{C}$, the map $$F_{A,B}\colon\Hom_\mathbf{C}(A,B)\to \Hom_\mathbf{D}(F(A),F(B)),\quad f\mapsto F(f)$$is injective.

>[!definition] Full Functor
>Functor $F$ is full if for all $A,B ∈ \obj\mathbf{C}$, the map $$F_{A,B}\colon\Hom_\mathbf{C}(A,B)\to \Hom_\mathbf{D}(F(A),F(B)),\quad f\mapsto F(f)$$is surjective.

>[!definition] Embedding
>A functor $F \colon \mathbf{C} → \mathbf{D}$ is called an embedding if it is full, faithful, and injective on objects.

>[!definition] 
>**Def**  <i><u>Full Subcategory</u></i>
>A full subcategory $\mathbf{U}\rightarrowtail\mathbf{C}$ consists of some objects of $\mathbf{C}$ and all of the morphisms between them.

## Representable Structure

>[!definition] Representable Functor
>Let $\mathbf{C}$ be a locally small category, we have the representable functors: $$\Hom_\mathbf{C}(C,-)\colon \mathbf{C} \to \mathbf{Sets}$$for all objects $C ∈ \mor \mathbf{C}$.

>[!definition] 
>**Def**  <i><u>Generator</u></i>
>A generator for category $\mathbf{C}$ is an object $C$ has the property that for any objects $X$ and $Y$ and morphisms f$,g \colon X \to Y$, if $f \neq g$ then there is an arrow $x \colon C → X$ such that $fx\neq gx$. That is, the arrows in the category are distinguished by their effect on generalized elements based at $C$.

>[!definition] Contravariant Representable Functors
>Let $\mathbf{C}$ be a locally small category, we have the contravariant representable functors: $$\Hom_\mathbf{C}(-,C)\colon \mathbf{C}^\text{op} \to \mathbf{Sets}$$taking $f \colon A → B$ to $f^{*} \colon \Hom_\mathbf{C}(B,C) → \Hom_\mathbf{C}(A,C)$ by $f^{*}(h) = h\circ f$ for $h \colon B → C$.

## Naturality

>[!definition] Natural Transformation
>Given categories $\mathbf{C}$ and $\mathbf{D}$ and [[Functoriality and Naturality#^653948|covariant functors]] $F,G\colon\mathbf{C}\to\mathbf{D}$, a natural transformation $\alpha\colon F \Rightarrow G$ consists of:
>- morphisms $\alpha_{X}\colon F(X) \to G(X)$, is called the component of $\alpha$ at $X$.
>- and components must be such that for every morphism $f\colon X\to Y$ in $\mathbf{C}$ we have:$$\alpha_{Y}\circ F(f)=G(f)\circ\alpha_X$$
>
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/natural_transformation.png" alt="natural_transformation" style="width:60%;"/> ^d73db0

>[!definition] Vertical Composition
>Suppose $α\colon F \to G$ and $β\colon G \to H$ are natural transformations between parallel functors $F, G, H \colon \mathbf{C}→ \mathbf{D}$. Then there is a natural transformation $β \circα \colon F \to H$ whose components $$(\beta \circ \alpha)_{C}=\beta_{C}\circ \alpha_{C}$$which is defined to be the vertical composition of the components of $α$ and $β$.

*Proof*  Naturality of $α$ and $β$ implies that for any $f \colon C → C^{\prime}$ in the domain category, each square, and thus also the composite rectangle, commutes:
![|420](https://i.imgur.com/GJHeWk8.png)

>[!definition] Functor Category
>Define the category of functors $\text{Fun}(\mathbf{C},\mathbf{D})$ having functors $F\colon\mathbf{C}\to\mathbf{D}$ as objects and natural transformations $\alpha \colon F → G$ as arrows. And for each functor object $F$, the natural transformation $1_{F}$ has components $$(1_{F})_{C}=1_{F(C)}\colon F(C)\to F(C)$$And the composite natural transformation of $\theta\colon F → G$ and $\phi\colon G → H$ is the vertical composition.

>[!proposition]
>If categories $\mathbf{C}$ and $\mathbf{D}$ are small, then $\text{Fun}(\mathbf{C},\mathbf{D})$ is again a small category, but if $\mathbf{C}$ and $\mathbf{D}$ are locally small, then $\text{Fun}(\mathbf{C},\mathbf{D})$ need not be. This is only guaranteed if $\mathbf{D}$ is locally small and $\mathbf{C}$ is small.

>[!definition] Natural Isomorphism
>A natural isomorphism is a natural transformation $\alpha\colon F\to G$ in which every component $\alpha_{X}$ is an isomorphism. In this case, the natural isomorphism may be depicted as $$\alpha \colon F \cong G$$ ^b8c1fd

>[!lemma] 
> A natural transformation is a natural isomorphism if and only if it forms an isomorphism in the functor category.

>[!lemma] 
>**Lemma**  Given locally small categories $\mathbf{A}$, $\mathbf{B}$, and $\mathbf{C}$, a map of arrows and objects, $$F_{0}\colon \obj \mathbf{A} \times \obj \mathbf{B} \to \obj \mathbf{C},\quad F_{1}\colon \mor \mathbf{A}\times \mor \mathbf{B} \to \mor\mathbf{C}$$forms a functor $F \colon \mathbf{A} \times \mathbf{B} \to \mathbf{C}$ iff 
>- $F$ is functorial in each argument: $F(A,−) \colon \mathbf{B} → \mathbf{C}$ and $F(−,B) \colon \mathbf{A} → \mathbf{C}$ are functors for all $A∈\obj\mathbf{A}$ and $B∈\obj \mathbf{B}$.
>- $F$ satisfies the following interchange law. Given $α \colon A → A^{\prime} ∈ \mor\mathbf{A}$ and $β : B → B^{\prime} ∈ \mor B$, $F(A^{\prime},β)\circ F(α,B)=F(α,B^{\prime})\circ F(A,β)$.
>$\quad$

>[!proposition] 
>**Prop**  $\mathbf{Cat}$ is cartesian closed, with the exponentials $\mathbf{D}^{\mathbf{C}}=\text{Func}(\mathbf{C},\mathbf{D})$.
>**Proof**  

## Equivalence of Categories

>[!definition] Equivalent Categories
>An equivalence of categories consists of a pair of functors $E\colon \mathbf{C}\to\mathbf{D}$ and $F\colon \mathbf{D}\to\mathbf{C}$ and a pair of natural isomorphisms $$\alpha\colon 1_\mathbf{C} \to F \circ E, \quad \beta\colon1_\mathbf{D}\to E\circ F$$In this situation, the functor $F$ is called a pseudo-inverse of $E$. The categories $\mathbf{C}$ and $\mathbf{D}$ are then said to be equivalent, written $\mathbf{C} ≃ \mathbf{D}$.

>[!proposition] 
>**Prop**  The following conditions on a functor $F \colon \mathbf{C} → \mathbf{D}$ are equivalent:
>- $F$ is part of an equivalence of categories.
>- $F$ is full and faithful and “essentially surjective” on objects: for every $D ∈ \obj \mathbf{D}$ there is some $C ∈\obj \mathbf{C}$ such that $F(C)\cong D$.
>$\quad$