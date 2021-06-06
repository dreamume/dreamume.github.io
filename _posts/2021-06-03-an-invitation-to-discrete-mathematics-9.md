---
layout:     post
title:      "An invitation to discrete mathematics(Chapter 9) by Matousek"
subtitle:   "Finite projective planes"
thumbnail-img: ""
date:       2021-06-03 09:00
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

1.  [定义和基本属性](#org26c438d)
    1.  [定义](#org00539b3)


<a id="org26c438d"></a>

# 定义和基本属性

finite projective plane是带某些属性的有限集合的子集的系统


<a id="org00539b3"></a>

## 定义

设X为一个有限集，且设 $ \\mathcal{L} $为X的子集的系统。二元组 $ (X, \\mathcal{L}) $被称为finite projective plane，如果它满足如下公理：

(P0) 存在一个4元素集合 $ F \\subseteq X $使得对每个集合 $ L \\in \\mathcal{L}, \| L \\cap F \| \\le 2 $

(P1) 任意两个不同的集合 $ L_ {1}, L_ {2} \\in \\mathcal{L} $ 相交只有一个元素，例如，$ \| L_ {1} \\cap L_ {2} \| = 1 $

(P2) 对任意两个不同的元素 $ x_ {1}, x_ {2} \\in X $，只存在一个集合 $ L \\in \\mathcal{L} $ 使得 $ x_ {1} \\in L, x_ {2} \\in L $

如果 $ (X, \\mathcal{L}) $是一个finite projective plane，我们X的元素为点，$ \\mathcal{L} $的集合为线。如果 $ x \\in X $是一个点而 $ L \\in \\mathcal{L} $是一条线，我们说“点x在线L上“或“线L穿过点x“

如果我们用这种新语言表达公里(P0) - (P2)，他们开始跟几何陈述相似。公里(P1)说任意两个不同的线只相交于一个点，公理(P2)告诉我们只有一条线穿过两个不同的点。公理(P0)需要4个点存在使得没有3个点共线

如果 $ a, b \\in X $为finite projective plane上两个不同的点，包含a和b的唯一的线 $ L \\in \\mathcal{L} $被记为符号 $ \\bar{ab} $。如果 $ L, L^{\\prime} \\in \\mathcal{L} $为不同的线，$ L_ {1} \\cap L_ {2} $的唯一点被称为它们的交

我们依然还欠读者一个projective plane中projective的解释。首先，我们应该显示什么是projective转换。考虑两个3维欧几里得空间中的平面 $ \\rho $ 和 $ \\sigma $和一个不在这两个平面中的点c，且从点c映射 $ \\rho $中的每个点到平面 $ \\sigma $。这定义了一个映射，称为从 $ \\rho $到 $ \\sigma $的projective转换。如果 $ x \\in \\rho $是一个点使得线段cx平行于平面 $ \\sigma $，则在欧几里得几何中，x的像是未定义的。但如果我们补充 $ \\rho $和 $ \\sigma $一个无穷远的线使得它们变成projective planes，则这个projective转换是这两个projective planes间的双射。如果 $ \\rho $和 $ \\sigma $被考虑为同一平面的拷贝，我们认为这个映射是projective plane到其自身的双射。projective plane是一个适当的域可做projective几何，一个考虑projective几何适当的域和保留projective转换的配置的几何分支。例如，projective转换映射conic部分（圆、椭圆、抛物线和双曲线）到conic部分，但一个椭圆可被转换为一个双曲线，等，且一个conic部分的伟大统一理论可在projective几何中建立

实际projective plane的finite projective plane的相似用来作为各种记号的动机，且通常也为目的（我们可绘制几何图像）。在真实projective plane上的几何考虑和使用公理(P0) - (P2)只运用在finite projective planes上。不要忘记一个finite projective plane只是一个带(P0) - (P2)属性的有限集合系统，因此其他几何记号不能自动转换到它身上。例如，在finite projective plane上没有距离，因此它没有圆的明确定义。另一个重要的不同是在通常的几何平面上，每条线的点可被该线自然排序，但在finite projective plane上没有这样的排序

![img](../img/the_fano_plane.png)

**例子** 一个有限projective plane最小可能的例子是7个点和7条线，每条线有3个点，且它称为Fano plane。如上图。这些点被标记为1-7，且每条线上的3个点被一个线段连接，这些连接线被标签为a-g

![img](../img/weekly_schedule_for_location_plano_bar.png)

Fano plane虽然小，但是一个有用的数学对象，且它也作为各种谜题或一些高级问题的解决方案出现，比如如下这个。7个警察被转换到第87区域的各个区，一个好的时机是让他们互相观察在西南C Drive的Plano Bar，这里是一个简单甚至乏味地值班因为酒吧的顾客通常是计算机罪犯，数字钱币伪造者或类似的人。需要一个3人移动小组，一周1天服务。如何安排每周调度使得7人中的每两人会值班一周？Fano plane提供了好的解决方案（点对应警察，移动对应线，以某种顺序排列）。每个人有相同编号的移动，没有人会超过连续两天，但另一方面，每个移动有一个人在前一天也在并知道发生了什么。我们不知道这样的调度在实际中会被警方使用，但例如，一些摩托循环赛会根据基于affine plane的order four来组织
