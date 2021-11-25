---
layout:     post
title:      "A Course in Combinatorics(Chapter 3) by J. H. van Lint"
subtitle:   "Colorings of graphs and Ramsey's Theorem"
thumbnail-img: ""
date:       2021-11-26 06:10
author:     "dreamume"
tags: 		[discrete]
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

1.  [Colorings of graphs and Ramsey's theorem](#org634776c)


<a id="org634776c"></a>

# Colorings of graphs and Ramsey's theorem

**定理** 如果 $ K_ {n} $的边着上红色或蓝色，且 $ r_ {i}, i = 1, 2, \\ldots, n $，记为顶点i作为端点的红边个数。且如果 $ \\Delta $记为单色三角形的个数，则

$ \\Delta = {n \\choose 3} - \\frac{1}{2} \\sum^{n}_ {i=1} r_ {i}(n - 1 - r_ {i}) $

证明：$ K_ {n} $中每个三角形不是单色的话有两个顶点是红边和蓝边的交点。在第i个顶点上，两个这样的边可被选择有 $ r_ {i} (n - 1 - r_ {i}) $个，进而得证

