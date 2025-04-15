---
layout:     post
title:      "The Cauchy-Schwarz master class(Chapter 6) by Steele"
subtitle:   "Convexity - The Third Pillar"
thumbnail-img: ""
date:       2025-04-12 16:00
author:     "dreamume"
tags: 		[elementary]
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

1.  [Jensen's Inequality](#orgb2c192c)
2.  [Differential Criterion for Convexity](#orga288ce4)


<a id="orgb2c192c"></a>

# Jensen's Inequality

假设 $ f: [a, b] \\to \\mathbb{R} $ 是一个凸函数且假设非负实数 $ p_ {j}, j = 1,2,\\ldots, n $ 满足

$ p_ {1} + p_ {2} + \\cdots + p_ {n} = 1 $

则对所有 $ x_ {j} \\in [a, b], j = 1,2,\\ldots, n $ 有

$ f \\left(\\sum^{n}_ {j=1}p_ {j}x_ {j} \\right) \\le \\sum^{n}_ {j=1}p_ {j}f(x_ {j}) $


<a id="orga288ce4"></a>

# Differential Criterion for Convexity

如果 $ f: (a, b) \\to \\mathbb{R} $ 是两次可微的，则

$ f^{\\prime \\prime}(x) \\ge 0, x \\in (a, b) $ 意味着 $ f(\\cdot) $ 在 (a, b) 上是凸的

且，同样

$ f^{\\prime \\prime} > 0, x \\in (a, b) $ 则意味着 $ f(\\cdot) $ 在 (a, b) 上是严格凸的
