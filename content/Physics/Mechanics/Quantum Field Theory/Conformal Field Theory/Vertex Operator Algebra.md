> [!definition] Vertex Algebra
> A *vertex algebra* is a collection of data:
> 1. A [[Vector Spaces#^f4b63e|vector space]] $V$ (usually over $\newcommand{\C}{\mathbb{C}}\C$), called the *state space*.
> 2. An element $\ket{0} \in V$, called the *vacuum vector*.
> 3. An endomorphism $T\colon V \to V$, called the *translation operator*.
> 4. A map $\newcommand{\(}{(\!(}\newcommand{\)}{)\!)} Y\colon V \otimes V \to  V\(z\)$, where $V\(z\)$ denotes the space of formal Laurent series in $z$ with coefficients in $V$. This map is called the *state-field correspondence*.
> 
> These data must satisfy the following axioms:
> 1. Vacuum Axiom: $Y(\ket{0}, z) = \id_{V}$ and $Y(a, z)\ket{0} \in a + zV[[z]]$.
> 2. Translation Axiom: $[T, Y(a, z)] = \partial_z Y(a, z)$ and $T\ket{0} = 0$.
> 3. Locality Axiom: For all $a, b \in V$, there exists an integer $N > 0$ such that $(z - w)^N [Y(a, z), Y(b, w)] = 0$ in $V[[z, w]]$.
> $\quad$
> 
