---
layout:     post
title:      "A Course in Combinatorics(Chapter 4) by J. H. van Lint"
subtitle:   "Turan's Theorem and extremal graphs"
thumbnail-img: ""
date:       2021-12-04 12:10
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



我们首先问一个问题，一个简单图上需要有多少个边来保证图中含有一个三角形。因为 $ K_ {m,m}, K_ {m,m+1} $不含有三角形，我们看到如果图像有n个点，则 $ \\lfloor n^{2} / 4 \\rfloor $条边是不够的。我们声称如果有更多的边，则图包含一个三角形（W. Mantel, 1907）。如下证明很奇怪。设G有n个点，没有三角形。我们给定点i一个权重 $ z_ {i} \\ge 0 $使得 $ \\sum z_ {i} = 1 $且我们希望最大化 $ S := \\sum z_ {i}z_ {j} $，和是所有边的端点权重相乘之和。假设点k和点l不相交。设k的邻居有总权重x，且l的邻居的总权重为y，$ x \\ge y $。因为 $ (z_ {k} + \\epsilon) x + (z_ {l} - \\epsilon)y \\ge z_ {k}x + z_ {l}y $，我们不减少S值如果我们移动l点的权重到k点。则S是最大的如果所有的权重集中在G的某个完全子图上，例如，在一条边！因此，$ S \\le \\frac{1}{4} $。另一方面，让所有 $ z_ {i} $等于 $ n^{-1} $，得到S的一个值 $ n^{-2} \| E \| $。因此，$ \| E \| \\le \\frac{1}{4} n^{2} $

注意Ramsey定理描述如果一个n个顶点的图有 $ n \\ge N(p,q;2) $，则图要么有一个p顶点的完全子图或一个q个顶点的集合，其互相不连接。我们现在问一个问题是否某个条件下的边数确保有一个 $ K_ {p} $的子图。我们看到答案是p = 3。我们也有了一个想法如何避免 $ K_ {p} $。分割顶点为p - 1个几乎相同大小的子集 $ S_ {1}, \\ldots, S_ {p-1} $，例如，大小为t + 1的r子集且大小为t的p - 1 - r子集，$ n = t(p-1) + r, 1 \\le r \\le p - 1 $。每个 $ S_ {i} $里没有边但 $ S_ {i} $里每个顶点连接 $ S_ {j} $的每个顶点，$ i \\ne j $

边的数目为

$ M(n, p) := \\frac{p - 2}{2(p - 1)} n^{2} - \\frac{r(p - 1 -r)}{2(p - 1)} $
