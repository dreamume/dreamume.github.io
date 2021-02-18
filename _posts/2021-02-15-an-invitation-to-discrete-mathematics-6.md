---
layout:     post
title:      "An invitation to discrete mathematics(Chapter 6) by Matousek"
subtitle:   "Drawing graphs in the plane"
thumbnail-img: ""
date:       2021-02-15 19:00
author:     "dreamume"
tags: 		[discrete math]
category:   maths
---
<head>
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({
            tex2jax: {
            skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
            inlineMath: [['$','$']]
            }
        });
    </script>
</head>

# Table of Contents

1.  [Drawing in the plane and on other surfaces](#org251e123)
    1.  [定义](#org88e35f4)
        1.  [图形绘制的面](#org6a8af02)


<a id="org251e123"></a>

# Drawing in the plane and on other surfaces

如你所见，本书中多数图形为一个图像（而不是点和边的列表）。但我们已学习图形的属性跟它们的画法无关，且绘画纯是辅助。在本章中分析主题为图形绘制本身且我们将主要关注能在平面上被绘画测的图形且边不会相交。这样的图形被称为planar

从前一章的非形式化定义中，读者可能获得了非常好的直观关于什么是图形绘制。这样的直观通常是高效的如果我们想要显示某些图形是planar的 - 我们可简单绘制一个无交叉边图形的适合的图片。然而，如果我们想要以严格地逻辑证明，某些图形不是planar的，在没有绘制符号的数学定义时我们没法证明。如今的数学完全构建于少数原始的记号和集合理论公理上 - 或至少多数数学家尝试确定是这样。例如，平面的记号被模型为Cartesian乘积R x R。每个实数被定义为有理数的cartesian子集，有理数从自然数创建，且最终自然数被定义为从空集产生的某种特殊集合（这在数学中很少看到，但如果你看一些数学基础书籍你可以找到它）

为了形式化地引入绘制符号，我们先定义一个弧形：一个平面上 $ \\alpha $的子集形如：$ \\alpha = \\gamma([0, 1]) = \\{ \\gamma(x): x \\in [0, 1] \\} $，且 $ \\gamma: [0, 1] \\to R^{2} $是一个闭合区间[0, 1]到平面的连续单射。点 $ \\gamma(0) $和 $ \\gamma(1) $被称为弧形 $ \\alpha $的端点

这个定义，跟绘制的直观符号非常接近。间隔[0, 1]可被认为一个时间段，期间我们绘制了一个线段从点 $ \\gamma(0) $到点 $ \\gamma(1) $。然后 $ \\gamma(t) $是在时刻t铅笔所在的位置。映射 $ \\gamma $的连续性意味着在纸的表面上的连续运动，且单射表示绘制的线段没有相交


<a id="org88e35f4"></a>

## 定义

一个图形G = (V, E)的绘制我们指一个如下赋值：对G中每个顶点v，赋值一个平面上的点b(v)，对每条边 $ e = \\{v, v'\\} \\in E $，赋值一个平面上端点b(v)到端点 $ b(v') $的弧线 $ \\alpha(e) $。我们假设映射b是单射（不同的顶点赋值给平面上不同的点），且没有形式为b(v)的点在任意弧线上除了弧线端点。一个图形及某些绘制被称为一个拓扑图形

一个图形G的绘制，其任意两个弧线对应不同的边要么没有相交要么只共享端点被称为一个planar绘制。一个图形G是planar的如果它有至少一个planar绘制

我们以给出以上一个图形绘制的形式化定义，为了阐述一个绘制的记号可被包含在数学逻辑构建中。我们将不继续以严格的逻辑构建planar图形的子序列理论。我们会使用planar曲线的记号和结果。这些属于数学分支称为拓扑。只有非常少的拓扑知识在基础数学课程中出现，我们不得不引入非常复杂的机制来使事情严谨。更多地，某些直观明显的陈述的证明非常困难。因此，我们将有时依赖读者的直觉，我们将要求读者相信某些没有证明的陈述。严谨的陈述可以找到，例如，在最近的Mohar和Thomassen的书中。幸运地是，在图形绘制理论中，基本的绘制直觉很少导致被曲解

一个planar绘制是图形可视化的高级形式（在非planar绘制中边交叉对顶点可能是错误的），在某些应用程序中其绘制有一个物理意义，边交叉是不可接受的（例如，单层集成电路的设计）


<a id="org6a8af02"></a>

### 图形绘制的面

设G = (V, E)为一个拓扑planar图形，例如，一个planar图形及一个给定的planar绘制。考虑在平面上不在绘制弧线的所有点的集合。该集合包含有限多个连接区域（想象我们沿着绘制的边剪切）:

![img](../img/example_planar_graph_cut.png)

（我们说一个集合 $ A \\subseteq R^{2} $是连通的如果对任意两个点 $ x, y \\in A $存在一个弧线 $ \\alpha \\in A $，x、y为端点。“连通“是一个拓扑记号的例子 ）这些区域将被称为被考虑的拓扑planar图形的面。这些区域扩展到无穷，比如上图中的 $ F_ {1} $，被称为绘制的外部面（或无边界面），且所有其他面被称为内部面（或有边界面）

让我们强调面被定义为一个给定的planar绘制。面通常不被定义为一个nonplanar绘制，且我们将不谈论一个planar图形的面没有特定的绘制

绘制在其他表面。一个图形也能被绘制在非平面的其他表面上。让我们列出一些有趣表面的例子

每个人都知道球形（例如，一个球的表面）。一个tire-tube的表面被称为环面

![img](../img/example_mobius_band.png)

如果我们把长纸条的一条边反转180度，再跟另一条边粘上，我们获得一个有趣的表面称为莫比乌斯环

![img](../img/example_sphere_with_2handles.png)

另一个例子是一个球形带两个柄

![img](../img/example_klein_bottle.png)

经过适当的变形，有这样的表面被称为Klein bottle

每个这样的表面可通过planar多边形通过粘贴和适当的变形创建。上述这些例子中，除了带两个柄的球，我们总是可从一个planar矩形开始，用适当的方式粘某些边。
