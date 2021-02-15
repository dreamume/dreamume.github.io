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


<a id="org251e123"></a>

# Drawing in the plane and on other surfaces

如你所见，本书中多数图形为一个图像（而不是点和边的列表）。但我们已学习图形的属性跟它们的画法无关，且绘画纯是辅助。在本章中分析主题为图形绘制本身且我们将主要关注能在平面上被绘画测的图形且边不会相交。这样的图形被称为planar

从前一章的非形式化定义中，读者可能获得了非常好的直观关于什么是图形绘制。这样的直观通常是高效的如果我们想要显示某些图形是planar的 - 我们可简单绘制一个无交叉边图形的适合的图片。然而，如果我们想要以严格地逻辑证明，某些图形不是planar的，在没有绘制符号的数学定义时我们没法证明。如今的数学完全构建于少数原始的记号和集合理论公理上 - 或至少多数数学家尝试确定是这样。例如，平面的记号被模型为Cartesian乘积R x R。每个实数被定义为有理数的cartesian子集，有理数从自然数创建，且最终自然数被定义为从空集产生的某种特殊集合（这在数学中很少看到，但如果你看一些数学基础书籍你可以找到它）

为了形式化地引入绘制符号，我们先定义一个弧形：一个平面上 $ \\alpha $的子集形如：$ \\alpha = \\gamma([0, 1]) = \\{ \\gamma(x): x \\in [0, 1] \\} $，且 $ \\gamma: [0, 1] \\to R^{2} $是一个闭合区间[0, 1]到平面的连续单射。点 $ \\gamma(0) $和 $ \\gamma(1) $被称为弧形 $ \\alpha $的端点

这个定义，跟绘制的直观符号非常接近。间隔[0, 1]可被认为一个时间段，期间我们绘制了一个线段从点 $ \\gamma(0) $到点 $ \\gamma(1) $。然后 $ \\gamma(t) $是在时刻t铅笔所在的位置。映射 $ \\gamma $的连续性意味着在纸的表面上的连续运动，且单射表示绘制的线段没有相交

