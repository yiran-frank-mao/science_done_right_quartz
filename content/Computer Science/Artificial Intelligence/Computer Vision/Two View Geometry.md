## Homographies

>[!definition] 
>**Def**  <i><u>Projective Transformation</u></i>
>$$\require{mhchem}\newcommand{\tr}[1]{#1^{\top}}\begin{bmatrix}x'\\y'\\1\end{bmatrix}=\begin{bmatrix}\mathbf{A}&t\\\mathbf{v}^\top&b\end{bmatrix}\begin{bmatrix}x\\y\\1\end{bmatrix}=\mathbf{H}\begin{bmatrix}x\\y\\1\end{bmatrix}$$

>[!definition] 
>**Def**  <i><u>Cross Ratio</u></i>
>The cross ratio of four points $A$, $B$, $C$ and $D$ is defined as: $$(A,B;C,D)=\frac{AC \cdot BD}{BC \cdot AD}$$

>[!proposition] 
>**Prop**  Projective transformation preserves colinearity.

>[!proposition] 
>**Prop**  Projective transformation preserves cross ratio of $4$ collinear points: ![|200](https://i.imgur.com/dDeX1Gg.png)$$(A,B;C,D)=(A^{\prime},B^{\prime};C^{\prime},D^{\prime})$$

>[!proposition] 
>**Prop**  <i><u>Transformation of 2D Points and Lines</u></i>
>Suppose we have transformation from points into points $\mathbf{H}$, i.e. $x^{\prime}=\mathbf{H} x$, then for any line $l\colon \tr{a}x=b$, it maps to $l^{\prime}\colon (\mathbf{H}^{-\top}a) x=b$. ![](https://i.imgur.com/Xq8Xgc5.jpeg)**Proof**  $b=\tr{a}x=\tr{a}(\mathbf{H}^{-1}\mathbf{H})x=\tr{(\mathbf{H}^{-\top}a)}\mathbf{H} x$.

>[!definition] 
>**Def**  <i><u>Homography (Matrix)</u></i>
>Homography is a projective transformation between two images of the same planar surface. It is represented by a $3\times 3$ transformation matrix under a homogenous coordinates.

## Homography Estimation

>[!algorithm] 
>**Algorithm** <i><u>Direct Linear Transformation</u></i>
>Given an equation of the form $$Ax=0$$in the presence of noise. The DLT solution is obtained by computing the SVD of $A=U\Sigma V^{\top}$ and taking the last column of $V$ as the solution for $x$.

>[!algorithm] 
>**Algorithm**  <i><u>Direct Linear Transformation for Homography Estimation</u></i>
>Goal: Given $n\geq 4$ 2D-2D point correspondences $\{\mathbf{x}_{i}\sim \mathbf{x}_{i}^{\prime}\}$, determine the $3×3$ homography matrix $\mathbf{H}$ such that $𝐱_{i}^\prime \approx \mathbf{H}𝐱_{i}$. 
>1. For each correspondence $x_{i}\sim x^{\prime}_{i}$ compute matrix $\mathbf{A}_{i}$, taking only the first $2$ rows.
>2. Assemble the $n$ $2×9$ $𝐀_{i}$ matrices into a single $2𝑛×9$ matrix $𝐀$.
>3. Compute the SVD of $𝐀=\mathbf{U}\mathbf{\Sigma}\mathbf{V}^{\top}$.
>4. Take the last column of $𝐕$ as the solution for $𝐡$.
>5. Rearrange $𝐡$ to obtain $𝐇$.
>
>where for $\mathbf{x}_{i}=[x_{1},y_{1},w_{1}]$ and ^8da8dc

>[!algorithm] 
>**Algorithm**  <i><u>Normalised DLT for Homography Estimation</u></i>
>Goal: Given $n\geq 4$ 2D-2D point correspondences $\{\mathbf{x}_{i}\sim \mathbf{x}_{i}^{\prime}\}$, determine the $3×3$ homography matrix $\mathbf{H}$ such that $𝐱_{i}^\prime \approx \mathbf{H}𝐱_{i}$.
>1. Normalise 2D points: $\tilde{\mathbf{x}}_{i}=\mathbf{T}\mathbf{x}_{i}$, $\tilde{\mathbf{x}}_{i}^{\prime}=\mathbf{T}^{\prime}\mathbf{x}_{i}^{\prime}$.
>2. Apply the [[Two View Geometry#^8da8dc|DLT algorithm]] to $\{\tilde{\mathbf{x}}_{i}\sim \tilde{\mathbf{x}}_{i}^{\prime}\}$, get $\tilde{\mathbf{H}}$.
>3. Denormalise the recovered solution $\tilde{\mathbf{H}}$ using $\mathbf{H}=\mathbf{T}^{\prime{-1}}\tilde{\mathbf{H}}\mathbf{T}$.
>
><u><b>e.g.</b></u>  Example normalisation matrices: $$\mathbf{T}=\begin{bmatrix}w+h&0&w/2\\0&w+h&h/2\\0&0&1\end{bmatrix}^{-1},\quad\mathbf{T}^{\prime}=\begin{bmatrix}w^{\prime}+h^{\prime}&0&w^{\prime}/2\\0&w^{\prime}+h^{\prime}&h^{\prime}/2\\0&0&1\end{bmatrix}^{-1}$$where $w$,$h$ and $w^{\prime}$,$h^{\prime}$ are image widths and heights respectively.

>[!algorithm] 
>**Algorithm**  <i><u>Gold Standard</u></i>
>Goal: Given $n\geq 4$ 2D-2D point correspondences $\{\mathbf{x}_{i}\sim \mathbf{x}_{i}^{\prime}\}$, determine the $3×3$ homography matrix $\mathbf{H}$ such that $𝐱_{i}^\prime \approx \mathbf{H}𝐱_{i}$.
>1. Initialisation: Compute an initial estimate using normalised DLT or RANSAC.
>2. Geometric minimisation of reprojection error:
>	1. Minimise using Levenberg-Marquardt over the $9$ entries of $𝐇$.
>	2. Compute initial estimate for optimal $\{\mathbf{x}_{i}\}$.
>	3. Minimise cost
>3. Denormalise the recovered solution.
>$\quad$

## Epipolar Geometry

>[!comment]
>Epipolar geometry is the intrinsic geometry of 2 different views of the same 3D scene.

>[!definition] 
>**Def**  <i><u>Baseline</u></i> and <i><u>Epipole</u></i>
>Baseline is the line joining the camera centers. Epipole is the point of intersection of baseline with image plane. Epipolar plane is the plane containing baseline and world point. Epipolar line is the intersection of epipolar plane with the image plane.
><u><b>e.g.</b></u>  In the following diagram, we have world point $X$, camera centers $C$ and $C^{\prime}$, then $CC^{\prime}$ is the baseline, $ex$ and $e^{\prime}x^{\prime}$ is the epipolar line, $\pi$ is the epipolar plane.
>![|320](https://i.imgur.com/WdAHEnB.jpeg)

>[!proposition] 
>**Prop**  All epipolar lines intersect at the epipole. ![|320](https://i.imgur.com/2wuyYCY.jpeg)

>[!proposition] 
>**Prop**  Epipole is the projection of one optical centre in the other image.

## Essential and Fundamental Matrices

>[!definition] 
>**Def**  <i><u>Essential Matrix</u></i>
>The essential matrix encapsulates the epipolar geometry constraints between two views of a 3D scene, with calibrated cameras and contains the intrinsic camera parameters. It is $$E := [t]_{\times}R$$where $R$ is the rotation matrix in $\R^{3\times 3}$ and $[t]_\times$ is the translation crossproduct matrix in $\R^{3\times 3}$ of rank $2$: $$[t]_{\times}=\begin{bmatrix}0&-t_z&t_y\\t_z&0&-t_x\\-t_y&t_x&0\end{bmatrix}$$

**Prop**  The essential matrix $E$ has following properties:
- It has a rank of $2$.
- It is singular, has singular values $\sigma_{1}= \sigma_{2}$ and $\sigma_{3}= 0$.
- $\det(E)=0$
- $2EE^{\top}E -\trace{EE^{\top}}E =0$.

**Algorithm**  <i><u>Recovering $R$ and $t$ from $E$</u></i>
1. Implement SVD: $E = U\Sigma V^{\top}$.
2. Output $R = U W^{-1} V^{\top}$ and $[t]_{\times}=UW\Sigma U^{\top}$ where $$W = \begin{bmatrix}0&-1&0\\1&0&0\\0&0&1\end{bmatrix}$$
3. To get all 4 solutions, solve for combinations of $W$ and $W^{-1}$.
4. Select solution where all of the 3D points are in front of both cameras.

>[!definition] 
>**Def**  <i><u>Fundamental Matrix</u></i>
>The fundamental matrix encodes the relationship between two images of a 3D scene by encapsulating the epipolar geometry constraints, while the intrinsics of both cameras are not known. Mathematically, such matrix $F$ is the unique $3\times3$ rank $2$ matrix that satisfies $𝑥_{i}^{\prime\top}𝐹𝑥_{i} = 0$ for all corresponding points $x_{i}^{\prime}$ and $x_{i}$.

**Prop**  The fundamental matrix $F$ has following properties:
- If $𝐹$ is fundamental matrix for $(𝑥,𝑥^{\prime})$,then $F^{\top}$ is the fundamental matrix for $(𝑥', 𝑥)$.
- $F$ maps from a point $x$ in one image to a line $l^{\prime} = F x$ in the other image.
- Lie on all epipolar lines, thus $x^{\prime\top}Fx = 0$ for all $x$ implies $Fe=0$.

>[!algorithm] 
>**Algorithm**  <i><u>DLT for Fundamental Matrix Estimation</u></i>
>It is also called the 8-point algorithm. Given $n\geq 8$ 2D-2D point correspondences $\{\mathbf{x}_{i}\sim \mathbf{x}_{i}^{\prime}\}$, determine the $3×3$ fundamental matrix $F$ such that $𝐱_{i}^{\prime\top} F𝐱_{i} = 0$.
>1. Let $x=[u,v,1]^\top$, $x^{\prime}=[u^{\prime},v^{\prime},1]^\top$ and $$F = \begin{bmatrix}f_{11}&f_{12}&f_{13}\\ f_{21}&f_{22}&f_{23}\\ f_{31}&f_{32}&f_{33}\end{bmatrix}$$
>2. Construct the matrix $\mathbf{A} = \begin{bmatrix}u^{\prime}u&u^{\prime}v&u^{\prime}&v^{\prime}u&v^{\prime}v&v^{\prime}&u&v&1\end{bmatrix}$. And construct the vector $\mathbf{f}= [f_{11},f_{12},f_{13},f_{21},f_{22},f_{23},f_{31},f_{32},f_{33}]^{\top}$.
>3. Minimise $\|A\mathbf{f}\|^{2}$ subject to $\|\mathbf{f}\|=1$, get $\mathbf{f}$ as the least right singular vector of $A$.
>4. Reshape $\mathbf{f}$ to get $F^{\prime}$.
>5. But since $\rank F=2$, replace $F^{\prime}$ with $F$ by computing the SVD of $F^{\prime}$ and setting the smallest singular value to $0$. That is to solve the following [[Convex Optimization Problems#^9790f7|optimization problem]]: $$F=\argmin_{F} \|F-F^{\prime}\|^{2} \quad \text{subject to} \quad \det(F) = 0$$Concretely, decompose $F^{\prime}=U\Sigma V^{\top}$ and set $F=U\Sigma^{\prime}V^{\top}$ where $$\Sigma = \begin{bmatrix}\sigma_{1}&0&0\\0&\sigma_{2}&0\\0&0&\sigma_{3}\end{bmatrix},\quad \Sigma^{\prime} = \begin{bmatrix}\sigma_{1}&0&0\\0&\sigma_{2}&0\\0&0&0\end{bmatrix}$$
>6. Return $F$. 
>$\quad$ ^c2bf24

>[!comment]
>The 8-Point Algorithm has advantage of being simple and fast, but it is sensitive to noise, and it optimises a non-physical algebraic quantity.

**Algorithm**  <i><u>Normalised DLT for Fundamental Matrix Estimation</u></i>
1. Transform the points using normalisation matrices ${T}$ and ${T}^{\prime}$: $\hat{x}_{i}=T x_{i}$ and $\hat{x}_{i}^{\prime}=T^{\prime} x_{i}^{\prime}$.
2. Apply the [[Two View Geometry#^c2bf24|DLT algorithm]] to $\{\hat{x}_{i}\sim \hat{x}_{i}^{\prime}\}$, get $\hat{F}$.
3. Then denormalise the recovered solution $\hat{F}$ using $F=T^{\prime\top}\hat{F}T$.

## Triangulation

**Def**  <i><u>Triangulation Problem</u></i>
The triangulation problem is to compute the 3D location $\mathbf{X}$, given image points $\mathbf{x}$ and $\mathbf{x}^{\prime}$ in correspondence across two or more images (taken from calibrated cameras with known intrinsics and extrinsics).

**Algorithm**  <i><u>DLT Triangulation</u></i>
Given camera projection matrix $\mathbf{P}$, $\mathbf{P}^{\prime}$ and corresponding points $\mathbf{x}$, $\mathbf{x}^{\prime}$:
1. Precondition points and projection matrices.
2. Create matrix $A$.
3. Compute SVD of $A=U\Sigma V^{\top}$.
4. Extract $\mathbf{X}$ from the last column of $V$.
5. Then refine with respect to a geometric error.
sample code can be found [here](https://www.robots.ox.ac.uk/~vgg/hzbook/code/vgg_multiview/vgg_X_from_xP_lin.m).

## Stereo Vision

>[!comment]
> Humans do 3D perception well from a single image and very well from stereo (binocular) images. An intermediate goal of computer vision was to mimic the functionality of the biological system.

>[!definition] 
>**Def**  <i><u>Disparity</u></i> 
>Disparity is the positional difference between the two retinal projections of a given point in space.
><u><b>e.g.</b></u>  In the following setting, we have disparity $d=u_{L}-u_{R}$.
>![|330](https://i.imgur.com/kkLnMR3.png)

>[!proposition] 
>**Prop**  If optical axes are parallel and heights of the camera centers are identical, then for points at a fixed depth, the disparity between the corresponding points in the two images is constant.

**Def**  <i><u>Rectified Stereo Images</u></i>
We say the stereo images are rectified if 
- Image planes of cameras are parallel;
- Principal axes are at same height;
- Identical focal lengths.

**Prop**  The epipolar lines fall along the horizontal scan lines of the images in a rectified stereo setting.

### The Correspondence Problem

**Def**  <i><u>Correspondence Problem</u></i>
The correspondence problem in stereo vision is the problem of measuring the disparity of each point in the two eye (camera) projections.

**Law**  <i><u>Colour Constancy Constraint</u></i>
Same world point has same intensity (or colour) in both images.

**Def**  <i><u>Sum of Squared (Pixel) Differences</u></i>
Suppose $W_{L}$ and $W_{R}$ are corresponding $m$ by $n$ windows of pixels. Define the following window function: $$W_{m}(x,y)=\left\{u,v \mid x- \frac{m}{2} \leq u \leq x + \frac{m}{2}, y- \frac{m}{2}\leq v \leq y+ \frac{m}{2}\right\}$$The sum of squared difference cost measures the intensity differences as a function of disparity: $$C_{r}(x,y,d) = \sum_{(u,v)\in W_{m}(x,y)}[I_{L}(u,v)-I_{R}(u-d,v)]^{2}$$


### Interpretation Problem

**Def**  <i><u>Interpretation Problem</u></i>
The interpretation problem in stereo vision is about how to use disparity information to recover the orientation and distance of surfaces in the scene.



