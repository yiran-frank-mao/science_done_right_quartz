**Def**  <i><u>Preorder</u></i>
A preorder is a set $P$ equipped with a binary relation $p \leq q$ that is both reflexive and transitive.

**Prop**  Any preorder $P$ can be regarded as a category by taking the objects to be the elements of $P$ and taking a unique arrow, $$a\to b \iff a\leq b$$**Proof**  For all $A,B, C\in P$, suppose $f\colon A\to B$ and $g\colon B \to C$. We have $g\circ f\colon A\to C$. Since $A\leq B$ and $B\leq C$, by transitivity, $A\leq C$. Additionally, $A\leq A$ guarantees $1_{A}$ exists.