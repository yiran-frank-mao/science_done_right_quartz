
We want extend our definition of Kontsevich integral to tangles, though it preserves the tangle composition, it does not preserve the horizontal stacking, because swapping the endpoints will affect the associated chord diagram.
To solve this, we will make $\otimes$ non-associative.

> [!definition] $\varepsilon$-Parametrised Tangle
> An $\varepsilon$-parametrised tangle is a unit wide tangle with parenthesised words in $\{\uparrow,\downarrow\}$ as ends, and any adjacent endpoints within $n$ closed parentheses are $\varepsilon^{n}$ apart.

<u><b>e.g.</b></u>  

> [!definition] Parenthesised Oriented Tangles
> A parenthesised oriented tangle category $\mathbf{PaTangle}$ is a category with
> - objects being parenthesised words in $\{\uparrow,\downarrow\}$,
> - morphisms being $\varepsilon$-parametrised tangles with objects as ends

<u><b>e.g.</b></u> 
![pt|500](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/parenthesised_tangle.svg)

But it turns out this is not finitely generated, so we need to add one more structure, strand doubling.

> [!theorem]
> There is a one to one correspondence between the set of formality maps for $\mathbf{PaTangle}$ and the set of Drinfeld associators.
 
