
> [!definition] Monoidal Category
> A monoidal category is a tuple $\newcommand{\obj}{\operatorname{\textbf{obj}}}(\mathbf{C},\otimes,\mathbb{1},\alpha,\lambda,\rho)$ where 
> - $\mathbf{C}$ is a [[Structure of Categories#^2f5c3a|category]];
> - [[Functoriality and Naturality#^653948|functor]] $\otimes\colon \mathbf{C}\times\mathbf{C}\to\mathbf{C}$ is called the monoidal product;
> - $\mathbb{1}\in\obj \mathbf{C}$ is called the monoidal unit;
> - $\alpha$ is a [[Functoriality and Naturality#^b8c1fd|natural isomorphism]]: $$\alpha_{X,Y,Z}\colon (X\otimes Y)\otimes Z \cong X\otimes (Y\otimes Z)$$for all $\mathbf{C}$-objects $X,Y, Z$, called the associativity isomorphism;
> - $\lambda$ and $\rho$ are also natural isomorphisms that $$\lambda\colon\mathbb{1}\otimes X \cong X,\quad \rho\colon X\otimes \mathbb{1}\cong X$$for all $\mathbf{C}$-objects $X$, called the left unit isomorphism and the right unit isomorphism respectively.
>
> And the following axioms hold:
> - **Middle Unity Axiom**:![monoidal_cat_triangle.svg|380](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/monoidal_cat_triangle.svg)
> - **Pentagon Axiom**: ![monoidal_cat_pentagon.svg|600](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/monoidal_cat_pentagon.svg)
>
> Moreover, a strict monoidal category is a monoidal category in which the components of $\alpha$, $\lambda$ and $\rho$ are all identity morphisms. ^bc017c

> [!remark]
> The triangle diagram and the pentagon diagram are somewhat to define the behavior of the tensor product morphisms $1_{X} \otimes \lambda_{Y}$ etc.

