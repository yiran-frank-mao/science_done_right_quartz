---
created: 2023-11-22
updated: 2026-06-26
completed: true
---
## Homomorphisms

>[!definition] Group Homomorphism
>Let $G$ and $H$ be groups. A *group homomorphism* $\varphi\colon G \to H$ is a map that satisfies $\varphi (ab) = \varphi (a) \varphi (b)$ for all $a,b \in G$. ^homo

>[!proposition] 
>If $\varphi\colon G \to H$ is a group homomorphism, then the identity of $G$ is mapped to the identity of $H$.

*Proof*  Let $e_G$ and $e_H$ be the identity elements of $G$ and $H$, respectively. Then we have $\varphi(e_G) = \varphi(e_G e_G) = \varphi(e_G)\varphi(e_G)$. Multiplying both sides by $\varphi(e_G)^{-1}$, we get $\varphi(e_G) = e_H$. $\square$

>[!definition] Kernel & Image
>Let $\varphi : G \to H$ be a group homomorphism. The *kernel* and the *image* of $\varphi$ are defined by $$ \begin{aligned} \ker(\varphi)&=\{g\in G\mid \varphi(g)=e_{H}\}\subset G, \\ \operatorname{im}(\varphi)&=\{h\in H\mid\exists g\in G,\varphi(g)=h\}\subset H. \end{aligned}$$

>[!proposition] 
> A homomorphism $\varphi \colon G \to H$ is injective if and only if $\ker(\varphi) = \{e_G\}$_._

*Proof*  If $φ$ is injective then clearly $\ker(φ) = {e }$. Conversely, suppose that $\ker(φ) = \{e_G\}$ and let $a,b \in G$ with $φ(a) = φ(b)$. Then $φ(a^{−1}b) = φ(a)^{−1}φ(b) = e_H$. Hence $a^{-1}b = e_G$ and therefore $a = b$. $\square$

## Normal Subgroup

>[!definition] Conjugate
>Let $G$ be a group. For any $a,b\in G$, we say $a$ and $b$ are *conjugate* if there exists $g\in G$ such that $a=gbg^{-1}$.

>[!definition] Normal Subgroup & Simple Group
> Let $G$ be a group. A subgroup $N \leq G$ is called *normal* if $gN g^{−1} \subset N$ for every $g \in G$. We denote a normal subgroup by $N \triangleleft G$. 
> A group is *simple* if there’s no non-trivial normal subgroups. ^normal

<u><b>e.g.</b></u>  Let $\varphi : G \to H$ be a [[Homomorphisms, Normal Subgroup & Conjugation#^homo|homomorphism]], then $\ker(\varphi) \triangleleft G$. Fix some $x\in \ker(\varphi)$, then for all $g\in G$ we have $\varphi(g x g^{-1})=\varphi(g)\varphi(x)\varphi(g^{-1})=\varphi(g)\varphi(g)^{-1}=e$.

From the definition of a normal subgroup, we immediately have the following properties:

>[!proposition] 
> The followings are true:
>1. $N \leq G$ is normal iff the right coset $Ng$ coincides with the left coset $gN$ for every $g \in G$.
>2. We required in the definition that $gN g^{−1} \subset N$ , but it follows that $gN g^{−1} = N$.
>3. Every subgroup of an [[Groups, Order and Subgroups#^6d511a|abelian group]] is normal.
>$\quad$

It is clear that not every subgroup is normal. For example, let $G=S_3$ and $H=\langle (1~2)\rangle$, then $(1~3)H(1~3)^{-1}=\langle (2~3)\rangle\neq H$. However, we can make an arbitrary subgroup as normal as possible by two ways. One is to instead of sticking to $G$, find the largest subgroup of $G$ in which $H$ is normal; the other is to fix $G$, but to find the largest normal subgroup of $G$ contained in $H$. The first one is called the *normaliser* of $H$ in $G$, and the second one is called the *normal core* of $H$ in $G$.

>[!definition] Normaliser
>Let $G$ be a group and $H\leq G$. The *normaliser* is the [[Groups, Order and Subgroups#^1ccb07|subgroup]] of $G$ that
>$$ N_G(H):=\{ g\in G \mid gHg^{-1}=H \} \supseteq H.$$ ^d4bf2b

>[!proposition] 
> $N_G(H)$ is the largest subgroup of $G$ in which $H$ is normal.

*Proof*  We first show that $N_{G}(H)\leq G$. For all $g_{1}, g_{2}\in N_{G}(H)$, and $h\in H$, we have $$g_{1}g_{2}^{-1} h (g_{1}g_{2}^{-1})^{-1}=g_{1}g_{2}^{-1} h g_{2}g_{1}^{-1}\in H,$$so $g_{1}g_{2}^{-1}\in N_{G}(H)$. Now let $K\leq G$ such that $H\triangleleft K$. Then for all $k\in K$, we have $k H k^{-1}=H$, so $k\in N_{G}(H)$. Thus $K\subseteq N_{G}(H)$, and the result follows. $\square$

> [!definition] Normal Core
> Let $G$ be a group and $H\leq G$. The *normal core* of $H$ in $G$ is  $$ H_{G}:=\bigcap_{g\in G} gHg^{-1}.$$ ^d4bf2b
> 

> [!proposition]
> $H_{G}$ is the largest normal subgroup of $G$ contained in $H$.
> 

*Proof*  We first show that $H_{G}\leq G$. For all $h_{1}, h_{2}\in H_{G}$, we have $h_{1}=g h_{1}'g^{-1}$, $h_{2}=g h_{2}'g^{-1}$ for some $h_{1}', h_{2}'\in H$ and any $g\in G$. Then $$h_{1}h_{2}^{-1}=g h_{1}'g^{-1} g h_{2}'^{-1}g^{-1}=g h_{1}'h_{2}'^{-1}g^{-1},$$so $h_{1}h_{2}^{-1}\in H_{G}$.
It is clear that $H_{G} \triangleleft G$. Now let $K\triangleleft G$ such that $K\leq H$. Then for all $k\in K$, we have $k=g k' g^{-1}$ for some $k'\in K\leq H$, so $k\in H_{G}$. Thus $K\subseteq H_{G}$, and the result follows. $\square$

> [!proposition]
> Normal core is the kernel of the left multiplication action of $G$ on the left coset space $G/H$.
> 

*Proof*  Recall the left multiplication action of $G$ on the left coset space $G/H$ is given by $$ \varphi\colon G \to S_{[G:H]},\quad g\mapsto (xH \mapsto gxH). $$Then the kernel of $\varphi$ is $$ \ker(\varphi)=\{g\in G\mid gxH=xH,\forall x\in G\}=\{g\in G\mid g\in x H x^{-1},\forall x\in G\}=\bigcap_{x\in G} xHx^{-1}=H_{G}, $$which is exactly the normal core of $H$ in $G$. $\square$

> [!corollary]
> $H$ is normal in $G$ if and only if $H_{G}=H$, if and only if $G=N_{G}(H)$. ^de930c

> [!proposition]
> Suppose $H,K\triangleleft G$, and $H\cap K=\{e\}$, then $H$ commutes with $K$. Moreover, the $H\times K$ can be embedded into $G$ by $(h,k)\mapsto hk$. ^579a54

*Proof*  For all $h\in H$ and $k\in K$, we have $hkh^{-1}k^{-1}\in K$ since $K\triangleleft G$, and $hkh^{-1}k^{-1}\in H$ since $H\triangleleft G$. Therefore, $hkh^{-1}k^{-1}\in H\cap K$, so $hkh^{-1}k^{-1}=e$ which implies that $hk=kh$. Then the "moreover" part is easy to verify. $\square$

## Isomorphisms

>[!definition] Group Isomorphism
> A [group homomorphism](Homomorphisms,%20Normal%20Subgroup%20&%20Conjugation.md#^homo) $\varphi\colon G \to H$ is called an *isomorphism* if it has an inverse, that is a homomorphism $ψ:H →G$ such that $\psi \circ \varphi=e_G$ and $\varphi \circ \psi=e_H$. Equivalently, a homomorphism $φ \colon G \to H$ is an isomorphism if and only if it is [[Relations and Functions#^042daf|bijective]].
> An *automorphism* is an isomorphism from a group $G$ to $G$. We denote $\text{Aut}(G)$ as the set of all automorphisms on $G$. ^c32ca8

<u><b>e.g.</b></u>  
- Any two [[Cyclic Groups#^c52ddd|cyclic group]] of the same order are isomorphic.
- Let $G$ be a [[Groups, Order and Subgroups#^6e0960|group]] and $g \in G$. The map$$ \gamma_{g}\colon G \to G, \quad a \mapsto gag^{-1},$$ called *conjugation by $g$*, is an isomorphism. We first check that $\gamma_g$ is a homomorphism:$$ \gamma_g(ab) = gabg^{-1} = ga(g^{-1}g)bg^{-1} = (gag^{-1})(gbg^{-1})=\gamma_g(a)\gamma_g(b) $$The map is injective because $\gamma_g(a) = e \implies gag^{-1}=e \implies ga=g \implies a=e$. And is surjective since for all $a \in G$, we have $\gamma_g(g^{-1}ag)=a$.
$\quad$

>[!theorem] Cayley’s Theorem
> For every $g \in G$ define a map by left multiplication with $g$: $$\lambda_{g}:G\to G,\quad x\mapsto g x$$
> Then $\lambda_g \in \text{Sym}(G)$, $\lambda_{g^{-1}}$ is the inverse of $\lambda_g$.
> Moreover, the map $\lambda \colon G \to \text{Sym}(G)$ given by $g \mapsto \lambda_g$ is an [[Relations and Functions#^042daf|injective]] group homomorphism. ^dcfefa

*Proof*  Clearly $\lambda(x)\circ\lambda(y)=\lambda(xy)$. Set $\lambda(g)=\lambda_{g}=\text{id}$ where $\text{id}$ is the identity map from $G$ to $G$. Then for all $x\in G$, we have $gx=x$. It follows that $g=1$. Thus $\lambda$ is injective. $\square$

>[!corollary] 
> Every finite group is isomorphic to a subgroup of a [[Permutations and Symmetric Groups#^5b562f|symmetric group]] $S_{n}$.

*Proof*  For any finite group $G$, $\lambda$ is moreover bijective. $\square$