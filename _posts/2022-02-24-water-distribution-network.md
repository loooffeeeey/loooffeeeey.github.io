---
layout:     post
title:      城市水网的基础概念
subtitle:   调研得到的一些城市水网的一些非常基础的定义，初步了解水网的构成
date:       2022-02-24
author:     loooffeeeey
header-img: img/post-bg-win.jpg
catalog: true
tags:
    - 调研
    - 水利工程
---


# 城市水网的基础概念

从不同来源，整理了一些对供水网络的一些知识

## epanet 2.2

从模拟的角度，参考epanet和一些城市水网的一些基础知识的搜索，整理一下一些基础概念

- 节点
  - Reservoirs
    - 提供无限的水源，模拟湖泊、大河、地下水等
    - 输入
      - 地理信息
        - 海拔
        - 位置
    - 输出
      - 固定的扬程
      - 水质
  - Tanks
    - 水池、水塔，中间储水
    - 输入
      - 静态属性
        - 容量
      - 初始水质
    - 输出
      - 扬程
      - 水质
  - junctions
    - 水管网的连接点
    - 流入管道，流出管道交叉
    - 输入
      - 静态属性
        - 海拔
      - demand
        - *Have negative demands indicating that water is entering the network*
      - 水质
    - 输出
      - 扬程
      - 水压
      - 水质
- 连接
  - Pipes
    - 静态属性
      - 节点类型中的起终点
      - 直径
      - 长度
      - 粗糙稀疏
    - 输入
      - *可能来自节点？*
    - 输出
      - 流量
      - 流速
      - Darcy-Weisbach friction factor
        - 计算扬程损失的经验方程中的一个系数
        - 取决于管径、粗糙系数、流体粘度、流速
      - 扬程损失
        - Hazen-Williams formula
        - Darcy-Weisbach formula
        - Chezy-Manning formula
        - 计算方法
          - $h_L \ = \  Aq^B$, 其中 $h_L$ 是扬程损失，q为流量(Volume/Time)，$A$是resistance coefficient，$B$是flow exponent
          - <img src="/img/2022-02-24-water-distribution-network/post-formula-headloss.jpg"/>
      - 平均水质
  - Pumps
    - 属性
      - 起点终点，节点类中
      - curve (the combination of heads and flows that the pump can produce)
    - 输出
      - 流量增益
      - 扬程增益
  - Valves
    - 属性
      - 起终点，节点类中
      - 类别
        - Pressure Reducing Valve (PRV)
        - Pressure Sustaining Valve (PSV)
        - Pressure Breaker Valve (PBV)
        - Flow Control Valve (FCV)
        - Throttle Control Valve (TCV)
        - General Purpose Valve (GPV)
    - 输出
      - 流量
      - 扬程损失

## 供水网络（百度百科）

从百度百科得到的一些可能算是常识性的东西，加深一点对供水的理解。

供水工程中向用户输水和配水的管道系统，又称给水管网。

- 水管网
  - 连接类
    - 输水管渠
      - 从水源地到水厂的管渠只起输水作用
    - 配水管网
      - 自水厂出来的管道称配水管网
      - 树枝形和环形
      - 干管
        - 支管
          - 用户支管
  - 节点类
    - 加压泵站
    - 水塔
      - 一般居民区里蓄水作用，有些还是水厂生产工艺的一个重要组成部分
    - 水池
  - 管网附属设施
  - 维持供需平衡
    - 所有供水点的总供水量应随着用水量的变化做相应调整，可通过调节水泵的开启台数、采用变频调速泵或调节重力供水管上阀门的开启度进行调整
