>[!definition]
>**Def**  <i><u>Adjunction</u></i>
An adjunction between categories $\mathbf{C}$ and $\mathbf{D}$ consists of functors $F\colon\mathbf{C}\to\mathbf{D}$ and $U\colon \mathbf{D}\to\mathbf{C}$, with a [[Functoriality and Naturality#^d73db0|natural transformation]]: $$\eta\colon1_\mathbf{C} \to U \circ F$$with the property:
For any $C\in \obj\mathbf{C}$, $D\in\obj\mathbf{D}$ and $f\colon C \to U(D)$, there exists a unique $g\colon F(C) \to D$ such that $$f=U(g)\circ \eta_{C}$$as indicated in 
![|200](https://svgshare.com/i/15dx.svg)
$F$ is called the left adjoint, $U$ is called the right adjoint, and $η$ is called the unit of the adjunction. One sometimes writes $F \dashv U$ for “$F$ is left and $U$ right adjoint.”
>Equivalently, we can also formally define adjunction between categories $\mathbf{C}$ and $\mathbf{D}$ as functors $F\colon\mathbf{C}\to\mathbf{D}$ and $U\colon \mathbf{D}\to\mathbf{C}$ with a [[Functoriality and Naturality#^b8c1fd|natural isomorphism]]: $$\phi:\Hom_\mathbf{D}(F(-),*)\to\Hom_\mathbf{C}(-,U(*))$$ which specifies a family of bijections: $$\phi_{X,Y}:\Hom_\mathbf{D}(F(X),Y)\to\Hom_\mathbf{C}(X,U(Y))$$ The unit $η\colon 1_{\mathbf{C}} →U\circ F$ and the counit $ε\colon F\circ U→1_\mathbf{D}$ of the adjunction are then determined as $$\eta_{C}= \phi_{C,F(C)}(1_{F(C)}),\quad \varepsilon_{D}= \phi_{U(D),D}^{-1}(1_{U(D)})$$

>[!remark]
>Note that the situation $F ⊣ U$ is a generalization of equivalence of categories, in that a pseudo-inverse is an adjoint. In that case, however, it is the relation between categories that one is interested in. Here, one is concerned with the relation between specific functors. That is to say, it is not the relation on categories “there exists an adjunction,” but rather “this functor has an adjoint” that we are concerned with.

**Prop**  Given a function $f \colon A → B$ between sets, the extended image operation functor$f \colon P(A) → P(B)$ is left adjoint to the inverse image functor $f^{−1} \colon P(B) → P(A)$, where $P(X)$ denotes the power set of set $X$, as a poset category ordered by subset inclusion.
**Proof**  

>[!proposition] 
>**Prop**  A category $\mathbf{C}$ has all binary products iff the diagonal functor has a right adjoint.

>[!proposition]
>**Prop**  Adjoints are unique up to isomorphism. Specifically, given a functor $F \colon\mathbf{C}→\mathbf{D}$ and right adjoints $U,V \colon \mathbf{D}→\mathbf{C}$, $$F\dashv U \text{ and } F \dashv V \implies U \cong V$$
>**Proof**  For any $D∈\mor\mathbf{D}$, and $C∈\mathbf{C}$, since $F\dashv U$ and $F \dashv V$ we have $$\Hom_\mathbf{C}(C,U(D))\cong \Hom_\mathbf{D}(F(C),D)\cong \Hom_\mathbf{C}(C,V(D))$$ Thus, by [[Yoneda Lemma#^ecd8f3|Yoneda lemma]], $U(D) \cong V(D)$. But this isomorphism is natural in $D$, again by adjointness.

## Order Adjoints


## 

>[!proposition] 
>**Prop**  Right adjoints preserve limits, and left adjoints preserve colimits.
