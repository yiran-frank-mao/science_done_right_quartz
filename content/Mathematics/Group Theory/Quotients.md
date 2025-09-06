> [!definition] Quotient
> Let $G$ be a group and $N \triangleleft G$ a [normal subgroup](Homomorphisms,%20Normal%20Subgroup%20&%20Conjugation.md#^normal). Let $G /N$ denote the set of cosets (left or right, they are the same) $$ G/N=\{g N\mid g\in G\}. $$

> [!proposition]
> $(G/N, \cdot)$ is a group with composition that $gN\cdot hN:=ghN$ for all $g,h \in G$. And the identity is $N$, while the inverse is given by $g^{-1}N$ for any $gN \in G/N$.

> [!proposition]
> $|G/N|=\frac{|G|}{|N|}=[G:N]$ for finite groups $G$ and $N$.

*Proof*  


**Def**  <i><u>Canonical(Natural) Map</u></i>
Let $G$ be a group and $N \triangleleft G$ a normal subgroup, then the canonical map is defined to be: $$ \pi:G \to G/N, g\mapsto gN $$

**Prop**  The canonical map $\pi$ is a surjective homomorphism whose kernel is $N$.