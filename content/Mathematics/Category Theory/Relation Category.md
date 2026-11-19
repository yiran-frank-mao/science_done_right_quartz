---
created: 2024-03-12
updated: 2024-09-17
---
**Def**  <i><u>Relation Category</u></i>
Take sets as objects and take [[Relations and Functions#^d801dc|binary relations]] as morphisms, written as $\mathbf{Rel}$. That is, an morphism $f \colon A \to B$ is a subset $f ⊆ A\times B$. And the identity morphism on a set $A$ is the identity [[Relations and Functions#^d801dc|relation]]:$$1_A=\{(a,a)\in A\times A\mid a\in A\}$$Given $R ⊆ A × B$ and $S ⊆ B × C$, define composition $S \circ R$ by$$(a,c)∈S\circ R \iff \exists b.(a,b)∈R,(b,c)∈S$$**Prop**  $\mathbf{Rel}$ is indeed a [[Structure of Categories#^2f5c3a|category]].
**Proof**  For all morphisms $S\colon A\to B$, $R\colon B\to C$ and $T\colon C\to D$ we have $$(b,c)\in R \circ 1_{B}\iff (b,b)\in 1_{B} , (b,c)\in R$$As $(b,b)\in1_{B}$ is guaranteed by unital definition, we have  $$(b,c)\in R \circ 1_{B}\iff  (b,c)\in R$$Thus $R \circ 1_{B} = R$ and similarly we have $1_{C} \circ R = R$. Moreover, $$\begin{aligned}(a,d)\in(T\circ R) \circ S \iff \exists b\in B.(a,b)\in S,(b,d)\in T \circ R \\
(a,d)\in T\circ (R \circ S) \iff \exists c\in C.(a,c)\in R \circ S,(c,d)\in T\end{aligned}$$Indeed, $$\begin{aligned}&\exists b\in B.(a,b)\in S,(b,d)\in T \circ R \\
\iff &\exists b\in B.(a,b)\in S,\left(\exists c\in C. (b,c)\in R, (c,d)\in T \right) \\
\iff &\exists b\in B.\exists c\in C.(a,b)\in S,(b,c)\in R, (c,d)\in T\end{aligned}$$And similarly $$\exists c\in C.(a,c)\in R \circ S,(c,d)\in T\iff \exists b\in B.\exists c\in C.(a,b)\in S,(b,c)\in R, (c,d)\in T$$Hence $(T\circ R) \circ S = T\circ (R \circ S)$, the composition law is associative.