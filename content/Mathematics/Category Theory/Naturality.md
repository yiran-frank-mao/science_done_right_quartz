## Natural Transformation

>[!definition] Natural Transformation
>Given categories $\mathsf{C}$ and $\mathsf{D}$ and [[Functoriality#^653948|covariant functors]] $F,G\colon\mathsf{C}\to\mathsf{D}$, a *natural transformation* $\alpha\colon F \Rightarrow G$ consists of:
>- morphisms $\alpha_{X}\colon F(X) \to G(X)$, is called the *component of $\alpha$ at $X$*.
>- and components must be such that for every morphism $f\colon X\to Y$ in $\mathsf{C}$ we have:$$\alpha_{Y}\circ F(f)=G(f)\circ\alpha_{X}$$
>
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/natural_transformation.png" alt="natural_transformation" style="width:65%;"/> ^d73db0

>[!definition] Vertical Composition
>Suppose $α\colon F \Rightarrow G$ and $β\colon G \Rightarrow H$ are natural transformations between parallel functors $F, G, H \colon \mathsf{C} \Rightarrow \mathsf{D}$. Then there is a natural transformation $β \circ α \colon F \to H$ whose components $$(\beta \circ \alpha)_{C}=\beta_{C}\circ \alpha_{C}.$$Such $β \circ α$ is called the *vertical composition* of $\alpha$ and $\beta$. ^70ad46

> [!remark]
> We shall check the vertical composition is a natural transformation. Naturality of $α$ and $β$ implies that for any $f \colon X \to Y$ in the domain category $\mathsf{C}$, each square, and thus also the composite rectangle, commutes:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/natural_transformation_vertical_composition.svg" style="width:50%;"/>
> 

>[!definition] Natural Isomorphism
>A *natural isomorphism* is a natural transformation $\alpha\colon F\Rightarrow G$ in which every component $\alpha_{X}$ is an [[Morphisms#^8927b3|isomorphism]]. In this case, the natural isomorphism may be depicted as $\alpha \colon F \cong G$. ^b8c1fd

## The Functor Category

>[!definition] Functor Category
> Define the *category of functors* $\mathsf{Fun}(\mathsf{C},\mathsf{D})$ having [[Functoriality#^653948|functors]] $F\colon\mathsf{C}\to\mathsf{D}$ as objects and [[Naturality#^d73db0|natural transformations]] $\alpha \colon F \Rightarrow G$ as arrows. And for each functor object $F$, the natural transformation $1_{F}$ has components $$(1_{F})_{C}=1_{F(C)}\colon F(C)\to F(C)$$And the composite natural transformation of $\theta\colon F \Rightarrow G$ and $\phi\colon G \Rightarrow H$ is the [[Functoriality#^70ad46|vertical composition]].

>[!proposition]
>If categories $\mathsf{C}$ and $\mathsf{D}$ are small, then $\mathsf{Fun}(\mathsf{C},\mathsf{D})$ is again a small category, but if $\mathsf{C}$ and $\mathsf{D}$ are locally small, then $\mathsf{Fun}(\mathsf{C},\mathsf{D})$ need not be. This is only guaranteed if $\mathsf{D}$ is locally small and $\mathsf{C}$ is small.

>[!proposition] 
> A [[Naturality#^d73db0|natural transformation]] is a [[Naturality#^b8c1fd|natural isomorphism]] if and only if it forms an [[Morphisms#^8927b3|isomorphism]] in the functor category.

*Proof*  If $\alpha\colon F\Rightarrow G$ is a natural isomorphism, then each $\alpha_{X}$ has an inverse $\alpha_{X}^{-1}$. Define $\alpha^{-1}\colon G\Rightarrow F$ by $(\alpha^{-1})_{X}=\alpha_{X}^{-1}$. It is clear that $\alpha^{-1}$ is a natural transformation, and $\alpha\circ \alpha^{-1}=1_{G}$ and $\alpha^{-1}\circ \alpha=1_{F}$. Conversely, if $\alpha$ is an isomorphism in the functor category, then there is a natural transformation $\beta\colon G\Rightarrow F$ such that $\alpha\circ \beta=1_{G}$ and $\beta\circ \alpha=1_{F}$. Hence each component $\alpha_{X}$ has an inverse $\beta_{X}$, so $\alpha$ is a natural isomorphism. $\square$

>[!lemma] 
> Given locally small categories $\mathsf{A}$, $\mathsf{B}$, and $\mathsf{C}$, a map of arrows and objects, $$F_{0}\colon \obj \mathsf{A} \times \obj \mathsf{B} \to \obj \mathsf{C},\quad F_{1}\colon \mor \mathsf{A}\times \mor \mathsf{B} \to \mor\mathsf{C}$$forms a functor $F \colon \mathsf{A} \times \mathsf{B} \to \mathsf{C}$ iff 
>- $F$ is functorial in each argument: $F(A,−) \colon \mathsf{B} → \mathsf{C}$ and $F(−,B) \colon \mathsf{A} → \mathsf{C}$ are functors for all $A∈\obj\mathsf{A}$ and $B∈\obj \mathsf{B}$.
>- $F$ satisfies the following interchange law. Given $α \colon A → A^{\prime} ∈ \mor\mathsf{A}$ and $β : B → B^{\prime} ∈ \mor B$, $F(A^{\prime},β)\circ F(α,B)=F(α,B^{\prime})\circ F(A,β)$.
>$\quad$

>[!proposition] 
> $\mathsf{Cat}$ is cartesian closed, with the exponentials $\mathsf{D}^{\mathsf{C}}=\text{Func}(\mathsf{C},\mathsf{D})$.

## Horizontal Composition

>[!definition] Horizontal Composition
>Given a pair of [[Naturality#^d73db0|natural transformation]] $\alpha\colon F \Rightarrow G$ and $\beta \colon H \Rightarrow K$ as indicated in the diagram:
><img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/natural_transformation_horizontal_composition.svg" style="width:45%;"/>
>there is a natural transformation $β ∗ α\colon HF \Rightarrow KG$ whose component at $C ∈ \obj \mathsf{C}$ is defined as $$(\beta * \alpha)_{C}=\beta_{G(C)} \circ H(\alpha_{C})=K(\alpha_{C})\circ \beta_{F(C)}$$

> [!remark]
> $\beta*\alpha$ is a well-defined natural transformation by observing the following commutative diagram:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/natural_transformation_horizontal_composition_proof.svg" style="width:60%;"/>
> 

>[!lemma] Middle Four Interchange
>Given functors and natural transformations 
><img src="https://i.imgur.com/HO0THYe.png" style="width:45%;"/>
>the natural transformation $JF \to LH$ defined by first composing vertically and then composing horizontally equals the natural transformation defined by first composing horizontally and then composing vertically:
><img src="https://i.imgur.com/pCUxEBQ.png" style="width:72%;"/>

*Proof*  