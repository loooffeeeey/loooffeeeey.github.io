---
layout:     post
title:      Complex network的一些笔记
subtitle:   在写本子调研城市脆弱性时收集到的一些概念，记录以便回忆
date:       2022-02-22
author:     loooffeeeey
header-img: img/post-bg-network.jpg
catalog: true
tags:
    - 复杂网络
---


# Complex network的一些笔记

复杂网络以后变成实验室会比较紧密相关的一个研究方向；初步做的一个城市脆弱性研究的本子，在调研水网脆弱性的时候遇到一些概念，感觉比较有用所以记录下来

## Spatial perspective

### Clustering coefficient

[聚簇系数](https://en.wikipedia.org/wiki/Clustering_coefficient)表征网络中成簇的程度。

- local：
  - 表征某一个节点的$N_i$的局部邻域聚簇程度，$N_i$是$i$节点的邻域
  - $C_i = \frac{|\{ e_{jk} : v_j,v_k \in N_i, e_{jk} \in E \}|}{k_i(k_i-1)}$, $k_i$是$N_i$中点的个数
- global:
  - 表征整个网络的聚簇程度
  - $\bar C = \frac{1}{n} \sum {n}{i=1} C_i$

### Meshedness coefficient

[网格系数](https://en.wikipedia.org/wiki/Meshedness_coefficient)表征网络中成环的程度。

网络的成环度，或者叫网格度（三角网格，或者四边网格等），计算方式如下
$$\alpha = \frac{m-n+1}{2n-5},$$
$n$为点数量，$m$为边数量，$2n-5$为欧拉定理给出的最大环化的环数，$m-n+1$为当前网络**环的数量**。

### Central-point dominance

**中心度** `Freeman, L.C., 1997. A set of measures of centrality based on betweenness. Soci- ometry 40 (1), 35e41.`
表征网络中点的中心程度。
度量方式：与最中心节点的“距离”
![计算方式](img/post-formula-center.jpg)

## Spectral perspective

计算方式来自网络 or 图 的邻接矩阵 or 拉普拉斯矩阵的 特征值与特征向量。

### Spectral gap

[Spectral gap](https://en.wikipedia.org/wiki/Spectral_gap#:%7E:text=In%20mathematics%2C%20the%20spectral%20gap,other%20properties%20of%20the%20system.)表征了图的可扩展性，计算方式为邻接矩阵的第一特征值与第二特征值之间的差。

### Algebraic connectivity

[代数连通度](https://en.wikipedia.org/wiki/Algebraic_connectivity)衡量了整个网络的连接程度，它的计算方式为拉普拉斯矩阵的第二小特征值。

