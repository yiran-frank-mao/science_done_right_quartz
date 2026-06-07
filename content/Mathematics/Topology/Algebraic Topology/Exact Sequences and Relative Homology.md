---
tags:
  - diagram-chase
  - exact-sequence
completed: true
updated: 2025-02-11
---
## Long Exact Sequence of a Good Pair

Let's recall the definition of exact sequences in the context of abelian groups:

![[Abelian Categories#^a7688c]]

> [!definition] Good Pair
> A pair $(X, A)$ with $A \subset X$ is called a *good pair* if $A$ is a non-empty [[Topological Spaces#^0849a0|closed]] subset of $X$ that has an open neighborhood which deformation retracts onto $A$. ^3637ee

![[Long Exact Sequence of a Good Pair#^a8a98c]]

To prove this theorem we need the notion of relative homology and several lemmas:

> [!definition] Relative Chains and Homology
> For any pair $(X,A)$, the *relative chain groups* are defined as the [[Quotients#^6d4873|quotient]] $C_n(X,A) := C_n(X)/C_n(A)$. The boundary map on $C_n(X)$ induces a boundary map $d_{n}\colon C_n(X,A) \to C_{n-1}(X,A)$, turning it into a chain complex. The homology of this complex, denoted $H_n(X,A)$, is called the *relative homology* of the pair $(X,A)$. ^f2fdd7

##  From Short to Long Exact Sequences

> [!lemma] 
> For any pair $(X,A)$, there is a [[Abelian Categories#^0c5eb9|long exact sequence]] relating their homology groups:
> $$\cdots \to H_n(A) \xrightarrow{i_{*}} H_n(X) \xrightarrow{j_{*}} H_n(X,A) \xrightarrow{\partial} H_{n-1}(A) \to \cdots$$

This sequence arises from a short exact sequence of chain complexes. Recall that the relative chain group is defined as the quotient $C_n(X,A) = C_n(X)/C_n(A)$. This gives a short exact sequence of chain complexes: $$0 \to C_*(A) \xrightarrow{i_*} C_*(X) \xrightarrow{j_*} C_*(X,A) \to 0$$where $i_*$ is induced by the inclusion and $j_*$ is the projection. The existence of the long exact sequence in homology is a general algebraic result stated as follows:

> [!proposition] From Short to Long Exact Sequences
> A short exact sequence of chain complexes
> $$0 \to A_* \xrightarrow{i} B_* \xrightarrow{j} C_* \to 0$$
> induces a long exact sequence in homology:
> $$\dots \to H_n(A) \xrightarrow{i_*} H_n(B) \xrightarrow{j_*} H_n(C) \xrightarrow{\partial} H_{n-1}(A) \to \dots$$

> [!remark]- Long Exact Sequence for a Triple
> For a triple of spaces $B \subseteq A \subseteq X$, there is a corresponding long exact sequence of relative homology groups:
> $$\dots \to H_n(A,B) \to H_n(X,B) \to H_n(X,A) \to H_{n-1}(A,B) \to \dots$$
> This arises from the short exact sequence of relative chain complexes:
> $$0 \to C_*(A,B) \to C_*(X,B) \to C_*(X,A) \to 0$$
> This follows from the isomorphism $C_n(X,A) \cong \frac{C_n(X)/C_n(B)}{C_n(A)/C_n(B)}$.

*Proof*  We need to construct the connecting map $\partial$ explicitly, and show that it is well-defined, making the sequence exact.
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/construction_of_connecting_map.svg" alt="https://q.uiver.app/#q=WzAsMjEsWzAsMSwiMCJdLFsxLDEsIkFfe24rMX0iXSxbMSwwLCJcXHZkb3RzIl0sWzIsMSwiQl97bisxfSJdLFszLDEsIkNfe24rMX0iXSxbMiwwLCJcXHZkb3RzIl0sWzMsMCwiXFx2ZG90cyJdLFs0LDEsIjAiXSxbMCwyLCIwIl0sWzEsMiwiQV9uIl0sWzEsMywiQV97bi0xfSJdLFsyLDIsIkJfbiJdLFszLDIsIkNfbiJdLFsyLDMsIkJfe24tMX0iXSxbMywzLCJDX3tuLTF9Il0sWzQsMiwiMCJdLFswLDMsIjAiXSxbNCwzLCIwIl0sWzEsNCwiXFx2ZG90cyJdLFsyLDQsIlxcdmRvdHMiXSxbMyw0LCJcXHZkb3RzIl0sWzAsMV0sWzIsMV0sWzEsMywiaV97bisxfSJdLFszLDQsImpfe24rMX0iXSxbNSwzXSxbNiw0XSxbNCw3XSxbOCw5XSxbMSw5LCJkX3tuKzF9XkEiXSxbOSwxMCwiZF97bn1eQSJdLFs5LDExLCJpX24iXSxbMTEsMTIsImpfbiJdLFsxMSwxMywiZF97bn1eQiJdLFsxMywxNCwial97bi0xfSJdLFsxMiwxNCwiZF97bn1eQyJdLFs0LDEyLCJkX3tuKzF9XkMiXSxbMywxMSwiZF97bisxfV5CIl0sWzEyLDE1XSxbMTAsMTMsImlfe24tMX0iXSxbMTYsMTBdLFsxNCwxN10sWzEwLDE4LCJkX3tuLTF9XkEiXSxbMTMsMTksImRfe24tMX1eQiJdLFsxNCwyMCwiZF97bi0xfV5DIl1d" style="width:50%;"/>
The construction of $\partial\colon H_n(C) \to H_{n-1}(A)$ is a classic example of a diagram chase:
1.  Take a homology class $[c] \in H_n(C)$ and choose a representative cycle $c \in \ker(d_{n}^{C})\subset C_{n}$ for this class.
2.  Since $j_{n}\colon B_n \to C_n$ is surjective, there exists some $b \in B_n$ such that $j_n(b) = c$.
3.  Consider the boundary $d^B_n(b) \in B_{n-1}$. By the commutativity of the diagram ($j_{n-1} \circ d^B_n = d^C_n \circ j_n$), we have: $$j_{n-1}(d^B_n(b)) = d^C_n(j_n(b)) = d^C_n(c) = 0$$
4.  This implies $d^B_n(b) \in \ker(j_{n-1})$. By exactness at $B_{n-1}$, $\newcommand{\im}{\operatorname{im}}\ker(j_{n-1}) = \im(i_{n-1})$. Therefore, there exists a unique $a \in A_{n-1}$ such that $i_{n-1}(a) = d^B_n(b)$. Uniqueness follows from $i_{n-1}$ being injective.
5.  This element $a$ is a cycle. To see this, note that $i_{n-2}$ is injective, and: $$i_{n-2}(d^A_{n-1}(a)) = d^B_{n-1}(i_{n-1}(a)) = d^B_{n-1}(d^B_n(b)) = 0$$Since $i_{n-2}$ is injective, $d^A_{n-1}(a) = 0$.

Finally, we define $\partial([c]) = [a] \in H_{n-1}(A)$. 
Notice that we made two choices in this construction: the choice of representative cycle  for the homology class $[c]$, and the choice of lift  in $B_n$. We need to show that the resulting homology class $[a]$ is independent of these choices, so that $\partial$ is well-defined.
- **Independence of the representative $c$**: Suppose we choose another representative $c' = c + d^C_{n+1}(c'')$ for the same homology class $[c]$. Since $j_{n+1}$ is surjective, we can find $b'' \in B_{n+1}$ such that $j_{n+1}(b'') = c''$. Let $b' = b + d^B_{n+1}(b'')$. Then $j_n(b') = j_n(b) + j_n(d^B_{n+1}(b'')) = c + d^C_{n+1}(j_{n+1}(b'')) = c + d^C_{n+1}(c'') = c'$. Now, we compute the boundary of $b'$: $$d^B_n(b') = d^B_n(b + d^B_{n+1}(b'')) = d^B_n(b) + d^B_n(d^B_{n+1}(b'')) = d^B_n(b)$$The new element $a$ we find is the same, so the result is unchanged.
- **Independence of the lift $b$**: Suppose we choose a different element $b' \in B_n$ such that $j_n(b') = c$. Then $j_n(b' - b) = c - c = 0$, so $b' - b \in \ker(j_{n}) = \im(i_{n})$. Thus, there exists some $a'' \in A_n$ such that $b' - b = i_n(a'')$, so $b' = b + i_n(a'')$. Now consider the boundary of $b'$: $$d^B_n(b') = d^B_n(b + i_n(a'')) = d^B_n(b) + d^B_n(i_n(a'')) = d^B_n(b) + i_{n-1}(d^A_n(a''))$$The new element $a' \in A_{n-1}$ is defined by $i_{n-1}(a') = d^B_n(b')$. Thus: $$i_{n-1}(a') = i_{n-1}(a) + i_{n-1}(d^A_n(a'')) = i_{n-1}(a + d^A_n(a''))$$Since $i_{n-1}$ is injective, $a' = a + d^A_n(a'')$. This means $a'$ and $a$ are in the same homology class.

Thus, the connecting homomorphism is well-defined. 
To prove the sequence is exact, one must verify that $\im \subseteq \ker$ and $\ker \subseteq \im$ at each group $H_n(A)$, $H_n(B)$, and $H_n(X,A)$. We sketch two of the six required arguments.
1.  **Exactness at $H_n(B)$**: We show $\im(i_*) = \ker(j_*)$.
    * $\im(i_*) \subseteq \ker(j_*)$: For any $[a] \in H_n(A)$, $j_*(i_*[a]) = (j \circ i)_*[a]$. Since the sequence of chain complexes is exact, $j \circ i = 0$, so the induced map is also zero. Thus $j_*(i_*[a])=0$.
2.  **Exactness at $H_n(C)$**: We show $\im(j_*) = \ker(\partial)$.
    * Let $[\beta] \in H_n(B)$, represented by a cycle $b \in B_n$ with $d^B_n(b)=0$. Then $j_*[\beta] = [j_n(b)]$. To compute $\partial(j_*[\beta])$, we follow the construction:
        1.  Representative cycle is $c = j_n(b)$.
        2.  Lift $c$ to $B_n$. We can choose $b$ itself.
        3.  Compute its boundary: $d^B_n(b) = 0$.
        4.  This means the corresponding element $a \in A_{n-1}$ is $0$.
        5.  Therefore, $\partial(j_*[\beta]) = [0] = 0$. So $\im(j_*) \subseteq \ker(\partial)$.
3.  **Exactness at $H_{n-1}(A)$**: We show $\im(\partial) = \ker(i_*)$.
    * Let $[a] \in H_{n-1}(A)$ such that $i_*[a]=0$. We want to find a class $[c] \in H_n(C)$ such that $\partial[c]=[a]$.
        1.  Let $a \in A_{n-1}$ be a cycle representing $[a]$.
        2.  $i_*[a]=0$ means that $i_{n-1}(a)$ is a boundary in $B_{n-1}$. So there is some $b \in B_n$ with $d^B_n(b) = i_{n-1}(a)$.
        3.  Let $c = j_n(b) \in C_n$.
        4.  We check if $c$ is a cycle: $d^C_n(c) = d^C_n(j_n(b)) = j_{n-1}(d^B_n(b)) = j_{n-1}(i_{n-1}(a))$. Since $j_{n-1} \circ i_{n-1} = 0$, we have $d^C_n(c) = 0$.
        5.  So, $[c] \in H_n(C)$. By construction, $\partial[c]$ is the class represented by the element $a'$ such that $i_{n-1}(a') = d^B_n(b)$. But $d^B_n(b)=i_{n-1}(a)$, so $a'=a$.
        6.  Thus $\partial[c]=[a]$, which shows $\ker(i_*) \subseteq \im(\partial)$. 

$\square$

## Applications and Examples

<u><b>e.g.</b></u>  Consider the pair $(D^n, \partial D^n)$. The long exact sequence in reduced homology is:
$$\dots \to \tilde{H}_k(\partial D^n) \to \tilde{H}_k(D^n) \to H_k(D^n, \partial D^n) \to \tilde{H}_{k-1}(\partial D^n) \to \dots$$
Since the disk $D^n$ is contractible, its reduced homology is zero in all dimensions, i.e., $\tilde{H}_k(D^n)=0$ for all $k$. The long exact sequence breaks down into short exact sequences:
$$0 \to H_k(D^n, \partial D^n) \to \tilde{H}_{k-1}(\partial D^n) \to 0$$
This implies that the map between them is an isomorphism:
$$H_k(D^n, \partial D^n) \cong \tilde{H}_{k-1}(\partial D^n)$$
Since $\partial D^n$ is homeomorphic to the sphere $S^{n-1}$, and we know $\tilde{H}_m(S^{n-1})$ is $\mathbb{Z}$ for $m=n-1$ and $0$ otherwise, we conclude:
$$H_k(D^n, \partial D^n) \cong \begin{cases} \mathbb{Z} & k=n \\ 0 & k \neq n \end{cases}$$

<u><b>e.g.</b></u>  Consider the pair $(X, x_0)$ where $x_0$ is a point in $X$. The long exact sequence in reduced homology is:
$$\dots \to \tilde{H}_k(\{x_0\}) \to \tilde{H}_k(X) \to H_k(X, x_0) \to \tilde{H}_{k-1}(\{x_0\}) \to \dots$$
A single point has zero reduced homology in all dimensions, so $\tilde{H}_k(\{x_0\}) = 0$ for all $k$. The sequence again breaks into short exact sequences:
$$0 \to \tilde{H}_k(X) \to H_k(X, x_0) \to 0$$
This gives an isomorphism:
$$\tilde{H}_k(X) \cong H_k(X, x_0)$$
This shows that the relative homology of a space with respect to a point is precisely the reduced homology of that space.

> [!theorem] Excision Theorem
> For any $U \subset A\subset X$ such that $\bar{U} \subset \text{int}(A)$, the inclusion $i\colon (X \setminus U, A \setminus U) \to (X,A)$ induces an isomorphism $i_{*}\colon H_{n}(X \setminus U, A \setminus U) \cong H_{n}(X, A)$. ^0c7a1e

> [!lemma]
> For a good pair $(X,A)$, the relative homology is isomorphic to the reduced homology of the quotient space: $$H_{n}(X,A) \cong H_{n}(X,\{*\}) \cong \tilde{H}_n(X/A).$$


