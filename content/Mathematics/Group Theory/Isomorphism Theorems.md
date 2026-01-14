## First Isomorphism Theorem

> [!proposition]
> Let $f\colon G\to H$ be a group homomorphism, $K=\ker(f)$ and $\pi\colon G\to G/K$ the canonical quotient map. There is a well-defined map $\varphi \colon G/K \to H$ given by $φ(gK) = f (g)$ such that $φ \circ \pi = f$, in other words the following diagram commutes: 
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/first_iso_thm.svg" alt="first_iso_thm" style="width:25%;"/>

> [!theorem] First Isomorphism Theorem
> Let $f : G \to H$ be a group homomorphism. Then $G/\ker(f) \cong \mathrm{im}(f )$. Specifically, the map $\varphi$ given by $$ \varphi:G/\ker(f)\to\operatorname{im}(f), \quad\varphi\left(g\operatorname{ker}(f)\right):=f(g) $$ is a group isomorphism.

*Proof*  Let $K=\ker(f)$. We saw $φ$ is well-defined. It is a homomorphism because
$$ \varphi(g K)\varphi(h K)=f(g)f(h)=f(g h)=\varphi(g h K)=\varphi(g K\cdot h K). $$
The map is clearly surjective as $f$ is surjective. Now compute its kernel:
$$ gK \in \ker \varphi \iff \varphi(gK) = f(g)=e \iff g \in \ker(f)=K \iff gK=K $$

## Second Isomorphism Theorem

> [!theorem] Second Isomorphism Theorem
> Let $G$ be a group, $H ≤ G$ a subgroup and $N \triangleleft G$ a normal subgroup.Then $HN/N \cong H/H \cap N$.

*Proof*

## Third Isomorphism Theorem

**Thrm**  <i><u>Third Isomorphism Theorem</u></i>
Let $G$ be a group and $K, N \triangleleft G$ normal subgroups with $K \subset N$. Then $G/N \cong (G/K)/(N /K)$.
**Proof**

## The Correspondence Theorem

> [!theorem] Correspondence Theorem
> Let $φ \colon G \to G^\prime$ be a [[Relations and Functions#^042daf|surjective]] group homomorphism with kernel $K$ . Then for every subgroup $H^\prime \leq G^\prime$ the inverse image $φ^{−1}(H^\prime)$ is a subgroup of $G$ containing $K$ . The map $H^\prime \mapsto H = φ^{−1}(H^\prime)$ sets up a bijection between the sets$$ \{\text{subgroups of }G \text{ containing }K\} \stackrel{1:1} {\longleftrightarrow}\{\text{subgroups of } G^{\prime}\}$$Under this correspondence $H/K \cong H^{\prime}$, and $H^\prime \triangleleft G^{\prime}$ if and only if $H \triangleleft G$. In particular, that subgroups in a quotient $G/K$ are always of the form $H/K$ for a subgroup $K ≤H ≤G$.


*Proof* See [1, Theorem 2.10.5] or [2, Theorem 2.7.2] or [3, Prop 2.76].

**Prop** Let $G$ be a group and let $H , K \triangleleft G$ be two normal subgroups with $H K = G$ and $H \cap K = \{e\}$. Then $G \cong H \times K$.
**Proof**

