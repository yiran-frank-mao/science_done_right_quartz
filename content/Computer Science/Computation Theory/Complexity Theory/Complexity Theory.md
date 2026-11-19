## Complexity Classes

>[!definition] 
>**Def**  <i><u>Complexity Classes</u></i>
>- $\mathbf{DTIME}(t(n))=\{ L\mid \exists \text{det.TM decides } L \text{ in } o(t(n)) \text{ time} \}$
>- $\mathbf{NTIME}(t(n))=\{ L\mid \exists \text{ndet.TM decides } L \text{ in } o(t(n)) \text{ time}  \}$
>- $\mathbf{DSPACE}(t(n))=\{ L\mid \exists \text{det.TM decides } L \text{ in } o(t(n)) \text{ time}  \}$
>- $\mathbf{NSPACE}(t(n))=\{ L\mid \exists \text{ndet.TM decides } L \text{ in } o(t(n)) \text{ time}  \}$
>They follows that
>- $\mathbf{P} = \cup_{k\in \mathbb{N}}  \mathbf{DTIME}(n^k)$
>- $\mathbf{NP} = \cup_{k\in \mathbb{N}}  \mathbf{NTIME}(n^k)$
>- $\mathbf{PSPACE} = \cup_{k\in \mathbb{N}}\mathbf{DSPACE}(n^k)$
>- $\mathbf{NPSPACE} = \cup_{k\in \mathbb{N}}\mathbf{NSPACE}(n^k)$
>- $\mathbf{expTIME} = \cup_{k\in \mathbb{N}} \mathbf{DTIME}(2^{n^k})$
>- $\mathbf{expSPACE} = \cup_{k\in \mathbb{N}} \mathbf{DSPACE}(2^{n^k})$
>- $\mathbf{NexpTIME} = \cup_{k\in \mathbb{N}} \mathbf{NTIME}(2^{n^k})$
>- $\mathbf{NexpSPACE} = \cup_{k\in \mathbb{N}} \mathbf{NSPACE}(2^{n^k})$
>
>Alternative definition for $\textbf{NP}$: a problem is in $\textbf{NP}$ if we have a polynomial time verification algorithm with polynomial size certificates/proofs.

>[!proposition] 
>**Prop**  
>- $\mathbf{P} \subseteq \mathbf{PSPACE}$ and $\mathbf{NP} \subseteq \mathbf{NPSPACE}$.
>- $\mathbf{expTIME} \subseteq \mathbf{expSPACE}$ and $\mathbf{NexpTIME} \subseteq \mathbf{NexpSPACE}$.
>- $\mathbf{P}\subseteq \mathbf{NP}$ and $\mathbf{expTIME} \subseteq \mathbf{NexpTIME}$.
>- $\mathbf{PSPACE} ⊆ \mathbf{NPSPACE}$ and  $\mathbf{expSPACE} ⊆ \mathbf{NexpSPACE}$.

>[!theorem] 
>**Thrm**  <i><u>Savitch’s Theorem</u></i>
>$\mathbf{PSPACE}=\mathbf{NPSPACE}$ and $\mathbf{expSPACE}=\mathbf{NexpSPACE}$.

## Reductions

>[!definition] 
>**Def**  <i><u>Polytime-Computable</u></i>
>$f : \Sigma^∗ \to \Sigma^∗$ is a polytime-computable function if some polynomial time Turing Machine $M$ exists that halts with just $f(w)$ on its tape, when started on any input $w \in Σ^*$.

>[!definition] 
>**Def**  <i><u>Polynomial Time Mapping-Reducible</u></i>
>$A ⊆ Σ_1^*$ is polynomial time mapping-reducible to $B ⊆ Σ_2^*$, written $A \leq_p B$, if a polytime-computable function $f : Σ^*_1 \to Σ^*_2$ exists. We also say it is a reduction from $A$ to $B$.

>[!definition] 
>**Def**  <i><u>Reduction</u></i>
>A reduction is a polytime-computable map $r: A \to B$ where $A ⊆ Σ_1^*$ and $A ⊆ Σ_1^*$ such that $$w \in A \iff r(w)\in B$$
><u><b>e.g.</b></u>  Reduction from ODD to EVEN: $r(k)=k +1$, so $k$ is odd iff $r(k)$ is even.

## Completeness & Hardness

>[!definition] 
>**Def**  <i><u>$\mathbf{NP}\text{-Hard}$</u></i>
>The definition of $\mathbf{NP}\text{-Hard}$ set is $$\mathbf{NP}\text{-Hard}=\{ L \mid \forall A\in \mathbf{NP}, A \leq_p L  \}$$

>[!definition] 
>**Def**  <i><u>$\mathbf{NP}\text{-Complete}$</u></i>
>A language $L$ is said to be $\mathbf{NP}$-complete if $L \in \mathbf{NP}$ and $L\in \mathbf{NP}\text{-Hard}$. And $\mathbf{NP}\text{-Complete}$ is the set of such languages.

>[!proposition] 
>**Prop**  $\mathbf{NP}$-complete problems are the hardest ones in $\mathbf{NP}$.

>[!theorem] 
> If $L\in \mathbf{NP}\text{-Hard}$ and $L\leq_pM$, then $M\in \mathbf{NP}\text{-Hard}$.

>[!corollary] 
> If  $L\in\mathbf{NP}\text{-Complete}$ and $L\leq_pM$ for some $M\in \mathbf{NP}$, then $M\in\mathbf{NP}\text{-Complete}$.

![P_np_np-complete_np-hard.svg|90%](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/P_np_np-complete_np-hard.svg)

>[!comment]
>List of known $\mathbf{NP}$-complete problems:
>- SAT (first problem proved $\mathbf{NP}\text{-Hard}$) and 3-SAT
>- Graph-Colorability and 3-Graph-Colorability
>- Independent Set and Vertex Cover
>- Hamiltonian path
>- Traveling Salesman Salesman Problem
>$\quad$
