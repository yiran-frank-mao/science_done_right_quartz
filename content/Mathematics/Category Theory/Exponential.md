
>[!definition] 
>**Def**  <i><u>Exponential</u></i>
>Let the category $\mathbf{C}$ have binary products. An exponential of objects $B$ and $C$ consists of an object $C^{B}$ and an morphism $\epsilon\colon C^B\times B\to C$ such that, for any object $A$ and morphism $f\colon A\times B\to C$ there is a unique morphism $\tilde{f}\colon A\to C^{B}$ such that $$\epsilon\circ(\tilde{f}\times1_B)=f$$And we call such $\epsilon$ evaluation, and $\tilde{f}$  the exponential transpose of $f$. ^8657d1

>[!definition] 
>**Def**  <i><u>Transpose</u></i>
>Given any morphism $g\colon A\to C^{B}$, the transpose of $g$ is given by$$\bar{g}=\epsilon\circ(g\times1_{B})\colon A\times B\to C$$

>[!proposition] 
>**Prop**  $\tilde{\bar{g}}=g$.

**Prop**  $\mathrm{Hom}_\mathbf{C}(A\times B,C)~\cong~\mathrm{Hom}_\mathbf{C}(A,C^B)$.
**Proof**  

>[!definition] 
>**Def**  <i><u>Cartesian Closed</u></i>
>A category is called cartesian closed, if it has all finite products and exponentials.
><u><b>e.g.</b></u>  We already have $\mathbf{Sets}$ as one example, but note that also $\mathbf{Sets}_\text{fin}$ is cartesian closed, since for finite sets $M,N$, the set of functions $N^{M}$ has cardinality $|N^{M}|=|N|^{|M|}$.

**Prop**  In cartesian closed category $\mathbf{C}$, we have $C^{1}=C$ for the terminal object $1$.

**Prop**  In any cartesian closed category $\mathbf{C}$, exponentiation by a fixed object $A$ defines a functor: $$(-)^{A}\colon \mathbf{C}\to\mathbf{C}$$
**Prop**  In a cartesian closed category with coproducts, the products necessarily distribute over the coproducts: $$(A+B)\times C\cong(A\times C)+(B\times C)$$
**Thrm**  In any cartesian closed category $\mathbf{C}$, there is always an isomorphism: $$(A^B)^C\cong A^{(B\times C)}$$for any $\mathbf{C}$-objects $A, B, C$.

**Thrm**  In any cartesian closed category $\mathbf{C}$, there is always an isomorphism: $$\Hom(A,C^{B})\cong\Hom(A\times B, C)$$for any $\mathbf{C}$-objects $A, B, C$.


## Heyting Algebra

**Def**  <i><u>Heyting Algebra</u></i>
A Heyting algebra is a poset with 
1. Finite meets: $1$ and $p ∧ q$
2. Finite joins: $0$ and $p ∨ q$
3. Exponentials: for each $a, b$, an element $a ⇒ b$ such that$$a\wedge b\leq c\text{ iff } a\leq b\Rightarrow c$$
