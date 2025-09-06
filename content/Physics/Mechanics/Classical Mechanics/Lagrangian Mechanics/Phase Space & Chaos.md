## Phase Space

> [!definition] Phase Space
> A phase space is a space in which all possible "states" of a dynamical system are represented, with each possible state corresponding to one unique point in the phase space. Specifically, the phase space usually consists of all possible values of position and momentums, which is a 6-dimensional space. ^e2ae52

> [!proposition]
> Any two distinct trajectories in the phase space will not cross with each other.

*Proof*  Assume two trajectories cross with each other at point $A(\mathbf{x},\mathbf{p},t)$, then they will be same as at time $t$ they have exactly same $\mathbf{x}$ and $\dot{\mathbf{x}}$, thus all states can be determined.  $\square$

**Def**  <i><u>Attractor</u></i>
In a phase space, an attractor is a point towards which neighbouring states in a given basin of attraction asymptotically approach in the course of dynamic evolution. That is system values that get close enough to the attractor values remain close even if slightly disturbed. In general, an attractor is a region in the space of possible states which the system can enter but not leave.

## Phase Flow & Liouville's Theorem

> [!definition] Phase Flow
> The phase flow is the one-parameter family of transformations of the phase space: $$g^{t}\colon (\mathbf{p}(0),\mathbf{q}(0)) \mapsto (\mathbf{p}(t),\mathbf{q}(t))$$where $\mathbf{p}(t)$ and $\mathbf{q}(t)$ are the solutions to the [[Hamiltonian & Symmetries#^5ef3ed|Hamilton's equations]].

> [!proposition]
> The set of phase flows $\left\{g^{t}\right\}$ is a group under composition.

> [!theorem] Liouville's Theorem
> The volume of a region in the phase space remains same under the phase flow.

*Proof*

<u><b>e.g.</b></u>  In a Hamiltonian system, it is impossible to have asymptotically stable equilibrium points in the phase space, because the phase flow preserves the volume.

> [!theorem] Poincare Recurrence Theorem
> Let $g$ be a volume preserving, continuous one-to-one mapping which maps a bounded region $D$ of Euclidean space onto itself: $gD=D$. Then in any neighborhood $U$ of any point of $D$, there exists a point $x$ such that $g^nx\in U$ for some $n>0$.

## Identify Chaos

**Def**  <i><u>Poincare Section</u></i>
Suppose $S$ is some hyperplane in the phase space, and $\Gamma$ is some trajectory. Points of intersection of $\Gamma$ and $S$ are denotes as $P_i$. The Poincare section is a continuous mapping $T$ of $S$ into itself:$$ P_{k+1}=T(P_k)=T\left[T(P_{k-1})\right]=T^2(P_{k-1})=\cdots$$Since the dynamic system is deterministic, $P_0$ determines $P_1$, $P_1$ determines $P_2$, etc.

**Def**  <i><u>Lyapunov Exponent</u></i>
Lyapunov exponent is a quantity that characterises the rate of separation of infinitesimally close trajectories. Quantitatively, two trajectories in phase space with initial separation $d_0$ diverge at a rate given by $$d(t)= d_0 e^{\lambda t}$$where $\lambda$ is the Lyapunov exponent. Alternatively, we can say $$\lambda = \lim_{t\to\infty}\lim_{d_0\to0}\frac{1}{t}\ln\left(\frac{d(t)}{d_0}\right)$$

**Algorithm**  <i><u>Determine Lyapunov Exponent</u></i>
For $i=1,\dots,n$ with considerably larger $n$, in each iteration, calculate $$\lambda_{i}= \frac{1}{\Delta t} \ln\left(\frac{d(t_{0}+i\Delta t)}{d_0}\right).$$Finally output the average of all $\lambda_i$.