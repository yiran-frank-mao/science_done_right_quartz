## Real Symplectic Hilbert Spaces

In the finite-dimensional setting, a vector space admits a symplectic structure only if its dimension is even. For a separable Hilbert space, dimension can no longer be the relevant criterion. Instead, one constructs a symplectic Hilbert space from a compatible complex structure. This section draws heavily on [[Symplectic Hilbert Spaces#^b29f2c|Sec. 2, Ner90]]. However, Neretin's definition of a symplectic Hilbert space is not entirely clear, so we streamline it here:

> [!definition] Symplectic Hilbert Space  
> A *symplectic Hilbert space* is a real separable Hilbert space $\H_{\R}$ with a compatible [[Almost Complex Structures#^5f4098|complex structure]] $J$. That is, a bounded linear operator $J\in B(\H_\R)$ such that 
> $$J^{2}=-\id,\qquad J^*=-J,$$
> where $J^*$ is the adjoint of $J$ with respect to the inner product $\langle\cdot,\cdot\rangle$.
> Then we can define $\omega(x,y):=\langle x, Jy\rangle$ as the canonical [[Symplectic Structures#^b558c2|symplectic form]] on it.

> [!remark]  
> $J^*=-J$ is the exact condition that makes $\omega$ alternating:
> $$\omega(x,y)=\langle x, Jy\rangle = \langle J^*x, y\rangle = -\langle Jx, y\rangle=-\langle y,Jx\rangle = -\omega(y,x).$$

> [!definition] Restricted Symplectic Group  
> Suppose $\H_{\R}$ is a symplectic Hilbert space, then we write $\RSP(\H_{\R}) \subset B(\H_\R)$ for the *restricted symplectic group*, that is, a subgroup of $\mathrm{Sp}(\H_{\R})$ such that the operators can be written as $U(1+T_{\mathrm{HS}})$ for some $J$-unitary operator $U$ and some [[Hilbert-Schmidt Operators#^5bb53a|Hilbert-Schmidt]] operator $\newcommand{\HS}{\mathrm{HS}}T_{\HS}$ on $\H_\R$.

> [!remark]  
> $\RSP(\H_{\R})$ captures the idea of "almost unitary" symplectic operators on a real Hilbert space. Note that if $\H_\R$ is finite-dimensional, then $\RSP(\H_{\R})$ coincides with $\mathrm{Sp}(\H_\R)$. To determine whether a symplectic operator $T$ on $\H_{\R}$ belongs to $\RSP(\H_{\R})$, it suffices to check that $T^{*}T$ is a Hilbert--Schmidt perturbation of the identity. Indeed, if $T^{*}T = 1 + K_{\HS}$, then $K_{\HS}$ is necessarily self-adjoint and compact. By the spectral calculus, $\sqrt{1+K_{\HS}}$ is again a Hilbert--Schmidt perturbation of the identity. Hence, by the polar decomposition,
> $$T = U\sqrt{T^{*}T} = U\sqrt{1+K_{\HS}}$$
> for some partial isometry $U$. Since $T$ is invertible, this partial isometry is in fact unitary.
> Moreover, note that both $\left( U(1+T_{\mathrm{HS}})U'(1+T_{\mathrm{HS}}') \right)^* \left( U(1+T_{\mathrm{HS}})U'(1+T_{\mathrm{HS}}') \right)$ and $U(1+T_{\HS})^{-*}(1+T_{\HS})^{-1}U^{-1}$
> are Hilbert--Schmidt perturbations of the identity. Therefore, $\RSP(\H_{\R})$ is a subgroup of $\mathrm{Sp}(\H_{\R})$.

For a concrete example of an element of $\RSP(\H_{\R})$, see [[Symplectic Hilbert Spaces#^d79082|example]] below, after the introduction of the *complexified symplectic Hilbert space*.

## Complexified Symplectic Hilbert Spaces

In fact, real symplectic Hilbert space is not well suited to our purposes, as it lacks the necessary structure and does not naturally fit into the framework of Fock space representations. We therefore pass to its complexification. Indeed, in Neretin's paper, a symplectic Hilbert space is constructed directly in this complexified sense. The *complexified symplectic Hilbert space* carries additional structure, notably a polarisation presented in the [[Symplectic Hilbert Spaces#^polarisation|proposition]], which allows each vector to be decomposed into a creation-like part and an annihilation-like part. We will discuss this at the beginning of the next section.
Let us first examine these additional structures, apart from the polarisation. Let $(\H_\R,\langle\cdot,\cdot\rangle, J)$ be a symplectic Hilbert space with the canonical symplectic form $\omega$. Define $$\H:=\H_{\R} \otimes \C=\H_{\R} \oplus i\H_{\R}$$ to be the complexification as a Hilbert space. Then the following additional
structures appear canonically on $\H$:
-   A real structure (i.e., conjugation) $C\colon \H \to \H$, $x\mapsto\bar{x}$ that flips the sign of the imaginary part;
-   An inner product $\llangle \cdot, \cdot \rrangle$, extending $\langle\cdot,\cdot\rangle$ sesquilinearly: $\llangle \lambda x,\eta y\rrangle := \lambda \overline{\eta}  \langle x,y \rangle$;
-   A skew Hermitian form $\Lambda$ extends $\omega$ sesquilinearly: $\Lambda(\lambda x,\eta y) := \lambda \overline{\eta} \omega (x, y) = \lambda \overline{\eta}  \langle x,Jy\rangle$;
-   The symplectic form $\omega$ extends to $\H$ bilinearly: $\omega(\lambda x,\eta y):= \lambda \eta \omega(x,y)= \lambda \eta\langle x,Jy\rangle$;
-   The complex structure $J$ extends to $\H$ linearly: $J(\lambda x):=\lambda J(x)$.


> [!proposition] Polarisation of Complexified Symplectic Hilbert Spaces
> Suppose $\H_\R$ is a symplectic Hilbert space with complexification $\H$. Let $\H^{\pm}:=\ker (i \mp J)$, then $\H=\H^{+}\oplus\H^{-}$ orthogonally, and $\H^{\pm}$ are Lagrangian. ^polarisation
> 

*Proof*  Let us first show that $\H=\H^{+}\oplus\H^{-}$. For any $x\in \H$, we can write $x_{-}:=\frac{1}{2}(x+iJ(x))$ and
$x_{+}:=\frac{1}{2}(x-iJ(x))$, then clearly this forms an orthogonal decomposition $x=x_{+}+x_{-}$ with $x_{\pm}\in \H^{\pm}$. Moreover, the only vector that can lie in both $\H^{+}$ and $\H^{-}$ is the zero vector, so the decomposition is unique. In fact, this is the eigenspace decomposition of the operator $J$.
For $x\in \H^{+}$, we have $(i-J)x=0$. For all $y\in \H^{+}$, there holds $$\omega(x,y)=\omega(Jx, Jy)=\omega(ix, iy)=-\omega(x,y),$$ so $\omega(x,y)=0$ and $\H^{+} \subset (\H^{+})^{\omega}$ is isotropic. 
Similarly $\H^{-}$ is also isotropic. To show $\H^{+}$ is maximal, it suffices to show that $\omega(x,\cdot)$ is nondegenerate on $\H^{-}$ for $x\in \H^{+}$. Suppose $\omega(x,y)=0$ for all $y\in \H^{-}$, then $\omega$ will vanish on the whole $\H$. Since $\omega$ is nondegenerate, $x=0$, thus $\omega(x,\cdot)$ is nondegenerate on $\H^{-}$. $\square$

> [!remark]
> The data of a symplectic Hilbert space is equivalent to that of a polarised complex Hilbert space equipped with a compatible real structure. Indeed, given a tuple
> $$(\H, \llangle\cdot,\cdot\rrangle, C, \H^+)$$ 
> consisting of a complex Hilbert space $\H$ with inner product $\llangle\cdot,\cdot\rrangle$, a real structure $C$, and a closed subspace $\H^+$ such that $\H^-=C\H^+$ and $\H=\H^+ \oplus \H^-$ orthogonally, we can recover:
> 1.  A real Hilbert subspace $\H_\R:=\ker(C-\id)$;
> 2.  A bounded linear map $J(x_+ + x_-):= i(x_+ - x_-)$ for $x_\pm\in \H^\pm$ that forms a complex structure on $\H_\R$.
> 
> So that $(\H_\R, \llangle\cdot,\cdot\rrangle|_{\H_\R}, J)$ is a symplectic Hilbert space.

Henceforth in this note, unless otherwise specified, $\H$ denotes a complexified symplectic Hilbert space consisting of the following data: $$(\H=\H_\R\oplus i \H_\R=\H^{+}\oplus \H^{-}, \llangle\cdot,\cdot\rrangle, \omega, \Lambda, J, C).$$

<u><b>e.g.</b></u> Utilising the polarisation on complexified symplectic Hilbert space, we can easily construct a nontrivial example of an operator in $\RSP(\H_{\R})$. Let $\{e_n\}_{n>0}$ be an orthonormal basis of $\H^+$, so $\{\bar{e}_n\}_{n>0}$ is an orthonormal basis of $\H^-$. Fix some $s\in \R$, define $T^s \colon \H \to \H$ by $$T^s(e_1) = \cosh(s)\, e_1 + \sinh(s)\, \bar{e}_1, \qquad T^s(\bar{e}_1) = \sinh(s)\, e_1 + \cosh(s)\, \bar{e}_1,$$and let $T^s$ act as the identity on all other basis vectors. Note that $\{ e_n+\bar{e}_n,\, i(e_n-\bar{e}_n) \}_{n>0}$ is a basis of $\H_\R$. Moreover, $$\begin{aligned} T^{s} (e_1+\bar{e}_1) &=  (\cosh(s)+\sinh(s))(e_1 + \bar{e}_1), \\T^{s} \bigl(i(e_1-\bar{e}_1)\bigr) &= (\cosh(s)-\sinh(s))\, i(e_1 - \bar{e}_1).\end{aligned}$$Hence $T^s|_{\H_\R}\colon \H_\R \to \H_\R$. Since $T^s|_{\H_\R}-1$ has finite rank, it is Hilbert-Schmidt, thus $T^s|_{\H_\R}^*T^s|_{\H_\R}-1$ is Hilbert-Schmidt as well. Furthermore, $T^s|_{\H_\R}$ is diagonal, and its diagonal entries occur in reciprocal pairs. In particular, $$(\cosh(s)+\sinh(s)) (\cosh(s)-\sinh(s)) = \cosh^2(s) - \sinh^2(s) = 1.$$Therefore $T^s|_{\H_\R}$ is symplectic, and hence belongs to $\RSP(\H_{\R})$. ^d79082

We now introduce a semigroup on a complexified symplectic Hilbert space, which serves as an extension of $\RSP(\H_{\R})$. Before doing so, we recall the usual notion of *transpose*:

> [!definition] Transpose
> Suppose $x\in \H$, then $x^{\top}$ is defined as the unique element in $\H$ such that $$\llangle x,y\rrangle = \Lambda(x^{\top}, y),\quad \text{for all } y\in \H.$$ 
> Moreover, for an operator $A\in B(\H)$, the transpose of $A$ is defined as $$A^{\top}x:= \overline{A^{*}\overline{x}},$$
> where $A^{*}$ is the adjoint of $A$ w.r.t the inner product $\llangle\cdot,\cdot\rrangle$.

> [!definition] Correct Operator & Potapov–Ginzburg Matrix
> Given a complexified symplectic Hilbert space $\H$, suppose $T\colon \mathcal{D}\to \H$ is an (possibly unbounded) operator on $\H$. If there exists
> $$\Omega_T \colon \H^+ \oplus \H^- \to \H^- \oplus \H^+, \quad \Omega_T=\begin{pmatrix} K &L \\ L^{\top} & M\end{pmatrix}$$
> satisfying
> $$\begin{pmatrix} f_{-} \\ (Tf)_{+} \end{pmatrix}=\begin{pmatrix} K &L \\ L^{\top} & M\end{pmatrix} \begin{pmatrix} f_{+} \\ (Tf)_{-} \end{pmatrix} \text{ for all } f\in \mathcal{D},$$
> where
> 1.  $K^{\top} =K, M^{\top}= M$;
> 2.  $\|\Omega_{T}\|_{\op}\leq 1, \|K\|_{\op}<1, \|M\|_{\op}<1$;
> 3.  $K$ and $M$ are [[Hilbert-Schmidt Operators#^5bb53a|Hilbert-Schmidt]],
> 
> then $T$ is called a *correct operator*, and $\Omega_T$ is called the *Potapov--Ginzburg transformation (matrix)* of $T$. The collection of correct operators forms a semigroup $\CSP(\H)$ under the usual composition of operators. Additionally, we endow $\CSP(\H)$ with the *strong Hilbert-Schmidt topology* such that $T_n\to T$ if and only if  $$\|K_n-K\|_{\HS} \to 0,\qquad \|M_n-M\|_{\HS}\to 0,$$ and $$L_n \to L, \qquad L^{\top}_n\to L^{\top}$$ strongly.

> [!remark]
> Note that the bottom left entry is $L^{\top}$, not $L^*$. Indeed, it must be $L^\top$. To see this, introduce the notation $\newcommand{\dom}{\mathrm{dom}}\newcommand{\cod}{\mathrm{cod}}\H_{\dom}$ and $\H_{\cod}$ to distinguish the domain and codomain of $T$ (although they coincide as Hilbert spaces, we distinguish them notationally). Then $L \colon \H_{\cod}^{-} \to \H_{\dom}^{-},$ so it is natural that $L^\top \colon \H_{\dom}^{+} \to \H_{\cod}^{+},$ whereas 
> $$L^* \colon \H_{\dom}^{-} \to \H_{\cod}^{-}.$$ 
> Moreover, $L^\top$ can be described as follows. Let 
> $$C_{\dom} \colon \H_{\dom}^+ \xrightarrow{\,\cong\,} \H_{\dom}^{-}, \qquad C_{\cod} \colon \H_{\cod}^{+} \xrightarrow{\,\cong\,} \H_{\cod}^{-}$$
>be the conjugation isomorphisms. Then $L^\top$ is the adjoint of $C_{\dom}^{-1} L  C_{\cod} \colon \H_{\cod}^{+} \to \H_{\dom}^{+}$ with respect to the inner product.

We can use the Potapov-Ginzburg matrix to describe these operators in $\CSP(\H)$. Given an operator $T\in\CSP(\H)$ with the block matrix presentation $$T = \begin{pmatrix} A & B \\ D & E  \end{pmatrix}$$with respect to the decomposition $\H=\H^{+} \oplus \H^{-}$, we have $$\begin{cases} A f_{+} + B f_{-}= (Tf)_{+}, \\ D f_{+} + E f_{-}= (Tf)_{-}.\end{cases}$$If $E$ is invertible, then we can rearrange the above equation to get $$\Omega_{T}=\begin{pmatrix} -E^{-1} D & E^{-1} \\ A-BE^{-1} D & BE^{-1} \end{pmatrix}.$$Conversely, if $\Omega_T=\begin{pmatrix}K&L\\L^{\top}&M\end{pmatrix}$ with invertible $L$, we can express the block matrix of $T$ (w.r.t the decomposition $\H=\H^{+} \oplus \H^{-}$) using $K$, $L$ and $M$: $$T=\begin{pmatrix}L^{\top}-ML^{-1}K & ML^{-1} \\ -L^{-1}K & L^{-1}\end{pmatrix}.$$

<u><b>e.g.</b></u>  Recall the operator $T^s$ from [[Symplectic Hilbert Spaces#^d79082|the previous example]], we claim it is correct. It has the block form $$T^s= \begin{pmatrix}
    A & B \\ \overline{B} & \overline{A}
\end{pmatrix}, \quad A\colon e_n \mapsto (1+\delta_{1,n}(\cosh(s)-1))\, e_n, \quad
   B\colon \bar{e}_n \mapsto \delta_{1,n}\sinh(s)\, e_n,$$where $\overline{A}=CAC$ and $\overline{B}=CBC$. If the Potapov-Ginzburg transformation exists, then by the above equations, it is given by $$\Omega_{T^s} = \begin{pmatrix}
    - \overline{A}^{-1} \overline{B} & \overline{A}^{-1} \\[0.3em]
    A-B\overline{A}^{-1}\overline{B} & B\overline{A}^{-1}
\end{pmatrix}.$$It is straightforward to verify that $$\overline{A}^{-\top}=A-B\overline{A}^{-1}\overline{B}.$$Since $B$ has finite rank, both $-\overline{A}^{-1}\overline{B}$ and $B\overline{A}^{-1}$ are Hilbert-Schmidt and have operator norm $$\left\| -\overline{A}^{-1}\overline{B} \right\|_{\op} = \left\|B\overline{A}^{-1}\right\|_{\op}=|\tanh(s)|<1.$$Hence $T^s$ is correct. So we have obtained an example of an operator which is both restricted symplectic and correct.

## $\RSP(\H_{\R})$ as a subgroup of $\CSP(\H)$

More generally, $\RSP(\H_{\R})$ embeds into $\CSP(\H)$ as a subgroup via complexification, and appears as a boundary of $\CSP(\H)$. This is established in the following theorem, adapted from [[Symplectic Hilbert Spaces#^b29f2c|Sec. 2.3, Ner90]]:

> [!theorem]
>Suppose $\H_\R$ is a symplectic Hilbert space with complexification $\H$. For any almost unitary symplectic operator $T_\R\in \RSP(\H_{\R})$, it can be complexified to an operator $T=T_\R\oplus i T_\R$ on $\H$. Then 
>$$T_\R \in \RSP(\H_{\R}) \iff T\in \CSP(\H) \text{ and }\Omega_{T} \text{ is unitary as an operator on } \H.$$

*Proof*  

$3\implies 1$:  Suppose $\Omega^{*}_{T}\Omega_{T}=1_{\H}$, that is , $$\begin{pmatrix} K^{*}K + L^{\top*} L^{\top} & K^{*}L + L^{\top*}M\\L^{*}K+M^{*}L^{\top} & L^{*}L + M^{*}M\end{pmatrix} = 1_{\H}.\tag{1}$$We can express the block matrix of $T^{*}T$ using $K$, $L$ and $M$: $$T^{*}T=\begin{pmatrix}(L^{\top*}-K^{*}L^{-*}M^{*})(L^{\top}-ML^{-1}K)+K^{*}L^{*}L^{-1}K & (L^{\top*}-K^{*}L^{-*}M^{*})ML^{-1}-K^{*}L^{-*}L^{-1} \\ L^{-*}M^{*}(L^{\top}-ML^{-1}K)-L^{-*}L^{-1}K & L^{-*}M^{*}ML^{-1}+L^{-*}L^{-1}\end{pmatrix}.$$To show that $T\in \RSP(\H)$, it is sufficient to show that $T^{*}T$ is a Hilbert-Schmidt perturbation of the identity. By $(1)$, we can simplify $T^{*}T$ to $$T^{*}T=\begin{pmatrix}K^{*}L^{-*}L^{-1}K+1 & -2K^{*}L^{-*}L^{-1} \\ -2L^{-*}L^{-1}K & 2L^{-*}L^{-1}-1\end{pmatrix}=1_{\H}+\begin{pmatrix}K^{*}L^{-*}L^{-1}K & -2K^{*}L^{-*}L^{-1} \\ -2L^{-*}L^{-1}K & 2L^{-*}L^{-1}-2\end{pmatrix}.$$Note that $K$ is [[Hilbert-Schmidt Operators#^2facfd|Hilbert-Schmidt]], so all of $K^{*}L^{-*}L^{-1}K$, $-2K^{*}L^{-*}L^{-1}$ and $-2L^{-*}L^{-1}K$ are Hilbert-Schmidt. Additionally, for the right-bottom entry, we have $$2L^{-*}L^{-1}-2=2((LL^{*})^{-1}-1)=2\left(L(1-M^{*}M)^{-1}L^{-1}-1\right)=2L\left((1-M^{*}M)^{-1}-1\right)L^{-1}.$$Now use the resolvent identity $$(1-M^{*}M)^{-1}-1=(1-M^{*}M)^{-1}M^{*}M,$$and the fact that $M^{*}M$ is a trace-class, so the right-bottom entry is Hilbert-Schmidt as well. $\square$

## References
[Neretin, *Holomorphic extensions of representations of the group of diffeomorphisms of the circle*, 1990](https://doi.org/10.1070/sm1990v067n01abeh001321) ^b29f2c