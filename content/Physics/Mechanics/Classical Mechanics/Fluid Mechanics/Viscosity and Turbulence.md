## Viscosity

**Def**  <i><u>Viscosity</u></i>
Viscosity prevents the formation of discontinuities in real fluids. In general, (kinematic) viscosity is the diffusion of momentum. Commonly, the viscosity is related to temperature. Let $\mu$ be dynamic viscosity and $\rho$ be density, we have
$$ \nu=\frac{\mu}{\rho} \quad(m/s^2) $$

**Def**  <i><u>Burgers' Equation</u></i>
For a given field $u(x,t)$ and diffusion coefficient $\nu$ (i.e. viscosity in fluid mechanics), the Burger’s equation is defined as:
$$ \frac{\partial u}{\partial t} + u\frac{\partial u}{\partial x}=\nu\frac{\partial^2u}{\partial x^2} $$

**Def**  <i><u>Newtonian Fluid</u></i>
A newtonian fluid is a type of fluid such that stress is proportional to strain.

**Prop**  <i><u>Viscosity as Stickiness</u></i>
The equation of motion of treating viscosity as stickiness between layers is given by:
$$ \ddot{x}=\nu \frac{\partial^2u}{\partial z^2} $$
![viscosity.svg|300](https://svgshare.com/i/zbG.svg)

**Def**  <i><u>Navier-Stokes Equations</u></i>
The Navier-Stokes equations model essentially all fluid flows are defined by:
$$\begin{aligned}
& \frac{D\vec{u}}{Dt}=-\frac{1}{\rho}\nabla P + \vec g + \nu \nabla^2\vec{u} \\ 
 &\frac{D \rho}{Dt}+\rho \nabla \cdot \vec{u}=0 
\end{aligned}$$
Specially, if $\nabla P = \vec g=0$ then the first equation reduces to the Burger's equation.

## Cascade to Turbulence

**Def**  <i><u>Reynold’s Number</u></i>
Th Reynold’s number is a non-dimensional number that quantifies the relative strength of the viscous terms compared to the inertial, assuming a velocity scale of $u$ and a length scale of $L$:
$$ \text{Re}=\frac{uL}{\nu} $$
When Reynold’s number is considerably larger, the fluid behaves as an inviscid fluid except the boundaries. When it is order one, we have a fluid system which is influenced by the viscosity everywhere.

**Def**  <i><u>Turbulence</u></i>
Turbulence is defined as continual cascade of instabilities at various scales. Turbulence is chaotic.

**Def**  <i><u>Reynold’s Decomposition</u></i>
Let $\bar u = \frac{1}{T} \int_0^Tu \mathrm{d}t$ be the average velocity over time interval $T$, which is independent on $t$. Then define the following decomposition as Reynold’s decomposition:
$$ u^\prime = u-\bar u $$
**Prop** $\frac{1}{T} \int_0^Tu^\prime \mathrm{d}t=0$

**Def**  <i><u>Turbulent Viscosity</u></i>
The turbulent or eddy viscosity $\nu_T \gg \nu$ is used to model the turbulence, which is known as large eddy simulation.
$$ \frac{D\bar{u}}{Dt}= \nabla \cdot ( (\nu_T+\nu) \nabla\bar{u} ) $$
where $\bar{u}$ is the mean velocity.