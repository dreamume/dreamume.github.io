---
layout:     post
title:      "An invitation to discrete mathematics(Chapter 4) by Matousek"
subtitle:   "Graphs: an introduction"
thumbnail-img: ""
date:       2020-12-10 14:00
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

1.  [subgraphs, components, adjacency matrix](#orgacd61fa)


<a id="orgacd61fa"></a>

# subgraphs, components, adjacency matrix

**命题** 设G = (V, E)是一个图，设顶点集合 $ V = \\{v_ {1}, v_ {2}, \\ldots, v_ {n} \\}, A = A_ {G} $为邻接矩阵。设 $ A^{k} $记为邻接矩阵的k次方，设 $ a_ {i j}^{\\left(k\\right)} $为矩阵 $ A^{k} $在(i, j)位置的元素。则 $ a_ {i j}^{\\left(k\\right)} $为图G中从点 $ v_ {i} $到 $ v_ {j} $路径长度为k的路径数。

**推论** 两个顶点的距离满足 $ d_ {G}\\left(v_ {i}, v_ {j}\\right) = min\\{k \\ge 0: a_ {i j}^{\\left(k\\right)} \\ne 0 \\} $
