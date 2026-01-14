## Matrix Linear Groups

>[!definition] General Linear Group
Claim that the set of all linear operators together with operation of ordinary matrix multiplication is a group. We write it as $\newcommand{\GL}{\mathrm{GL}}\GL_n(\mathbb{F})$, where $n$ denotes the dimension of the corresponding square matrix. That is:$$ \text{GL}_n(\mathbb{F})= \{ A\in\mathbb{F}^{n\times n} \mid \text{$A$ is invertible} \}. $$ ^264ff5

>[!definition] Special Linear Group
> Claim that the set of all linear operators such that determinant is $1$ is a group. Write it as $\mathrm{SL}_n(\mathbb{F})$where $n$ denotes the dimension of the corresponding square matrix. ^e54947

> [!definition] Orthogonal Group
> The orthogonal group, often denoted $\mathrm{O}_{n}$, is the [[Groups, Order and Subgroups#^6e0960|group]] of all [[Inner Products#^f76c1a|orthogonal transformations]] of $n$-dimensional real space $\R^{n}$ under the operation of composition.

>[!definition] Rotation Group
>The rotation group, often denoted $\mathrm{SO}_{n}$, is the [[Groups, Order and Subgroups#^6e0960|group]] of all rotations about the origin of $n$-dimensional Euclidean space $\R^{n}$ under the operation of composition.  ^2ce0d2

<u><b>e.g.</b></u> In $\mathrm{SO}_{3}$, counterclockwise rotation about the positive axis by some angle $\phi$ is given by$$\begin{aligned}
{R}_x(\alpha)=\begin{bmatrix}1&0&0\\0&\cos\alpha&-\sin\alpha\\0&\sin\alpha&\cos\alpha\end{bmatrix} \\ R_{y}(\beta)=\begin{bmatrix}\cos\beta&0&\sin\beta\\0&1&0\\-\sin\beta&0&\cos\beta\end{bmatrix}\\ R_{z}(\phi)=\begin{bmatrix}\cos\phi&-\sin\phi&0\\\sin\phi&\cos\phi&0\\0&0&1\end{bmatrix}
\end{aligned}$$

>[!proposition]
>$\mathrm{SO}_{3}\leq \text{GL}_{3}(\R)$.

## Projective Linear Group

> [!definition] Projective Linear Group
> The projective linear group $\newcommand{\PL}{\mathrm{PL}}$ on a [[Vector Spaces#^f4b63e|vector space]] $V$ is the quotient group $\PL(V):=\GL(V)/Z(V)$, where $Z(V)$ is the subgroup of all nonzero scalar transformations of $V$. These are quotiented out because they act trivially on the associated projective space $\mathrm{P}(V)$.
>


