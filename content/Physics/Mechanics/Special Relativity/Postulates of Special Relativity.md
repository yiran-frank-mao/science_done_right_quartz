## The Two Postulates

Einstein founded Special Relativity (1905) on two fundamental axioms:

> [!principle] The Principle of Relativity
> The laws of physics are the same in all inertial frames of reference (frames moving at constant velocity relative to each other). There is no "absolute" rest frame.

> [!principle] Constancy of the Speed of Light
> The speed of light in a vacuum, $c \approx 3.00 \times 10^8 \, \text{m/s}$, is invariant. It is the same for all observers, regardless of the motion of the source or the observer.

To transition between frames, we define dimensionless quantities.

> [!definition] Normalized Velocity & Lorentz Factor
> We define the following dimensionless quantities:
> - **Normalized Velocity:** $\beta = \frac{v}{c}$
> - **The Lorentz Factor:** $\gamma = \frac{1}{\sqrt{1 - \beta^2}}$
> 
> Since $v < c$, $\gamma \geq 1$, as $v \to c$, $\gamma \to \infty$.

## The Lorentz Transformations

The above postulates lead to the Lorentz transformations, which replace the classical [[The Principles of Relativity and Determinacy#^ed935d|Galilean transformations]].

![[The Lorentz Transformations#^dfb384]]

For the derivation, refer to [[The Lorentz Transformations]].

## Consequences of Transformations

### Relativity of Simultaneity (Clock Synchronization)

Events that are simultaneous in frame $S$ ($\Delta t = 0$) are **not** simultaneous in frame $S'$ if the events are separated spatially ($\Delta x \neq 0$): $$\Delta t' = -\gamma \frac{v}{c^2} \Delta x$$This leads clocks lag behind.

### Time Dilation

A clock moving relative to an observer ticks slower than a clock at rest.
- **Proper Time ($\Delta t_0$):** Time interval measured in the frame where the clock is at rest (same spatial location).
- **Coordinate Time ($\Delta t$):** Time interval measured by the moving observer. $$\Delta t = \gamma \Delta t_0$$
Since $\gamma \geq 1$, $\Delta t \geq \Delta t_0$.

### Length Contraction

An object moving relative to an observer appears shorter along the direction of motion.
- **Proper Length ($L_0$):** Length measured in the frame where the object is at rest.
- **Observed Length ($L$):** Length measured in the frame where the object is moving. $$L = \frac{L_0}{\gamma}$$

### **V. Relativistic Velocity Addition**

If an object moves with velocity $u'$ in frame $S'$, and $S'$ moves at $v$ relative to $S$, the velocity $u$ observed in $S$ is:

$$u = \frac{u' + v}{1 + \frac{u' v}{c^2}}$$

_Note: If $u' = c$ or $v=c$, the result $u$ is always $c$._

---

### **VI. Relativistic Dynamics**

#### **1. Momentum**

Newtonian momentum $p=mv$ is replaced to preserve conservation laws.

$$\mathbf{p} = \gamma m \mathbf{v}$$

($m$ is the invariant "rest mass").

#### **2. Energy**

- **Total Energy:** $E = \gamma m c^2$
    
- **Rest Energy:** $E_0 = m c^2$
    
- **Kinetic Energy:** $K = E - E_0 = (\gamma - 1)mc^2$
    

#### **3. The Energy-Momentum Relation**

A vital invariant equation (independent of velocity $v$):

$$E^2 - (pc)^2 = (mc^2)^2$$

For massless particles (photons), $m=0$, so $E = pc$.

---

