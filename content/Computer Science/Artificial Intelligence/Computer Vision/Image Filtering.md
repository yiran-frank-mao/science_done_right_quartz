## Correlation and Convolution

>[!definition] 
>**Def**  <i><u>Image Filtering</u></i>
>Image filtering is an transformation such that compute the function value of local neighbourhood at each pixel.

>[!definition] 
>**Def**  <i><u>Linear Filters</u></i>
>Linear filtering is the filtering method in which the value of output pixel is linear combinations of the neighbouring input pixels.

>[!definition] Correlation Filtering
>Given the averaging window size is $(2k+1) \times (2k+1)$:$$G[x,y]=\frac1{(2k+1)^2}\sum_{u=-k}^{k}\sum_{v=-k}^kF[x+u,y+v]$$We can generalize to allow different weights: $$G[x,y]=\sum_{u=-k}^k\sum_{v=-k}^kH[u,v]F[x+u,y+v]$$where $H[u,v]$ is a non-uniform weights. We write this as $G=H\otimes F$.

<u><b>e.g.</b></u>  $$\begin{bmatrix}1 & 1 & 1 \\  1 &1 & 1 \\ 1 & 1 & 1\end{bmatrix}\otimes \begin{bmatrix}
>1 & 2 \\ 3 & 4 \end{bmatrix} = \begin{bmatrix}10 & 10 \\ 10 & 10 \end{bmatrix}$$

>[!definition] Convolution Filtering
>Convolution filtering is the filtering method in which the output is the correlation of the input image with a flipped kernel. The kernel is flipped in both dimensions: $$G[x,y]=\sum_{u=-k}^k\sum_{v=-k}^kH[u,v]F[x-u,y-v]$$We write this as $G=H*F$.

<u><b>e.g.</b></u>  $$G \otimes \begin{bmatrix}1 & 2 \\ 3 & 4 \end{bmatrix} = G * \begin{bmatrix}4 & 3 \\ 2 & 1 \end{bmatrix}$$

> [!remark]
> As its name suggests, convolution filtering is the [[The Space of Integrable Functions#^472754|convolution]] of the kernels, in the function sense.

>[!definition] Separable Kernel
>A kernel is separable if it can be written as the outer product of two vectors: $$H[u,v]=h[u]*g[v]$$And hence the convolution can be computed in two steps: $$G=H*F=(h*g)*F=h*(g*F)$$ ^05577c
>

<u><b>e.g.</b></u>  $$\begin{bmatrix}\frac{1}{9}&\frac{1}{9}&\frac{1}{9}\\\frac{1}{9}&\frac{1}{9}&\frac{1}{9}\\\frac{1}{9}&\frac{1}{9}&\frac{1}{9}\end{bmatrix}=\begin{bmatrix}0&\frac{1}{3}&0\\0&\frac{1}{3}&0\\0&\frac{1}{3}&0\\0&\frac{1}{3}&0\end{bmatrix}\begin{bmatrix}0&0&0\\\frac{1}{3}&\frac{1}{3}&\frac{1}{3}\\0&0&0\end{bmatrix}$$

>[!lemma] 
> Suppose we have singular value decomposition of a kernel matrix $H$: $$H=U\Sigma V^{\top}$$Then $H$ is separable if all singular values except the largest (first) one are zeroes. In such case, we have $H=U\Sigma V^{\top}=(\sqrt{\sigma_{1}}u_{1})(\sqrt{\sigma_{1}}v_1^{\top})$.

>[!proposition] 
> The time complexity of filtering an $n×n$ image with an $m×m$ kernel is $O(n^{2}m^{2})$. If the kernel is separable, the time complexity can be reduced to $O(n^{2}m)$.

## Image Smoothing

>[!definition] Salt and Pepper Noise
>Salt and pepper noise is random occurrences of black and white pixels.
>![|300](https://i.imgur.com/eRULhWV.jpeg) ^7d7b95

>[!definition] 
>**Def**  <i><u>Impulse Noise</u></i>
>Impulse noise is random occurrences of white pixels, sometimes, it is also referred to as a special case of salt and pepper noise.

>[!definition] 
>**Def**  <i><u>Gaussian Noise</u></i>
>Variations in intensity drawn from a Gaussian normal distribution.

>[!definition] 
>**Def**  <i><u>Gaussian Filtering</u></i>
>Gaussian filter is a specific filter such that the kernel $H[u,v]$ in correlation filter is a 2D gaussian function. The variance of the Gaussian function determines extent of smoothing.

>[!proposition] 
>**Prop**  
>- Gaussian filter is linear.
>- Gaussian filter is isotropic, i.e. it smooths the image in all directions equally.
>- A Gaussian filter convolves with itself gives another Gaussian. Concretely, convolving two times with Gaussian kernel of width $σ$ is equivalent to convolving once with a Gaussian kernel of width $σ\sqrt{2}$.
>- Gaussian filter is [[Image Filtering#^05577c|separable]], i.e. it can be decomposed into two 1D filters.
>$\quad$

>[!definition] 
>**Def**  <i><u>Median Filter</u></i>
>Median filter replaces centre pixel by median within window. It is good for removing [[Image Filtering#^7d7b95|salt-and-pepper (impulse) noise]].

>[!proposition] 
>**Prop**  Median filter is non-linear.

>[!definition] 
>**Def**  <i><u>Bilateral Filter</u></i>
>The bilateral filter combines domain filtering and range filtering. The domain filter is a Gaussian filter spatially, and the range filter is a Gaussian filter in intensity space. Intuitively, pixels that are closer together spatially, or with similar intensities (or colors) have a higher influence on each other. The output $I^{\prime}_{p}$ at pixel $p$ of the filtered image is given by: $$I^{\prime}_{p}=\frac{1}{W_{p}}\sum_{q\in N}G_{\sigma_{d}}(||p-q||)G_{\sigma_{r}}(|I_{p}-I_{q}|)I_{q}$$where $N$ is the neighbourhood of pixel $p$, $G_{\sigma_{d}}$ is the spatial Gaussian filter, $G_{\sigma_{r}}$ is the intensity Gaussian filter, and $W_{p}$ is the normalization factor. Consequently, the bilateral filter can preserve edges while smoothing the image:
>![|250](https://i.imgur.com/XnEj8Bh.jpeg)

>[!proposition] 
>**Prop**  Bilateral filter is non-linear. The Bilateral filter is a generalization of the Gaussian filter, specifically, it reduces to the Gaussian filter when $\sigma_{r}\to \infty$.

>[!definition] 
>**Def**  <i><u>Sharpening Filter</u></i>
>The sharpening filter kernel is $$\begin{bmatrix}0 & 0 &0 \\0 &2&0\end{bmatrix}$$

## Edge Detectors

>[!definition] 
>**Def**  <i><u>Sobel Filter</u></i>
>The Sobel filter is a discrete differentiation operator, computing an approximation of the gradient of the image intensity function. It is implemented as a convolution of the image with Sobel kernel matrices in horizontal and vertical directions. The Sobel kernel matrices are given by: $$M_{x}=\begin{bmatrix}-1&0&1\\-2&0&2\\-1&0&1\end{bmatrix},\quad M_{y}=\begin{bmatrix}1&2&1\\0&0&0\\-1&-2&-1\end{bmatrix}$$The edge strength is given by the gradient magnitude: $$\|\nabla I\|=\sqrt{I_{x}^2+I_{y}^2}$$The gradient direction (orientation of edge normal) is given by: $$\theta=\arctan\left(\frac{I_{y}}{I_{x}}\right)$$where $I_{x}$ and $I_{y}$ are the gradient components in the $x$ and $y$ directions respectively.

>[!proposition] 
>**Prop**  Sobel filter is a linear filter.

>[!algorithm] 
>**Algorithm**  <i><u>Canny Edge Detector</u></i>
>1. Filter image with derivative of Gaussian.
>2. Find magnitude and orientation of gradient.
>3. Non-maximum suppression: thin wide “ridges” down to single pixel width.
>4. Apply double threshold to determine potential edges.
>$\quad$

## Corner Detection

>[!definition] 
>**Def**  <i><u>Flat Region</u></i>
>We say that a region is flat if it has an isotropic structure.

>[!definition] 
>**Def**  <i><u>Edge Region</u></i>
>We say that a region is an edge if it has a linear structure.

>[!definition] 
>**Def**  <i><u>Corner Region</u></i>
>We say that a region is a corner if it has a bi-directional structure.

>[!algorithm] 
>**Algorithm**  <i><u>Harris Corner Detector</u></i>
>The measure of change of intensity for the shift $[u,v]$: $$E(u,v)=\sum_{x,y}w(x,y){\left[I(x+u,y+v)-I(x,y)\right]}^{2} \approx \begin{bmatrix}u&v\end{bmatrix}M\begin{bmatrix}u\\v\end{bmatrix}$$where $w$ is the window function and $M$ is a $2\times 2$ matrix computed from image derivatives, called the auto-correlation matrix:$$M=\sum_{x,y}w(x,y)\begin{bmatrix}I_x^2&I_xI_y\\I_xI_y&I_y^2\end{bmatrix}=Q\begin{bmatrix}\lambda_{1}&0\\0&\lambda_{2}\end{bmatrix}Q^{-1}$$The cornerness score with empirical constant $k\in[0.01,0.1]$ is then given by $$R=\det M - k\left(\operatorname{\textbf{tr}}(M)\right)^{2}=\lambda_{1}\lambda_{2}-k(\lambda_{1}+\lambda_{2})^{2}$$Thus the algorithm is by
>1. Compute $M$ matrix for each image window to get their cornerness scores.
>2. Find points whose surrounding window gave large corner response ($R>$ threshold). The convention is $R$ is positive for corners, negative for edges, and small for flat regions.
>3. Take the points of local maxima, i.e. perform non-maximum suppression.
>```python
>import numpy as np
>
>detM = Ix2 * Iy2 - Ixy ** 2
>traceM = Ix2 + Iy2
>R = detM - k * traceM ** 2
>
>threshold = thresh * R.max()
>corners = np.where(R > threshold)
>coordinates = np.array(corners).T
>```

^7a835f

>[!proposition] 
>**Prop**  Harris corner detector is rotationally invariant, but not scale invariant.
>**Proof**  Suppose $R\in \R^{2\times 2}$ is some rotation matrix. Then before rotating, $$\begin{aligned}M&=\sum_{x,y}w(x,y)\begin{pmatrix}I_x^2&I_xI_y\\I_xI_y&I_y^2\end{pmatrix}\\&=X\begin{pmatrix}\lambda_1&0\\0&\lambda_2\end{pmatrix}X^{\top}\end{aligned}$$After rotating, we have: $$\begin{aligned}M'&=R\times M\times R^{\top}\\&=RX\begin{pmatrix}\lambda_1&0\\0&\lambda_2\end{pmatrix}(RX)^{\top}\end{aligned}$$

## SIFT Feature Detector

>[!definition] 
>**Def**  <i><u>Interest Points</u></i>
>Interest points are local maxima in both position and scale in an image.

