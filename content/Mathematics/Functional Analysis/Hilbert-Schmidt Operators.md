## Abstract Hilbert-Schmidt Operators

Hilbert-Schmidt operators are a special class of compact operators that play an important role in functional analysis and quantum mechanics. They can be thought of as infinite-dimensional analogues of matrices with finite Frobenius norm.

> [!definition] Hilbert-Schmidt Operator
> An operator $T$ on a [[Hilbert Spaces#^ae0212|Hilbert space]] $\newcommand{\H}{\mathcal{H}}$ is called *Hilbert-Schmidt* if its *Hilbert-Schmidt* norm $$\newcommand{\HS}{\text{HS}}\|T\|^{2}_{\HS} := \sum_{j}\|Te_{j}\|^{2}<\infty. $$  ^5bb53a

e.g.
- In finite-dimensional [Euclidean space](https://www.wikiwand.com/en/articles/Euclidean_space "Euclidean space"), the Hilbert–Schmidt norm is identical to the [Frobenius norm](https://www.wikiwand.com/en/articles/Matrix_norm#Frobenius_norm "Matrix norm").


> [!proposition] 
> The product of two Hilbert-Schmidt operators is a trace class operator. Thus we can define the *Hilbert–Schmidt inner product* of two [[Hilbert-Schmidt Operators#^5bb53a|Hilbert-Schmidt operators]] as $$\newcommand{\Tr}{\operatorname{Tr}}\langle A, B\rangle_{\HS}:= \Tr(B^{*} A)=\sum_{j}\langle Ae_{j}, Be_{j}\rangle.$$
> 

> [!proposition]
> Suppose $\H$ is a complex Hilbert space. Then the space of all Hilbert-Schmidt operators, denoted $B_{\HS}(\H)$ or $S_{2}(\H)$, is an two-sided $*$-ideal in the [[Normed and Banach Algebras#^040470|Banach algebra]] $B(\H)$. Moreover, $B_{\HS}(\H)$ is isometrically isomorphic to the [[Hilbert Spaces#^ae0212|Hilbert space]] tensor product $\overline{\H} \otimes \H$, where $\overline{\H}$ is the conjugate Hilbert space of $\H$.
> This means for each Hilbert-Schmidt operator $T$, we can define a bilinear form $$\beta_{T}\colon \H \times \H \to \C,\quad (x,y) \mapsto \langle x, Ty \rangle_{\H}.$$
> 

*Proof*  

## Integral Operators

> [!definition] Integral Operator
> On $\newcommand{\R}{\mathbb{R}}L^{2}(\R^d)$, we can define an operator $\newcommand{\dd}{\,\mathrm{d}}T_{K}\colon L^{2}(\R^{d})\to L^{2}(\R^{d})$ by the formula $$T_{K}(f):=\int_{\R^{d}} K(x,y)f(y)\dd y,$$ we call it an *integral operator* with associated *kernel* $K\colon \R^{d}\times\R^{d}\to\R$, where $K$ is a measurable function such that $\int_{\R^{d}}|K(x,y)|^{2}\dd y<\infty$ for almost every $x\in\R^{d}$.
> 

> [!proposition] 
> An integral operator $T_{K}$ is *Hilbert-Schmidt* if the associated kernel $K$ is an element of $L^{2}(\R^{d}\times \R^{d})$. 

> [!proposition]
> Let $T$ be a Hilbert-Schmidt operator on $L^{2}(\R^{d})$ with kernel $K$. Then 
> - for every $f\in L^{2}(\R^{d})$, and almost every $x\in \R^{d}$, the function $y\mapsto K(x,y)f(y)$ is integrable.
> - $T$ is bounded, and $\|T\|\leq\|K\|_{L^{2}(\R^{d}\times \R^{d})}$.
> - the adjoint of $T$ is also a Hilbert-Schmidt operator with kernel $\overline{K(y,x)}$.
> $\quad$
