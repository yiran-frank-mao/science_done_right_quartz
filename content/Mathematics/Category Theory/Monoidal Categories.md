> [!definition] Monoidal Category
> A *monoidal category* is a tuple $\newcommand{\obj}{\operatorname{obj}}(\mathsf{C},\otimes,\mathbb{1},\alpha,\lambda,\rho)$ where 
> - $\mathsf{C}$ is a [[Structure of Categories#^2f5c3a|category]];
> - [[Functoriality and Naturality#^653948|functor]] $\otimes\colon \mathsf{C}\times\mathsf{C}\to\mathsf{C}$ is called the *monoidal product*;
> - $\mathbb{1}\in\obj \mathsf{C}$ is called the *monoidal unit*;
> - $\alpha$ is a [[Functoriality and Naturality#^b8c1fd|natural isomorphism]]: $$\alpha_{X,Y,Z}\colon (X\otimes Y)\otimes Z \cong X\otimes (Y\otimes Z)$$for all $\mathsf{C}$-objects $X,Y, Z$, called the *associativity isomorphism*;
> - $\lambda$ and $\rho$ are also natural isomorphisms that $$\lambda\colon\mathbb{1}\otimes X \cong X,\quad \rho\colon X\otimes \mathbb{1}\cong X$$for all $\mathsf{C}$-objects $X$, called the *left unit isomorphism* and the *right unit isomorphism* respectively.
>
> And the following axioms hold:
> - Middle Unity Axiom: 
>   <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/monoidal_cat_triangle.svg" style="width:50%;"/>
> - Pentagon Axiom: 
>   <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/monoidal_cat_pentagon.svg" style="width:80%;"/>
>
> Moreover, a *strict monoidal category* is a monoidal category in which the components of $\alpha$, $\lambda$ and $\rho$ are all identity morphisms. ^bc017c

> [!remark]
> The triangle diagram and the pentagon diagram are somewhat to define the behavior of the tensor product morphisms $1_{X} \otimes \lambda_{Y}$ etc.

<u><b>e.g.</b></u>  
- The category of [[Groups, Order and Subgroups#^6d511a|abelian groups]] $(\mathsf{Ab},\otimes,\mathbb{Z})$ is a monoidal category with the usual tensor product of abelian groups and the group of integers $\mathbb{Z}$ as the monoidal unit.
- The category of sets $(\mathsf{Set}, \sqcup, \emptyset)$ is a monoidal category. The monoidal product is the disjoint union of sets, and the monoidal unit is the empty set.
$\quad$

> [!definition] Enriched Category
> We call a category $\mathsf{C}$ a *$\mathsf{V}$-category*, or *a category enriched in $\mathsf{V}$*, where $\mathsf{V}=(\mathbf{V},\otimes,\mathbb{1},\alpha,\lambda,\rho)$ is a monoidal category, if
> - For each pair of objects $X, Y$ in $\mathsf{C}$, there is an object $\mathsf{C}(X, Y)$ in $\mathbf{V}$, called the *hom object with domain $X$ and codomain $Y$*. Every morphism $f\colon X \to Y$ in $\mathsf{C}$ can be uniquely described by $\tilde{f}\colon \mathbb{1} \to \mathsf{C}(X,Y)$ in $\mathsf{V}$.
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

