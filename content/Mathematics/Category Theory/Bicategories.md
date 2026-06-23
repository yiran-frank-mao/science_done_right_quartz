
>[!definition] Bicategory
>A *bicategory* or *weak $2$-category* is a tuple $\newcommand{\dom}{\operatorname{dom}}\newcommand{\cod}{\operatorname{cod}}\newcommand{\obj}{\operatorname{obj}}\newcommand{\mor}{\operatorname{mor}}\newcommand{\Hom}{\mathrm{Hom}}(\mathsf{B}, 1, c, a, l, r)$ consisting of
>- A [[Structure of Categories#^2f5c3a|category]] $\mathsf{B}$;
>- *Hom Categories*: for each pair of objects (*$0$-cells*) $X,Y ∈ \obj \mathsf{B}=\mathsf{B}_{0}$, it is equipped with a category $\mathsf{B}(X,Y)$, called a *hom category*.
>	- Its objects are called *$1$-cells* in $\mathsf{B}$. The collection of all the $1$-cells ($1$-morphisms) in $\mathsf{B}$ is denoted by $\mathsf{B}_{1}$.
>	- Its morphisms are called *$2$-cells* in $\mathsf{B}$. The collection of all the $2$-cells in $\mathsf{B}$ is denoted by $\mathsf{B}_{2}$.
>	- Composition law and identity morphisms in the category $\mathsf{B}(X,Y)$ are called *vertical composition* and *identity $2$-cells*, respectively.
>	- An isomorphism in $\mathsf{B}(X,Y)$ is called an invertible $2$-cell, and its inverse is called a vertical inverse. For a $1$-cell $f$, its identity $2$-cell is denoted by $1_{f}$.
>	- For $1$-cells $f,f' \in \mathsf{B}(X,Y)$, we display each $2$-cell $\alpha\colon f\to f'$ in diagrams as: 
>- Identity $1$-Cells: For each object $X ∈ \mathsf{B}_{0}$, denote $\mathbf{1}$ as the singleton category, $$1_{X}\colon \mathbf{1} \to \mathsf{B}(X,X)$$is a functor. We identify the functor $1_{X}$ with the $1$-cell $1_{X}(*) ∈ \mathsf{B}(X, X)$, called the identity $1$-cell of $X$.
>- *Horizontal Composition*: For each triple of objects $X,Y, Z ∈ \mathsf{B}_{0}$, $$c_{X,Y,Z}\colon\mathsf{B}(Y,Z)\times \mathsf{B}(X,Y) \to \mathsf{B}(X,Z)$$is a functor, called the horizontal composition. For $1$-cells $f ∈ \mathsf{B}(X,Y)_{0}$ and $g ∈ \mathsf{B}(Y, Z)_{0}$, and $2$-cells $α ∈ B(X,Y)_{1}$ and $β ∈ B(Y, Z)_{1}$, we use the notations $$c_{X,Y,Z}(g,f)=g \circ f \text{  or  } gf, \quad c_{X,Y,Z}(\alpha, \beta)=\alpha * \beta$$
>- Associator: For objects $W, X,Y, Z ∈ \mathsf{B}_{0}$, $$a_{W,X,Y,Z}\colon c_{W,X,Z}{\left(c_{X,Y,Z}\times\mathrm{Id}_{{\mathsf{B}(W,X)}}\right)}\to c_{W,Y,Z}{\left(\mathrm{Id}_{{\mathsf{B}(Y,Z)}}\times c_{W,X,Y}\right)}$$is a natural isomorphism, called the associator, between functors $$\mathsf{B}(Y,Z)\times\mathsf{B}(X,Y)\times\mathsf{B}(W,X)\to\mathsf{B}(W,Z)$$
>- Unitors: For each pair of objects $X,Y ∈ \mathsf{B}_{0}$, $$c_{XYY}(1_Y\times\mathrm{Id}_{\mathsf{B}(X,Y)})\xrightarrow{\ell_{XY}}\mathrm{Id}_{\mathsf{B}(X,Y)}\xleftarrow{r_{XY}}c_{XXY}(\mathrm{Id}_{\mathsf{B}(X,Y)}\times1_X)$$are natural isomorphisms, called the left unitor and the right unitor, respectively.
>
> And the following axioms hold for all $1$-cells $f\in \mathsf{B}(V,W)_{0}$, $g\in\mathsf{B}(W,X)_{0}$, $h\in\mathsf{B}(X,Y)_{0}$ and $k\in\mathsf{B}(Y,Z)_{0}$:
>- Unity Axiom: The middle unity diagram in $\mathsf{B}(V,X)$ commutes: 
>  <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/bicategory_middle_unity.svg" style="width:40%;"/>
>- Pentagon Axiom: The following diagram in $\mathsf{B}(V,Z)$ commutes: 
>  <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/bicategory_pentagon.svg" style="width:55%;"/>
>
>We usually abbreviate a bicategory as above to $\mathsf{B}$.

<u><b>e.g.</b></u>
- A [[Monoidal Categories#^bc017c|monoidal category]] $\mathsf{C}$ may be regarded a bicategory with a single object $*$, where it serves as the hom category $\mathsf{B}(*, *)$, and the horizontal composition is given by the monoidal product $\otimes$.

>[!definition] 
>**Def**  <i><u>Local Property</u></i>
>Suppose $P$ is a property of categories. A bicategory $\mathsf{B}$ is locally $P$ if each hom category in $\mathsf{B}$ has property $P$. In particular, $\mathsf{B}$ is:
>- locally small if each hom category is a small category.
>- locally discrete if each hom category is discrete.
>- locally partially ordered if each hom category is a partially ordered set regarded as a small category.
>$\quad$