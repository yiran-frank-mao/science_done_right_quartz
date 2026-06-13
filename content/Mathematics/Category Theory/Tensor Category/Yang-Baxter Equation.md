> [!definition] Yang-Baxter Object
> Suppose $(\mathsf{C}, \otimes, \one,\alpha,\lambda,\eta)$ is a monoidal category. A Yang-Baxter object is an object $X$ equipped with an automorphism $r\colon X \otimes X \to X \otimes X$ called a *Yang-Baxter operator* such that 
> 
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/Yang_Baxter_operator.svg" style="width:60%;"/>
> 
> commutes.

> [!theorem]
> In a braided monoidal category $(\mathsf{C},\otimes, \one, \alpha,\lambda,\rho,\tau)$, we have the following diagram commutes for all objects $X,Y,Z$:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/braided_category_yb_property_org.svg" style="width:60%;"/>
> 

*Proof*  We cut the diagram into three parts as illustrated below. The left (red) and right (blue) parts are exactly the hexagon axioms for the braiding, and the middle square commutes by naturality of the braiding. Therefore, the whole diagram commutes.  $\square$
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/braided_category_yb_property.svg" style="width:60%;"/>