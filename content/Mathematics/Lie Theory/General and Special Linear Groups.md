## Special Linear Groups

Recall the special linear groups:

![[Linear Groups#^e54947]]

<u><b>e.g.</b></u>
- The Lie algebra $\newcommand{\sl}{\mathfrak{sl}}\sl_{2}(\R)$ consists of all $2\times 2$ real matrices with trace zero. A standard basis is given by $$n^{+} = \begin{pmatrix}0 & 1 \\ 0 & 0\end{pmatrix}, \quad n^{-} = \begin{pmatrix}0 & 0 \\ 1 & 0\end{pmatrix}, \quad h = \begin{pmatrix}1 & 0 \\ 0 & -1\end{pmatrix}$$with Lie brackets $$[h,n^{+}] = 2n^{+}, \quad [h,n^{-}] = -2n^{-}, \quad [n^{+},n^{-}] = h.$$As $\sl_{2}(\R)$ is so important in physics, people give special names to these basis elements: $n^{+}$ is called the *raising operator*, $n^{-}$ the *lowering operator*, and $h$ the *Cartan operator*. ^62ffcf
- The complexification of $\sl_{2}(\R)$ is $\sl_{2}(\C)$. i.e., $\sl_{2}(\R) \otimes_{\R} \C \cong \sl_{2}(\C)$. So the above basis also works for $\sl_{2}(\C)$. It is also sometimes useful to use [[Spin#^773ff2|Pauli matrices]] as a basis of it. Suppose $\{H,E,F\}$ is a basis of $\sl_{2}(\C)$ satisfying $$[H,E]=2E,\quad [H,F]=-2F,\quad [E,F]=H.$$Then the *Casimir operator* of $\sl_{2}(\C)$ is defined as $$\Omega=\frac{1}{2}H^{2}+EF+FE = \frac{1}{2}H^{2}+H+2FE.$$A notable result is that $\Omega$ lies in the [[Central Extensions of Lie Algebras#^e35973|center]] of $\sl_{2}(\C)$, for which one can verify that $$[\Omega,E]=[\Omega,F]=[\Omega,H]=0.$$ ^4c1fe6