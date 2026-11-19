---
created: 2024-04-23
updated: 2024-10-23
cssclasses:
  - img-grid
  - img-zoom
---
> [!definition] Domain Adaptation
> Domain adaptation is a field of computer vision, where the goal is to train a neural network on a source dataset and secure/achieve a good accuracy on the target dataset which is significantly different from the source dataset.

<u><b>e.g.</b></u>  From CAD models to real images: 

![domain_adaptation_plane1.png](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/domain_adaptation_plane1.png)
![domain_adaptation_plane2.png](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/domain_adaptation_plane2.png)


## Maximum Mean Discrepancy (MMD)

> [!definition] Maximum Mean Discrepancy Loss
> Suppose the mean of source and target features is given by $$\mu_{S}=\frac{1}{n_{S}}\sum_{i}f_{S}^{i},\quad \mu_{T}=\frac{1}{n_{T}}\sum_{i}f_{T}^{i}$$where $f_{S}^{i}$ is the feature of the $𝑖$th source image, $n_{S}$ is the number of source features, $f_{T}^{i}$ is the feature of the $i$th target image, $n_{T}$ is the number of target features. Then the maximum mean discrepancy is defined as $$L_{\text{MMD}}=\|\mu_{S}-\mu_{T}\|_{2}^{2}$$

> [!algorithm] Maximum Mean Discrepancy Method
> Suppose we have a pre-trained feature extraction network $\mathscr{N}$ with $L_\text{class}$ be the normal classification loss that extracts features from both source and target dataset. In each training mini-batch, we minimize the following overall loss: $$L = L_{\text{class}}+\lambda L_{\text{MMD}}$$where $\lambda>0$ controls the balance between the two losses.

## Correlation Alignment

> [!definition] CORAL Loss
> The CORAL loss is defined as the distance between the second-order statistics (covariances) of the source and target features: $$L_{\text{coral}}=\frac{1}{4d^{2}}\|C_{S}-C_{T}\|_{\text{F}}^{2}$$where $d$ is the feature dimension, and $𝐶_{S}$ and $𝐶_{T}$ represent covariance matrix of the source and target domains respectively.

> [!algorithm] Correlation Alignment
> Suppose we have a pre-trained feature extraction network $\mathscr{N}$ with $L_\text{class}$ be the normal classification loss that extracts features from both source and target dataset. In each training mini-batch, we minimize the following overall loss: $$L = L_{\text{class}}+ \sum_{i=1}^{t} L_{\text{coral}}$$where where $𝑡$ is the number of layers that apply this loss.

## Adversarial Alignment

> [!definition] Domain Classification Loss and Domain Confusion Loss
> Domain classification loss is defined as $$L_{\text{domain}}(x_{S},x_{T},\theta_{\text{feature}};\theta_{\text{domain}})=-\sum_{d}[y_{D}=d]\log p_{d}$$Domain confusion loss is defined as$$L_{\text{conf}}(x_{S},x_{T},\theta_{\text{domain}};\theta_{\text{feature}})=-\sum_{d}\frac{1}{D}[y_{D}=d]\log p_{d}$$where $x_{S}$, $x_{T}$ indicate source, target domain samples. $\theta_\text{feature}$ is the parameters of feature extraction network, $\theta_\text{domain}$ is the parameters of domain classifier. $y_{D}$ means the predicted domain of an input sample, and $𝐷$ is the ground truth domain of this sample. 𝑝 is the softmax of the domain classifier activation: $$p=\mathrm{SoftMax}\left(\theta_\text{domain}^{\top} f(x;\theta_\text{feature})\right)$$

> [!algorithm] Adversarial Alignment
> Perform iterative updates for the following two objectives given the fixed parameters from the previous iteration: $$\begin{aligned} \min_{\theta_\text{domain}}&L_{\text{domain}}(x_{S},x_{T},\theta_{\text{feature}};\theta_{\text{domain}}) \\ \min_{\theta_\text{feature}}&L_{\text{conf}}(x_{S},x_{T},\theta_{\text{domain}};\theta_{\text{feature}}) \end{aligned}$$
> 
> ![|450](https://i.imgur.com/dDRWURO.png)

