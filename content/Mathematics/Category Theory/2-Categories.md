## Horizontal Composition

>[!definition] 
>**Def**  <i><u>Pasting Diagram</u></i>
>Given a category $\newcommand{\obj}{\operatorname{\textbf{obj}}}\newcommand{\mor}{\operatorname{\textbf{mor}}}\newcommand{\Hom}{\mathrm{Hom}}\mathbf{C}$, a pasting diagram in $\mathbf{C}$ is a sequence of composable morphisms:
>![|330](https://i.imgur.com/v92Naw3.png)


## 2-Category

>[!definition]
>**Def**  <i><u>2-Category</u></i>
>A 2-category is comprised of:
>- A collection of $0$-cells, also known as objects.
>- A collection of $1$-cells, also known as $1$-morphisms between pairs of objects: $$f\colon A \to B$$
>- A collection of $2$-cells, also known as $2$-morphisms between parallel pairs of $1$-morphisms $\alpha\colon f \Rightarrow g$: ![|170](https://i.imgur.com/m4nU8YQ.png)
>
>So that the following conditions hold:
>- The objects and $1$-morphisms form a category, with identities $1_{C} \colon C → C$.
>- For each fixed pair of objects $C$ and $D$, the $1$-morphisms $f \colon C → D$ and $2$-morphisms between such form a category under an operation called vertical composition with identities $1_{f}\colon f \to f$. ![|170](https://i.imgur.com/R06P5YJ.png)
>- There is also a category whose objects are the objects in which a morphism from $C$ to $D$ is a $2$-cell $\alpha\colon f\Rightarrow g$ under an operation called horizontal composition, with identities $1_{1_{C}}$.
>- The horizontal composite $1_{h} * 1_{f}$ of identities for vertical composition must be the identity $1_{h\circ f}$ for the composite $1$-morphisms.
>- The law of middle four interchange holds.
>$\quad$