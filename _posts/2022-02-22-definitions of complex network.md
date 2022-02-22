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

