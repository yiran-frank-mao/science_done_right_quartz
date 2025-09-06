---
created: 2024-10-21
updated: 2024-11-02
completed: true
---
By the [[The Open Mapping Theorem#^2ea31f|theorem]], we know that if $f$ is [[Relations and Functions#^042daf|bijective]], it is [[Holomorphic and Conformal Maps#^3dad2a|biholomorphic]]. So that we can study the group of conformal transformations of some domain.

> [!definition] Group of Conformal Transformations
> The group of conformal transformations of some domain $D$ is defined as $$\newcommand{\conf}{\mathrm{Conf}}\conf(D):=\{ f\colon D\to D\mid f \text{ is biholomorphic} \}$$

> [!proposition]
> Suppose $|w|<1$ and $|\beta|=1$, and let $$f(z)=\beta\frac{z-w}{-\bar{w}z+1}=\beta\alpha_{w}(z)$$Then $f\in\conf(\Delta)$. ^e99ce6

*Proof*  Since [[Möbius Transformations#^da9a62|Möbius transformations]] map [[Möbius Transformations#^391810|generalized disks]] to generalized disks, it is enough to show that $f(0)\in \Delta$ and $f(\partial\Delta)\subset \partial\Delta$. We have $f(0)=-\beta w$, and since $|-\beta w|=|w|<1$, we have $f(0)\in \Delta$. For $z\in \partial\Delta$, we have $$\begin{aligned}|f(z)|&=\left|\frac{z-w}{-\overline{w}z+1}\right|\\&=\frac1{|\overline{z}|}\left|\frac{z-w}{-\overline{w}z+1}\right|\\&=\left|\frac{z-w}{-\overline{w}+\overline{z}}\right|\\&=\frac{|z-w|}{|\overline{z}-\overline{w}|}=1\end{aligned}$$$\square$

## The Schwarz Lemma

> [!theorem] The Schwarz Lemma
> Let $f\in H(\Delta)$ with $|f(z)|\leq 1$ for all $z\in \Delta$ and $f(0)=0$. Then $|f(z)|\leq |z|$ for all $z\in \Delta$, and $|f'(0)|\leq 1$. 
> Moreover, if $|f'(0)|= 1$ or $|f(z)|= |z|$ for some non-zero $z ∈∆$, then $f$ is a rotation $f(z) = βz$ for some $\newcommand{\C}{\mathbb{C}}β\in \C$ with $|β|= 1$. ^5147f4

*Proof*  Since $f(0)=0$, $f(z)/z$ has a [[Isolated Singularities#^451c12|removable singularity]] at $z=0$, and $\lim_{z\to 0} \frac{f(z)}{z}=f'(0)$. Hence the function $g$ defined by $$g(z)=\begin{cases} \frac{f(z)}{z} &\quad z\in \Delta, z\neq 0 \\ f'(0)&\quad z=0 \end{cases}$$satisfies $g\in H(D)$. Fix $z\in \Delta$, and let $|z|<r<1$. Apply the [[The Open Mapping Theorem#^34ad01|weak maximum principle]] to $g$ on $\overline{\Delta(0,r)}$, we obtain:$$|g(z)|\leq \max_{|w|=r}|g(w)|=\max_{|w|=r}\frac{|f(w)|}{|w|}\leq \frac1r$$This holds for any $|z|<r<1$, so we may take limit as $r\to 1$ to obtain $|g(z)|\leq 1$ for all $z\in \Delta$. Thus $|f(z)|\leq |z|$ for all $z\in \Delta$. Since $|g(0)|\leq 1$, we have $|f'(0)|\leq 1$.
Moreover, if $|f'(0)|= 1$ or $|f(z)|= |z|$ for some non-zero $z ∈∆$, then $|g(z)|= 1$ for some $z\in \Delta$. Thus by the [[The Open Mapping Theorem#^5a8a82|strong maximum principle]], $g$ is constant, with constant value $\beta$ having modulus $1$. Thus $f(z)=\beta z$ for all $z\in \Delta$ as required. $\square$

> [!lemma]
> Let $f ∈\conf(∆)$ and suppose $f(0) = 0$. Then $f$ is a rotation, i.e. there is some $β$ with $|β|= 1$ such that $f(z) = βz$ for all $z ∈∆$. ^dcdcdf

*Proof*  Since $f^{-1} (f(z))=z$ for all $z\in\Delta$ and $f$ is biholomorphic, the chain rule gives $${f^{-1}}^{\prime}(f(z))f^{\prime}(z)=1$$In particular, $f^{\prime}(0){f^{-1}}^{\prime}(0)=1$. Since $f(\Delta)=\Delta$, we have $|f(z)|<1$ for all $z\in\Delta$. By the [[Conformal Transformations of The Disk#^5147f4|Schwarz lemma]], we have $|f^{\prime}(0)|\leq 1$. We can apply the same reasoning to $f^{-1}$ to obtain $|{f^{-1}}^{\prime}(0)|\leq 1$. But $f^{\prime}(0){f^{-1}}^{\prime}(0)=1$, so we must have $|f^{\prime}(0)|=|{f^{-1}}^{\prime}(0)|=1$. By the Schwarz lemma again, $f(z)=\beta z$ for some $|\beta|=1$. $\square$

> [!theorem]
> $$\conf(\Delta)=\left\{z\mapsto\beta \frac{z-w}{-\bar{w}z+1} : |\beta|=1, |w|<1\right\}$$

*Proof*  By the [[Conformal Transformations of The Disk#^e99ce6|proposition]], it suffices to prove the inclusion. Let $f\in \conf(\Delta)$, $w=f^{-1}(0)$. Recall that $\alpha_w(z)=\frac{{z-w}}{-\bar{w}z+1}\in\conf(\Delta)$ and $\alpha_w(w)=0$. Then $\alpha_{w}^{-1}(0)=w$, and $f\circ \alpha_{w}^{-1}$ is a conformal transformation of $\Delta$ that fixes $0$. By the [[Conformal Transformations of The Disk#^dcdcdf|previous lemma]], $f\circ \alpha_{w}^{-1}(z)=\beta z$ for some $|\beta|=1$. Thus $f(z)=\beta \frac{z-w}{-\bar{w}z+1}$ as required. $\square$

>[!remark]+
> We can now describe the geometric meaning of a conformal transformation of the disk. $w\in\Delta$ is the point that being sent to $0$, and $|\beta|=1$ is the rotation factor.

