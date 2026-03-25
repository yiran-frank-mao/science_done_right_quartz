## Products

>[!definition] Product of Objects
>In a category $\mathsf{C}$, a *product* for the objects $A$ and $B$ consists of an object $P$ and arrows $p_{1}\colon P\to A$ and $p_{2}\colon P\to B$:
><img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/category_object_product_1.svg" alt="category_object_product_1" style="width:30%;"/>
>satisfying the following universal property: for all $X$ with $x_{1}$ and $x_2$, there exists unique $u\colon X\to P$ such that the following diagram commutes:
><img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/category_object_product_2.svg" alt="category_object_product_2" style="width:30%;"/>
>We write such product $P$ as $A\times B$, and write $\langle x_{1},x_{2}\rangle$ for $u\colon X\to A\times B$.

<u><b>e.g.</b></u> 
- Products in $\mathsf{Set}$ is [[Construction of Sets#^bd02ce|Cartesian products]].
- Products in $\mathsf{Pos}$ is the meet (i.e., greatest lower bound) as we require that $p\times p\leq p$, $p\times q\leq q$ and $x\leq p,x\leq q\implies x\leq p\times q$.
- Products in $\mathsf{Top}$ is the [[Topological Spaces#^fbf303|product topology]].
$\quad$

>[!proposition] 
> Products are unique up to [[Morphisms#^8927b3|isomorphism]].

**Proof**  Suppose we have $P$ and $Q$ are products of $A,B\in\mathsf{C}_{0}$:
![|250](https://svgshare.com/i/13p9.svg)
Then there is unique $u\colon P\to Q$ such that $q_{2}\circ u=p_{2}$ and $q_{1}\circ u = p_1$. Similarly, exists unique $w\colon Q\to P$ such that $p_{1}\circ w = q_{1}$ and $p_{2}\circ w = q_{2}$. Therefore,$$q_{1}\circ u\circ w=q_{1},\quad p_{1}\circ w\circ u = p_{1} $$It follows that $u\circ w= 1_{Q}$ and $w\circ u=1_{P}$, thus $P\cong Q$.  $\square$

>[!proposition] 
> The binary product of objects is associative up to isomorphism:$$(A\times B)\times C\cong A\times (B\times C)$$

**Def**  <i><u>All Finite Products</u></i>
A category $\mathbf{C}$ is said to have all finite products if it has a terminal object and all binary products. The category $\mathbf{C}$ has all (small) products if every set of objects in $\mathbf{C}$ has a product.

## Duality Principle

>[!proposition] Formal Duality
>For any statement $\Sigma$ in the language of category theory, if $\Sigma$ follows from the axioms for categories, then so does $\Sigma^*$:$$\mathbf{C}\vdash\Sigma \implies \mathbf{C}\vdash\Sigma^*$$

>[!proposition] Conceptual Duality
>For any statement $\Sigma$ about categories, if $\Sigma$ holds for all categories, then so does the dual statement $\Sigma$.

*Proof*  If $\Sigma$ holds for all categories $\mathbf{C}$, then it also holds in all categories $\mathbf{C}^\text{op}$, but then $\Sigma^*$ holds in all categories $(\mathbf{C}^\text{op})^\text{op}$, thus in all categories $\mathbf{C}$. $\square$

## Coproducts

>[!definition] Coproduct
> In any category $\mathsf{C}$, $Q$ is a *coproduct* (dual product) of objects $A$ and $B$ if for any $Z$ and $z_{1}\colon A \to Z$ and $z_{2}\colon B \to Z$, there is a unique $u\colon Q \to Z$ with $u\circ q_i=z_i$ for $i=1,2$, all as indicated in:
><img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/coproduct.svg" style="width:30%;"/>
> In other words, a coproduct of two objects is exactly their product in the opposite category.
> We usually write $Q=A+B$ for the coproduct, and $[z_{1}, z_{2}]$ for the uniquely determined morphism $u \colon A + B \to Z$. And $q_1,q_2$ are usually called *coproduct injections*.
>

<u><b>e.g.</b></u>  
- In $\mathsf{Set}$, the coproduct $A+B$ of two sets is their disjoint union $A+B=\{(a,A)\mid a\in A\}\cup\{(b,B)\mid b\in B\}$ with evident coproduct injections $i_{1}(a)=(a,A)$ and $i_{2}(b)=(b,B)$. And we we have $$[z_{1},z_{2}](x,\delta)=\begin{cases}z_{1}(x)&\delta=A,\\z_{2}(x)&\delta=B.\end{cases}$$So every finite set $A$ is a coproduct: $$A\cong 1+1+\dots+1 \quad \left(\car{A} \text{ times}\right)$$This is because a function $f \colon A \to Z$ is uniquely determined by its values $f(a)$ for all $a ∈ A$.
- If $M(A)$ and $M(B)$ are free [[Free Groups and Relations#^587eee|monoids]] on sets $A$ and $B$, then in $\mathsf{Mon}$ we can construct their coproduct as $M(A)+M(B)\cong M(A+B)$.
- In a fixed poset $\mathsf{Pos}$, a coproduct of two elements $p, q$ is the join (i.e., supremum) of $p$ and $q$.
- In $\mathsf{Group}$, given groups $A$ and $B$, the [[Free Groups and Relations#^f3b924|free group]] of [[Free Groups and Relations#^dc7a31|words]] $G(|A|+|B|)/{\sim}$ is usually called the free product of  $A$ and $B$, written $A \oplus B$ or $A \ast B$. The free product is actually a coproduct.
- In the category $\mathsf{Ab}$ of [[Groups, Order and Subgroups#^6d511a|abelian groups]], the coproduct of $A$ and $B$ is the Cartesian product of the underlying sets $A$ and $B$.
- The tensor product of [[Noncommutative Rings#^2c3d07|algebras]] is the coproduct in the category of commutative algebras $\mathsf{CAlg}$.
$\quad$

> [!proposition]
> In the category $\mathsf{Ab}$ of abelian groups, there is a canonical isomorphism between the binary coproduct and product, $$A+B\cong A\times B.$$

*Proof*  Let $\pi = [\langle1_A,0_B\rangle,\langle0_A,1_B\rangle]\colon A+B\to A\times B$. Then for all $(a,b)\in A+B$, $$\begin{aligned}\pi(a,b)&=[\langle1_A,0_B\rangle,\langle0_A,1_B\rangle](a,b)\\&=\langle1_A,0_B\rangle(a)+\langle0_A,1_B\rangle(b)\\&=(1_A(a),0_B(a))+(0_A(b),1_B(b))\\&=(a,0_B)+(0_A,b)\\&=(a+0_A,0_B+b)\\&=(a,b)\end{aligned}$$$\square$

> [!corollary]
> The following properties hold for coproducts:
> - Coproducts are unique up to isomorphism.
> - Coproducts are associative. That is $(A+B)+C\cong A+(B+C)$.
> $\quad$

 *Proof*  By duality, and the fact that the dual of an isomorphism is an isomorphism. $\square$

>[!definition] Coproduct Functor
> Since we define the coproduct of two morphisms as $$f+f^{\prime}\colon A+A^{\prime}\to B+B^{\prime}$$which leads to a coproduct functor $+ \colon \mathsf{C} \times \mathsf{C} \to \mathsf{C}$ on categories $\mathsf{C}$ with binary coproducts.