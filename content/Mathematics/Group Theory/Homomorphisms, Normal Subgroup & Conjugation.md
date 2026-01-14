---
created: 2023-11-22
updated: 2024-10-28
---
## Homomorphisms

>[!definition] Group Homomorphism
>Let $G$ and $H$ be groups. A *homomorphism* $\varphi: G \to H$ is a map that satisfies $\varphi (ab) = \varphi (a) \varphi (b)$ for all $a,b \in G$. ^homo

>[!proposition] 
>If $\varphi: G \to H$ is a group homomorphism, then the identity of $G$ is mapped to the identity of $H$.

>[!definition] Kernel & Image
>Let $\varphi : G \to H$ be a group homomorphism. The kernel and the image of $\varphi$ are defined by $$ \begin{aligned} \ker(\varphi)&=\{g\in G\mid \varphi(g)=e_{H}\}\subset G, \\ \operatorname{im}(\varphi)&=\{h\in H\mid\exists g\in G,\varphi(g)=h\}\subset H. \end{aligned}$$

>[!proposition] 
> A homomorphism $\varphi : G \to H$ is injective if and only if $\ker(\varphi) = \{e_G\}$_._

*Proof*  If $φ$ is injective then clearly $\ker(φ) = {e }$. Conversely, suppose that $\ker(φ) = \{e_G\}$ and let $a,b \in G$ with $φ(a) = φ(b)$. Then $φ(a^{−1}b) = φ(a)^{−1}φ(b) = e_H$. Hence $a^{-1}b = e_G$ and therefore $a = b$. $\square$

## Normal Subgroup

>[!definition] Conjugate
>Let $G$ be a group. For any $a,b\in G$, we say $a$ and $b$ and conjugate if there exists $g\in G$ such that $a=gbg^{-1}$.

>[!definition] Normal Subgroup & Simple Group
> Let $G$ be a group. A subgroup $N \leq G$ is called *normal* if $gN g^{−1} \subset N$ for every $g \in G$. We denote a normal subgroup by $N \triangleleft G$. 
> A group is *simple* if there’s no non-trivial normal subgroups. ^normal

<u><b>e.g.</b></u>  Let $\varphi : G \to H$ be a [[Homomorphisms, Normal Subgroup & Conjugation#^homo|homomorphism]], then $\ker(\varphi) \triangleleft G$. Fix some $x\in \ker(\varphi)$, then for all $g\in G$ we have $\varphi(g x g^{-1})=\varphi(g)\varphi(x)\varphi(g^{-1})=\varphi(g)\varphi(g)^{-1}=e$.

>[!proposition] 
> The followings are true:
>1. $N \leq G$ is normal iff the right coset $Ng$ coincides with the left coset $gN$ for every $g \in G$.
>2. We required in the definition that $gN g^{−1} \subset N$ , but it follows that $gN g^{−1} = N$.
>3. Every subgroup of an abelian group is normal.
>$\quad$

>[!definition] Normaliser
>Let $G$ be a group and $H\leq G$. The normaliser is the subgroup of $G$ that
>$$ N_G(H)=\{ g\in G \mid gHg^{-1}=H \} \supseteq H.$$ 
> In other words, it is the largest [[Groups, Order and Subgroups#^1ccb07|subgroup]] of $G$ in which $H$ is normal. ^d4bf2b

>[!proposition] 
> $N_G(H) \triangleleft G$.

## Isomorphisms

>[!definition] Group Isomorphism
>A [group homomorphism](Homomorphisms,%20Normal%20Subgroup%20&%20Conjugation.md#^homo) $\varphi\colon G → H$ is called isomorphism if it has an inverse, that is a homomorphism $ψ:H →G$ such that $\psi \circ \varphi=e_G$ and $\varphi \circ \psi=e_H$. ^c32ca8

>[!proposition] 
>**Prop**  A homomorphism $φ : G → H$ is an isomorphism if and only if it is bijective.

>[!proposition] 
>**Prop**  Groups of prime order are cyclic.

>[!proposition] 
>**Prop**  Any two cyclic group of the same order are isomorphic.

>[!definition] 
>**Def**  <i><u>Lambda-Map</u></i>
>For every $g \in G$ define a map by left multiplication with $g$: $$\lambda_{g}:G\to G,\quad x\mapsto g x$$

>[!proposition] 
>**Prop** $\lambda_g \in \text{Sym}(G)$.

>[!proposition] 
>**Prop** $\lambda_{g^{-1}}$ is the inverse of $\lambda_g$.

>[!theorem] Cayley’s Theorem
>The map $\lambda \colon G \to \text{Sym}(G)$ given by $g \mapsto \lambda_g$ is an injective group homomorphism. ^dcfefa

*Proof*  Clearly $\lambda(x)\circ\lambda(y)=\lambda(xy)$. Set $\lambda(g)=\lambda_{g}=\text{id}$ where $\text{id}$ is the identity map from $G$ to $G$. Then for all $x\in G$, we have $gx=x$. It follows that $g=1$. Thus $\lambda$ is injective. $\square$

>[!corollary] 
>**Corollary** Every finite group is isomorphic to a subgroup of a [[Symmetric Group#^5b562f|symmetric group]] $S_{n}$.
>**Proof**  For any finite group $G$, the $\lambda$ map forms an isomorphism, thus $G\cong S_{n}$ for some $n$.

>[!definition] 
>**Def**  <i><u>Automorphism</u></i>
>An automorphism is an isomorphism from a group $G$ to $G$. Denote $\text{Aut}(G)$ as the set of all automorphisms on $G$.

## Conjugation

>[!definition] Conjugation
>Let $G$ be a group and $g \in G$. The map$$ \gamma_{g}\colon G \to G, \quad a \mapsto gag^{-1} $$is called conjugation by $g$. We say that the elements $a$ and $gag^{-1}$ are conjugate.

>[!proposition] 
> Let $G$ be a [[Groups, Order and Subgroups#^6e0960|group]] and $g \in G$. Then $\gamma_{g}\colon G \to G$ is an isomorphism.

*Proof*  We first check that $\gamma_g$ is a homomorphism:$$ \gamma_g(ab) = gabg^{-1} = ga(g^{-1}g)bg^{-1} = (gag^{-1})(gbg^{-1})=\gamma_g(a)\gamma_g(b) $$The map is injective because $\gamma_g(a) = e \implies gag^{-1}=e \implies ga=g \implies a=e$. And is surjective since for all $a \in G$, we have $\gamma_g(g^{-1}ag)=a$. $\square$