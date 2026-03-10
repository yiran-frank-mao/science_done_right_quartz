> [!definition] Cobordism
> Suppose $\Sigma_{-}$ and $\Sigma_{+}$ are two [[Manifolds and Atlases#^3407e4|closed manifolds]] of dimension $n-1$, then a *cobordism* between $\Sigma_{-}$ and $\Sigma_{+}$ is a [[Compactness of Topological Space#^da2511|compact]] $n$-manifold $M$ whose boundary is $\Sigma_{-}\sqcup \Sigma_{+}$. If such $M$ exists, we say $\Sigma_{-}$ and $\Sigma_{+}$ are *cobordant* to each other. ^4998ff

> [!definition] Oriented Cobordism
> Let $\Sigma_{-}$ and $\Sigma_{+}$ be two oriented [[Manifolds and Atlases#^3407e4|closed manifolds]] of dimension $n-1$. An oriented cobordism from $\Sigma_{-}$ to $\Sigma_{+}$ is a [[Compactness of Topological Space#^da2511|compact]] oriented manifold $M$ together with orientation-preserving smooth maps $\gamma_{\pm}\colon \Sigma_{\pm} \to M$ such that $\Sigma_{\pm}$ maps diffeomorphically onto the in/out-boundary of $M$.
> 

> [!definition] Cobordism Equivalence
> Two oriented cobordisms $(M, \gamma_{-}, \gamma_{+})$ and $(M', \gamma_{-}', \gamma_{+}')$ from $\Sigma_{-}$ to $\Sigma_{+}$ are *equivalent* if there is an orientation-preserving diffeomorphism $\phi\colon M\to M'$ such that the following diagram commutes:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/equivalent_cobordisms.svg" alt="equivalent_cobordisms" style="width:30%;"/>
> Clearly this is an equivalent relation and we can accordingly define a *cobordism class*. ^78cd16

## Axiomatic TQFTs

Atiyah first gave a set of axioms for a topological quantum field theory in 1988, for which is now characterized as a symmetric monoidal functor. The following is a modernized version of Atiyah’s original axioms:

An $n$-dimensional *topological quantum field theory* (TQFT) is a rule $\mathscr{A}$ that assigns to each closed $(n-1)$-dimensional manifold $\Sigma$ a vector space $\mathscr{A}(\Sigma)$, and to each $n$-dimensional cobordism $M\colon \Sigma_{-}\to \Sigma_{+}$ a linear map $\mathscr{A}(M)\colon \mathscr{A}(\Sigma_{-})\to \mathscr{A}(\Sigma_{+})$, such that the following five axioms hold: 
1. Two equivalent cobordisms must have the same image;
2. The cylinder $\Sigma\times [0,1]$ must be sent to the identity map on $\mathscr{A}(\Sigma)$;
3. $\mathscr{A}$ preserves the decomposition of cobordisms;
4. Disjoint union of manifolds must be sent to the tensor product of vector spaces, and disjoint union of cobordisms must be sent to the tensor product of linear maps;
5. The empty manifold must be sent to the ground field $\newcommand{\K}{\mathbb{K}}\K$.

The first two axioms guarantee that the theory is "topological", in the sense that it does not depend on any additional structure like metric or curvature. The fourth axiom is a standard principle of quantum mechanics that the state space of two independent systems is the tensor product of the two state spaces.

> [!proposition]
> The state space $\mathscr{A}(\Sigma)$ assigned to a closed $(n-1)$-manifold $\Sigma$ is always finite-dimensional.

 *Proof*  To show $V:=\mathscr{A}(\Sigma)$ is finite dimensional, it suffices to find a spanning set for $V$. Note that we have the following diagram commutes: 
 <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/state_space_of_TQFT_finite_dim.svg" alt="state_space_of_TQFT_finite_dim" style="width:35%;"/>
$\gamma$ is a copairing $\K\to W \otimes V$, suppose that $\gamma(1_{\K})$ is the finite sum $\sum_{i} c_i w_{i}\otimes v_{i}$, then for each $u\in V$, there holds $$u= (\beta\otimes 1_{V}) (1_{V}\otimes \gamma)(u)=(\beta\otimes 1_{V}) \left(\sum_{i} c_{i} u\otimes w_{i} \otimes v_{i} \right)= \sum_{i}c_{i} \beta(u\otimes w_{i}) v_{i}.$$This means $\{v_{i}\}_{i}$ forms a spanning set for $V$. $\square$

## The Cobordism Category

> [!definition] Cobordism Category
> The *cobordism category* $n\mathsf{Cob}$ is the [[Structure of Categories#^2f5c3a|category]] whose objects are closed $(n-1)$-manifolds, and morphisms are [[Cobordisms#^78cd16|cobordism classes]] between them. The composition of morphisms is given by [[Topological Gluing#^a3afdb|gluing]] of cobordisms, and the identity morphism on $\Sigma$ is given by the cobordism class represented by the cylinder $\Sigma\times [0,1]$.
> 

## Cobordism Classes Induced by Diffeomorphisms

> [!proposition]
> Two diffeomorphisms $\phi_{0},\phi_{1}\colon \Sigma_{0} \to \Sigma_{1}$ induce the same cobordism class if and only if they are [[Homotopy Types#^2c10b4|smoothly homotopic]].
> 

*Proof*  We have the following diagram commute as $\phi_{0}$, $\phi_{1}$ are homotopic:
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/homotopic_diffeomorphisms_give_same_cobordism_class.svg" alt="homotopic_diffeomorphisms_give_same_cobordism_class" style="width:35%;"/>
Let us define $$\eta\colon \Sigma_{0}\times I \to \Sigma_{1}\times I,\quad (x,t)\mapsto (\phi(x,t),t),$$so that the diagram 
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/homotopic_diffeomorphisms_give_same_cobordism_class_2.svg" alt="homotopic_diffeomorphisms_give_same_cobordism_class_2" style="width:35%;"/>
commute. This shows that the induced cobordisms are equivalent. The other implication follows by composing $\eta\colon \Sigma_{0}\times I \to \Sigma_{1}\times I$ with the projection $\Sigma_{1}\times I \to \Sigma_{1}$, we get a homotopy from $\phi_{0}$ to $\phi_{1}$. $\square$

## Disjoint Union and Twists

> [!definition] Twist Map
> 
> 
