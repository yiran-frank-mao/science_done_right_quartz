## Poisson Bracket of Vector Fields

> [!definition] Poisson Bracket of Vector Fields
> The Poisson bracket of two [[Vector Fields and Lie Algebra#^a87ff1|vector fields]] $\newcommand{\R}{\mathbb{R}}X$ and $Y$ is defined as minus the Lie bracket of the two vector fields: $\newcommand{\ddf}[2]{\frac{\mathrm{d}#1}{\mathrm{d}#2}}\newcommand{\pddf}[2]{\frac{\partial#1}{\partial#2}}\newcommand{\ddt}{\ddf{}{t}}\{X,Y\}=-[X,Y]$.
> 

## Poisson Bracket of Functions

> [!definition] Poisson Bracket of Functions
> Suppose $(M,\omega)$ is a [[Symplectic Structures#^b558c2|symplectic manifold]]. The Poisson bracket of two functions $F,G\in C^{\infty}(M)$ is defined as a function in $\newcommand{\d}{\mathrm{d}}\newcommand{\L}{\mathcal{L}}C^{\infty}(M)$: $$\{F,G\}:=\omega(X_{G},X_{F}).$$

Note that the above definition is equivalent to say that $\{F,G\}=\L_{X_{G}}F$, because $$\L_{X_{G}}F=\d F(X_{G})=\omega(X_{G},X_{F}).$$

> [!proposition]
> Suppose $(M,\omega)$ is a [[Symplectic Structures#^b558c2|symplectic manifold]]. For any $F,G\in C^{\infty}(M)$, there holds $$X_{\{F,G\}}=\{X_{F},X_{G}\}.$$

*Proof*  By definition of a Hamiltonian vector field, it suffices to show that $\d\{F,G\}=-i_{\{X_{F},X_{G}\}}\omega$. We start from the RHS. Recall [[Differential Forms#^d9e627|the proposition]], we can write $$-i_{\{X_{F},X_{G}\}}\omega=-i_{\L_{X_{G}}X_{F}}\omega=i_{X_{F}}\L_{X_{G}}\omega-\L_{X_{G}}i_{X_{F}}\omega.$$Note that [[Symplectic Structures#^72585c|a Hamiltonian vector field preserves the symplectic form]], so $\L_{X_{G}}\omega=0$. Moreover, $i_{X_{F}}\omega=-\d F$ by definition. Hence, $$-i_{\{X_{F},X_{G}\}}\omega=\L_{X_{G}}\d F.$$The LHS can be computed as follows: $$\d\{F,G\}=\d\L_{X_{G}}F=\L_{X_{G}}\d F,$$it implies $\d\{F,G\}=-i_{\{X_{F},X_{G}\}}\omega.$ $\square$

> [!proposition]
> The Poisson bracket gives functions on a [[Symplectic Structures#^b558c2|symplectic manifold]] the structure of a [[Vector Fields and Lie Algebra#^5007ba|Lie algebra]].
> 

*Proof*  Bilinearity comes from the linearity of $X_{-}\colon C^{\infty}(M)\to \mathfrak{X}(M)$. Indeed, $X_{cH+F}$ satisfies $$-i_{X_{cH+F}}\omega = \d(cH+F)=c\d H+\d F=- i_{cX_{H}}\omega - i_{X_{F}}\omega=-i_{cX_{H}+X_{F}}\omega,$$so $X_{-}$ is linear. Anti-symmetry inherits from the anti-symmetry of the symplectic form; It also satisfies the Jacobi identity: $$\{\{F,G\},H\}=\L_{X_{H}}\{F,G\}=\{\L_{X_{H}}F,G\}+\{F,\L_{X_{H}}G\}=\{\{F,H\},G\}+\{F,\{G,H\}\}.$$$\square$

## Noether's Theorem

> [!theorem] Noether's Theorem
> A function $H$ is $G$-symmetric iff $G$ is preserved under $X_{H}$. In fact,
> $$\L_{X_{G}}H=-\L_{X_{H}}G.$$ ^1f3e3a

*Proof*  It is easy to see that $$\L_{X_{G}}H=\{H,G\}=-\{G,H\}=-\L_{X_{H}}G.$$$\square$

> [!remark]
> Noether's theorem states that every differentiable symmetry of the action of a physical system has a corresponding conservation law. In the context of Hamiltonian mechanics, this means that if the Hamiltonian is invariant under a continuous symmetry transformation, then there exists a conserved quantity associated with that symmetry. (See [[Hamiltonian & Symmetries#^05c1b6|Noether's Theorem]].)
> 

> [!lemma] Cotangent Lift Flow
> Any global flow $\Phi_t$ on a [[Manifolds and Atlases#^6ef2ef|smooth manifold]] $M$ induces a cotangent lift flow $\tilde{\Phi}_t$ on the [[Tensor Fields#^f98eed|cotangent bundle]] $T^*M$. For any $(q, \alpha) \in T^*M$ (where $q \in M$ and $\alpha \in T_q^*M$), this flow is defined by $$\tilde{\Phi}_t(q,\alpha) = (\Phi_t(q), \Phi_t^*\alpha),$$ where the [[Tensor Fields#^bd6c33|covector]] $\Phi_t^*\alpha \in T_{\Phi_t(q)}^*M$ is determined by the condition $$\Phi_t^*\alpha(v) = \alpha(\d_{\Phi_t(q)}\Phi_{-t}(v)) \quad \text{for all } v \in T_{\Phi_t(q)}M.$$ ^32c822

*Proof*  We shall verify that $\tilde{\Phi}_t$ is a valid global flow on $T^*M$. Clearly, $\tilde{\Phi}_t$ is a diffeomorphism as $\Phi_t$ is, and $$\tilde{\Phi}_0(q,\alpha) = (\Phi_0(q),\Phi_0^*\alpha) = (q,\alpha).$$So $\tilde{\Phi}_0$ is the identity map. Moreover, to show the group property $\tilde{\Phi}_{t+s} = \tilde{\Phi}_t \circ \tilde{\Phi}_s$, consider $(q, \alpha) \in T^*M$, we have $$\begin{aligned}\Phi_{s+t}^*\alpha (v) &= \alpha(\d_{\Phi_{t+s}(q)}\Phi_{-(t+s)}(v))\\ &=\alpha((\d_{\Phi_{t+s}(q)}\Phi_{-t}\circ\d_{\Phi_{t+s}(q)}\Phi_{-s})(v)) \\ &=(\Phi_t^* (\Phi_s^* \alpha))(v). \end{aligned}$$Thus, $$\tilde{\Phi}_{t+s}(q,\alpha)=(\Phi_t(\Phi_s(q)), \Phi_t^* (\Phi_s^* \alpha)=\tilde{\Phi}_{t}(\tilde{\Phi}_{s}(q,\alpha)).$$Therefore, $\tilde{\Phi}_t$ is a valid global flow on $T^*M$. $\square$

> [!remark]+ Coordinate Form of Cotangent Lift Flow
> Let $(q^1,\dots,q^n)$ be local coordinates on $M$ in coordinate form, and $(q^1,\dots,q^n,p_1,\dots,p_n)$ be the corresponding canonical coordinates on $T^*M$. Then the above lifted flow has the following coordinate form: $$ \tilde{\Phi}_t(q^1,\dots,q^n,p_1,\dots,p_n) = \left(\Phi_t^1(q),\dots, \Phi_t^n(q), p_k\pddf{q^k}{\Phi_t^1(q)},\dots, p_k\pddf{q^k}{\Phi_t^n(q)}\right),$$ where $p_k\pddf{q^k}{\Phi_t^j (q)}$ represents the components of the Jacobian matrix of the inverse transformation $\Phi_{-t}$ evaluated at $\Phi_{t}(q^1,\dots,q^n)$.
> 

<u><b>e.g.</b></u>  Rotation around the $z$ axis in $\mathbb{R}^3$ determines a Hamiltonian flow on $T^*\mathbb{R}^3$. What is the corresponding Hamiltonian vector field on $T^*\mathbb{R}^3$, and what is its Hamiltonian function $M_z$? What are $M_x$ and $M_y$, the Hamiltonians generating rotations around the $x$ and $y$ axis and what is $\{M_x, M_y\}$? For a rotationally symmetric Hamiltonian $H$, why is $M_z$ preserved by the flow of $X_H$?
We use the standard coordinates $(x,y,z)$ for $\R^{3}$, and $(x,y,z,p_{x},p_{y},p_{z})$ for the cotangent bundle $T^{*}\R^{3}$. A rotation around the $z$-axis can be expressed as a flow (of unit speed): $$ \Phi_{t}=\begin{pmatrix}\cos t& -\sin t & 0 \\ \sin t&\cos t& 0\\0&0&1\end{pmatrix} $$We can lift this flow to the cotangent bundle according to the [[Poisson Bracket#^32c822|lemma]]. Note that the lifted covector transform via the inverse transpose of the Jacobian matrix of $\Phi_{t}$. In this case, it transforms exactly like the coordinates:$$ \begin{aligned} \, \tilde{\Phi}_t (x,y,z,p_x,p_y,p_z) =&\,(\Phi_t(x,y,z), \Phi_t^*(p_x,p_y,p_z))\\ =&\, (x\cos t-y\sin t, x\sin t+ y\cos t,z p_x\cos t-p_y\sin t, p_x\sin t+ p_y\cos t, p_z). \end{aligned} $$Hence, the Hamiltonian vector field $X_{M_z}$ on $T^*\R^3$ can be derived by differentiating with respect to $t$ at $t=0$:$$ \begin{aligned} \newcommand{\ddtz}{\ddt{}\bigg|_{t=0}} \dot{x}=\ddtz x\cos t-y\sin t = -y,\quad \dot{y}=\ddtz x\sin t+ y\cos t = x,\quad \dot{z}= 0. \end{aligned} $$Similarly, $\dot{p_x} = -p_y$, $\dot{p_y}=p_x$, $\dot{p_z}= 0$, so$$ X_{M_z}=-y\pddf{}{x} + x\pddf{}{y} - p_y \pddf{}{p_x} + p_x \pddf{}{p_y}. $$We can therefore find the associated Hamiltonian function by solving the Hamilton's equations:$$ \begin{aligned} \pddf{M_z}{p_x}=-y, \quad \pddf{M_z}{p_y}=x, \quad \pddf{M_z}{p_z}=0, \\ \pddf{M_z}{x}=p_y, \quad \pddf{M_z}{y}=-p_x, \quad \pddf{M_z}{z}=0. \end{aligned} $$Integrating these equations, we obtain (up to some constant)$$ M_z(x,y,z,p_x,p_y,p_z)= xp_y -y p_x, $$which is recognizable as the $z$-component of the angular momentum.
By symmetry, the Hamiltonians generating rotations around the $x$ and $y$ axes are $$ M_x(x,y,z,p_x,p_y,p_z)= yp_z -z p_y,\quad M_y(x,y,z,p_x,p_y,p_z)=zp_x-xp_z. $$Furthermore, we can derive the Poisson bracket of $M_x$ and $M_y$: $$ \begin{aligned} &\{M_x, M_y\}(x,y,z,p_{x},p_{y},p_{z}) \\ =&\, \L_{X_{M_y}} M_x \\ =&\, X_{M_y}(M_x) \\ =&\, -x\pddf{M_x}{z}+z\pddf{M_x}{x}-p_x\pddf{M_x}{z} + p_z \pddf{M_x}{p_x} \\ =&\, xp_y -p_x y\\ =&\, M_z. \end{aligned} $$A Hamiltonian $H$ is rotationally symmetric (specifically, around the $z$-axis) if it remains unchanged under rotations around the $z$-axis. This invariance implies that the Lie derivative of $H$ along the Hamiltonian vector field $X_{M_z}$ is zero: $\L_{X_{M_z}}H=0$. Observe that $$ \L_{X_{M_z}}H=\{H, M_z\}=-\{M_z,H\}=-\L_{X_H} M_z, $$which implies that $\L_{X_H} M_z=0$, i.e., $M_z$ is preserved by the flow of $X_H$.