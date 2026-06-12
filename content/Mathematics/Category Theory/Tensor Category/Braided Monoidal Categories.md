## Braided Monoidal Category

> [!definition] Braided Monoidal Category ^2361b7
> A *braided monoidal category* is a [[Monoidal Categories#^bc017c|monoidal category]] with an additional structure, a *braiding*, which is a [[Functoriality and Naturality#^b8c1fd|natural isomorphism]] $\tau_{A,B}\colon A\otimes B \to B\otimes A$ that is compatible with the associativity and unit constraints. That is, the following hexagon diagrams commute for all objects $X,Y,Z$:
> 
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/braiding_hexagon_one.svg" style="width:80%;"/>
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/braiding_hexagon_two.svg" style="width:80%;"/>
> 
> A *symmetric monoidal category* is a braided monoidal category with the braiding satisfying the symmetry axiom: $\tau_{A,B}=\tau_{B,A}^{-1}$.

> [!definition] Braided Monoidal Functor
> A *braided monoidal functor* $F$ between two braided monoidal categories is a [[Monoidal Categories#^e5952b|monoidal functor]] such that 

> [!definition] Braided Commutative Monoid Object
> A monoid object $(M,\mu,\eta)$ in a braided monoidal category is *braided commutative* if the following diagram commutes:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/braided_monoid.svg" style="width:35%;"/>
> 

<u><b>e.g.</b></u>  

> 


| Category                                                                | Universal Property                                                              | Category Equivalence                                                                |
| ----------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| $(\mathsf{N}, +, 0)$                                                    | Free monoidal category on a single object $1$                                   | $\mathsf{MonFunc}(\mathsf{N}, \mathsf{C}) \cong \mathsf{C}$                         |
| $(\mathsf{\Delta}, +, 0)$                                               | Free monoidal category on a single monoid $1$                                   | $\mathsf{MonFunc}(\mathsf{\Delta}, \mathsf{C}) \cong \mathsf{Mon}(\mathsf{C})$      |
| $(\mathsf{PlanGraph}, \sqcup, 0)$                                       | Free monoidal category on a single Frobenius object $1$                         | $\mathsf{MonFunc}(\mathsf{PlanGraph}, \mathsf{C}) \cong \mathsf{Frob}(\mathsf{C})$  |
| $(\mathsf{Braid}, +,0)$                                                 | Free braided monoidal category on a single object                               |                                                                                     |
| $(\mathsf{Vine}, +, 0)$                                                 | Free braided monoidal category on a single braided commutative monoid           | $\mathsf{BrMonFunc}(\mathsf{Vine}, \mathsf{C}) \cong \mathsf{C}$                    |
| $(\mathsf{2BrCod}, \sqcup, \emptyset)$                                  | Free braided monoidal category on a single braided Frobenius object             | $\mathsf{BrMonFunc}(\mathsf{2BrCod}, \mathsf{C}) \cong \mathsf{C}$                  |
| $(\mathsf{FinCard}, +, 0)$                                              | Free symmetric monoidal category on on a single commutative monoid $1$          | $\mathsf{SymMonFunc}(\mathsf{FinCard}, \mathsf{C}) \cong \mathsf{cMon}(\mathsf{C})$ |
| [[Morphisms#^2e268d\|Skeleton]] of $(\mathsf{2Cob}, \sqcup, \emptyset)$ | Free symmetric monoidal category on a single commutative Frobenius object $S^1$ | $\mathsf{SymMonFunc}(\mathsf{2Cob}, \mathsf{C}) \cong \mathsf{cFrob}(\mathsf{C})$   |

## Yang-Baxter Property

> [!theorem]
> In a braided monoidal category $(\mathsf{C},\otimes, \one, \alpha,\lambda,\rho,\tau)$, we have the following diagram commutes for all objects $X,Y,Z$:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/braided_category_yb_property_org.svg" style="width:60%;"/>
> 

*Proof*  We cut the diagram into three parts as illustrated below. The left (red) and right (blue) parts are exactly the hexagon axioms for the braiding, and the middle square commutes by naturality of the braiding. Therefore, the whole diagram commutes.  $\square$
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/braided_category_yb_property.svg" style="width:60%;"/>

An immediate consequence of the above theorem is that 

> [!corollary] 
> In a braided monoidal category $(\mathsf{C},\otimes, \one, \alpha,\lambda,\rho,\tau)$, every $(X, \tau_{X,X})$ is a Yang-Baxter object.
> 

^d7b677

