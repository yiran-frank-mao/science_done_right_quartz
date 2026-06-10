## Monoidal Categories

> [!definition] Monoidal Category
> A *monoidal category* is a tuple $\newcommand{\one}{\mathbb{1}}\newcommand{\obj}{\operatorname{obj}}(\mathsf{C},\otimes,\mathbb{1},\alpha,\lambda,\rho)$ where 
> - $\mathsf{C}$ is a [[Structure of Categories#^2f5c3a|category]];
> - [[Functoriality and Naturality#^653948|functor]] $\otimes\colon \mathsf{C}\times\mathsf{C}\to\mathsf{C}$ is called the *monoidal product*;
> - $\mathbb{1}\in\obj \mathsf{C}$ is called the *monoidal unit*;
> - $\alpha$ is a [[Functoriality and Naturality#^b8c1fd|natural isomorphism]] called an *associator*: $$\alpha_{X,Y,Z}\colon (X\otimes Y)\otimes Z \cong X\otimes (Y\otimes Z)$$for all $\mathsf{C}$-objects $X,Y, Z$, called the *associativity isomorphism*;
> - $\lambda$ and $\rho$ are also natural isomorphisms that $$\lambda\colon\mathbb{1}\otimes X \cong X,\quad \rho\colon X\otimes \mathbb{1}\cong X$$for all $\mathsf{C}$-objects $X$, called the *left unit isomorphism* and the *right unit isomorphism* respectively.
>
> And the following axioms hold:
> - Middle Unity Axiom: 
>   <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/monoidal_cat_triangle.svg" style="width:50%;"/>
> - Pentagon Axiom: 
>   <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/monoidal_cat_pentagon.svg" style="width:80%;"/>
>
> Moreover, a *strict monoidal category* is a monoidal category in which the components of $\alpha$, $\lambda$ and $\rho$ are all identity morphisms. ^bc017c

> [!definition] Monoid Object
> A *monoid object* in a monoidal category $(\mathsf{C},\otimes,\mathbb{1},\alpha,\lambda,\rho)$ is an object $M$ with two morphisms
> - multiplication $\mu\colon M\otimes M \to M$;
> - unit $\eta:\one \to M$,
> 
> such that the unit diagram and the pentagon diagram hold:
> 
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/monoid_object_unit_relation.svg" style="width:50%;"/>
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/monoid_object_pentagon_relation.svg" style="width:50%;"/>
> 
> Dually, a *comonoid object* is a monoid object in the dual category $\mathsf{C}^{\text{op}}$. ^2438f8

<u><b>e.g.</b></u>  
- It is called monoidal because the structure is “monoid-like”. Any monoid $(M, \cdot, 1)$ forms a small monoidal category with object set $M$, $\cdot$ as monoidal product and the identity of $M$ as its identity object.
- The category of [[Groups, Order and Subgroups#^6d511a|abelian groups]] $(\mathsf{Ab},\otimes,\mathbb{Z})$ is a monoidal category with the usual tensor product of abelian groups and the group of integers $\mathbb{Z}$ as the monoidal unit. [[Ring, Field and Integral Domain#^178485|Rings]] are monoid objects.
- The category of sets $(\mathsf{Set}, \sqcup, \emptyset)$ is a monoidal category. The monoidal product is the disjoint union of sets, and the monoidal unit is the empty set.
- The category sets can carry another monoidal category $(\mathsf{Set}, \times, \{*\})$, where the monoidal product is the Cartesian product of sets, and the monoidal unit is the singleton set $\{*\}$. [[Free Groups and Relations#^587eee|Monoids]] are monoid objects; Every set $X$ has a unique comonoid structure given by the diagonal map $X \to X\times X$ and the unique map $X \to \{*\}$.
- The category of vector spaces over a field $\newcommand{\K}{\mathbb{K}}\K$ $(\mathsf{Vect}_{\K}, \otimes_{\K}, \K)$ is a monoidal category with the usual tensor product of vector spaces and the field $\K$ as the monoidal unit. Algebras are monoid objects; coalgebras are comonoid objects.
$\quad$

> [!definition] Monoidal Functor
> A *(lax) monoidal functor* between monoidal categories $(\mathsf{C},\otimes,\mathbb{1},\alpha,\lambda,\rho)$ and $(\mathsf{D},\otimes',\mathbb{1}',\alpha',\lambda',\rho')$ is a tuple $F=(F_{0}, F_{1}, F_{2})$, where functor $F_{1} \colon \mathsf{C} \to \mathsf{D}$ is a functor, $F_{0}\colon \mathbb{1}' \to F(\mathbb{1})$ is a morphism  in $\mathsf{D}$ and $F_{2}\colon F(-)\otimes' F(-) \Rightarrow F(-\otimes -)$ is a natural transformation such that the following diagrams commute for all objects $X,Y,Z$ in $\mathsf{C}$:
> ^e5952b

## The Category of Monoid Objects

> [!definition] Monoid Homomorphism
> For any two monoid objects $M_{1}$ and $M_{2}$, a *monoid homomorphism* $f\colon M_{1}\to M_{2}$ is a morphism in the corresponding Monoidal category that is compatible with the monoid structure. That is, the following diagrams commute:
> 
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/monoid_object_homomorphism.svg" style="width:70%;"/>
> 
> 

> [!proposition]
> The 
> 


## Enriched Categories

> [!definition] Enriched Category ^5e1a68
> We call a category $\mathsf{C}$ a *$\mathsf{V}$-category*, or *a category enriched in $\mathsf{V}$*, where $\mathsf{V}=(\mathbf{V},\otimes,\mathbb{1},\alpha,\lambda,\rho)$ is a monoidal category, if
> - For each pair of objects $X, Y$ in $\mathsf{C}$, there is an object $\mathsf{C}(X, Y)$ in $\mathsf{V}$, called the *hom object with domain $X$ and codomain $Y$*. Every morphism $f\colon X \to Y$ in $\mathsf{C}$ can be uniquely described by $\tilde{f}\colon \mathbb{1} \to \mathsf{C}(X,Y)$ in $\mathsf{V}$.
> - For each triple of objects $X, Y, Z$ in $\mathsf{C}$, there is a morphism $$ m_{X,Y,Z}\colon \mathsf{C}(Y,Z) \otimes \mathsf{C}(X,Y) \to \mathsf{C}(X,Z) $$ in $\mathsf{V}$, called the *composition*;
> - For each object $X$ in $\mathsf{C}$, there is a morphism $$ i_X\colon \mathbb{1} \to \mathsf{C}(X,X) $$ in $\mathsf{V}$, called the *identity of $X$*.
>
> And they make the associativity diagram 
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/enriched_category_associativity.svg" alt="enriched_category_associativity" style="width:80%;"/>
> and the unity diagram
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/enriched_category_unity.svg" alt="enriched_category_unity" style="width:80%;"/>
> commutes for all objects $W,X,Y,Z$ in $\mathsf{C}$.

> [!definition] Preadditive Category
> A *preadditive category* is a category enriched over the monoidal category of abelian groups. ^610215

