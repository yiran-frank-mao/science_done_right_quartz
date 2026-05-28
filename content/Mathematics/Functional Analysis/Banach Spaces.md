>[!definition]
> A [[Normed Spaces#^345fd3|normed space]] $(X,\|\cdot\|)$ is a Banach space if it is [[Complete Metric Space#^67b510|complete]] as a [[Metric Spaces#^0eacc7|metric space]].

^7196a5

<u><b>e.g.</b></u>  Let $\Omega \subset \mathbb{R}^n$ be a domain and $\alpha \in (0,1]$. A function $f\colon \Omega \to \mathbb{R}$ is said to belong to the *Hölder space* $C^{0,\alpha}(\Omega)$ if $$\|f\|_{C^{0,\alpha}(\Omega)} := \sup_{x \in \Omega} |f(x)| + \sup_{\substack{x,y \in \Omega\\ x \neq y}} \frac{|f(x) - f(y)|}{|x-y|^\alpha} < \infty.$$
- The first term $\sup_{x \in \Omega} |f(x)|$ measures the boundedness of $f$.
- The second term $\sup_{x \neq y} \frac{|f(x) - f(y)|}{|x-y|^\alpha}$ measures the *$\alpha$-Hölder continuity* of $f$.  

Equipped with this norm, $C^{0,\alpha}(\Omega)$ is a Banach space.