## Point Operations

>[!definition] 
>**Def**  <i><u>Point Operation</u></i>
>Point operation or histogram operation is an operation such that the output of such transformation only depends on the the corresponding input pixel (intensity, color) value. In other words, it's context free, can be performed on the image histogram. A point operation can be defined as a mapping: $$\nu^{\prime}=M(\nu)$$where $\nu$ stands for pixel gray scale/intensity values.
><u><b>e.g.</b></u> Globally adjust brightness and contrast: $M(\nu)=\alpha\nu+\beta$.

>[!definition] 
>**Def**  <i><u>Image Histogram</u></i>
>The histogram of a digital image with gray values $r_{0},r_{1},\dots,r_{L-1}$ is the discrete function $$p(r_{k})=\frac{n_{k}}{n}$$where $n_{k}$ is the number of pixels with gray value $r_{k}$ and $n$ is the total number of pixels in the image. If we consider the gray values in the image as realizations of a random variable $X$ with some probability density, histogram provides an approximation to this probability density.

>[!remark]
>Usually, we require $M$ maps the full gray-level range ($256$ levels) to its full range while keeping the gray-level order, $M$ should be non-decreasing monotonic. We also need the area under $H_{a}$ between $0$ and $\nu_{a}$ is equal to the area under $H_{b}$ between $0$ and $\nu_{b}=M(\nu_{a})$.

>[!definition] 
>**Def**  <i><u>Power-Law Transformation</u></i>
>Power law transformation is a family of point operations such that$$M(\nu)=C\cdot\nu^\gamma$$<u><b>e.g.</b></u>  If $\gamma<1$, the image will be brightened, if $\gamma>1$, the image will be darkened.

### Histogram Equalization

>[!example] Comment
>For a better visual discrimination of an image, we would like to reassign gray-levels so that gray-level resource will be optimally assigned. That is
>- The transformed histogram $H_{b}$ is as flat as possible.
>- The order of gray-levels is maintained.
>- The histogram bars are not fragmented.
>$\quad$

>[!algorithm]
>**Algorithm**  <i><u>Histogram Equalization</u></i>
>1. For images with discrete gray values, compute:$$p_{in}(r_{k})=\frac{n_k}n,\quad0\leq r_k\leq1,\quad0\leq k\leq L-1$$where $L$ is total number of gray levels, $n_{k}$ is the number of pixels with intensity $r_{k}$, $n$ is total number of pixels in the image.
>2. Based on CDF, compute the transformation:$$s_k=T(r_k)=\sum_{j=0}^kp_{in}(r_{j}),\quad0\leq k\leq L-1$$
>3. Now define $$f(v_{b})=\sum_{j=0}^{v_{b}}\frac1L$$and we assign $M(v_{a})=f^{-1}(T(v_{a}))$.
![he|450](https://i.imgur.com/uk6fxdR.png)

>[!attention] 
>Histogram equalization may not always produce desirable results, particularly if the given histogram is very narrow. It can produce false edges and regions. It can also increase image “graininess” and “patchiness.”

## Neighborhood Operations

>[!definition] 
>**Def**  <i><u>Neighborhood Operation</u></i>
>Operation depends on Pixel's value and its spatial neighbors (coordinates-dependent) is called neighborhood operation. It's context dependent.
><u><b>e.g.</b></u>  Image denoising.

## Geometric Operations

**Def**  <i><u>Geometric Operation</u></i>
Geometric operation is an operation that applied on pixel's coordinates, independent of pixels gray scale/intensity value.
<u><b>e.g.</b></u>  Translation of an image.

**Def**  <i><u>Image Warping</u></i>
Image warping is the operation that change the spatial domain of an image.
<u><b>e.g.</b></u> 
![|400](https://i.imgur.com/vb50GCi.jpeg)

>[!algorithm] 
>**Algorithm**  <i><u>Forward Warping</u></i>
>Iterate over source, copy pixel intensity value or color at source image $S(x,y)$ to target image $T(u,v)$.  It has the following facts:
>- Some source pixels map to the same target pixel.
>- Some target pixels may have no corresponding source.
>- Holes in reconstruction.
$\quad$

>[!algorithm] 
>**Algorithm**  <i><u>Inverse Warping</u></i>
>Iterate over target image, finding pixels from source. It has the following facts:
>- Non-integer evaluation source image, resample.
>- May over sample source.
>- But no holes.
>- In general simpler, better than forward mapping.
>```Python
>def bilinear_interpolate(image, x, y):
>    # Get the integer and fractional parts of the coordinates
>    x_int, y_int = int(x), int(y)
>    x_frac, y_frac = x - x_int, y - y_int
>    # Get the four nearest pixels
>    top_left = image[y_int, x_int]
>    top_right = image[y_int, x_int+1] if x_int+1 < image.shape[1] else top_left
>    bottom_left = image[y_int+1, x_int] if y_int+1 < image.shape[0] else top_left
>    bottom_right = image[y_int+1, x_int+1] if x_int+1 < image.shape[1] and y_int+1 < image.shape[0] else top_left
>    # Interpolate between the four pixels
>    top = top_left + x_frac * (top_right - top_left)
>    bottom = bottom_left + x_frac * (bottom_right - bottom_left)
>    pixel_value = top + y_frac * (bottom - top)
>    return pixel_value
>
>def inverse_warp(image, inv_transform_matrix, output_size):
>    warped_image = np.zeros(output_size, dtype=np.uint8)
>    # Iterate over each pixel in the output image
>    for y in range(output_size[0]):
>        for x in range(output_size[1]):
>            # Apply the inverse transformation matrix to get the original image coordinates
>            original_coord = np.dot(inv_transform_matrix, np.array([y, x, 1]))
>            original_coord = original_coord / original_coord[2]
>            # Perform bilinear interpolation if the coordinate falls within the input image bounds
>            if 0 <= original_coord[0] < image.shape[0] and 0 <= original_coord[1] < image.shape[1]:
>                warped_image[y, x] = bilinear_interpolate(image, original_coord[1], original_coord[0])   
>    return warped_image
>
># Load an image
>input_image = cv2.imread('image')
># Define an inverse transformation matrix
>inv_transform_matrix = np.linalg.inv(np.array([[0, 1, 0],[-1, 0, 0],[0, 0, 1]]))
>inv_transform_matrix[0, 2] = input_image.shape[0]
># Define the output image size
>output_size = (input_image.shape[1], input_image.shape[0], 3)
># Get the transformed image
>transformed_image = inverse_warp(input_image, inv_transform_matrix, output_size)
>plt.imshow(transformed_image)
>plt.show()
>```
>^002ac0

**Def**  <i><u>Scaling</u></i>
Scaling a coordinate means multiplying each of its components by a scalar. Uniform scaling means this scalar is the same for all components: $$\begin{bmatrix}
x^{\prime} \\ y^{\prime}\end{bmatrix}=\begin{bmatrix} a & 0 \\ 0 & b\end{bmatrix}\begin{bmatrix} x\\ y \end{bmatrix}$$

**Def**  <i><u>Rotation</u></i>
Rotating a coordinate by $\theta$ is defined as $$\begin{bmatrix}
x^{\prime} \\ y^{\prime}\end{bmatrix}=\begin{bmatrix} \cos\theta & \sin\theta \\ -\sin\theta & \cos\theta\end{bmatrix}\begin{bmatrix} x\\ y \end{bmatrix}$$

**Def**  <i><u>Affine Transformation</u></i>
Affine transformation is defined as follows: $$\begin{bmatrix}
x^{\prime} \\ y^{\prime}\end{bmatrix}=\begin{bmatrix} a_{11} & a_{12} \\ a_{21} & a_{22}\end{bmatrix}\begin{bmatrix} x\\ y \end{bmatrix}+\begin{bmatrix}
d_{x}\\d_{y}\end{bmatrix}$$

**Def**  <i><u>Shear</u></i>
Shear is a special case of affine transformation: $$\begin{bmatrix}
x^{\prime} \\ y^{\prime}\end{bmatrix}=\begin{bmatrix} s & 1 \\ 1 & 0\end{bmatrix}\begin{bmatrix} x\\ y \end{bmatrix}+\begin{bmatrix}
d_{x}\\d_{y}\end{bmatrix}$$

**Def**  <i><u>Projection</u></i>
Projection is defined as follows: $$x^{\prime}=\frac{a_1x^2+a_2y+a_3}{a_7x^2+a_8y+1},\quad y^{\prime}=\frac{a_4x+a_5y+a_6}{a_7x+a_8y+1}$$![proj|430](https://i.imgur.com/D8lLqN0.png)

**Def**  <i><u>Control Points</u></i>
Unique points in the reference and target images. The coordinates of corresponding control points in images are used to determine a transformation function.