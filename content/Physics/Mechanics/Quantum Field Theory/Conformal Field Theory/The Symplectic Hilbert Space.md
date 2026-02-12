Given a complex [[Hilbert Spaces#^ae0212|Hilbert space]] $\newcommand{\C}{\mathbb{C}}\newcommand{\H}{\mathcal{H}}\newcommand{\G}{\mathcal{G}}\H_{J}$ with an inner product $\langle\cdot,\cdot\rangle$ and a [[Almost Complex Structures#^5f4098|complex structure]] $J$, let $\newcommand{\R}{\mathbb{R}}\H_{\R}$ be the same set considered as a vector space over $\R$. Define $\H$ to be the complexification of $\H_{\R}$:$$\H:=\H_{\R} \otimes \C=\H_{\R} \oplus i\H_{\R}.$$Observe the following structures on $\H$:
1. A conjugate $\overline{ }\colon \H \to \H$ that flips the sign of the imaginary part;
2. An [[Inner Products#^ad5686|inner product]] $\newcommand{\llangle}{\left\langle\!\left\langle}\newcommand{\rrangle}{\right\rangle\!\right\rangle}\llangle \cdot, \cdot \rrangle$, extending the real part of $\langle\cdot,\cdot\rangle$ sesquilinearly, makes $\H$ a Hilbert space: $$\llangle \lambda x,\eta y\rrangle := \lambda \overline{\eta}  \Re\langle x,y \rangle.$$
3. A [[Symplectic Structures#^b558c2|symplectic form]] $\omega$, extending the imaginary part of $\langle\cdot,\cdot\rangle$ bilinearly: $$\omega(\lambda x,\eta y):= \lambda \eta \Im \langle x,y\rangle.$$
4. A [[Sesquilinear Forms#^5a2a7f|skew Hermitian form]] $\Lambda$, extending the imaginary part of $\langle\cdot,\cdot\rangle$ sesquilinearly: $$\Lambda(\lambda x,\eta y) := \lambda \overline{\eta} \Im \langle x, y\rangle.$$
5. Extend $J$ to $\H$ linearly, so it becomes a complex structure on $\H$: $$J(\lambda x)=\lambda J(x).$$

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

> [!definition] Correct Subspace
> A subspace $W\subset \H \oplus \G$ is *correct* if it is the graph of an operator $$\Omega_{W}\colon \H^{+} \oplus \G^{-} \to \H^{-}\oplus \G^{+},\quad \Omega_{W}=\begin{pmatrix} K &L \\ L^{\top} & M\end{pmatrix}$$
> such that 
> 1. $K^{\top} =K$, $M^{\top}= M$;
> 2. $\|\Omega\|_{\text{op}}<1$, $\|K\|_{\text{op}}<1$, $\|M\|_{\text{op}}<1$;
> 3. $K$ and $M$ are Hilbert-Schmidt.
> 
> 

> [!proposition]
> A correct subspace is always Lagrangian. In fact, $W$ is Lagrangian if and only if $(1)$ holds.

*Proof*  

## The Symplectic Semigroup

> [!definition] Restricted Symplectic Semigroup
> Suppose $\G$ is a real symplectic Hilbert space, then we write $\newcommand{\RSP}{\mathrm{Sp}_{\text{res}}}\RSP(\G)$ for the *restricted symplectic group*, that is, a [[Groups, Order and Subgroups#^1ccb07|subgroup]] of $\mathrm{Sp}(\G)$ such that the operators can be written as $U(1+T_{\mathrm{HS}})$ for some unitary operator $U$ and some Hilbert-Schmidt operator $T_{\mathrm{HS}}$.

## Application: Embed $\newcommand{\Diff}{\mathrm{Diff}}\Diff^+(S^1)$ into $\RSP(\H)$

Consider the real vector space $C^{\infty}(S^{1},\R)/\R$ of smooth real-valued functions on the circle modulo constants (i.e. mean-zero functions on the ), equipped with the (real) inner product $$\newcommand{\pv}{{\small{\operatorname{p.v.}}}} \langle f,g\rangle=\frac{1}{4\pi^{2}} \int_{0}^{2\pi} \pv \int^{2\pi}_{0} \cot\left(\frac{\theta-\zeta}{2}\right) f(\theta) g'(\zeta) \dd\theta \dd\zeta. $$Let $\H_{\R}=\overline{C^{\infty}(S^{1},\R)/\R}$ be the completion of $C^{\infty}(S^{1},\R)/\R$ with respect to the above inner product. The Hilbert transform $$\newcommand{\sgn}{\operatorname{sgn}}(J f)(\theta) = \frac{1}{2\pi} \int^{2\pi}_{0} \cot\left(\frac{\theta-\zeta}{2}\right) f(\zeta) \dd\zeta=\sum_{n\neq 0} i\sgn(n) f_{n}e^{in \theta}$$forms a complex structure on $\H_{\R}$. Now, let us apply the procedure described at the beginning of this section to construct a symplectic Hilbert space $\H$ from $\H_{\R}$. Then the underlying set of $\H$ is $\overline{C^{\infty}(S^{1})/\C}$, the orthogonal subspaces $\H^{+}$ and $\H^{-}$ consists of functions that can extend holomorphically to $D_{+}$ and $D_{-}$ respectively. The symplectic form is given by $$\omega(f,g)=\langle f, g\rangle = i\sum_{n\neq 0} n f_{-n}g_{n} = \frac{1}{2\pi} \oint_{S^{1}} f(z)\dd g(z).$$Note that $i\sum_{n\neq 0} n f_{-n}g_{n}$ is real for real functions $f$ and $g$.

> [!proposition]
> Suppose $\phi\in\Diff^{+}(S^{1})$, then the operator $V_{\phi}\in \RSP(\H_{\R})$.  
> 

*Proof*  $V_{\phi}$ is symplectic, because $$\omega(V_{\phi} f, V_{\phi} g)=\frac{1}{2\pi}\oint_{S^{1}} f(\phi(z))\dd g(\phi(z))=\omega(f,g).$$To show that $V_{\phi}$ is in $\RSP(\H)$, it suffices to show that $V_{\phi}^{*}V_{\phi}$ can be written as a Hilbert-Schmidt perturbation of the identity. Once we can write $\newcommand{\HS}{\text{HS}}V_{\phi}^{*}V_{\phi}=1+T_{\HS}$, we can apply the polar decomposition 
We first show that $[J,V_{\phi}]$ is Hilbert-Schmidt. Note that $$\begin{aligned} (JV_{\phi}f)(\theta)&= \frac{1}{2\pi} \pv \int^{2\pi}_{0} \cot\left( \frac{\theta-\zeta}{2} \right) f(\phi(\zeta)) \dd \zeta \\ &= \frac{1}{2\pi} \pv \int^{2\pi}_{0} \cot\left(\frac{\theta-\phi^{-1}(\zeta)}{2} \right) (\phi^{-1})'(\zeta) f(\zeta) \dd \zeta, \\ (V_{\phi}Jf)(\theta)&=\frac{1}{2\pi} \pv \int^{2\pi}_{0} \cot\left(\frac{\phi(\theta)-\zeta}{2}\right)f(\zeta)\dd\zeta.\end{aligned}$$Therefore, the kernel of $[J, V_{\phi}]$ is $$K_{\phi}(\theta, \zeta) = \frac{1}{2\pi}\left[(\phi^{-1})'(\zeta) \cot\left(\frac{\theta-\phi^{-1}(\zeta)}{2}\right) - \cot\left(\frac{\phi(\theta)-\phi(\zeta)}{2}\right)\right].$$Utilize the Laurent expansion of $\cot$ at $0$, we can write $\cot(x)=\frac{1}{x}+h(x)$, where $h$ is a real-analytic function vanishes at $0$. Let $u=\phi(\theta)-\zeta$ Hence, $$2\pi K_{\phi}(\theta, \zeta) = \frac{2(\phi^{-1})'(\phi(\theta)-u)}{\theta-\phi^{-1}(\phi(\theta)-u)} + (\phi^{-1})'(\phi(\theta)-u) h(\theta-\phi^{-1}(\phi(\theta)-u))-\frac{2}{u}-h(u).$$Observe that the only potentially non-smooth term is $\frac{2(\phi^{-1})'(\phi(\theta)-u)}{\theta-\phi^{-1}(\phi(\theta)-u)}-\frac{2}{u}$. Let $\varphi_{\theta}(u):=\theta-\phi^{-1}(\phi(\theta)-u)$. Then $\varphi_{\theta}'(0)=0$, $\varphi_{\theta}'(u)=1/\phi'(\theta)$, we can write $\varphi_{\theta}(u)=u q(u)$ for some smooth $q$ such that $q(0)=1/\phi'(\theta)$. Therefore, the potentially non-smooth term can be written as $$\frac{2(q(u)+uq'(u))}{uq(u)} - \frac{2}{u} = 2 \frac{q'(u)}{q(u)},$$which is smooth. Hence, $K_{\phi}$ is smooth and thus $[J,V_{\phi}]$ is [[Compact Operators#^5bb53a|Hilbert-Schmidt]].
Since $V_{\phi}$ is real, let us write $V_{\phi}=\begin{pmatrix} A & B \\ C & D\end{pmatrix}$ according to the decomposition $\H=\H^{+}\oplus \H^{-}$. Computing the commutator $[J, V_{\phi}]$ gives $$[J,V_{\phi}]=\begin{pmatrix}0 & 2i B \\ -2iC & 0\end{pmatrix},$$so $B$ and $C$ have to be Hilbert-Schmidt. As $V_{\phi}$ is symplectic, we have $$A^{*}A=1_{\H^{+}} + C^{*}C, \quad D^{*}D=1_{\H^{-}}+B^{*}B, \quad A^{*}B=C^{*}D, \quad B^{*}A=D^{*}C.$$Then $$V_{\phi}^{*}V_{\phi} = \begin{pmatrix} A^{*}A+C^{*}C & A^{*}B+C^{*}D \\ B^{*}A + D^{*}C & B^{*}B+D^{*}D \end{pmatrix} = 1_{\H} + 2\begin{pmatrix}C^{*}C &  C^{*}D \\ D^{*}C & B^{*}B\end{pmatrix},$$hence $V_{\phi}^{*}V_{\phi}$ can be written as $1+T_{\text{HS}}$.
 