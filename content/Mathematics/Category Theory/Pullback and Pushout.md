## Subobjects

>[!definition] Subobject
>A *subobject* of an object $X$ in a category $\mathbf{C}$ is a [[Morphisms#^4e0259|monomorphism]] $$m\colon M\rightarrowtail X$$Given subobjects $m, m^{\prime}$ of $X$, a morphism $f \colon m \to m^{\prime}$ is an morphism in $\mathbf{C}/X$. Thus we have a category $\mathrm{Sub}_{\mathbf{C}}(X)$ of subobjects of $X$ in $\mathbf{C}$. ^c9da67

>[!definition] Inclusion of Subobjects
>We define the relation of inclusion of subobjects by: $$m \subseteq m^{\prime} \iff\exists f\colon m\to m^{\prime}\in\mor(\mathbf{C}/X)\iff\exists\phi\colon M\to M^{\prime}.m=m^{\prime} \circ \phi$$

>[!definition] Equivalence of Subobjects
>We say that subobjects $m$ and $m^{\prime}$ are equivalent if $m \subseteq m^{\prime}$ and $m^{\prime} \subseteq m$,  write $m\equiv m^{\prime}$.

>[!proposition] 
> Equivalent subobjects have isomorphic domains.

*Proof*  Observe that, if $m\equiv m^{\prime}$ then $m = m^{\prime}f = mf^{\prime}f$, and since $m$ is [[Morphisms#^4e0259|monic]], $f^{\prime}f = 1_{M}$ and similarly $ff^{\prime} = 1_{M^{\prime}}$. So $M \cong M^{\prime}$ via $f$. $\square$

>[!remark]
> We sometimes abuse notation and language by calling $M$ the subobject when the [[Morphisms#^4e0259|monomorphism]] $m \colon M\to X$ is clear.

>[!definition] Local Membership
>In terms of generalized elements $z \colon Z\to X$ of an object $X$, we define the local membership relation as $$z\in_{X}M$$

## Pullback

>[!definition] Pullback
> In any [[Structure of Categories#^2f5c3a|category]] $\mathsf{C}$, a *pullback* of morphisms $f,g$ with $\newcommand{\cod}{\operatorname{cod}}\cod(f) =\cod(g)$ consists of an object $P$ together with morphisms $p_{1}$, $p_{2}$ such that $f\circ p_{1} = g\circ p_{2}$, and universal with this property. i.e., given any $z_{1} \colon Z→A$ and $z_{2} \colon Z→B$ with $f\circ z_{1} =g \circ z_{2}$, there exists a unique $u\colon Z \to P$ with $z_{1}= p_{1}\circ u$ and $z_{2}= p_{2}\circ u$:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/category_pullback.svg" alt="category_pullback" style="width:25%;"/>
> We write such $P$ as $A\times_{X}B$. ^5810df

<u><b>e.g.</b></u>  In $\mathsf{Set}$, the pullback of functions $f\colon X\to Z$ and $g\colon Y\to Z$ always exists and is given by $$X\times_{Z} Y = \{ (x,y)\in X\times Y \mid f(x)=g(y) \}.$$

> [!corollary] 
> If a category $\mathsf{C}$ has binary products and equalizers, then it has pullbacks.

<u><b>e.g.</b></u>  An explicit construction of a pullback in $\mathsf{Set}$ of objects $f\colon A \to C$ and $g\colon B\to C$ as a subset of the product: $$\{\langle a,b\rangle\mid fa=gb\}=A\times_CB\hookrightarrow A\times B$$

>[!proposition] 
> Given a pullback $A \times_{X} B$ in any category: 
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/category_pullback.svg" alt="category_pullback" style="width:25%;"/>
> If $g$ is [[Morphisms#^4e0259|monic]], then $p_{1}$ is monic as well.

>[!lemma] Two-Pullbacks
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

## Pushout

> [!definition] Pushout
> In any [[Structure of Categories#^2f5c3a|category]] $\mathsf{C}$, a *pushout* of morphisms $f,g$ with $\newcommand{\dom}{\operatorname{dom}}\dom(f) =\dom(g)$ consists of an object $P$ together with morphisms $p_{1}$, $p_{2}$ such that $p_{1}\circ f = p_{2}\circ g$, and universal with this property. i.e., given any $z_{1} \colon Z\to A$ and $z_{2} \colon Z\to B$ with $z_{1} \circ f = z_{2} \circ g$, there exists a unique $u\colon Z \to P$ with $z_{1}= p_{1}\circ u$ and $z_{2}= p_{2}\circ u$:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/category_pushout.svg" alt="category_pushout" style="width:25%;"/>
> We write such $P$ as $A\sqcup_{X}B$.
> 
