# Graph Neural Networks (GNN) Survey 

This document gathers a survey on the most relevant paper in the field of GNN for three specific applications. These are:

- **GNNs for social navigation**: These works make use of the GNNs for helping or guiding a robot navigate safely across a room. Some of them consider the social aspects of the navigation.

- **GNNs for sensorised environments**: This encompass the use of GNNs for fusing data from different sensors sources. As well as the encoding of sensor data into a latent and dimensionality reduced space to be use for other models.

- **Temporal GNNs**: These models leverage the information passed through time. They not only extract spatial feature but also temporal evolution features. There are several approaches such as: 3D convolutions, GNN in combination with RNN, spectral analysis...

All the papers are ordered by year of publication, and they can have different general types as indicated in the table below:

| Type        | `M`            | `A`            | `other`     |
|:----------- |:--------------:|:--------------:|:-----------:|
| Explanation | Model descriptions | Applications | Other types |

| Emoji       | :star:         | :shit:            | :negative_squared_cross_mark:     |
|:----------- |:--------------:|:--------------:|:-----------:|
| Explanation | Good paper | Not so good or relevant | No GNN used |

## Table of Contents

- [GNNs for social navigation](#GNNs-for-social-navigation)

- [GNNs for sensorised environments](#GNNs-for-sensorised-environments)

- [Temporal GNNs](#Temporal-GNNs)


## GNNs for social navigation

| Title        | Year           | Type           | Code     |
|:----------- |:--------------:|:--------------:|:-----------:|
| :star: :negative_squared_cross_mark: [Human-Aware Navigation Planner for DiverseHuman-Robot Contexts](https://hal.archives-ouvertes.fr/hal-03262888/document) | 2021 | `MA` | [Author](https://github.com/sphanit/human_layers/tree/tested) |
| This paper introduce a planner for social navigation with robots. They don't use GNNs but Gaussian mixture models to get the cost function for the planner. They use different types of elastic bands for the planer. This planner is able to change it mode of actuation depending on the context of the environments. It would be an interesting approach to replace their cost function with the one obtained in SNGNN which introduce a bit more of state of mind.|
| :star: [Graph Neural Networks for Human-aware Social Navigation](https://arxiv.org/abs/1909.09003) | 2019 | `A` | [DGL(Author)](https://github.com/robocomp/sngnn)  |
| :star: [SocNav1 : A Dataset to Benchmark and Learn Social Navigation Conventions ???](https://arxiv.org/abs/1909.02993) | 2019 | `A` | [Author](https://github.com/gnns4hri/SocNav1) |
| :star: :negative_squared_cross_mark: [Motion Planing Among Dynamic, Decision-Making Agents with Deep Reinforcement Learning]( https://arxiv.org/pdf/1805.01956.pdf) | 2018 | `A` | [Author (ROS)](https://github.com/mfe7/cadrl_ros) |
| They use a reinforcement learning algorithm to train an agent to navigate socially in a multiagent scenario with humans and obstacles. The main novelty of this work is the use of RNN to allow the perception of a flexible number of humans in the environment. Previous methods could only take a fixed number of observable agents at a time. The main problem is that it is not clear how it interpolates throughout time and what kind of memory it has apart from the accumulated reward in RL. This can maybe be approached with a temporal GNN to get better results. |

## GNNs for sensorised environments

| Title    | Year       | Type    | Code     |
|:-------|:--------:|:-------:|:-------:|
| [Modeling IoT Equipment with Graph Neural Networks](https://ieeexplore.ieee.org/document/8658112) | 2019 | `A` | - |
| Use of GNNs. Graphs are formed using each sensor data as a node and an edge denotes relations among data. They are undirected graphs. They use an encode-decoder configuration where both of them are GNNs. The goal is to predict the state of the IoT environment. |
| [An adaptive multi-sensor data fusion method based on deep convolutional neural networks for fault diagnosis of planetary gearbox](https://www.mdpi.com/1424-8220/17/2/414) | 2017 | `A` | - |
| No use of GNN (DCNN). The aim of the work is to detect faults in gears using data from 4 different sensors (accelerometer, microphone, current sensor, optical encoder). What they do is to concatenate segments of the 4 different sensor signals and input it into a 1D Deep Convolutional Network. It is 1D in order to leverage the temporal information implicit to this kind of sensor signals. Supervised learning. Fusion in the raw data. |



## Temporal GNNs

| Subtype     | `Rn`                 |      `Conv`           |
|:----------- |:--------------------:|:---------------------:|
| Explanation | Combination with RNN | Temporal convolutions |

| Title    | Year       | Type    | Code     |
|:-------|:--------:|:-------:|:-------:
| :star: :negative_squared_cross_mark: [Spatio-Temporal Graph Scattering Transform](https://arxiv.org/abs/2012.03363) | 2021 | `Other` | - |
| They don't use a GNN but graph wavelets transforms to apply filters in the frequency domine. It performs better that the GCRN but just in early predictions since it doesn't have any memory element. |
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

