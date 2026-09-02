## Diagonal
**Prop** For any matrix $A \in \R^{n\times n}$, pre-multiply by a diagonal matrix scales its the rows, while post-multiply by a diagonal matrix scales its the columns.

## Inverse 
**Def**  <i><u>Pseudo-Inverse</u></i>
The Pseudo-Inverse of some matrix $X$ is defined as $X^{\dagger} = (X^\mathrm{T}X)^{-1} X^\mathrm{T}$. Specifically, if $X$ is invertible, we have $X^{\dagger} = X^{-1}$

## Trace
**Def**  <i><u>Trace</u></i>
The trace of a square matrix $A ∈ \R^{n×n}$ is the sum of diagonal elements: $$\newcommand{\trace}{\operatorname{\textbf{tr}}}\trace\left(A\right)=\sum_{i=1}^{n}A_{ii}$$


**Prop**  Trace satisfies the following properties:
- $\newcommand{\tr}[1]{{#1}^{\top}} \operatorname{\textbf{tr}}(A)=\operatorname{\textbf{tr}}(\tr{A})$.
- $\operatorname{\textbf{tr}}\left(\alpha A+\beta B\right)=\alpha\operatorname{\textbf{tr}}\left(A\right)+\beta\operatorname{\textbf{tr}}\left(B\right)$ for all $\alpha,\beta\in\R$.
- if $AB$ is square then $\trace{(AB)}=\trace\left(BA\right)$.

## Factorizations
**Thrm**  <i><u>LU Factorization</u></i>
Every non-singular matrix $A ∈ \R^{n×n}$ can be factored as
$$A=PLU$$
where $P ∈ \R^{n×n}$ is a permutation matrix, $L ∈ \R^{n×n}$ is unit lower triangular, and $U ∈ \R^{n×n}$ upper triangular and non-singular.

**Thrm**  <i><u>Cholesky Factorization</u></i>
Every symmetric positive definite matrix $A ∈ \R^{n×n}$ can be factored as
$$A=L\tr{L}$$
where $L ∈ \R^{n×n}$ is lower triangular and non-singular with positive diagonal elements.

**Thrm**  <i><u>Singular Value Decomposition</u></i>
Any matrix $A$ can be decomposed as
$$A=U\Sigma\tr{V}$$

## Differentiation
**Def**  <i><u>Jacobian</u></i>
Suppose $f : \R^{m×n} → \R$ is a function. Then the gradient of $f(A)$ with respect to $A ∈ \R^{m×n}$ is the matrix of partial derivatives called Jacobian:
$$
\nabla_Af(A)=\begin{bmatrix}\frac{\partial f}{\partial A_{11}}&\frac{\partial f}{\partial A_{12}}&\cdots&\frac{\partial f}{\partial A_{1n}}\\\frac{\partial f}{\partial A_{21}}&\frac{\partial f}{\partial A_{22}}&\cdots&\frac{\partial f}{\partial A_{2n}}\\\vdots&\vdots&\ddots&\vdots\\\frac{\partial f}{\partial A_{m1}}&\frac{\partial f}{\partial A_{m2}}&\cdots&\frac{\partial f}{\partial A_{mn}}\end{bmatrix}
$$

**Def**  <i><u>Hessian</u></i>
Suppose that $f : \R^n → \R$ is a function. Then the hessian of $f(x)$ with respect to $x ∈ \R^n$ is the $n × n$ matrix of second partial derivatives:
$$
\nabla_x^2f(x)=\begin{bmatrix}\frac{\partial^2f}{\partial x_1^2}&\frac{\partial^2f}{\partial x_1\partial x_2}&\cdots&\frac{\partial^2f}{\partial x_1\partial x_n}\\\frac{\partial^2f}{\partial x_2\partial x_1}&\frac{\partial^2f}{\partial x_2^2}&\cdots&\frac{\partial^2f}{\partial x_2\partial x_n}\\\vdots&\vdots&\ddots&\vdots\\\frac{\partial^2f}{\partial x_n\partial x_1}&\frac{\partial^2f}{\partial x_n\partial x_2}&\cdots&\frac{\partial^2f}{\partial x_n^2}\end{bmatrix}
$$
**Prop**  Hessian is symmetric.

**Thrm**  <i><u>Differentiation Laws</u></i>
- Constant: $\partial{C}=0$
- Addition: $\partial{(X \pm Y)} = \partial{X} \pm \partial Y$
- Matrix multiplication: $\partial{(XY)} = (\partial{X})Y + X(\partial{Y})$
- Element-wise multiplication: $\partial{(X \odot Y)} = (\partial{X}) \odot Y + X \odot (\partial{Y})$
- Transpose: $\partial{(X^{\top})} = (\partial{X})^\top$
- Inverse: $\partial{X^{-1}} = -X^{-1} (\partial{X}) X^{-1}$
- Trace: $\partial{(\mathrm{tr}(X))} = \mathrm{tr}(\partial{X})$
- Differential: Suppose $f\colon \R^{m\times n}\to \R$, then $\newcommand{\pddf}[2]{\frac{\partial#1}{\partial#2}}\newcommand{\d}{\mathrm{d}} \d f = \mathrm{tr}\left(\tr{\left( \pddf{f}{X}\right) }\dd X\right)$
- Determinant: $\partial{|X|} = \trace(X^{\#}\partial{X})$
    - Specially, if $X$ is invertible, $\partial{|X|} = |X|\mathrm{tr}(X^{-1}\partial{X})$.

<b><u>e.g.</u></b>  Suppose $a\in \R^m,b\in\R^n,X\in\R^{m\times n}$. Consider  $f(X)=\tr{a}Xb$. Then we have
$$\d f=\tr{a}(\d X )b = \trace{\tr{a}(\d X )b} = \trace{b\tr{a}(\dd X )}  \implies \pddf{f}{X}=\tr{(b\tr{a})}=a\tr{b}.$$

## Block Matrix
**Thrm**  <i><u>Block matrix Determinant</u></i>
$$
\begin{aligned}
&\det\begin{bmatrix}A&0\\C&D\end{bmatrix}=\det(A)\det(D)=\det\begin{bmatrix}A&B\\0&D\end{bmatrix}\\
\text{ $A$ is invertible:} \quad &\det\begin{bmatrix}A&B\\C&D\end{bmatrix}=\det(A)\det\left(D-CA^{-1}B\right) \\
\text{$C$ and $D$ commute:}\quad &\det\begin{bmatrix}A&B\\C&D\end{bmatrix}=\det(AD-BC) \\
&\det\begin{bmatrix}A&B\\B&A\end{bmatrix}=\det(A-B)\det(A+B) \\
\end{aligned}
$$

**Thrm**  <i><u>Block Matrix Inverse</u></i>
$$
\begin{bmatrix}\mathbf{A}&\mathbf{B}\\\mathbf{C}&\mathbf{D}\end{bmatrix}^{-1}=\begin{bmatrix}\mathbf{A}^{-1}+\mathbf{A}^{-1}\mathbf{B}\big(\mathbf{D}-\mathbf{C}\mathbf{A}^{-1}\mathbf{B}\big)^{-1}\mathbf{C}\mathbf{A}^{-1}&-\mathbf{A}^{-1}\mathbf{B}\big(\mathbf{D}-\mathbf{C}\mathbf{A}^{-1}\mathbf{B}\big)^{-1}\\-\left(\mathbf{D}-\mathbf{C}\mathbf{A}^{-1}\mathbf{B}\right)^{-1}\mathbf{C}\mathbf{A}^{-1}&\left(\mathbf{D}-\mathbf{C}\mathbf{A}^{-1}\mathbf{B}\right)^{-1}\end{bmatrix}
$$