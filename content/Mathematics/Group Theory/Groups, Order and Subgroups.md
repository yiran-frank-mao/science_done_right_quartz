## Groups

>[!definition] Group
>A group is a set $G$ together with a composition law $\circ: G \times G \rightarrow G$ such that the following properties hold:
>- **Associativity:** $(a \circ b) \circ c = a \circ (b \circ c)$ for all $a,b,c \in G$.
>- **Identity:** there exists $e \in G$ such that $e \circ a = a \circ e = a$ for all $a \in G$.
>- **Inverse:** for every $a \in G$ there exists $b \in G$ such that $a \circ b = b \circ a = e$.
>
>We may sometime denote the group by $(G,\circ)$ to emphasize the law of composition. ^6e0960

>[!proposition] 
>Let $G$ be a group. Then
>1. For any $a \in G$, the inverse is unique and denoted $a^{-1}$.
>2. For any $a \in G$, $(a^{-1})^{-1} = a$.
>3. $(ab)^{-1} = b^{-1}a^{-1}$.
>4. In $G$ the cancellation laws holds: for $a,b,c \in G$, $ab=ac$ implies that $b=c$.
>$\quad$

## Subgroups and Order

>[!theorem] Generalized Associativity
>Whilst the definition of associativity involves only three elements it implies the generalized associative law, that is, a product of $n$ elements in a group $a_1a_2 · · · a_n$ has the same value regardless of any parentheses.

> [!definition] Abelian Group
> A group is called abelian if the composition law is commutative. ^6d511a

> [!definition] Finite Group
> A group is called finite if $G$ is a finite set; otherwise the group is called infinite. The order of a finite group is the number of elements in a finite group, denoted $|G|$. ^3bce31

**Def**  <i><u>Power</u></i>
- For an element $a$ and in a group $G$ and $n \in \N$ we write $a^{n}$ for the unambiguous composition of $a$ with itself $n$ times (this follows from generalized associativity). We also define $a^{0} := e$ and $a^{−n} = (a^{−1})^n$.
- An element $g \in G$ has finite order if there is $n \in \N$ such that $g^n = e$; the minimal such $n$ is the order of $g$ and denoted $o(g)$. Otherwise we say that $g$ has infinite order.

**Prop**  <i><u>Laws of Exponents</u></i>
Let $G$ be a group, let $a, b ∈ G$ , and let $m$ and $n$ be integers. Then
1. If $a$ and $b$ commute, then $(ab)^n = a^nb^n$.
2. $a^ma^n=a^{m+n}$.
3. $(a^n)^m = a^{mn}$.

> [!definition] Subgroup
> Let $G$ be a group, a nonempty subset $H \subset G$ is called a subgroup of $G$ if it is a group under the same law of composition of $G$. In such case we write $H \leq G$. ^1ccb07


**Thrm**  A nonempty subset $H \subset G$ is a subgroup if and only if it is closed under composition and under taking inverses. That is $a,b \in H \implies ab \in H$ and $a \in H \implies a^{-1} \in H$. The latter two can be consolidated to $a,b \in H \implies ab^{-1} \in H$.