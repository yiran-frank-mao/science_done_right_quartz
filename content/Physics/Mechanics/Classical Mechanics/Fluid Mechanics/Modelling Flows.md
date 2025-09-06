**Def**  <i><u>Steady Flow</u></i>
A steady flow is one in which the partial time derivative is zero for all variables in the system.

**Def**  <i><u>Incompressible Flow</u></i>
A flow is incompressible if density $\rho$ is constant with respect to time.

**Def**  <i><u>Material(Total) Derivative</u></i>
The material derivative of some particle with velocity $\mathbf{u}$ is defined as follows: $$ \frac{D}{Dt}=\frac{\partial}{\partial t}+ \mathbf{u} \cdot \nabla_{\mathbf{x}} $$

**Def**  <i><u>Vorticity</u></i>
The vorticity in fluid mechanics for a 2D flow field is defined as: $$ w=\frac{\partial \mathbf{u}_x}{\partial x} - \frac{\partial \mathbf{u}_y}{\partial y} $$

## Lagrangian and Eulerian Views

**Fact**  <i><u>Lagrangian and Eulerian Views on Fluid</u></i>
Lagrangian description deals with the individual particles and calculates the velocity, acceleration, position or other parameters of each particle separately. Whereas in the Eulerian description of fluid flow, a finite volume called a flow domain or control volume is defined, through which fluid flows in and out. They're related through the material derivative.

## Equations of Motion

**Thrm** For any fluid we have the following equations holds:
$$ \begin{aligned}
\frac{\mathrm{D}\vec{u}}{\mathrm{D}t}= -\frac{1}{\rho} \nabla P + g  &\quad\text{(Conservation of Momentum)}\\
\frac{\mathrm{D}\vec{u}}{\mathrm{D}t}= \left[\frac{\partial}{\partial t}+ \vec{u} \cdot \nabla_{\mathbf{x}} \right]\vec{u}&\quad\text{(Material Derivative)}\\
\frac{\mathrm{D}\rho}{\mathrm{D}t}+\rho(\nabla \cdot \vec{u})=0 &\quad\text{(Conservation of Mass)}
\end{aligned}$$

**Prop**  If a flow is incompressible, then the conservation of mass reduces to conservation of volume (i.e. $\nabla \cdot u=0$)
**Proof**  Clearly $\frac{\mathrm{D}\rho}{\mathrm{D}t}=0$ if a flow is incompressible, then by conservation of mass we have $\nabla \cdot u=0$.

**Thrm**  <i><u>Hydrostatic Balance</u></i>
When the vertical velocity is zero (or considerably small), the pressure in the fluid is equivalent to the weight of fluid above the given height:
$$
\pddf{P}{z}=-\rho g
$$
**Proof**  By conservation of momentum, $0=-\frac{1}{\rho}\nabla_{zP+g}\implies \pddf{P}{z}=-\rho g$.