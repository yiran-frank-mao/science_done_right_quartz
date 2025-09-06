> [!definition] Systems with Two Degrees of Freedom
> A system with two degrees of freedom is a system defined by $$ \newcommand{\E}{\mathbb{E}}\newcommand{\x}{\mathbf{x}}\newcommand{\dd}{\,\mathrm{d}}\ddot{\mathbf{x}}(t)=\mathbf{f}(\mathbf{x}(t)),\quad \mathbf{x}\colon \R\to \E^{2} $$ where $\mathbf{f}$ is a [[Tangent Vectors and Spaces#^a87ff1|vector field]] on $\E^{2}$.

> [!definition] Conservative System
> A system with two degrees of freedom is conservative if there exists a function $U\colon \E^{2}\to \R$ such that $\mathbf{f}=-\nabla U$.

> [!remark]
> In a system of one degree of freedom, it is always possible to construct the potential energy by taking the integral, but in a system of two degrees of freedom, the this is not so.

> [!theorem] Law of Conservation of Energy
> The total energy of a conservative system is conserved, that is, $$\newcommand{\x}{\mathbf{x}}E=T+U=\frac{1}{2}\langle \dot{\x},\dot{\x}\rangle + U$$ is a constant along the trajectory of the system.

*Proof*  $$\frac{\dd E}{\dd t}=\langle\dot{\x},\ddot{\x}\rangle + \langle \nabla U(\x), \dot{\x} \rangle = \langle\ddot{\x}+\nabla U(\x), \dot{\x} \rangle=0$$


