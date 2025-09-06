## Extension of Lie Algebras

> [!definition] Lie Algebra Extension
> An *extension* of a [[Lie Algebra#^5007ba|Lie algebra]] $\newcommand{\g}{\mathfrak{g}}\g$ is another Lie algebra $\hat{\g}$ that is equipped with a [[Relations and Functions#^042daf|surjective]] Lie algebra homomorphism to $\g$.
> For non-trivial extensions, this homomorphism has a kernel $\newcommand{\a}{\mathfrak{a}}\a \subset \hat{g}$, and one says that *$\hat{\g}$ is an extension of $\g$ by $\a$*.
> In particular, if $\a$ happens to be abelian, i.e., its Lie bracket is trivial, then we call it an *abelian extension*.

> [!definition] Center of a Lie Algebra
> The *center* of a [[Lie Algebra#^5007ba|Lie algebra]] $L$ is an abelian Lie subalgebra $Z(L)$, consisting of all elements $z\in L$ such that $[a,z]=0$ for all $a\in L$.
> 

> [!definition] Central Extension
> An abelian Lie algebra extension $\a \hookrightarrow \hat{\g} \to \g$ is called a *central extension* if the Lie bracket of $\hat{\g}$ vanishes as soon as already one of its arguments is in $\a$. That is, $\mathfrak{a}$ lies in the center of $\hat{\g}$.

## The Projective Representation

> [!definition] Projective Representation
> Let $\g$ be a [[Lie Algebra#^5007ba|Lie algebra]] over a field $F$, $V$ be an $F$-vector space. A *projective representation* loosens the requirement of a Lie algebra homomorphism, it allows $\newcommand{\gl}{\mathfrak{gl}}\rho\colon \g \to \gl (V)$ to only satisfy
> $$ \rho([X,Y]) = [\rho(X), \rho(Y)] - \omega(X,Y) I, $$
> for some (typically central) bilinear map $\omega\colon \g \times  \g \to \C$ and identity $I\in\gl(V)$.
> Alternatively, it is a map $\newcommand{\pu}{\mathfrak{pu}}\rho\colon \g \to \pu(V)$.

For a projective representation, the usual Lie bracket relations are preserved up to a scalar, which obstructs them from being honest (linear) representations in $\gl (V)$.
To correct this, one can enlarge the Lie algebra by adding a central element governed by a 2-cocycle $\omega$. This results in a central extension $\hat{\g}=\g \oplus \C Z$ with Lie bracket: $$ [X\oplus tZ, Y\oplus sZ]_{\hat{\g}} = [X,Y] \oplus \omega (X,Y)Z.$$We obtained the following theorem:

> [!theorem]
> A projective representation of a Lie algebra can be lifted to a (linear) representation of its central extension.
> 

*Proof*  Define $\hat{\rho}\colon \hat{\g}\to \gl (V)$ by $\hat{\rho}(X):=\rho(X)$ and $\hat{\rho}(Z)=I$. Then $$\begin{aligned}
\hat{\rho}([X\oplus tZ , Y\oplus sZ]_{\hat{\g}}) &= \rho([X,Y]) + \omega(X,Y) I \\ &= [\rho(X),\rho(Y)] \\ &= [\rho(X)+t I, \rho(Y)+s I] \\ &= [\hat{\rho}(X\oplus t Z), \hat{\rho}(Y\oplus s Z)].\end{aligned}$$Therefore, $\hat{\rho}$ forms a linear representation. $\square$