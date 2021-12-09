---
layout:     post
title:      "A Course in Combinatorics(Chapter 5) by J. H. van Lint"
subtitle:   "Systems of distinct representatives"
thumbnail-img: ""
date:       2021-12-09 08:10
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



我们首先给出两个不同的定理公式作为P. Hall's marriage theorem。我们给出一个构造证明和一个计数证明。如果A是一个图的顶点的子集，则记为 $ \\Gamma(A) $，集合 $ \\cup_ {a \\in A} \\Gamma(a) $。考虑一个两分图G有顶点集合 $ X \\cup Y $。一个G中的匹配为一个边集的子集 $ E_ {1} $使得在 $ E_ {1} $中没有顶点邻接超过一条边。一个从X到Y的完全匹配是一个匹配使得X中每个顶点在 $ E_ {1} $中有一条边邻接。如果X和Y中的顶点认为是男孩和女孩，且一条边代表一端的人对另一端友好，则一个完全的匹配代表在X中一个可能的结婚对象

**定理** 对G中从X到Y有一个完全匹配的充分必要条件为 $ \| \\Gamma(A) \| \\ge \| A \|, \\forall A \\subset X $

证明：(i)对充分条件来说这是明显的

(ii) 假设 $ \| \\Gamma(A) \| \\ge \| A \|, \\forall A \\subset X $。设 $ \| X \| = n $，m < n，且假设我们有一个匹配M有m条边。我们将显示一个更大的匹配存在

记M的边为红色其他边为蓝色。设 $ x_ {0} \\in X $为一个不邻接匹配边的顶点。我们声称存在一个简单的路径（奇数长度）开始于 $ x_ {0} $且是一条蓝边，使用红蓝交替的边，且终止于一条蓝边其末点是不邻接匹配边的点y。如果我们找到这样的一个路径p，我们就完成了因为我们通过删除p的红色边且用p的蓝色边替换就获得了一个m+1的匹配。即我们交换p的边颜色
