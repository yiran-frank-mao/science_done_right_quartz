## Deck Transformations

> [!definition] Deck Transformation
> A *deck transformation* of a [[Covering Spaces#^b33205|covering space]] $p\colon \widetilde{X} \to X$ is a [[Fundamental Theorem of Covering Spaces#^4783f4|covering space automorphism]] $f\colon \widetilde{X} \to \widetilde{X}$. That is, the following diagram commutes:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/deck_transformation.svg" alt="deck_transformation" style="width:28%;"/>
> In other words, $p \circ f = p$. The set of all deck transformations forms a group under composition, denoted $\newcommand{\Aut}{\mathrm{Aut}}\Aut_X(\widetilde{X})$ or $\Aut_{X}(p)$. ^988018

> [!remark]
> For a path-connected covering space $\widetilde{X}$, a deck transformation is uniquely determined by its action on a single point. (ref. [[Fundamental Theorem of Covering Spaces#^6ba239|proposition]]) If $f(\tilde{x}_0) = g(\tilde{x}_0)$ for two deck transformations $f, g$, then $f=g$.

<u><b>e.g.</b></u>  
- For the covering $p\colon \mathbb{R} \to S^1$ given by $p(t) = e^{2 \pi i t}$, the deck transformations are homeomorphisms $f\colon \mathbb{R} \to \mathbb{R}$ such that $p(f(t)) = p(t)$. This implies $e^{2 \pi i f(t)} = e^{2 \pi i t}$, which holds if and only if $f(t) = t + n$ for some integer $n \in \mathbb{Z}$. The group of deck transformations is therefore isomorphic to the integers under addition: $\Aut_{S^1}(\mathbb{R}) \cong \mathbb{Z}$.
- Consider $\newcommand{\RP}{\mathbb{R}\mathrm{P}}p\colon S^{n} \to \RP^{n}$. Then $\newcommand{\Z}{\mathbb{Z}}\Aut_{\RP^{n}}(S^{n})=\{\mathrm{id}, f\}\cong\Z/(2)$, where $f(x)=-x$. ^80fb30
- Take any $X\neq \emptyset$, and let $\widetilde{X}=\sqcup_{n=1}^{N} X$. i.e., $\widetilde{X}$ is just $N$ copies of $X$. The deck transformations are simply permutations of the $N$ copies, so $\Aut_{X}(\widetilde{X})\cong S_{N}$, the [[Symmetric Group#^5b562f|symmetric group]] on $N$ letters.
$\quad$

> [!proposition]
> If $X$ is [[Connectedness and Paths#^630354|PC]], [[Connectedness and Paths#^ba4f32|LPC]], and [[Fundamental Theorem of Covering Spaces#^a1129b|SLSC]]. Fix some $x_{0}\in X$ and $\tilde{x}_{0}\in \widetilde{X}_{\text{univ}}$, then $\Aut_{X}(\widetilde{X}_{\text{univ}})\cong \pi_{1}(X,x_{0})$.
> 

*Proof*  By the [[Fundamental Theorem of Covering Spaces#^35ad1a|lifting criterion]], for any $\tilde{x}_{1}\in p^{-1}(x_{0})$, there exists a unique lifting map $f\colon (\widetilde{X}_{\text{univ}},\tilde{x}_0) \to (\widetilde{X}_{\text{univ}}, \tilde{x}_{1})$ such that $p\circ f=p$. It is clearly invertible with inverse sending $\tilde{x}_{1}$ to $\tilde{x}_{0}$. Note that $p^{-1}(x_{0})$ is exactly all the homotopy classes of loops at $x_{0}$ (ref. [[Fundamental Theorem of Covering Spaces#^353690|proof of the fundamental theorem of covering spaces]]), so $\Aut_{X}(\widetilde{X})\cong \pi_{1}(X,x_{0})$. $\square$

## Normal Covers

A key question is when the deck transformation group is "large enough" to connect any two points in the same fiber. That is, for $\tilde{x}_0, \tilde{x}_1 \in p^{-1}(x_0)$, when does there exist a deck transformation $f$ with $f(\tilde{x}_0) = \tilde{x}_1$?

> [!definition] Normal Covering Space
> $p\colon \widetilde{X}\to X$ is *normal* if for any $\tilde{x}_{1},\tilde{x}_{2}\in\widetilde{X}$ with $p(\tilde{x}_{1})=p(\tilde{x}_{2})$, there exists a deck transformation $f\in \Aut_{X}(\widetilde{X})$ such that $f(\tilde{x}_{1})=\tilde{x}_{2}$.

> [!remark]+ Topological Interpretation of Normal Covering Spaces
> This means the covering space must "look the same" from the perspective of any two points in the fiber.

<u><b>e.g.</b></u>  Consider the following [[Covering Spaces#^b33205|covering space]] of $S^{1}\vee S^{1}$: <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/normal_covering_space_nonex.svg" alt="normal_covering_space_nonex" style="width:50%;"/>It is not a normal covering space. Observe that at $\tilde{x}_{0}$, $a$ is a loop, but at $\tilde{x}_{1}$, $a$ is just a simple path, so $p_{*}(\pi_{1}(\widetilde{X},\tilde{x}_{0}))\neq p_{*}(\pi_{1}(\widetilde{X},\tilde{x}_{1}))$ (ref. [[Covering Spaces#^92b0f0|remark]]), they are different [[Groups, Order and Subgroups#^1ccb07|subgroups]] of $\pi_1(S^1 \vee S^1)$. Hence, by the [[Fundamental Theorem of Covering Spaces#^35ad1a|lifting criterion]], there is no deck transformation from the point $\tilde{x}_0$ to the point $\tilde{x}_1$.

> [!proposition]
> Suppose $X$ is [[Connectedness and Paths#^630354|PC]] and [[Connectedness and Paths#^ba4f32|LPC]]. Let $p\colon \widetilde{X} \to X$ be a PC [[Covering Spaces#^b33205|covering space]] (automatically LPC) with basepoint $\tilde{x}_0 \in p^{-1}(x_0)$. Let $G:=\pi_{1}(X,x_{0})$ and $H:=p_{*}(\pi_{1}(\widetilde{X},\tilde{x}_{0}))$. Then the following holds:
> - $p\colon \widetilde{X}\to X$ is normal iff $H \triangleleft G$ is a [[Homomorphisms, Normal Subgroup & Conjugation#^normal|normal subgroup]].
> - $\Aut_{X}(\widetilde{X})\cong N(H)/H$, where $N(H)$ is the [[Homomorphisms, Normal Subgroup & Conjugation#^d4bf2b|normaliser]] of $H$ in $G$. In particular, if $p\colon \widetilde{X}\to X$ is normal, then $\Aut_{X}(\widetilde{X})\cong G/H$.
>$\quad$
> 

> [!remark]
> For $X$ [[Connectedness and Paths#^630354|path-connected]],  to check if $p\colon \widetilde{X}\to X$ is normal, it suffices to fix some $x_{0}\in X$ and $\tilde{x}_{0}\in \widetilde{X}$, and check if for any $\tilde{x}_{1}\in p^{-1}(x_{0})$, there exists a deck transformation $f\in \Aut_{X}(\widetilde{X})$ with $f(\tilde{x}_{0})=\tilde{x}_{1}$.
> 

*Proof*  

<u><b>e.g.</b></u>  We can use this to compute the fundamental group of $\RP^{2}$. The antipodal map $S^{2}\to \RP^{2}$ is a 2-sheeted universal cover. Hence $\pi_{1}(\RP^{2})\cong  \pi_{1}(\RP^{2})/\pi_{1}(S^{2}) \cong  \Aut_{\RP^{2}}(S^{2})\cong \mathbb{Z}/2$ (ref. [[Deck Transformations and Normal Covers#^80fb30|example]]). In fact, $\pi_{1}(\RP^{n})=\Z/2$ for all $n\geq 2$, because $S^{n}\to \RP^{n}$ is still the double universal cover.