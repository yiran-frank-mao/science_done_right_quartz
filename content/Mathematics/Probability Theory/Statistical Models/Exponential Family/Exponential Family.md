**Def**  <i><u>Exponential Family</u></i>
A [[Statistical Models#^25685d|parametric family]] of univariate continuous distributions is said to be an exponential family if the probability density function of any member of the family can be written as$$f(x)=h(x)\exp(\eta(\theta)^{\top}T(x)-A(\theta))$$where 
- $\theta\in\R^{k}$ is the vector of natural parameters;
- $h:\R\to\R^{+}, x\mapsto h(x)$ is base measure;
- $\eta:\R^{k}\to\R^{l}$ is natural parameters.
- $T:\R\to\R^{l}$ is sufficient statistic.
- $A:\R^{k}\to\R$ is log-partition.
Equivalently, we can also write it as:$$f(x)=\exp\left(\mathcal{A}(x)+\theta^\top t(x)-\psi(\theta)\right)$$

**Thrm** The natural parameter space is a [[Convex Sets#^3a9d82|convex]] domain, and $ψ$ is a [[Convex Functions#^c53709|convex function]].

**Def**  <i><u>Dual Parameter</u></i>
Given an exponential family $f(x)=\exp\left(\mathcal{A}(x)+\theta^\top t(x)-\psi(\theta)\right)$, $\eta = \nablaψ(θ) = \E[t (x )]$ is the dual/mean/expectation parameter of the exponential family.

**Prop**  The exponential family is conjugate.

**Prop**  The maximum likelihood estimator of an exponential family is simply arithmetic average: $$\hat{\eta} = \nabla\psi(\hat{\theta})=\frac1n\sum_{i=1}^{n} t(x_i)=\overline{t(x)}$$
**Prop**  The [[Fisher Information#^40ed31|fisher information matrix]] of an exponential family $f(x)=\exp\left(\mathcal{A}(x)+\theta^\top t(x)-\psi(\theta)\right)$ is given by $$I(\theta)=-\mathbb{E}_p\left[\frac{\partial^2L}{\partial\theta\partial\theta^\top}\right]=\frac{\partial^2\psi}{\partial\theta\partial\theta^\top}=\frac{\partial\eta}{\partial\theta}$$

