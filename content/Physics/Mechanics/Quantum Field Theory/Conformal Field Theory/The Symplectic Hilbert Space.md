Given a complex [[Hilbert Spaces#^ae0212|Hilbert space]] $\newcommand{\C}{\mathbb{C}}\newcommand{\H}{\mathcal{H}}\newcommand{\G}{\mathcal{G}}\H_{J}$ with an inner product $\langle\cdot,\cdot\rangle$ and a [[Almost Complex Structures#^5f4098|complex structure]] $J$, let $\newcommand{\R}{\mathbb{R}}\H_{\R}$ be the same set considered as a vector space over $\R$. Define $\H$ to be the complexification of $\H_{\R}$:$$\H:=\H_{\R} \otimes \C=\H_{\R} \oplus i\H_{\R}.$$Observe the following structures on $\H$:
1. A conjugate $\overline{ }\colon \H \to \H$ that flips the sign of the imaginary part;
2. An [[Inner Products#^ad5686|inner product]] $\newcommand{\llangle}{\left\langle\!\left\langle}\newcommand{\rrangle}{\right\rangle\!\right\rangle}\llangle \cdot, \cdot \rrangle$, extending the real part of $\langle\cdot,\cdot\rangle$ sesquilinearly, makes $\H$ a Hilbert space: $$\llangle \lambda x,\eta y\rrangle := \lambda \overline{\eta}  \Re\langle x,y \rangle.$$
3. A [[Symplectic Structures#^b558c2|symplectic form]] $\omega$, extending the imaginary part of $\langle\cdot,\cdot\rangle$ bilinearly: $$\omega(\lambda x,\eta y):= \lambda \eta \Im \langle x,y\rangle.$$
4. A [[Sesquilinear Forms#^5a2a7f|skew Hermitian form]] $\Lambda$, extending the imaginary part of $\langle\cdot,\cdot\rangle$ sesquilinearly: $$\Lambda(\lambda x,\eta y) := \lambda \overline{\eta} \Im \langle x, y\rangle.$$
5. Extend $J$ to $\H$ linearly, so it becomes a [[Almost Complex Structures#^5f4098|complex structure]] on $\H$: $$J(\lambda x)=\lambda J(x).$$

> [!proposition]
> Let $\H^{\pm}:=\ker (i \pm J)$, then $\H=\H^{+}\oplus\H^{-}$, and $\H^{\pm}$ are [[Linear Symplectic Geometry#^651b51|Lagrangian]].
> 

*Proof*  Let us first show that $\H=\H^{+}\oplus\H^{-}$. For any $x\in \H$, we can write $x_{+}:=\frac{1}{2}(x+iJ(x))$ and $x_{-}:=\frac{1}{2}(x-iJ(x))$, then clearly this forms a decomposition $x=x_{+}+x_{-}$ with $x_{\pm}\in \H^{\pm}$. Moreover, the only vector that can lie in both $\H^{+}$ and $\H^{-}$ is the zero vector, so the decomposition is unique. In fact, this is the eigenspace decomposition of the operator $J$.
For $x\in \H^{\pm}$, we have $(i+J)x=0$. For all $y\in \H^{+}$, there holds $$\omega(x,y)=\omega(Jx, Jy)=\omega(ix, iy)=-\omega(x,y),$$so $\omega(x,y)=0$ and $\H^{+} \subset (\H^{+})^{\omega}$ is isotropic. Similarly $\H^{-}$ is also isotropic. To show $\H^{+}$ is maximal, t suffices to show that $\omega(x,\cdot)$ is nondegenerate on $\H^{-}$ for $x\in \H^{+}$. Suppose $\omega(x,y)=0$ for all $y\in \H^{-}$, then $\omega$ will vanish on the whole $\H$. Since $\omega$ is nondegenerate, $x=0$, thus $\omega(x,\cdot)$ is nondegenerate on $\H^{-}$. $\square$

In summary, we have the data $(\H=\H^{+}\oplus \H^{-}, \llangle\cdot,\cdot\rrangle, \omega, \Lambda, J, \overline{ })$

> [!definition] Transpose
> Suppose $x\in \H$, then $x^{\top}$ is defined as the unique element in $\H$ such that $$\llangle x,y\rrangle = \Lambda(x^{\top}, y),\quad \text{for all } y\in \H.$$ 
> Moreover, for an operator $A\in B(\H)$, the transpose of $A$ is defined as $$A^{\top}x:= \overline{A^{*}\overline{x}},$$
> where $A^{*}$ is the adjoint of $A$ w.r.t the inner product $\llangle\cdot,\cdot\rrangle$.

## The Symplectic Semigroup

> [!definition] Restricted Symplectic Semigroup
> Suppose $\G$ is a real symplectic Hilbert space, then we write $\newcommand{\RSP}{\mathrm{RSp}}\RSP(\G)$ for the *restricted symplectic group*, that is, a [[Groups, Order and Subgroups#^1ccb07|subgroup]] of $\mathrm{Sp}(\G)$ such that the operators can be written as $U(1+T_{\mathrm{HS}})$ for some unitary operator $U$ and some [[Compact Operators#^5bb53a|Hilbert-Schmidt]] operator $T_{\mathrm{HS}}\newcommand{\Diff}{\mathrm{Diff}}$.

> [!definition] Correct Operator & Potapov–Ginzburg Matrix
> Given a symplectic Hilbert space $\H$, suppose $T\colon D(T)\to \H$ is an (possibly unbounded) operator on $\H$. If $T$ satisfies $$\begin{pmatrix} f_{-} \\ (Tf)_{+} \end{pmatrix}=\begin{pmatrix} K &L \\ L^{\top} & M\end{pmatrix} \begin{pmatrix} f_{+} \\ (Tf)_{-} \end{pmatrix} \text{ for all } f\in D(T),$$
> where
> 1. $K^{\top} =K$, $M^{\top}= M$;
> 2. $\newcommand{\op}{\text{op}}\|\Omega_{T}\|_{\op}\leq 1$, $\|K\|_{\op}<1$, $\|M\|_{\text{op}}<1$;
> 3. $K$ and $M$ are [[Hilbert-Schmidt Operators#^5bb53a|Hilbert-Schmidt]],
> 
> then $T$ is called a *correct operator*, and the above matrix is called the *Potapov–Ginzburg matrix* of $T$, denoted as $\Omega_{T}$. The collection of correct operators forms a semigroup $\newcommand{\CSP}{\mathrm{CSp}}\CSP(\H)$ under the usual composition of operators.

%% TODO: What is the norm of \Omega? %%

We can use the associated matrix to describe these operators in $\CSP(\H)$. Given an operator $T\in\CSP(\H)$ with the matrix presentation $$\begin{pmatrix} T_{+}^{+} & T_{+}^{-} \\ T_{-}^{+} & T_{-}^{-}  \end{pmatrix}$$with respect to the decomposition $\H=\H^{+} \oplus \H^{-}$, we have $$\begin{cases} T_{+}^{+} f_{+} + T_{+}^{-} f_{-}= (Tf)_{+}, \\ T_{-}^{+} f_{+} + T_{-}^{-} f_{-}= (Tf)_{-}.\end{cases}$$If $T_{-}^{-}$ is invertible, then we can rearrange the above equation to get $$\Omega_{T}=\begin{pmatrix} -(T_{-}^{-})^{-1} T_{-}^{+} & (T_{-}^{-})^{-1} \\ T^{+}_{+}-T_{+}^{-}(T^{-}_{-})^{-1} T_{-}^{+} & T_{+}^{-}(T_{-}^{-})^{-1} \end{pmatrix}$$

Conversely, if $\begin{pmatrix}K&L\\L^{\top}&M\end{pmatrix}$is the Potapov–Ginzburg matrix of $T$ and $L$ is invertible, we can express the block matrix of $T$ (w.r.t the decomposition $\H=\H^{+} \oplus \H^{-}$) using $K$, $L$ and $M$: $$T=\begin{pmatrix}L^{\top}-ML^{-1}K & ML^{-1} \\ -L^{-1}K & L^{-1}\end{pmatrix}.$$ 


> [!proposition]
> The graph of a correct operator is always Lagrangian. In fact, $W$ is Lagrangian if and only if $(1)$ holds.

*Proof*  

> [!proposition]
> For some $T\in \CSP(\H)$, the followings are equivalent:
> 1. $T\in \RSP(\H)$;
> 2. 
> 3. $\Omega_{T}^{*}\Omega_{T}=1_{\H}$.
> 
> Therefore, $\RSP(\H)$ is a subsemigroup of $\CSP(\H)$, and in fact, it is the Shilov boundary of $\CSP(\H)$.

*Proof*  

$3\implies 1$:  Suppose $\Omega^{*}_{T}\Omega_{T}=1_{\H}$, that is , $$\begin{pmatrix} K^{*}K + L^{\top*} L^{\top} & K^{*}L + L^{\top*}M\\L^{*}K+M^{*}L^{\top} & L^{*}L + M^{*}M\end{pmatrix} = 1_{\H}.\tag{1}$$We can express the block matrix of $T^{*}T$ using $K$, $L$ and $M$: $$T^{*}T=\begin{pmatrix}(L^{\top*}-K^{*}L^{-*}M^{*})(L^{\top}-ML^{-1}K)+K^{*}L^{*}L^{-1}K & (L^{\top*}-K^{*}L^{-*}M^{*})ML^{-1}-K^{*}L^{-*}L^{-1} \\ L^{-*}M^{*}(L^{\top}-ML^{-1}K)-L^{-*}L^{-1}K & L^{-*}M^{*}ML^{-1}+L^{-*}L^{-1}\end{pmatrix}.$$To show that $T\in \RSP(\H)$, it is sufficient to show that $T^{*}T$ is a Hilbert-Schmidt perturbation of the identity. By $(1)$, we can simplify $T^{*}T$ to $$T^{*}T=\begin{pmatrix}K^{*}L^{-*}L^{-1}K+1 & -2K^{*}L^{-*}L^{-1} \\ -2L^{-*}L^{-1}K & 2L^{-*}L^{-1}-1\end{pmatrix}=1_{\H}+\begin{pmatrix}K^{*}L^{-*}L^{-1}K & -2K^{*}L^{-*}L^{-1} \\ -2L^{-*}L^{-1}K & 2L^{-*}L^{-1}-2\end{pmatrix}.$$Note that $K$ is [[Hilbert-Schmidt Operators#^2facfd|Hilbert-Schmidt]], so all of $K^{*}L^{-*}L^{-1}K$, $-2K^{*}L^{-*}L^{-1}$ and $-2L^{-*}L^{-1}K$ are Hilbert-Schmidt. Additionally, for the right-bottom entry, we have $$2L^{-*}L^{-1}-2=2((LL^{*})^{-1}-1)=2\left(L(1-M^{*}M)^{-1}L^{-1}-1\right)=2L\left((1-M^{*}M)^{-1}-1\right)L^{-1}.$$Now use the resolvent identity $$(1-M^{*}M)^{-1}-1=(1-M^{*}M)^{-1}M^{*}M,$$and the fact that $M^{*}M$ is a trace-class, so the right-bottom entry is Hilbert-Schmidt as well. $\square$

> [!definition] The Weyl Representation
> For some $T\in S(\H)$, define the *Weyl representation* of $S(\H)$ on the Fock space:
> $$W(T):=c(T)\exp\left(\frac12 \hat{a}^*(K)\hat{a}^* + \hat{a}^*(\lambda)\right)\Gamma(L)\exp\left(\frac12 \hat{a}(M)\hat{a} + \hat{a}(\mu)\right),$$
> where $c(T)$ is some normalization constant, $\Gamma(L)$ is the second quantization of $L$, and $\hat{a}^*(K)\hat{a}^*$ and $\hat{a}(M)\hat{a}$ are defined as follows: $$\hat{a}^*(K)\hat{a}^*:=\sum_{i,j} K_{ij}\hat{a}_{i}^{\dagger}\hat{a}_{j}^{\dagger},\quad \hat{a}(M)\hat{a}:=\sum_{i,j} M_{ij}\hat{a}_{i}\hat{a}_{j},$$for some orthonormal basis $\{\ket{i}\}$ of $\H^{+}$, and $K_{ij}$, $M_{ij}$ are the matrix elements of $K$ and $M$ w.r.t this basis.
> 
