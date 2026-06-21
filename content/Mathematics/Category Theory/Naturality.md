## Natural Transformation

>[!definition] Natural Transformation
>Given categories $\mathsf{C}$ and $\mathsf{D}$ and [[Functoriality#^653948|covariant functors]] $F,G\colon\mathsf{C}\to\mathsf{D}$, a *natural transformation* $\alpha\colon F \Rightarrow G$ consists of:
>- morphisms $\alpha_{X}\colon F(X) \to G(X)$, is called the *component of $\alpha$ at $X$*.
>- and components must be such that for every morphism $f\colon X\to Y$ in $\mathsf{C}$ we have:$$\alpha_{Y}\circ F(f)=G(f)\circ\alpha_{X}$$
>
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/natural_transformation.png" alt="natural_transformation" style="width:60%;"/> ^d73db0

>[!definition] Vertical Composition
>Suppose $α\colon F \Rightarrow G$ and $β\colon G \Rightarrow H$ are natural transformations between parallel functors $F, G, H \colon \mathsf{C} \Rightarrow \mathsf{D}$. Then there is a natural transformation $β \circ α \colon F \to H$ whose components $$(\beta \circ \alpha)_{C}=\beta_{C}\circ \alpha_{C}.$$Such $β \circ α$ is called the *vertical composition* of $\alpha$ and $\beta$. ^70ad46

> [!remark]
> We shall check the vertical composition is a natural transformation. Naturality of $α$ and $β$ implies that for any $f \colon X \to Y$ in the domain category $\mathsf{C}$, each square, and thus also the composite rectangle, commutes:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/natural_transformation_vertical_composition.svg" style="width:50%;"/>
> 

>[!definition] Natural Isomorphism
>A *natural isomorphism* is a natural transformation $\alpha\colon F\Rightarrow G$ in which every component $\alpha_{X}$ is an [[Morphisms#^8927b3|isomorphism]]. In this case, the natural isomorphism may be depicted as $$\alpha \colon F \cong G.$$ ^b8c1fd

## The Functor Category

>[!definition] Functor Category
> Define the *category of functors* $\mathsf{Fun}(\mathsf{C},\mathsf{D})$ having [[Functoriality#^653948|functors]] $F\colon\mathsf{C}\to\mathsf{D}$ as objects and [[Naturality#^d73db0|natural transformations]] $\alpha \colon F \Rightarrow G$ as arrows. And for each functor object $F$, the natural transformation $1_{F}$ has components $$(1_{F})_{C}=1_{F(C)}\colon F(C)\to F(C)$$And the composite natural transformation of $\theta\colon F \Rightarrow G$ and $\phi\colon G \Rightarrow H$ is the [[Functoriality#^70ad46|vertical composition]].

>[!proposition]
>If categories $\mathsf{C}$ and $\mathsf{D}$ are small, then $\mathsf{Fun}(\mathsf{C},\mathsf{D})$ is again a small category, but if $\mathsf{C}$ and $\mathsf{D}$ are locally small, then $\mathsf{Fun}(\mathsf{C},\mathsf{D})$ need not be. This is only guaranteed if $\mathsf{D}$ is locally small and $\mathsf{C}$ is small.

>[!lemma] 
> A [[Naturality#^d73db0|natural transformation]] is a natural isomorphism if and only if it forms an [[Morphisms#^8927b3|isomorphism]] in the functor category.

>[!lemma] 
>**Lemma**  Given locally small categories $\mathsf{A}$, $\mathsf{B}$, and $\mathsf{C}$, a map of arrows and objects, $$F_{0}\colon \obj \mathsf{A} \times \obj \mathsf{B} \to \obj \mathsf{C},\quad F_{1}\colon \mor \mathsf{A}\times \mor \mathsf{B} \to \mor\mathsf{C}$$forms a functor $F \colon \mathsf{A} \times \mathsf{B} \to \mathsf{C}$ iff 
>- $F$ is functorial in each argument: $F(A,−) \colon \mathsf{B} → \mathsf{C}$ and $F(−,B) \colon \mathsf{A} → \mathsf{C}$ are functors for all $A∈\obj\mathsf{A}$ and $B∈\obj \mathsf{B}$.
>- $F$ satisfies the following interchange law. Given $α \colon A → A^{\prime} ∈ \mor\mathsf{A}$ and $β : B → B^{\prime} ∈ \mor B$, $F(A^{\prime},β)\circ F(α,B)=F(α,B^{\prime})\circ F(A,β)$.
>$\quad$

>[!proposition] 
> $\mathsf{Cat}$ is cartesian closed, with the exponentials $\mathsf{D}^{\mathsf{C}}=\text{Func}(\mathsf{C},\mathsf{D})$.

## Horizontal Composition

>[!definition] Horizontal Composition
>Given a pair of natural transformations $\alpha\colon F\to G$ and $\beta \colon H \to K$ as indicated in the diagram:
>![|350](https://i.imgur.com/125TXbI.png)
>there is a natural transformation $β ∗ α\colon HF \to KG$ whose component at $C ∈ \obj \mathbf{C}$ is defined as $$(\beta * \alpha)_{C}=\beta_{G(C)} \circ H(\alpha_{C})=K(\alpha_{C})\circ \beta_{F(C)}$$

>[!lemma]
>**Lemma**  <i><u>Middle Four Interchange</u></i>
>Given functors and natural transformations 
>![|320](https://i.imgur.com/HO0THYe.png)
>the natural transformation $JF \to LH$ defined by first composing vertically and then composing horizontally equals the natural transformation defined by first composing horizontally and then composing vertically:
>![|530](https://i.imgur.com/pCUxEBQ.png)
>**Proof**  
