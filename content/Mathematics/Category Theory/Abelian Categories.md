The notion of abelian category is a generalization of $\mathbf{Ab}$, the category of abelian groups.

> [!definition] Abelian Category
> A [[Monoidal Categories#^610215|preadditive]] category is *abelian* if 
> - it has a [[Objects and Elements#^a7dd74|zero object]];
> - it has all binary products and coproducts;
> - it has all kernels and cokernels;
> - all monomorphisms and epimorphisms are normal.
> $\quad$ ^3c8ffc

> [!definition] Kernel
> In a preadditive category with a zero object, a *kernel* of a morphism $f: A \to B$ is a morphism $k: K \to A$ such that $f \circ k = 0$ and for any morphism $g: X \to A$ with $f \circ g = 0$, there exists a unique morphism $u: X \to K$ such that $\ker(f) \circ u = g$. That is, the following diagram commutes:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/abelian_category_kernel.svg" style="width:48%;"/>

> [!definition] Exact Sequence
> A sequence of morphisms between objects in an [[Abelian Categories#^3c8ffc|abelian category]] $\dots \xrightarrow{f_{n-1}} A_n \xrightarrow{f_n} A_{n+1} \xrightarrow{f_{n+1}} \dots$ is *exact* at $A_n$ if $\text{im}(f_{n-1}) = \ker(f_n)$. The sequence is an *exact sequence* if it is exact at every object.
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/exact_sequence_of_groups.svg" alt="exact_sequence_of_groups" style="width:50%;"/> ^a7688c

> [!definition] Short Exact Sequence & Long Exact Sequence
> A *short exact sequence* is an exact sequence of the form $0 \to A \xrightarrow{i} B \xrightarrow{p} C \to 0$. Consequently,
> - $i$ is [[Morphisms#^4e0259|monic]].
> - $p$ is [[Morphisms#^09ba17|epic]].
> - $A \cong \text{im}(i) = \ker(p)$.
> - $C \cong B/\ker(p) \cong B/\text{im}(i) = \mathrm{coker}(i)$.
> 
> A longer exact sequence is called a *long exact sequence*. ^0c5eb9
