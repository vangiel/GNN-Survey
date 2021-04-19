# Graph Neural Networks (GNN) Survey 

This document gathers a survey on the most relevant paper in the field of GNN for three specific applications. These are:

- GNNs for social navigation: These works make use of the GNNs for helping or guiding a robot navigate safely across a room. Some of them consider the social aspects of the navigation.

- GNNs for sensorised environments: This encompass the use of GNNs for fusing data from different sensors sources. As well as the encoding of sensor data into a latent and dimensionality reduced space to be use for other models.

- Temporal GNNs: These models leverage the information passed through time. They not only extract spatial feature but also temporal evolution features. There are several approaches such as: 3D convolutions, GNN in combination with RNN, spectral analysis...

- Basic Theory of GNNs: This section cover papers about GNNs theory and basic models that serves as scaffolding for more complicated ones.

All the papers are ordered by year of publication and they can have different types as indicated in the table below:

| Type        | `M`            | `A`            | `other`     |
|:----------- |:--------------:|:--------------:|:-----------:|
| Explanation | Model descriptions | Applications | Other types |

## Table of Contents

- [GNNs for social navigation](#GNNs-for-social-navigation)

- [GNNs for sensorised environments](#GNNs-for-sensorised-environments)

- [Temporal GNNs](#Temporal-GNNs)

- [Basic GNNs theory](#Basic-GNNs-theory)


## GNNs for social navigation

| Title        | Year           | Type           | Code     |
|:----------- |:--------------:|:--------------:|:-----------:|
| [Graph Neural Networks for Human-aware Social Navigation](https://arxiv.org/abs/1909.09003) | 2019 | `A`     | [DGL(Author)](https://github.com/robocomp/sngnn)   |
| [SocNav1 : A Dataset to Benchmark and Learn Social Navigation Conventions ∗](https://arxiv.org/abs/1909.02993) | 2019 | `A`     | [Author](https://github.com/gnns4hri/SocNav1) |

## GNNs for sensorised environments

| Title    | Year       | Type    | Code     |
|:-------|:--------:|:-------:|:-------:|
| [Modeling IoT Equipment with Graph Neural Networks](https://ieeexplore.ieee.org/document/8658112) | 2019 | `A`     | -  |



## Temporal GNNs

| Title    | Year       | Type    | Code     |
|:-------|:--------:|:-------:|:-------:|
| [Spatio-Temporal Graph Scattering Transform](https://arxiv.org/abs/2012.03363)                                                                             | 2021         | `M`     | -             |
| [Spatio-temporal graph convolutional networks: A deep learning framework for traffic forecasting](https://arxiv.org/abs/1709.04875)                                                                                                                        | 2018         | `M`     | [PG-temporal](https://pytorch-geometric-temporal.readthedocs.io/en/latest/modules/root.html#temporal-graph-convolutional-layers)                              |
| [Spatial Temporal Graph Convolutional Networks for Skeleton-Based Action Recognition](https://arxiv.org/abs/1801.07455)                                                                             | 2018         | `M`     | [PyTorch(Author)](https://github.com/yysijie/st-gcn)        |

                

## Basic GNNs theory

| Title    | Year       | Type    | Code     |
|:-------|:--------:|:-------:|:-------:|
| [Relational inductive biases, deep learning, and graph networks](https://arxiv.org/abs/1806.01261)                                                                             | 2018         | `other`     | ** Survey **          |

## Related Repo

[DGL](https://www.dgl.ai)

[Pytorch-geometric](https://pytorch-geometric.readthedocs.io/en/latest/#)

[Temporal pytorch-geometric](https://pytorch-geometric-temporal.readthedocs.io/en/latest/#)

[GNNs for human-robot interactions](http://gnns4hri.org/index.html)

