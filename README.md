# Graph Neural Networks (GNN) Survey 

This document gathers a survey on the most relevant paper in the field of GNN for three specific applications. These are:

- **GNNs for social navigation**: These works make use of the GNNs for helping or guiding a robot navigate safely across a room. Some of them consider the social aspects of the navigation.

- **GNNs for sensorised environments**: This encompass the use of GNNs for fusing data from different sensors sources. As well as the encoding of sensor data into a latent and dimensionality reduced space to be use for other models.

- **Temporal GNNs**: These models leverage the information passed through time. They not only extract spatial feature but also temporal evolution features. There are several approaches such as: 3D convolutions, GNN in combination with RNN, spectral analysis...

All the papers are ordered by year of publication, and they can have different general types as indicated in the table below:

| Type        | `M`            | `A`            | `other`     |
|:----------- |:--------------:|:--------------:|:-----------:|
| Explanation | Model descriptions | Applications | Other types |

## Table of Contents

- [GNNs for social navigation](#GNNs-for-social-navigation)

- [GNNs for sensorised environments](#GNNs-for-sensorised-environments)

- [Temporal GNNs](#Temporal-GNNs)


## GNNs for social navigation

| Title        | Year           | Type           | Code     |
|:----------- |:--------------:|:--------------:|:-----------:|
| [Graph Neural Networks for Human-aware Social Navigation](https://arxiv.org/abs/1909.09003) | 2019 | `A` | [DGL(Author)](https://github.com/robocomp/sngnn)   |
| [SocNav1 : A Dataset to Benchmark and Learn Social Navigation Conventions ∗](https://arxiv.org/abs/1909.02993) | 2019 | `A` | [Author](https://github.com/gnns4hri/SocNav1) |

## GNNs for sensorised environments

| Title    | Year       | Type    | Code     |
|:-------|:--------:|:-------:|:-------:|
| [Modeling IoT Equipment with Graph Neural Networks](https://ieeexplore.ieee.org/document/8658112) | 2019 | `A` | - |



## Temporal GNNs

| Subtype     | `Rn`                 |      `Conv`           |
|:----------- |:--------------------:|:---------------------:|
| Explanation | Convination with RNN | Temporal convolutions |

| Title    | Year       | Type    | Code     |
|:-------|:--------:|:-------:|:-------:
| [Spatio-Temporal Graph Scattering Transform](https://arxiv.org/abs/2012.03363) | 2021 | `Other` | - |
| :star: [Spatio-temporal graph convolutional networks: A deep learning framework for traffic forecasting](https://arxiv.org/abs/1709.04875) | 2018 | `M_Conv` | [PG-temporal](https://pytorch-geometric-temporal.readthedocs.io/en/latest/modules/root.html#temporal-graph-convolutional-layers) |
| (STGCN) This work try to overcome the limitations of the temporal GNN models that use RNNs. The main drawback of RNN is the accumulation of error through an iterative process. For that they substitute the recurrent network with convolutions in the time domain. Thus, Each layer of their model is composed of a spatial convolution in between of two temporal convolution using a Gate Linear Unit as non-linearity. Chebyshev polynomial approximation of the spatial kernel. They compare with other temporal models with RNN gettig a lower error in traffic forecasting. |
| :shit: [Spatial Temporal Graph Convolutional Networks for Skeleton-Based Action Recognition](https://arxiv.org/abs/1801.07455) | 2018  | `M_Conv` | [PyTorch(Author)](https://github.com/yysijie/st-gcn) |
| (ST-GCN) This paper present a model called Spatio Temporal Graph Convolutional Network. It is similar than STGCN but they just use a normal GCN without modifications to do the convolution along the full graph. The graphs are formed by several frames of human key-points connected among then through edges (they call it temporal edges, they are just normal edges). They compare to other models in the task of action recognition in videos. They don't compare to any model with GNN.|
| :star: [Structured Sequence Modeling with Graph Convolutional Recurrent Networks](https://arxiv.org/abs/1612.07659)  | 2016  | `M_Rn`  | [PG-temporal](https://pytorch-geometric-temporal.readthedocs.io/en/latest/modules/root.html#temporal-graph-convolutional-layers) |
| (GCRN) This paper introduce two models: the first one use a GNN to encode the input space to a latent space that is taken by a RNN. The second one (best results) use a RNN but the input vector is a graph signal and the internal operations of the RNN are graph convolutions in the spectral domain. They use a Chebyshev polynomial approximation of the convolution kernel to minimise the computational load. They test their model in a version of the MNIST dataset called MOVING-MNIST and also for natural language modeling. The MOVING-MNIST contains 2 numbers bouncing and rotating and the network is able to predict is future movement from previous frames. It outperforms the same model but based on CNN!!! This is notorious because the domain is a 2D fixed grid (an image) that is what CNN are made for, in principle. Explanation: the GNN use less parameters for bigger kernels. |


## Related repos and documentation

[DGL](https://www.dgl.ai)

[Pytorch-geometric](https://pytorch-geometric.readthedocs.io/en/latest/#)

[Temporal pytorch-geometric](https://pytorch-geometric-temporal.readthedocs.io/en/latest/#)

[GNNs for human-robot interactions](http://gnns4hri.org/index.html)

