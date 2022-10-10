---
title: 2. 运动学
author: Tao He
date: 2019-04-27
category: Jekyll
layout: post
mathjax: yes
---

## 2.1 物体、构型、运动

我们先给出物体的定义。一个**物体**$\mathcal{B}$是一个集合。这个集合中的每个元素都与区域$B$中的点集一一对应。区域$B$包含于一个三维的Euclidean空间中。$\mathcal{B}$中的元素被称为**粒子**，或者**物质点**，$B$被称为$\mathcal{B}$的**构型**。

随着物体的运动，它的构型也随之变化。$I$ 表示$\mathbb{R}$中的一个区间，$t\in I\subset\mathbb{R}$表示时间，将每一时刻$t$都与$\mathcal{B}$的一个构型$B_t$关联起来，那么称这一族构型$\{B_t:t\in I\}$为物体$\mathcal{B}$的**运动**。假设$\mathcal{B}$是连续运动的，那么$B_t$也是连续变化的。

确定一个 **参考构型** $B_r$ 。参考构型是任意选定的，$\mathcal{B}$ 的任意粒子 $P$ 在 $B_r$ 中都有一个位置向量$\mathbf{X}$，我们用 $\mathbf{X}$ 标记粒子。令 $\mathbf{x}$ 为$t$时刻粒子在构型 $B_t$ 中的坐标。$\mathbf{X}$和$\mathbf{x}$可以选用不同的原点，分别记为$O$和$o$。下图展示了参考构型、即时构型、位置向量等之间的关系。

![image-20221001234721532](https://raw.githubusercontent.com/mapengfei-nwpu/personal_pictures/main/typora_picgo/202210012347824.png)

我们可以这样说，$\mathcal{B}$ 在 $t$ 时刻占据构型$B_t$，$B_t$是**即时构型**。需要注意的是，我们并不要求 $B_r$ 是在运动过程中出现过的构型，但是一般会选用$t=0$时刻的构型。

因为 $B_r$ 和 $B_t$ 都是物体 $\mathcal{B}$ 的构型，因此存在双射$\chi:B_r\rightarrow B_t$ 使得
$$
\mathbf{x} = \chi(\mathbf{X}) \quad\forall \;\mathbf{X}\in B_r,\quad\quad\mathbf{X}=\chi^{-1}(\mathbf{x})\quad\forall \;\mathbf{x}\in B_t
$$
我们称映射 $\chi$ 为物体从 $B_r$ 到 $B_t$ 的形变。因为 $B_t$ 依赖于时间$t$，我们可以将上式写成
$$
\mathbf{x} = \chi_t(\mathbf{X}) \quad,\quad\quad\mathbf{X}=\chi_t^{-1}(\mathbf{x})
$$
或者
$$
\mathbf{x} = \chi_t(\mathbf{X},t) \quad \forall\quad \mathbf{X}\in B_r,\; t\in I.
$$
对任意粒子$P$（标为 $\mathbf{X}$ ），上面的方程能够描述粒子$P$随时间$t$的运动，因此也能描述物体$\mathcal{B}$的运动。通常我们假设$\chi(\mathbf{X},t)$是一个关于位置和时间二阶连续可微的函数，但是有些场合需要放宽这个限制。例如，跨越相场边界时，$\chi$的一阶、二阶导数会出现间断。

#### 一个例子：刚体运动

在运动过程中，如果$\mathcal{B}$的任意两个粒子之间的距离不发生变化，那么这样的运动称为刚体运动。刚体运动可以描述成
$$
\mathbf{x} = \chi(\mathbf{X},t)=\mathbf{c}(t)+\mathbf{Q}(t)\mathbf{X},
$$
其中，$\mathbf{c}(t)$是一个向量，$\mathbf{Q}(t)$是一个本征正交二阶张量。

> 此处的本征正交有疑问。我的理解，是$\mathbf{Q}(t)$是一个旋转矩阵，即它是一个正交矩阵并且它的行列式是单位一。

我们可以证明任意两个粒子之间的距离不发生变化。

假设另一个粒子$\mathbf{Y}$的即时坐标为$\mathbf{y}=\mathbf{c}(t)+\mathbf{Q}(t)\mathbf{Y}$，那么
$$
\begin{aligned}
|\boldsymbol{x}-\boldsymbol{y}|^2 &=(\boldsymbol{x}-\boldsymbol{y}) \cdot(\boldsymbol{x}-\boldsymbol{y}) \\
&=[\boldsymbol{Q}(\boldsymbol{X}-\boldsymbol{Y})] \cdot[\boldsymbol{Q}(\boldsymbol{X}-\boldsymbol{Y})] \\
&=\left[\boldsymbol{Q}^T \boldsymbol{Q}(\boldsymbol{X}-\boldsymbol{Y})\right] \cdot(\boldsymbol{X}-\boldsymbol{Y}) \\
&=(\boldsymbol{X}-\boldsymbol{Y}) \cdot(\boldsymbol{X}-\boldsymbol{Y}) \\
&=|\boldsymbol{X}-\boldsymbol{Y}|^2,
\end{aligned}
$$
其中用到了$\mathbf{Q}^T\mathbf{Q}=\mathbf{I}$。事实上，尽管我们没有证明这一点，任何刚体运动都可以写成上述表达式。其中，$\mathbf{c}(t)$表示平移，$\mathbf{Q}(t)$表示旋转。
