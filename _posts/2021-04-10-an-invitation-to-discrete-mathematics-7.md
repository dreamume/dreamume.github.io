---
layout:     post
title:      "An invitation to discrete mathematics(Chapter 7) by Matousek"
subtitle:   "Double-counting"
thumbnail-img: ""
date:       2021-04-10 11:00
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

1.  [Parity arguments](#org5c64a74)
    1.  [命题（Sperner引理 - planar版本）](#org6779ace)
    2.  [命题（一维固定点定理）](#orgba6cb2d)


<a id="org5c64a74"></a>

# Parity arguments

让我们画一个大三角形，顶点为 $ A_ {1}, A_ {2}, A_ {3} $。我们分割它为任意有限个小三角形，如下图：

![img](../img/example_of_divide_triangle.png)

其中每个三角形都不会在其他三角形的边的里面，这样如果我们考虑该结果图为一个planar图形的绘制，所有内部的面都是三角形。让我们给大三角形和小三角形的顶点标签为1、2、3，在如下规则中：给顶点 $ A_ {i} $一个标签i，i = 1,2,3，且所有在边 $ A_ {i} A_ {j} $上的大三角形的顶点只能给标签为i或j，其他的顶点则可任意赋值


<a id="org6779ace"></a>

## 命题（Sperner引理 - planar版本）

在如上的描述中，一个顶点被赋值为1、2、3的小三角形总是存在

![img](../img/proof_of_sperner_lemma.png)

**证明** 我们定义一个辅助图形G；如上图。它的顶点为我们三角度量的面，例如，所有小三角形加上外层的面。在图中，顶点被描述为对应面中的小黑三角形。外层的面的顶点被记为v。两个顶点，例如，原始图形的面，由G的一条边连接如果有相邻的面且它们共同的边的端点标签为1和2。也考虑最外层面的顶点v，它连接所有小三角形邻接大三角周边边标签为12

一个小三角形在这个图形G中可连接一些它的邻居只在它的顶点标签为1且另一个标签为2。如果仍然有顶点标签为1或2，考虑的小三角形邻接两个邻居。如果仍然有顶点标签为3，则考虑三角形邻接一个邻居，且唯一的情况是图形G中小三角形的度数是奇数。我们现在显示顶点v（外层的面）在G中有奇数的度数。然后，通过握手引理，在G中存在至少另一个奇数度数的顶点，且这是想要的小三角形标签为1,2,3

图形G的边邻接v明显只与大三角形的边 $ A_ {1} A_ {2} $交叉。通过标签规则，该边只包含标签为1或2的顶点。让我们写下这些标签序列，开始于 $ A_ {1} $，结束于 $ A_ {2} $。v的邻居的数量是在这个序列中交替的1和2。因为序列开始于1结束于2，这样交替的数必须为奇数。因此v在G中是奇数的度数


<a id="orgba6cb2d"></a>

## 命题（一维固定点定理）

对任意连续函数 $ f: [0, 1] \\to [0, 1] $，存在一个点 $ x \\in [0, 1] $使得f(x) = x

这样的x被称为函数f的固定点。该命题可通过考虑函数g(x) = f(x) - x来证明。这是一个连续函数其 $ g(0) \\ge 0 $且 $ g(1) \\le 0 $。直观上非常明显这样的连续函数的图形不能跳过x轴且因此g在[0,1]之间的某个点是0

固定点理论一般描述如下，在某种环境下，某些函数f必须有一个固定点，例如，存在一个x使得f(x) = x。这样的定理在数学的许多领域都是重要的结果。通常作为工具证明各种类型等式（积分、微分等）的存在方案

在Brouwer的固定点定理中，命题的一维间隔被平面的三角形替代，或三维空间中的四面体，或更高维的类似物。这里我们只证明2维空间版本因为我们只证明了2维的Sperner引理。

设 $ \\Delta $记为平面上的一个三角形。为简化，让我们记三角形的顶点为 $ A_ {1} = (1, 0), A_ {2} = (0, 1), A_ {3} = (0, 0) $：

![img](../img/proof_of_fixed_point_theorem.png)

一个函数 $ f: \\Delta \\to \\Delta $被称为连续的如果对 $ \\all a \\in \\Delta $且 $ \\all \\epsilon > 0 $存在 $ \\delta > 0 $使得如果 $ b \\in \\Delta $是从a开始距离最大为 $ \\delta $的一个点则f(a)和f(b)的距离最多为 $ \\epsilon $
