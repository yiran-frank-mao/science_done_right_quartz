## Subobjects

>[!definition] Subobject
>A subobject of an object $X$ in a category $\mathbf{C}$ is a [[Morphisms#^4e0259|monomorphism]] $$m\colon M\rightarrowtail X$$Given subobjects $m, m^{\prime}$ of $X$, a morphism $f \colon m \to m^{\prime}$ is an morphism in $\mathbf{C}/X$. Thus we have a category $\mathrm{Sub}_{\mathbf{C}}(X)$ of subobjects of $X$ in $\mathbf{C}$. ^c9da67

>[!definition] Inclusion of Subobjects
>We define the relation of inclusion of subobjects by: $$m \subseteq m^{\prime} \iff\exists f\colon m\to m^{\prime}\in\mor(\mathbf{C}/X)\iff\exists\phi\colon M\to M^{\prime}.m=m^{\prime} \circ \phi$$

>[!definition] Equivalence of Subobjects
>We say that subobjects $m$ and $m^{\prime}$ are equivalent if $m \subseteq m^{\prime}$ and $m^{\prime} \subseteq m$,  write $m\equiv m^{\prime}$.

>[!proposition] 
> Equivalent subobjects have isomorphic domains.

*Proof*  Observe that, if $m\equiv m^{\prime}$ then $m = m^{\prime}f = mf^{\prime}f$, and since $m$ is [[Morphisms#^4e0259|monic]], $f^{\prime}f = 1_{M}$ and similarly $ff^{\prime} = 1_{M^{\prime}}$. So $M \cong M^{\prime}$ via $f$.

>[!example] Comment
> We sometimes abuse notation and language by calling $M$ the subobject when the [[Morphisms#^4e0259|monomorphism]] $m \colon M\to X$ is clear.

>[!definition] 
>**Def**  <i><u>Local Membership</u></i>
>In terms of generalized elements $z \colon Z\to X$ of an object $X$, we define the local membership relation as $$z\in_{X}M$$

## Pullback

>[!definition] Pullback
>In any category $\mathbf{C}$, a pullback of morphisms $f,g$ with $\cod(f) =\cod(g)$ ![|140](https://svgshare.com/i/15ep.svg)consists of morphisms ![|140](https://svgshare.com/i/15fz.svg)such that $f\circ p_{1} = g\circ p_{2}$, and universal with this property. i.e., given any $z_{1} \colon Z→A$ and $z_{2} \colon Z→B$ with $f\circ z_{1} =g \circ z_{2}$, there exists a unique $u\colon Z \to P$ with $z_{1}= p_{1}\circ u$ and $z_{2}= p_{2}\circ u$:
>![|180](https://svgshare.com/i/15eq.svg) And we write such $P$ as $A\times_{C}B$. ^5810df

> [!corollary] 
> If a category $\mathbf{C}$ has binary products and equalizers, then it has pullbacks.

<u><b>e.g.</b></u>  An explicit construction of a pullback in $\mathbf{Sets}$ of objects $f\colon A \to C$ and $g\colon B\to C$ as a subset of the product: $$\{\langle a,b\rangle\mid fa=gb\}=A\times_CB\hookrightarrow A\times B$$

>[!proposition] 
>**Prop**  Given a pullback $A \times_{C} B$ in any category: 
>![|200](https://svgshare.com/i/14Qo.svg)
>If $g$ is [[Objects and Elements#^4e0259|monic]], then $p_{1}$ is [[Objects and Elements#^4e0259|monic]].

>[!lemma] 
>**Lemma**  <i><u>Two-Pullbacks</u></i>
>Consider the commutative diagram below in a category with pullbacks:
>![|300](https://svgshare.com/i/14SP.svg)
>- If the two squares are pullbacks, so is the outer rectangle. That is $$E \times_{A}(A \times_{C} B) \cong E \times_{C} B$$
>- If the right square and outer square are pullbacks, so is the left square.
>$\quad$

**Corollary**  The pullback of a commutative triangle is a commutative triangle. Specifically, given a commutative triangle as on the right end of the following “prism diagram”:

**Prop**  For fixed $h \colon C^{\prime} \to C$ in a category $\mathbf{C}$ with pullbacks, there is a functor$$h^{*}\colon \mathbf{C}/C\to\mathbf{C}/C^{\prime}$$defined by $(\alpha\colon A\to C) \mapsto (\alpha^{\prime}\colon C^{\prime}\times_{C}A \to C^{\prime})$. We call $\alpha^{\prime}$ the pullback of $\alpha$ along $h$.
**Proof**  

**Prop**  A category has finite products and equalizers iff it has pullbacks and a terminal object.
**Proof**  The “only if” direction has already been done. For the other direction, suppose $\mathbf{C}$ has pullbacks and a terminal object $1$.