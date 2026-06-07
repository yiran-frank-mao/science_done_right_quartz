## Pinhole Camera Model

>[!theorem]
>**Thrm**  For the pinhole camera model with focal length $f$, given the world coordinate of a point $(x,y,z)$ we have the following projection equation: $$(x^{\prime},y^{\prime})=\left(f\frac{x}{z},f\frac{y}{z}\right)$$![|650](https://i.imgur.com/MScdnk7.jpeg)

<u><b>e.g.</b></u>  Given a lens with a focal length of 30, and a world point at $(20, 20, 200)$, where the camera center sits at $(0, 0, 0)$, and the optical axis is in direction $(0, 0, 1)$, with the $x$ and $y$ axes aligned to the world axes, this world point will project to pixel$$(x^{\prime},y^{\prime})=\left(f\frac{x}{z},f\frac{y}{z}\right)=\left(\frac{-30\cdot20}{200},\frac{-30\cdot 20}{200}\right)=(-3,-3).$$

## Intrinsic Camera Parameters

>[!attention] 
> For the following contents, we will use $[x\colon y \colon z]$ or $\begin{bmatrix}x \\ y\\ z\end{bmatrix}$ to denote [[Homogeneous Coordinates#^c9ee91|homogeneous coordinates]] of the corresponding point $(x,y)$ or $\begin{pmatrix}x \\ y\\ z\end{pmatrix}$   in Euclidean space.

>[!theorem] Perspective Camera Projection
> Assuming that the origin of points in the image plane is at [[Basic of Optics#^464846|principal point]], the projection onto the image plane can be calculated by homogeneous camera projection matrix: $$\begin{bmatrix}fx \\ fy\\ z\end{bmatrix}=\begin{bmatrix}f\\&f\\&&1\end{bmatrix}\begin{bmatrix}1&&&0\\&1&&0\\&&1&0\end{bmatrix}\begin{bmatrix}x\\y\\z\\1\end{bmatrix}=\begin{bmatrix}f&&&0\\&f&&0\\&&1&0\end{bmatrix}\begin{bmatrix}x\\y\\z\\1\end{bmatrix}$$If the origin of the image plane is not at principal point, we then apply an offset: $$\begin{pmatrix}x\\y\\z\end{pmatrix}\mapsto\begin{pmatrix}fx / z+p_{x}\\fy / z+p_{x}\end{pmatrix}\text{ or } \begin{bmatrix}x\\y\\z\\1\end{bmatrix}\mapsto\begin{bmatrix}fx+Zp_x\\fY+zp_y\\z\end{bmatrix}=\begin{bmatrix}f&&p_{x}&0\\&f&p_{y}&0\\&&1&0\end{bmatrix}\begin{bmatrix}x\\y\\z\\1\end{bmatrix}$$Now map from image plane to pixel coordinates by matrix $$\begin{bmatrix}m_{x} && \\ & m_{y} & \\ && 1\end{bmatrix}$$where $𝑚_{x} = \text{\# pixels} / \text{unit distance along } x$, $𝑚_{y} = \text{\# pixels} / \text{unit distance along } y$.

>[!definition]
>**Def**  <i><u>Camera Calibration Matrix</u></i>
The camera calibration (intrinsics) matrix is defined as follows: $$\begin{aligned}K = \begin{bmatrix}\alpha_{x}&&x_{0}&0\\&\alpha_{y}&y_{0}&0\\&&1&0\end{bmatrix}=\begin{bmatrix}m_xf_x&&m_xp_x&0\\&m_yf_y&m_yp_y&0\\&&1&0\end{bmatrix}\\=\begin{bmatrix}m_{x} && \\ & m_{y} & \\ &&1\end{bmatrix}\begin{bmatrix}f_{x}&&p_{x}&0\\&f_{y}&p_{y}&0\\&&1&0\end{bmatrix}\end{aligned}$$ where $(x_{0},y_{0})$ is the principal point, $\alpha_{y}/\alpha_{x}$ is called the aspect ratio, and $𝑚_{x} = \text{\# pixels} / \text{unit distance along } x$, $𝑚_{y} = \text{\# pixels} / \text{unit distance along } y$. Clearly the result of perspective camera projection then can be represented as: $$\begin{bmatrix}fx+Zp_x\\fY+zp_y\\z\end{bmatrix}=K\begin{bmatrix}I \mid 0\end{bmatrix}\begin{bmatrix}x\\y\\z\\1\end{bmatrix}$$

## Extrinsic Camera Parameters

>[!comment]
>The image is also related to some extrinsic camera parameters, such as camera rotation and translation in the world coordinate system.

>[!theorem] Transformation to Camera Coordinate
Suppose $z_\text{cam}$ is the [[Basic of Optics#^464846|principal axis]], $\mathbf{c}$ is the camera center vector in the world coordinate, $\mathbf{x}$ is some point, $R\in \mathrm{SO}_{3}$ is a [[Linear Groups#^2ce0d2|3D rotation matrix]], then in camera coordinates, we have $$\begin{aligned}\mathbf{x}_\text{cam}&=R(\mathbf{x}-\mathbf{c}),\quad \text{in camera coordinates} \\\mathbf{x}_\text{cam}&=\begin{bmatrix}R & -RC \\ 0 & 1\end{bmatrix}\mathbf{x},\quad \text{in homogeneous coordinates}\end{aligned}$$![|350](https://i.imgur.com/9DLJQqu.jpeg)

**Def**  <i><u>Complete Camera Matrix</u></i>
The complete camera matrix, or projective camera matrix, is defined as $$P=KR\begin{bmatrix}I \mid -\mathbf{c}\end{bmatrix}=K\begin{bmatrix}
R & -R\mathbf{c} \\ 0 & 1 \end{bmatrix}$$where $R\in \mathrm{SO}_{3}$ is the rotation matrix, $\mathbf{c}\in\R^{3}$ is the location vector denoting the camera center. Consequently, for any point $\mathbf{x}$ in the world coordinate, we have its coordinate in the image by $$\mathbf{u}= P\mathbf{x}=P\begin{bmatrix}x \\ y \\ z \\ 1 \end{bmatrix}$$
**Algorithm**  Gold Standard for Camera Calibration
1. Prepare a calibration target/object with known 3D coordinates.
2. Capture images of the calibration target/object.
3. Find corners of the target in the images, obtain $n\geq 6$ 2D–3D correspondences.
	1. Option 1: Detect edges with Canny detector, fit straight lines to detected linked edges, intersect lines to obtain 2D image coordinates, match image corners & 3D target checkerboard corners.
	2. Option 2: Apply a corner detector directly.
4. Solve for the normalised $3\times 4$ camera projection matrix $P$ using the normalised DLT algorithm.
5. Refine the normalised solution using iterative minimisation of a geometric error.
6. Denormalise solution.

## Radial Lens Distortion

>[!definition]
>**Def**  <i><u>Barrel Distortion</u></i>
Barrel Distortion is the phenomenon that image magnification decreases with distance from optical axis.

>[!definition]
>**Def**  <i><u>Pincushion Distortion</u></i>
Pincushion distortion is the phenomenon that image magnification increases with distance from optical axis.

>[!definition]
>**Def**  <i><u>Mustache Distortion</u></i>
A mixture of both above types.

>[!definition]
>**Def**  <i><u>Model for Radial Distortion</u></i>
Change based on distance of point on image plane from principal point: $$\mathbf{x}=K\begin{bmatrix}r&&\\&r&\\&&1\end{bmatrix}[I\mid0]\mathbf{x}_{\text{cam}}$$where $r=1+k_1(x_{\text{cam}}^2+y_{\text{cam}}^2)+k_2(x_{\text{cam}}^2+y_{\text{cam}}^2)^2$.