---
created: 2024-04-23
updated: 2024-10-07
---
>[!definition] Subobject Classifier
>Let $\mathbf{E}$ be a category with all finite limits. A subobject classifier in $\mathbf{E}$ consists of an object $\Omega$ together with an arrow $t \colon 1 → \Omega$ that is a “universal subobject”, i.e. Given any object $E$ and any [[Pullback and Pushout#^c9da67|subobject]] $U\rightarrowtail E$, there is a unique arrow $u \colon E → \Omega$ making the following diagram a [[Pullback and Pushout#^5810df|pullback]]: 
>![|160](https://i.imgur.com/tWUBLo4.png) The arrow $u$ is called the classifying arrow of the subobject $U \rightarrowtail E$.
><u><b>e.g.</b></u>  The most familiar example of a subobject classifier is of course the set $\mathbb{2} = \{0, 1\}$ with a selected element as $t \colon \mathbb{1} → \mathbb{2}$. The fact that every subset $U ⊆ S$ of any set $S$ has a unique characteristic function $u \colon S → \mathbb{2}$ is then exactly the subobject classifier condition.

>[!proposition] 
>A subobject classifier is unique up to [[Morphisms#^8927b3|isomorphism]].
>**Proof**  The pullback condition is clearly equivalent to requiring the contravariant subobject functor $$\mathrm{Sub}_\mathbf{E}(-)\colon\mathbf{E}^\mathrm{op}\to\mathbf{Sets}$$to be representable:$$\mathrm{Sub}_\mathbf{E}(-)\cong\mathrm{Hom}_\mathbf{E}(-,\Omega)$$The required isomorphism is just the pullback condition stated in the definition of a subobject classifier.

**Prop**  For any [[Posets Category#^b87e8b|poset category]] $\mathbf{P}$, the subobject classifier $\Omega$ in $\mathbf{Sets}^\mathbf{P}$ is the functor: $$\Omega(p)=\{F\subseteq\mathbf{P}\mid(x\in F\Rightarrow p\leq x)\land(x\in F\land x\leq y\Rightarrow y\in F)\}$$that is, $\Omega(p)$ is the set of all upper sets above $p$.
**Proof**  


>[!definition] Topos
>A topos is a category $\mathbf{E}$ such that
>- $\mathbf{E}$ has all [[Limits and Colimits#^d7e9c8|finite limits]];
>- $\mathbf{E}$ has a subobject classifier;
>- $\mathbf{E}$ has all [[Exponential#^8657d1|exponentials]].
>$\quad$

>[!proposition] 
>**Prop**  For any [[Structure of Categories#^20e64e|small category]] $\mathbf{C}$, the category of diagrams $\mathbf{Sets}^{\mathbf{C}^{\mathrm{op}}}$ is a topos.