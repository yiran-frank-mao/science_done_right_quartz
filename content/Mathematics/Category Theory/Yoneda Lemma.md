---
updated: 2025-03-02
cssclasses:
  - img-grid
  - img-zoom
---
> [!definition] Yoneda Embedding
> The Yoneda embedding is the functor $y \colon \mathbf{C} → \mathbf{Sets}^{\mathbf{C}^\text{op}}$ taking $C ∈ \obj\mathbf{C}$ to the contravariant representable functor: $$y(C)=\Hom_\mathbf{C}(-,C)\colon\mathbf{C}^\mathrm{op}\to\mathbf{Sets},$$and taking $f\colon C\to D$ to the natural transformation: $$y(f)=\Hom_\mathbf{C}(-,f)\colon\Hom_\mathbf{C}(-,C)\to\mathrm{Hom}_\mathbf{C}(-,D).$$

> [!lemma] Yoneda Lemma
> Let $\mathbf{C}$ be a locally small category. For any object $C ∈ \obj\mathbf{C}$ and functor $F ∈ \mathbf{Sets}^{\mathbf{C}^\text{op}}$, there is an isomorphism $$\Hom_{\mathbf{Sets}^{\mathbf{C}^\text{op}}}(y(C),F)\cong F(C)$$which is natural in both $F$ and $C$.
> - Naturality in $F$ means that, given any $θ \colon F → G$, the following diagram commutes:
> ![yonedaLemma_1.svg|300](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/yonedaLemma_1.svg)
> - Naturality in $C$ means that, given any $h \colon C → D$, the following diagram commutes: 
> ![yonedaLemma_2.svg|300](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/yonedaLemma_2.svg)
$\quad$ ^ecd8f3

> [!theorem]
> The Yoneda embedding $y \colon \mathbf{C} → \mathbf{Sets}^{\mathbf{C}^\text{op}}$ is full and faithful.

**Proof**  For any objects $C, D ∈ \obj\mathbf{C}$, we have an isomorphism: $$\Hom_{\mathbf{C}}(C,D)=yD(C)\cong\Hom_{\mathbf{Sets}^{\mathbf{C}^{\text{op}}}}(y(C),y(D))$$And this isomorphism is indeed induced by the functor $y$, since it takes an element $h \colon C → D$ of $yD(C)$ to the natural transformation $θ_h\colon yC → yD$ given by $$\begin{aligned}(\vartheta_h)_{C^{\prime}}(f\colon C^{\prime}\to C)&=yD(f)(h)\\&=\mathrm{Hom}_\mathbf{C}(f,D)(h)\\&=h\circ f\\&=(yh)_{C^{\prime}}(f)\end{aligned}$$where $yh \colon yC → yD$ has component at $C^{\prime}$:$$(yh)_{C^{\prime}}:\mathrm{Hom}(C^{\prime},C)\longrightarrow\mathrm{Hom}(C^{\prime},D),\quad f\mapsto h\circ f$$So, $\vartheta_h=y(h)$.

**Corollary**  <i><u>Yoneda Principle</u></i>
Given objects $A$ and $B$ in any locally small category $\mathbf{C}$, $y(A)\cong y(B)$ implies $A\cong B$, where $y$ is the Yoneda embedding.

**Prop**  If the cartesian closed category $\mathbf{C}$ has coproducts, then $\mathbf{C}$ is distributive, that is, there is always a canonical isomorphism: $$(A\times B)+(A\times C)\cong A\times(B+C)$$