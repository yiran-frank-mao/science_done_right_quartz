The notion of abelian category is a generalization of $\mathsf{Ab}$, the category of abelian groups.

## Preadditive and Abelian Categories

> [!definition] Preadditive Category
> A *preadditive category* is a category [[Monoidal Categories#^5e1a68|enriched]] over the monoidal category of abelian groups. ^610215

> [!definition] Abelian Category
> A [[Mathematics/Category Theory/Chain Complexes and Abelian Categories#^610215|preadditive]] category is *abelian* if 
> - it has a [[Objects and Elements#^a7dd74|zero object]];
> - it has all binary [[Mathematics/Category Theory/Products of Objects#^728bf5|products]] and [[Mathematics/Category Theory/Products of Objects#^e08759|coproducts]];
> - it has all [[Objects and Elements#^74fe30|kernels]] and [[Objects and Elements#^74fe30|cokernels]];
> - all monomorphisms are *normal*, i.e., it is the kernel of some morphism;
> - all epimorphism is *conormal*, i.e., it is the cokernel of some morphism;
> $\quad$ ^3c8ffc


> [!definition] Exact Sequence
> A sequence of morphisms between objects in an [[Chain Complexes and Abelian Categories#^3c8ffc|abelian category]] $\dots \xrightarrow{f_{n-1}} A_n \xrightarrow{f_n} A_{n+1} \xrightarrow{f_{n+1}} \dots$ is *exact* at $A_n$ if $\text{im}(f_{n-1}) = \ker(f_n)$. The sequence is an *exact sequence* if it is exact at every object.
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/exact_sequence_of_groups.svg" alt="exact_sequence_of_groups" style="width:50%;"/> ^a7688c

> [!definition] Short Exact Sequence & Long Exact Sequence
> A *short exact sequence* is an exact sequence of the form $0 \to A \xrightarrow{i} B \xrightarrow{p} C \to 0$. Consequently,
> - $i$ is [[Morphisms#^4e0259|monic]].
> - $p$ is [[Morphisms#^09ba17|epic]].
> - $A \cong \text{im}(i) = \ker(p)$.
> - $C \cong B/\ker(p) \cong B/\text{im}(i) = \mathrm{coker}(i)$.
> 
> A longer exact sequence is called a *long exact sequence*. ^0c5eb9
