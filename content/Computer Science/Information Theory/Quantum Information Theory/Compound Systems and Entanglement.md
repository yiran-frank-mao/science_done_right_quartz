
**Postulate**  Given two quantum systems with state spaces given independently by Hilbert spaces $H$ and $K$, as a compound (joint) system their overall state space is $H \otimes K$, the [[Tensors and Tensor Products#^732917|tensor product]] of the two [[Hilbert Spaces#^ae0212|Hilbert spaces]].

>[!remark]
>As a result, state spaces of quantum systems grow large very rapidly: a collection of n qubits will have a state space isomorphic to $\C^{2^{n}}$ , requiring $2^{n}$ complex numbers to specify its state vector exactly. In contrast, a classical system consisting of $n$ bits can have its state specified by a single binary number of length $n$.

**Def**  <i><u>Product State</u></i> and <i><u>Entangled State</u></i>
For a compound system with state space $H \otimes K$, a product state is a state of the form $a\otimes b$ with $a ∈ H$ and $b ∈ K$. An entangled state is a state not of this form.

>[!remark]
>The definition of product and entangled state also generalizes to systems with more than two components. When using Dirac notation, if $\ket{a} ∈ H$ and $\ket{b}∈ K$ are chosen states, we will often write $\ket{ab}$ for their product state $\ket{a}\otimes\ket{b}$.

**Def**  <i><u>Bell State</u></i>
The Bell basis for a pair of qubits with state space $\C^{2} \otimes \C^{2}$ is the orthonormal basis given by the following states: $$\begin{aligned}\ket{\mathrm{Bell}_{0}}&=\frac{1}{\sqrt{2}}(|00\rangle+|11\rangle)\\ \ket{\mathrm{Bell}_{1}}&=\frac{1}{\sqrt{2}}(|00\rangle-|11\rangle)\\\ket{\mathrm{Bell}_{2}}&=\frac{1}{\sqrt{2}}(|01\rangle+|10\rangle)\\\ket{\mathrm{Bell}_{3}}&=\frac{1}{\sqrt{2}}(|01\rangle-|10\rangle)\end{aligned}$$The state $\ket{\mathrm{Bell}_{0}}$ is often called ‘the Bell state’, and is very prominent in quantum information. The Bell states are maximally entangled, meaning that they induce an extremely strong correlation between the two systems involved.