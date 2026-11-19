Classical computer science often considers systems to have a finite set of states. An important simple system is the bit, with state space given by the set $\{0, 1\}$. Quantum information theory instead assumes that systems have [[Quantum State Space#^00f394|state spaces]] given by finite-dimensional [[Hilbert Spaces|Hilbert spaces]]. The quantum version of the bit is the qubit.

>[!definition] 
>**Def**  <i><u>Qubit</u></i>
>A qubit is a quantum system with state space $\C^{2}$.

>[!definition] 
>**Def**  <i><u>Pure State</u></i>
>A pure state of a quantum system is given by a vector $v ∈ \mathbb{H}$ in its associated Hilbert space. Such a state is normalized when the vector in the Hilbert space has norm $1$:$$\braket{a|a}=1$$In particular, a complex number of norm $1$ is called a phase. A pure state of a qubit is therefore a vector of the form $$a=\begin{pmatrix}s \\ t\end{pmatrix}$$with $s, t ∈ \C$, which is normalized when $|s|^{2} + |t|^{2} = 1$.

>[!attention]
>We will encounter a more general notion of state, called a mixed state. However, when our meaning is clear, we’ll often just say state instead of pure state.

**Def**  <i><u>Z Basis</u></i>
For the Hilbert space $\C^{n}$, the computational basis, or Z basis is the orthonormal basis given by the following vectors: $$\ket{0}=\begin{pmatrix}1\\0\\\vdots\\0\end{pmatrix}\quad\ket{1}=\begin{pmatrix}0\\1\\\vdots\\0\end{pmatrix}\quad\cdots\quad\ket{n-1}=\begin{pmatrix}0\\0\\\vdots\\1\end{pmatrix}$$

>[!remark]
>This orthonormal basis is no better than any other, but it is useful to fix a standard choice. Every state $a ∈ \C^{n}$ can be written in terms of the computational basis; for a qubit, we can write $a = s\ket{0} + t\ket{1}$ for some $s, t ∈ \C$.

**Def**  <i><u>X Basis</u></i>
The X basis for a qubit $\C^{2}$ is given by the following states: $$\ket{+}=\frac{1}{\sqrt{2}}(\ket{0}+\ket{1}),\quad \ket{-}=\frac{1}{\sqrt{2}}(\ket{0}-\ket{1})$$