**Algorithm** <i><u>Minimum Norm Interpolation</u></i>
Suppose we have a linear regression problem $(X,y,f_\theta)$, the minimum norm interpolation is a training algorithm solves the optimization problem: $$\begin{aligned}
\text{minimize}_{\theta\in\mathbb{H}} \quad &\|\theta\|^2\\\mathrm{such~that}\quad&\|X\theta-y\|^2=\min_{\beta}\|X\beta-y\|^{2}\end{aligned}$$
**Prop**  <i><u>Analytic Solution to Minimum Norm Interpolation</u></i>
Assume overparametrization happens, the analytic solution to minimum norm interpolation is$$\theta^{\star}=X^{\top}(XX^{\top})^{-1}y$$**Proof**  Since overparametrization happens, there exists $\beta$ such that $\|X\beta-y\|=0$. Then by KKT conditions, we have the following equations hold: $$\begin{aligned}
g(\theta,\lambda)\end{aligned}$$