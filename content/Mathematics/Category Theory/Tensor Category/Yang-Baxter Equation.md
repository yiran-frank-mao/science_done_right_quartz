> [!definition] Yang-Baxter Object
> Suppose $(\mathsf{C}, \otimes, \one,\alpha,\lambda,\eta)$ is a monoidal category. A Yang-Baxter object is an object $X$ equipped with an automorphism $r\colon X \otimes X \to X \otimes X$ called a *Yang-Baxter operator* such that 
> 
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/Yang_Baxter_operator.svg" style="width:60%;"/>
> 
> commutes.

> [!definition] Yang-Baxter Operator ^9fa28c
> Let $(\mathsf{C}, \otimes, \one,\alpha,\lambda,\rho)$ be a monoidal category. A *Yang-Baxter object* is an object $X$ equipped with an automorphism $r\colon X \otimes X \to X \otimes X$, called a *Yang--Baxter operator*, such that the Yang--Baxter equation holds for $X$, $X$, $X$, and $r$.
> In the case of a strict monoidal category, this is equivalent to the equation
> $$(r\otimes \id_X) (\id_X\otimes r) (r \otimes \id_X) = (\id_X \otimes r) (r \otimes \id_X) (\id_X\otimes r)$$
> holding.

> [!proposition]
> Suppose $(X,r)$ is a Yang--Baxter operator. Fix some integer $n>1$. For all $1\leq j\leq n-1$, define $$c_j^{(n)}\colon X^{\otimes n} \to X^{\otimes n}, \qquad  c_j^{(n)} := \id_X^{\otimes (j-1)} \otimes r \otimes \id_{X}^{\otimes (n-j-1)}.$$
> Then $c_j^{(n)} c_{j+1}^{(n)} c_j^{(n)}=c_{j+1}^{(n)} c_j^{(n)} c_{j+1}^{(n)}$.
> 

^7c4536

*Proof*  Without loss of generality, we assume strict monoidal category is strict. For the non-strict case, we only need to insert some associators carefully in the computation. Observe that in $c_j^{(n+1)} c_{j+1}^{(n+1)} c_j^{(n+1)}$ only affects the three tensor factors, this means
$$\begin{aligned}
	 & c_j^{(n)} c_{j+1}^{(n)} c_j^{(n)} \\
	=&\, \left(\id_X^{\otimes (j-1)} \otimes r \otimes \id_{X}^{\otimes (n-j-1)}\right) \left(\id_X^{\otimes (j)} \otimes r \otimes \id_{X}^{\otimes (n-j-2)}\right) \left(\id_X^{\otimes (j-1)} \otimes r \otimes \id_{X}^{\otimes (n-j-1)}\right) \\
	=&\, \id_X^{\otimes (j-1)} \otimes [(r\otimes \id_X) (\id_X\otimes r) (r \otimes \id_X)] \otimes \id_X^{\otimes(n-j-2)}.
\end{aligned}$$
Similarly, 
$$c_{j+1}^{(n)} c_j^{(n)} c_{j+1}^{(n)} = \id_X^{\otimes (j-1)} \otimes [(\id_X \otimes r) (r \otimes \id_X) (\id_X\otimes r)] \otimes \id_X^{\otimes(n-j-2)}.$$
So the equation in the [[Yang-Baxter Equation#^9fa28c|definition]] implies the desired equality.