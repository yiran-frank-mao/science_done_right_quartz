>[!definition] 
>**Def**  <i><u>Optical Flow</u></i>
>Optical flow is the pattern of apparent motion of image objects between two consecutive frames caused by the movement of object or camera. It is 2D vector field where each vector is a displacement vector showing the projection of velocity of points in the real world to the image plane.

>[!theorem] 
>**Thrm**  <i><u>Brightness Constancy Equation</u></i>
>The brightness constancy equation states that the intensity of a pixel does not change between two consecutive frames: $$I(x,y,t)=I(x+\Delta x,y+\Delta y,t+\Delta t)$$Under first order Taylor expansion, we have: $$I(x+\Delta x,y+\Delta y,t+\Delta t)\approx I(x,y,t)+\frac{\partial I}{\partial x}\Delta x+\frac{\partial I}{\partial y}\Delta y+\frac{\partial I}{\partial t}\Delta t=I(x,y,t)$$Therefore, we have the brightness constancy equation: $$\frac{\partial I}{\partial x}u+\frac{\partial I}{\partial y}v+\frac{\partial I}{\partial t}=0$$where $(u,v)$ is the optical flow vector.

>[!algorithm] 
>**Algorithm**  <i><u>Lucas–Kanade's Algorithm</u></i>
>Assume constant small motion within a small neighbourhood, and brightness constancy is satisfied. Then a $5\times 5$ image patch gives us $25$ brightness constancy equations. We can stack them into a matrix form: $$\begin{aligned}
>\begin{bmatrix}\frac{\partial I}{\partial x}(x_1,y_1) & \frac{\partial I}{\partial y}(x_1,y_1) \\ \vdots & \vdots \\ \frac{\partial I}{\partial x}(x_{25},y_{25}) & \frac{\partial I}{\partial y}(x_{25},y_{25})\end{bmatrix}\begin{bmatrix}u \\ v\end{bmatrix}&=-\begin{bmatrix}\frac{\partial I}{\partial t}(x_1,y_1) \\ \vdots \\ \frac{\partial I}{\partial t}(x_{25},y_{25})\end{bmatrix} \\
>\implies A\begin{bmatrix}u \\ v\end{bmatrix}&=b
>\end{aligned}$$Then the least square solution is given by: $$\begin{bmatrix}u \\ v\end{bmatrix}=(A^{\top}A)^{-1}A^{\top}b$$

>[!remark]
>Indeed, we saw the matrix $$A^{\top}A = \begin{bmatrix}\sum \frac{\partial I}{\partial x}^2 & \sum \frac{\partial I}{\partial x}\frac{\partial I}{\partial y} \\ \sum \frac{\partial I}{\partial x}\frac{\partial I}{\partial y} & \sum \frac{\partial I}{\partial y}^2\end{bmatrix}$$ in the [[Image Filtering#^7a835f|Harris corner detector]]. Harris corners are where eigenvalues $𝜆_{1}$ and $𝜆_{2}$ are both big, this is also when Lucas–Kanade optical flow estimation works best. It implies that corners are good places to compute optical flow.

>[!algorithm] 
>**Algorithm**  <i><u>Coarse-to-Fine Optical Flow Estimation</u></i>
>The coarse-to-fine optical flow estimation is based on Gaussian pyramid. The algorithm is as follows:
>1. Construct Gaussian pyramid for both images.
>2. Start from the coarsest level, estimate optical flow.
>3. Upsample the optical flow to the next finer level.
>4. Refine the optical flow estimate at the finer level.
>5. Repeat until the original image level is reached.
>6. The final optical flow is the refined estimate at the original image level.
>$\quad$