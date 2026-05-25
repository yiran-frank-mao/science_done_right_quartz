> [!definition] Graded Vector Space
> Given a set $G$, a $G$-graded vector space is a vector space $V$ together with a decomposition into subspaces indexed by $G$: 
> $$ V=\bigoplus_{g\in G} V_{g}. $$
> A *graded linear map* between two $G$-graded vector spaces $V$ and $W$ is a linear map $f\colon V\to W$ such that $f(V_g) \subseteq W_g$ for all $g \in G$. $G$-graded vector spaces with graded linear maps form a category, denoted $\Vect_{\F}^{G}$.
> Alternatively, one can think of it as a [[Functoriality and Naturality#^653948|functor]] $\newcommand{\Vect}{\mathsf{Vect}}\newcommand{\F}{\mathbb{F}}V\colon G \to \Vect_{\F}$, where the set $G$ is treated as a [[Structure of Categories#^008eea|discrete category]] and $\mathsf{Vect}_{\F}$ is the category of vector spaces, and a morphism of $G$-graded vector spaces is a natural transformation between such functors.

By far the most widely-used examples are $\newcommand{\Z}{\mathbb{Z}}G=\Z$ and $\newcommand{\N}{\mathbb{N}}G=\N$. Indeed, the term graded vector space is often used to mean a $G$-graded vector space with one of these choices of $G$. The case $G=\Z/2$ is also important: a $\Z/2$-graded vector space is also called a *supervector space*.

People are usually interested in $G$-graded vector spaces when the set $G$ is equipped with extra structure. In general, adding algebraic structure onto $G$ will add categorical structure onto $\Vect_{\F}^{G}$:

| $G$                  | $\Vect_{\F}^{G}$        |
| -------------------- | ----------------------- |
| Set                  | Category                |
| Monoid               | Monoidal category       |
| Finite Group         | Fusion category         |
| Finite abelian group | Braided fusion category |



