**Def**  <i><u>Law of Composition</u></i>
A law of composition on a set $S$ is a rule that takes two elements of $S$ and produces a new one. It is a function $S \times S \rightarrow S$. Depending on the context we will denote a composition law by $(a, b) \mapsto a \circ b, a * b, a+b, a b$.

**Def**  <i><u>Associativity</u></i> and <i><u>Commutativity</u></i>
We say that a law of composition on $S$ is associative if $(ab)c = a(bc)$ for all $a,b,c \in S$
We say that it is commutative if $ab = ba$ for all $a,b \in S$.

**Def**  <i><u>Identity</u></i>
Let *S* be a set with a law of composition. An element $e \in S$ is called an identity of S (or unit, or neutral element) if $ae = ea = a,\forall a \in S$.

**Prop**  For any composition law an identity element (if exists) is unique.
**Proof**  Assume there are two identities $e_1$ and $e_2$. Then we have:$$e_1 = e_1e_2 = e_2$$

**Def**  <i><u>Inverse</u></i>
Let $S$ be a set with a law of composition and identity. An element $a \in S$ is called invertible if there exists $b \in S$ such that $ab = ba = e$.