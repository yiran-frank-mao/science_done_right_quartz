## Camera Calibration

**Algorithm**  <i><u>Camera Calibration</u></i>
1. Prepare a calibration target/object, e.g. 2 orthogonal planes with a checkerboard pattern.
2. Position camera in front of target, capture image of the calibration target.
3. Find corners of the target in the image.
	 Option1:
	- Detect edges with Canny detector.
	- Fit straight lines to detected linked edges (Hough).
	- Intersect lines to obtain 2D image coordinates
	- Match image corners & 3D target checkerboard corners.
	- Result: 2D–3D correspondences.
	Option2:
	- Apply a corner detector directly (Harris, Susan, FAST).
4. Derive constraints on camera matrix.
5. 


>[!attention]
>3D points cannot all be on the same plane.

**Algorithm**  <i><u>Direct Linear Transformation</u></i>


**Algorithm**  <i><u>Normalised Direct Linear Transformation</u></i>
**Objective**: Given $𝑛 ≥ 6$ 2D–3D point correspondences $\{\mathbf{x}_i \leftrightarrow \mathbf{X}_{i}\}$, determine the $3×4$ projection matrix $\mathbf{P}$ such that $𝐱_{i} \approx \mathbf{P}\mathbf{X}_{i}$.
1. Normalise 2D and 3D points: $\tilde{𝐱}_{i} = 𝐓𝐱_{i}$, $\tilde{\mathbf{X}}_{i} = 𝐒𝐗_{i}$.
2. Apply the DLT algorithm to $\{\mathbf{x}_i \leftrightarrow \mathbf{X}_{i}\}$.
3. Denormalize the recovered solution $\tilde{\mathbf{P}}$ using $\mathbf{P=T^{-1}\tilde{P}S}$.

##  Recovering The Camera Intrinsics


