>[!definition] Adjunction
>An *adjunction* between categories $\mathsf{C}$ and $\mathsf{D}$ consists of functors $F\colon\mathsf{C}\to\mathsf{D}$ and $U\colon \mathsf{D}\to\mathsf{C}$, with a [[Naturality#^d73db0|natural transformation]]: $$\eta\colon1_\mathsf{C} \to U \circ F$$with the property:
>For any $C\in \mathsf{C}_{0}$, $D\in\mathsf{D}_{0}$ and $f\colon C \to U(D)$, there exists a unique $g\colon F(C) \to D$ such that $$f=U(g)\circ \eta_{C}$$as indicated in 
> ![|200](https://svgshare.com/i/15dx.svg)
> $F$ is called the *left adjoint*, $U$ is called the *right adjoint*, and $\eta$ is called the *unit of the adjunction*. One sometimes writes $F \dashv U$ for “$F$ is left and $U$ right adjoint.”
> Equivalently, we can also formally define adjunction between categories $\mathsf{C}$ and $\mathsf{D}$ as functors $F\colon\mathsf{C}\to\mathsf{D}$ and $U\colon \mathsf{D}\to\mathsf{C}$ with a [[Functoriality#^b8c1fd|natural isomorphism]]: $$\phi:\Hom_\mathsf{D}(F(-),*)\to\Hom_\mathsf{C}(-,U(*))$$ which specifies a family of bijections: $$\phi_{X,Y}:\Hom_\mathsf{D}(F(X),Y)\to\Hom_\mathsf{C}(X,U(Y))$$ The unit $η\colon 1_{\mathsf{C}} →U\circ F$ and the counit $ε\colon F\circ U→1_\mathsf{D}$ of the adjunction are then determined as $$\eta_{C}= \phi_{C,F(C)}(1_{F(C)}),\quad \varepsilon_{D}= \phi_{U(D),D}^{-1}(1_{U(D)})$$

>[!remark]
>Note that the situation $F ⊣ U$ is a generalization of equivalence of categories, in that a pseudo-inverse is an adjoint. In that case, however, it is the relation between categories that one is interested in. Here, one is concerned with the relation between specific functors. That is to say, it is not the relation on categories “there exists an adjunction,” but rather “this functor has an adjoint” that we are concerned with.

**Prop**  Given a function $f \colon A → B$ between sets, the extended image operation functor$f \colon P(A) → P(B)$ is left adjoint to the inverse image functor $f^{−1} \colon P(B) → P(A)$, where $P(X)$ denotes the power set of set $X$, as a poset category ordered by subset inclusion.
**Proof**  

>[!proposition] 
>**Prop**  A category $\mathsf{C}$ has all binary products iff the diagonal functor has a right adjoint.

>[!proposition]
>**Prop**  Adjoints are unique up to isomorphism. Specifically, given a functor $F \colon\mathsf{C}→\mathsf{D}$ and right adjoints $U,V \colon \mathsf{D}→\mathsf{C}$, $$F\dashv U \text{ and } F \dashv V \implies U \cong V$$
>**Proof**  For any $D∈\mor\mathsf{D}$, and $C∈\mathsf{C}$, since $F\dashv U$ and $F \dashv V$ we have $$\Hom_\mathsf{C}(C,U(D))\cong \Hom_\mathsf{D}(F(C),D)\cong \Hom_\mathsf{C}(C,V(D))$$ Thus, by [[Yoneda Lemma#^ecd8f3|Yoneda lemma]], $U(D) \cong V(D)$. But this isomorphism is natural in $D$, again by adjointness.

## Order Adjoints


## 

>[!proposition] 
>**Prop**  Right adjoints preserve limits, and left adjoints preserve colimits.
