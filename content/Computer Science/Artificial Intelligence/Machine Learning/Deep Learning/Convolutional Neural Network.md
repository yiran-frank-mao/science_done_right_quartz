## Convolutional Layer

>[!definition] Convolutional Layer
>Convolutional layer is the core building block of a convolutional neural network. The layer's parameters consist of a set of learnable filters (or kernels), which have a small receptive field, but extend through the full depth of the input volume. During the forward pass, each filter is convolved across the width and height of the input volume: $$h_{j}^{(n)}=\max\left(0, \sum_{k=1}^{K}h_{k}^{(n-1)}*w_{k,j}^{n}\right)$$where $h_{j}^{(n)}$ is the $j$-th feature map in the $n$-th layer, $h_{k}^{(n-1)}$ is the $k$-th feature map in the $(n-1)$-th layer, $w_{k,j}^{n}$ is the kernel, and $K$ is the kernel size. We call the stride of the convolution the number of pixels by which we move the filter at each step.
>![|300](https://i.imgur.com/cmmLLl9.jpeg)

>[!definition] Receptive Field
>The receptive field of a neuron is the area in the input space that can affect the neuron's output. In a convolutional neural network, the receptive field of a neuron in layer $n$ is the area in the input space that can affect the neuron's output in layer $n$. ^070654

>[!definition] Pooling Layer
>Pooling layer is a special convolutional layer used to reduce the spatial dimensions of the input volume. 

>[!definition] Max Pooling
>The most common pooling operation is max pooling, which partitions the input volume into a set of non-overlapping rectangles and, for each such sub-region, outputs the maximum value. 
>![|350](https://i.imgur.com/NpyloK6.png)

>[!proposition] 
>If convolutional filters have size $k\times k$ and stride $1$, and pooling layer has pools of size $p\times p$, then each unit in the pooling layer has a [[Convolutional Neural Network#^070654|receptive field]] of size: $(p+k-1)\times (p+k-1)$.

>[!definition] Convolutional Neural Network
>A convolutional neural network (CNN) is a neural network whose hidden layers contain at least one convolutional layer, and some pooling layers. CNNs are particularly effective for image recognition tasks.