## Cones and Limits

>[!definition] Diagram
> Suppose $\mathsf{C}$ is a category and $\mathsf{J}$ is a [[Structure of Categories#^20e64e|small category]]. A *diagram of type $\mathsf{J}$* in $\mathsf{C}$ is a functor $D\colon \mathsf{J}\to\mathsf{C}$. We write the objects in the index category $\mathsf{J}$ lower case, $i, j, \dots$ and the values of the functor $D \colon \mathsf{J} → \mathsf{C}$ in the form $D_{i},D_{j},\dots$ etc.

>[!definition] Cone
> A *cone* over a diagram $D \colon \mathsf{J} \to \mathsf{C}$ with the *summit* or *apex* $X \in \mathsf{C}_{0}$ is a [[Naturality#^d73db0|natural transformation]]  $\lambda\colon C \Rightarrow D$ whose domain $C\colon \mathsf{J}\to\mathsf{C}$ is the constant functor at $X$. The components $λ_j \colon C \to D_{j}$ are called the *legs of the cone*. Explicitly:
>- The data of a cone over $D\colon \mathsf{J} → \mathsf{C}$ with summit $C$ is a collection of morphisms $λ_j \colon C \to D_{j}$, indexed by the objects $j ∈ \obj\mathsf{J}$.
>- A family of morphisms $(λ_j \colon C → D_{j})_{j∈\obj\mathsf{J}}$ defines a cone over $D$ if and only if, for each morphism $f \colon k → j$ in $\mathsf{J}$, the following triangle commutes in $\mathsf{C}$:![|200](https://svgshare.com/i/15kz.svg)
>$\quad$

>[!proposition] 
>**Prop**  Cones form a category $\mathbf{Cone}(D)$ for $D\in\obj\mathsf{C}$ by its morphisms are defined by morphisms in $\mathsf{C}$: $$\vartheta\colon (C,\lambda)\to(C^\prime,\lambda^\prime)$$such that the following diagram commutes in $\mathsf{C}$ for all $j\in\obj \mathsf{J}$: 
>![|200](https://svgshare.com/i/15ke.svg)

>[!definition] Limit & Colimit
>A limit for a diagram $D \colon \mathsf{J} → \mathsf{C}$ is a [[Objects and Elements#^a7dd74|terminal object]] in $\mathbf{Cone}(D)$, written as $$\lim_{\leftarrow} D$$A finite limit is a limit for a diagram on a finite index category $\mathsf{J}$. A colimit is an [[Objects and Elements#^a7dd74|initial object]] in the category of cones under $D$. ^d7e9c8

## Continuity

>[!definition] 
>**Def**  <i><u>Continuity</u></i>
>A functor $F \colon \mathsf{C} → \mathbf{D}$ is said to preserve limits of type $\mathsf{J}$ if, whenever $p_{j} \colon L→D_{j}$ is a limit for a diagram $D\colon\mathsf{J}→C$, the cone $Fp_{j}\colon FL\to FD_j$ is then a limit for the diagram $FD \colon \mathsf{J} → \mathbf{D}$. Briefly, $$F(\lim_{\leftarrow} D_j)\cong\lim_{\leftarrow} F(D_j)$$A functor that preserves all limits is said to be continuous.

> [!proposition]
> Representable functors $\Hom(C,-)$ are continuous.

>[!definition] Contravariant Functor
>A functor of the form $F \colon \mathsf{C}^\mathrm{op} → \mathbf{D}$ is called a contravariant functor on $\mathsf{C}$. Explicitly, such a functor takes $f \colon A → B$ to $F(f) \colon F(B) → F(A)$ and $F(g \circ f) = F(f) \circ F(g)$.
><u><b>e.g.</b></u>  A typical example of a contravariant functor is a representable functor of the form, $$\Hom_\mathsf{C}(-,C)\colon\mathsf{C}^\mathrm{op}\to\mathbf{Sets}$$

> [!proposition]
> Contravariant representable functors map all colimits to limits.

>[!definition] 
>**Def**  <i><u>Complete</u></i>
>A complete category is a category in which all small limits exist. That is, a category $\mathsf{C}$ is complete if every diagram $F \colon J → C$ (where $J$ is small) has a limit in $\mathsf{C}$.
><u><b>e.g.</b></u>  $\mathbf{Cat}$ has all small limits and colimits, thus complete.

**Prop**  A category is complete if and only if it has equalizers (of all pairs of morphisms) and all (small) products.

## Inverse Limit

>[!definition] Inverse System
>Let $\mathsf{C}$ be a category, $(I,\leq)$ a [[Preorder, Partial Order and Posets#^fa7f22|poset]]. Suppose $\{X_{i}\}_{i\in I}$ is a family of objects with morphisms $\{f_{ij}\colon X_{j}\to X_{i}\}$ for $i\leq j$ with the following properties:
>- $f_{ii}=\id_{X_{i}}$ for all $i\in I$.
>- $f_{ij}\circ f_{jk}=f_{ik}$ for all $i\leq j\leq k$.
> 
> Then the pair $\left(\{X_{i}\}_{i\in I},\{f_{ij}\}_{i\leq j\in I}\right)$ is called an inverse system in $\mathsf{C}$. ^938e99

> [!definition] Inverse Limit
> Suppose $\left(\{X_{i}\}_{i\in I},\{f_{ij}\}_{i\leq j\in I}\right)$ is an [[Limits and Colimits#^938e99|inverse system]] of objects and morphisms in a category $\mathsf{C}$. The inverse limit of this system is an object $X$ in $\mathsf{C}$ with morphisms $\{\pi_{i}\colon X\to X_{i}\}$, called projections, such that the following diagram commutes for all $i\leq j$, and for all $Y$:
> ![inverse_limit.svg|350](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/inverse_limit.svg)
> The inverse limit is denoted by $\varprojlim X_{i}$. ^24df42
