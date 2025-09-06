## Stern-Gerlach Experiment

> [!definition] Bohr Magneton
> Bohr magneton is a physical constant that is defined as: $$\mu_{B}:=\frac{e\hbar}{2m_{e}}=9.27\times10^{-24}\:\mathrm{J/T}$$


**Def**  Stern-Gerlach Experiment
The Stern-Gerlach experiment is the experiment showing that the 


## Intrinsic Spin

>[!definition] 
>**Def**  <i><u>Spin</u></i>
>Spin is an intrinsic property of particles that is not associated with any spatial coordinates. It is a form of angular momentum that is not due to the motion of the particle. The spin quantum number $s$ is a half-integer or integer value that determines the magnitude of the spin angular momentum.

**Def**  <i><u>Spin Angular Momentum Operator</u></i>
The spin angular momentum operators are denoted by $\hat{S}_{x}$, $\hat{S}_{y}$, and $\hat{S}_{z}$, 

**Prop**  The spin angular momentum operators satisfy the same commutation relations as the orbital angular momentum operators: $$\begin{aligned}[][\hat{S}_{x}, \hat{S}_{y}]=i \hbar \hat{S}_{z} \\ [\hat{S}_{y}, \hat{S}_{z}]=i \hbar \hat{S}_{x} \\ [\hat{S}_{z}, \hat{S}_{x}]=i \hbar \hat{S}_{y}\end{aligned}$$
**Def**  <i><u>Spin Ladder Operators</u></i>
The spin ladder operators are defined as: $$\hat{S}_{+}=\hat{S}_{x}+i\hat{S}_{y},\quad \hat{S}_{-}=\hat{S}_{x}-i\hat{S}_y$$

**Prop**  The action of the operators on states of definite spin is given by: $$\begin{aligned}&\hat{S}^{2}|s,m_{s}\rangle=s(s+1)\hbar^{2}|s,m_{s}\rangle\\&\hat{S}_{z}|s,m_{s}\rangle=m_{s}\hbar|s,m_{s}\rangle\\ &\hat{S}_{+}|s,m_{s}\rangle=\hbar\sqrt{s(s+1)-m_{s}(m_{s}+1)}|s,m_{s}+1\rangle\\&\hat{S}_{-}|s,m_{s}\rangle=\hbar\sqrt{s(s+1)-m_{s}(m_{s}-1)}|s,m_{s}-1\rangle\end{aligned}$$

>[!definition] 
>**Def**  <i><u>Eigenspinors</u></i>
>The eigenfunctions of the spin operator $\hat{S}_{z}$ are called eigenspinors. The eigenspinors of the spin angular momentum operators are denoted by $\chi_{s}^{m_{s}}$.
><u><b>e.g.</b></u>  In matrix representation, $\chi_{\frac{1}{2}}^{+\frac{1}{2}}=\begin{pmatrix}1 \\ 0\end{pmatrix}$ and $\chi_{\frac{1}{2}}^{-\frac{1}{2}}=\begin{pmatrix}0 \\ 1\end{pmatrix}$. Thus an arbitrary spin state for such a particle can then be represented by $\chi = a\chi_{\frac{1}{2}}^{+\frac{1}{2}}+b\chi_{\frac{1}{2}}^{-\frac{1}{2}}=\begin{pmatrix}a \\ b\end{pmatrix}$.

>[!definition] Pauli Spin Matrices
>The Pauli spin matrices are defined as: $$\sigma_{x}=\begin{pmatrix}0&1\\1&0\end{pmatrix},\quad \sigma_{y}=\begin{pmatrix}0&-i\\i&0\end{pmatrix},\quad \sigma_{z}=\begin{pmatrix}1&0\\0&-1\end{pmatrix}$$

<u><b>e.g</b></u>  If a particle has intrinsic spin $s = 1/2$, then the spin operator can be represented by the Pauli matrices: $$\hat{S}_{x}=\frac{\hbar}{2}\sigma_{x},\quad \hat{S}_{y}=\frac{\hbar}{2}\sigma_{y},\quad \hat{S}_{z}=\frac{\hbar}{2}\sigma_{z}$$


## The Hydrogen Atom

>[!proposition] 
>**Prop**  In spherical polar coordinates, the squared angular momentum operator can be expressed as: $$\hat{L}^{2}=-\hbar^{2}\left[\frac{1}{\sin \theta}\frac{\partial}{\partial\theta}\left(\sin\theta\frac{\partial}{\partial\theta}\right)+\frac{1}{\sin^{2}\theta}\frac{\partial^{2}}{\partial \phi^{2}}\right]$$**Proof**  Simply because $\hat{L}^{2}=\hat{L}_{x}^{2}+\hat{L}_{y}^{2}+\hat{L}_{z}^{2}$.

>[!definition] Bohr Radius
>In an atomic system, the Bohr radius is a natural length scale: $$a_{0}=\frac{4\pi\epsilon_{0}\hbar^{2}}{e^{2}m_{e}}=0.529\times10^{-10}\:\mathrm{m}$$ ^2eed8e

>[!definition] Rydberg Constant
>The Rydberg constant is a scale for energy that defined as $$E_\mathrm{R}=\frac{\hbar^{2}}{2m_{e}a_{0}^{2}}=13.6 \: \mathrm{eV}$$

>[!definition] 
>**Def**  <i><u>Effective Potential</u></i>
>The effective potential in a hydrogen system is defined as: $$V_{\mathrm{eff}}=\frac{l(l+1)\hbar^{2}}{2mr^{2}}-\frac{e^{2}}{4\pi\epsilon_{0}r}$$

>[!proposition] 
>**Prop**  The minimum of the effective potential is achieved at $r_{\mathrm{min}}=l(l+1)a_{0}$ where $a_{0}$ is the [[Angular Momentum#^2eed8e|Bohr radius]]. And the minimum value of the effective potential is given by $$V_{\mathrm{eff}}(r_\mathrm{min})=-\frac{E_\mathrm{R}}{l(l+1)}$$

>[!theorem] 
>**Thrm**  <i><u>Bohr Expression</u></i>
>The eigenvalues of the hydrogen system is given by $$E_{n_{r},l}=-\frac{E_\mathrm{R}}{(n_{r}+l+1)^{2}}=-\frac{E_\mathrm{R}}{n^{2}}$$where $n=n_{r}+l+1$ is defined as the principle quantum number.

>[!definition] Spectroscopic Notation
>In spectroscopic notation, we use combination of a number and a letter to denote the principle quantum number $n$ and orbital quantum number $l$ respectively. If $l=0$, we use $s$; If $l=1$, we use $p$; If $l=2$, we use $d$.
><u><b>e.g.</b></u>  
>- $2s$ stands for $n=n_{r}+l+1=2$, $l=0$; 
>- $2p$ stands for $n=n_{r}+l+1=2$, $l=1$;
>- The atom Trusconium has $8$ protons, $9$ neutrons and $8$ electrons, then its shell structure is $1s^22s^22p^4$