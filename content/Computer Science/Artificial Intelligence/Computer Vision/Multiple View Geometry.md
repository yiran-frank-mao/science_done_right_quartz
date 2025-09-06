---
completed: true
updated: 2025-08-31
---
## Structure From Motion

>[!definition] Structure From Motion
>*Structure from motion (SfM)* is the process of estimating the 3D structure of a scene from a set of 2D images. It is a fundamental problem in computer vision and photogrammetry. Core steps of SfM include:
>1. Feature detection: Identify points of interest within images that can be tracked across a series;
>2. Feature matching: find scene points seen by multiple cameras;
>3. Reconstruction: Robustly estimate camera poses and triangulation;
>4. Refinement (Bundle Adjustment): Refine camera poses $R$, $T$ and scene structure $\{\mathbf{X}_{i}\}$.
>$\quad$

>[!algorithm] COLAMP
> *COLAMP* is a robust and efficient algorithm for SfM. It is based on the idea of local bundle adjustment and global optimization. Detail of the algorithm can be found [here](https://colmap.github.io/tutorial.html).

>[!algorithm] FlowMap
>*FlowMap* is a method for dense 3D reconstruction from a set of images. It is based on the idea of optical flow and depth map estimation. Detail of the algorithm can be found [here](https://arxiv.org/abs/2404.15259).

>[!algorithm] Neural Radiance Fields
>*Neural Radiance Fields (NeRF)* is a method for synthesizing novel views of complex scenes. It is based on the idea of learning a continuous 5D implicit representation of the scene. It involves following steps:
>1. Let take photos;
>2.  Use COLMAP (SfMs) to calculate camera poses, i.e. detect and match features across the images;
>3. Volumetric formulation of NeRF:
>	1. Select one pixel with its corresponding ray;
>	2. Ray tracing for this pixel (straight ray);
>	3. Construct two MLPs: one for the chance the ray hits a particle, and one for the color.
>	4. Accumulation for this ray and get its rendered pixel.
>
> Detail of the algorithm can be found [here](https://arxiv.org/abs/2003.08934).

## A Framework Unifying All 3D Vision Tasks

>[!algorithm] DUSt3R
>*DUSt3R* is a method for dense 3D reconstruction from a set of images. It is based on the idea of depth map estimation and surface reconstruction. The input to the model is multiple camera views (without intrinsic), and the output is corresponding point maps. Detail of the algorithm can be found [here](https://arxiv.org/abs/2312.14132).
>![fig](https://i.imgur.com/RlhYjJx.jpeg)
