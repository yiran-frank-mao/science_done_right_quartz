---
updated: 2025-03-02
cssclasses:
  - img-grid
  - img-zoom
---
> [!definition] Yoneda Embedding
> The *Yoneda embedding* is the functor $y \colon \mathsf{C} \to \mathsf{Set}^{\mathsf{C}^\text{op}}$ taking $C ∈ \obj\mathsf{C}$ to the contravariant representable functor: $$y(C)=\Hom_\mathsf{C}(-,C)\colon\mathsf{C}^\mathrm{op}\to\mathsf{Sets},$$and taking $f\colon C\to D$ to the natural transformation: $$y(f)=\Hom_\mathsf{C}(-,f)\colon\Hom_\mathsf{C}(-,C)\to\mathrm{Hom}_\mathsf{C}(-,D).$$

> [!lemma] Yoneda Lemma
> Let $\mathsf{C}$ be a locally small category. For any object $C ∈ \obj\mathsf{C}$ and functor $F ∈ \mathsf{Sets}^{\mathsf{C}^\text{op}}$, there is an isomorphism $$\Hom_{\mathsf{Sets}^{\mathsf{C}^\text{op}}}(y(C),F)\cong F(C)$$which is natural in both $F$ and $C$.
> - Naturality in $F$ means that, given any $θ \colon F → G$, the following diagram commutes:
> ![yonedaLemma_1.svg|300](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/yonedaLemma_1.svg)
> - Naturality in $C$ means that, given any $h \colon C → D$, the following diagram commutes: 
> ![yonedaLemma_2.svg|300](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/yonedaLemma_2.svg)
$\quad$ ^ecd8f3

> [!theorem]
> The Yoneda embedding $y \colon \mathsf{C} → \mathsf{Sets}^{\mathsf{C}^\text{op}}$ is full and faithful.

**Proof**  For any objects $C, D ∈ \obj\mathsf{C}$, we have an isomorphism: $$\Hom_{\mathsf{C}}(C,D)=yD(C)\cong\Hom_{\mathsf{Sets}^{\mathsf{C}^{\text{op}}}}(y(C),y(D))$$And this isomorphism is indeed induced by the functor $y$, since it takes an element $h \colon C → D$ of $yD(C)$ to the natural transformation $θ_h\colon yC → yD$ given by $$\begin{aligned}(\vartheta_h)_{C^{\prime}}(f\colon C^{\prime}\to C)&=yD(f)(h)\\&=\mathrm{Hom}_\mathsf{C}(f,D)(h)\\&=h\circ f\\&=(yh)_{C^{\prime}}(f)\end{aligned}$$where $yh \colon yC → yD$ has component at $C^{\prime}$:$$(yh)_{C^{\prime}}:\mathrm{Hom}(C^{\prime},C)\longrightarrow\mathrm{Hom}(C^{\prime},D),\quad f\mapsto h\circ f$$So, $\vartheta_h=y(h)$.

**Corollary**  <i><u>Yoneda Principle</u></i>
Given objects $A$ and $B$ in any locally small category $\mathsf{C}$, $y(A)\cong y(B)$ implies $A\cong B$, where $y$ is the Yoneda embedding.

**Prop**  If the cartesian closed category $\mathsf{C}$ has coproducts, then $\mathsf{C}$ is distributive, that is, there is always a canonical isomorphism: $$(A\times B)+(A\times C)\cong A\times(B+C)$$