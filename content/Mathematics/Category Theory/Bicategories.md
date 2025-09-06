
>[!definition] 
>**Def**  <i><u>Bicategory</u></i>
>A bicategory or weak $2$-category is a tuple $\require{mhchem}\newcommand{\dom}{\operatorname{\textbf{dom}}}\newcommand{\cod}{\operatorname{\textbf{cod}}}\newcommand{\obj}{\operatorname{\textbf{obj}}}\newcommand{\mor}{\operatorname{\textbf{mor}}}\newcommand{\Hom}{\mathrm{Hom}}(\mathsf{B}, 1, c, a, l, r)$ consisting of
>- A [[Structure of Categories#^2f5c3a|category]] $\mathsf{B}$;
>- **Hom Categories**: for each pair of objects ($0$-cells) $X,Y ∈ \obj \mathsf{B}=\mathsf{B}_{0}$, $\mathsf{B}$ is equipped with a category $\mathsf{B}(X,Y)$, called a hom category.
>	- Its objects are called $1$-cells in $\mathsf{B}$. The collection of all the $1$-cells ($1$-morphisms) in $\mathsf{B}$ is denoted by $\mathsf{B}_{1}$.
>	- Its morphisms are called $2$-cells in $\mathsf{B}$. The collection of all the $2$-cells in $\mathsf{B}$ is denoted by $\mathsf{B}_{2}$.
>	- Composition law and identity morphisms in the category $\mathsf{B}(X,Y)$ are called vertical composition and identity $2$-cells, respectively.
>	- An isomorphism in $\mathsf{B}(X,Y)$ is called an invertible $2$-cell, and its inverse is called a vertical inverse. For a $1$-cell $f$, its identity $2$-cell is denoted by $1_{f}$.
>- **Identity $1$-Cells**: For each object $X ∈ \mathsf{B}_{0}$, denote $\mathbf{1}$ as the singleton category, $$1_{X}\colon \mathbf{1} \to \mathsf{B}(X,X)$$is a functor. We identify the functor $1_{X}$ with the $1$-cell $1_{X}(*) ∈ \mathsf{B}(X, X)$, called the identity $1$-cell of $X$.
>- **Horizontal Composition**: For each triple of objects $X,Y, Z ∈ \mathsf{B}_{0}$, $$c_{X,Y,Z}\colon\mathsf{B}(Y,Z)\times \mathsf{B}(X,Y) \to \mathsf{B}(X,Z)$$is a functor, called the horizontal composition. For $1$-cells $f ∈ \mathsf{B}(X,Y)_{0}$ and $g ∈ \mathsf{B}(Y, Z)_{0}$, and $2$-cells $α ∈ B(X,Y)_{1}$ and $β ∈ B(Y, Z)_{1}$, we use the notations $$c_{X,Y,Z}(g,f)=g \circ f \text{  or  } gf, \quad c_{X,Y,Z}(\alpha, \beta)=\alpha * \beta$$
>- **Associator**: For objects $W, X,Y, Z ∈ \mathsf{B}_{0}$, $$a_{W,X,Y,Z}\colon c_{W,X,Z}{\left(c_{X,Y,Z}\times\mathrm{Id}_{{\mathsf{B}(W,X)}}\right)}\to c_{W,Y,Z}{\left(\mathrm{Id}_{{\mathsf{B}(Y,Z)}}\times c_{W,X,Y}\right)}$$is a natural isomorphism, called the associator, between functors $$\mathsf{B}(Y,Z)\times\mathsf{B}(X,Y)\times\mathsf{B}(W,X)\to\mathsf{B}(W,Z)$$
>- **Unitors**: For each pair of objects $X,Y ∈ \mathsf{B}_{0}$, $$c_{XYY}(1_Y\times\mathrm{Id}_{\mathsf{B}(X,Y)})\xrightarrow{\ell_{XY}}\mathrm{Id}_{\mathsf{B}(X,Y)}\xleftarrow{r_{XY}}c_{XXY}(\mathrm{Id}_{\mathsf{B}(X,Y)}\times1_X)$$are natural isomorphisms, called the left unitor and the right unitor, respectively.
>
>And the following axioms hold for $1$-cells $f\in \mathsf{B}(V,W)_{0}$, $g\in\mathsf{B}(W,X)_{0}$, $h\in\mathsf{B}(X,Y)_{0}$ and $k\in\mathsf{B}(Y,Z)_{0}$:
>- **Unity Axiom**: The middle unity diagram commutes: ![|300](https://i.upmath.me/svg/%0A%5Cusetikzlibrary%7Bcalc%7D%0A%5Cusetikzlibrary%7Bdecorations.pathmorphing%7D%0A%5Ctikzset%7Bcurve%2F.style%3D%7Bsettings%3D%7B%231%7D%2Cto%20path%3D%7B(%5Ctikztostart)%0A%20%20%20%20..%20controls%20(%24(%5Ctikztostart)!%5Cpv%7Bpos%7D!(%5Ctikztotarget)!%5Cpv%7Bheight%7D!270%3A(%5Ctikztotarget)%24)%0A%20%20%20%20and%20(%24(%5Ctikztostart)!1-%5Cpv%7Bpos%7D!(%5Ctikztotarget)!%5Cpv%7Bheight%7D!270%3A(%5Ctikztotarget)%24)%0A%20%20%20%20..%20(%5Ctikztotarget)%5Ctikztonodes%7D%7D%2C%0A%20%20%20%20settings%2F.code%3D%7B%5Ctikzset%7Bquiver%2F.cd%2C%231%7D%0A%20%20%20%20%20%20%20%20%5Cdef%5Cpv%23%231%7B%5Cpgfkeysvalueof%7B%2Ftikz%2Fquiver%2F%23%231%7D%7D%7D%2C%0A%20%20%20%20quiver%2F.cd%2Cpos%2F.initial%3D0.35%2Cheight%2F.initial%3D0%7D%0A%5Ctikzset%7Btail%20reversed%2F.code%3D%7B%5Cpgfsetarrowsstart%7Btikzcd%20to%7D%7D%7D%0A%5Ctikzset%7B2tail%2F.code%3D%7B%5Cpgfsetarrowsstart%7BImplies%5Breversed%5D%7D%7D%7D%0A%5Ctikzset%7B2tail%20reversed%2F.code%3D%7B%5Cpgfsetarrowsstart%7BImplies%7D%7D%7D%0A%5Ctikzset%7Bno%20body%2F.style%3D%7B%2Ftikz%2Fdash%20pattern%3Don%200%20off%201mm%7D%7D%0A%25%20diagram%20begins%3A%0A%25%20https%3A%2F%2Fq.uiver.app%2F%23q%3DWzAsMyxbMCwwLCIoZzFfVylmIl0sWzIsMCwiZygxX1cgZikiXSxbMSwxLCJnZiJdLFswLDEsIlxcYWxwaGEiXSxbMCwyLCJyX2cgKiAxX2YiLDJdLFsxLDIsIjFfZyAqIGxfZiJdXQ%3D%3D%0A%5C%5B%5Cbegin%7Btikzcd%7D%0A%09%7B(g1_W)f%7D%20%26%26%20%7Bg(1_W%20f)%7D%20%5C%5C%0A%09%26%20gf%0A%09%5Carrow%5B%22a%22%2C%20from%3D1-1%2C%20to%3D1-3%5D%0A%09%5Carrow%5B%22%7Br_g%20*%201_f%7D%22'%2C%20from%3D1-1%2C%20to%3D2-2%5D%0A%09%5Carrow%5B%22%7B1_g%20*%20l_f%7D%22%2C%20from%3D1-3%2C%20to%3D2-2%5D%0A%5Cend%7Btikzcd%7D%5C%5D%0A)
>- **Pentagon Axiom**: 
>
>We usually abbreviate a bicategory as above to $\mathsf{B}$.


>[!definition] 
>**Def**  <i><u>Local Property</u></i>
>Suppose $P$ is a property of categories. A bicategory $\mathsf{B}$ is locally $P$ if each hom category in $\mathsf{B}$ has property $P$. In particular, $\mathsf{B}$ is:
>- locally small if each hom category is a small category.
>- locally discrete if each hom category is discrete.
>- locally partially ordered if each hom category is a partially ordered set regarded as a small category.
>$\quad$