---
layout:     post
title:      "An Introduction to the theory of numbers(Chapter 3) by hardy"
subtitle:   "Farey Series and a Theorem of Minkowski"
thumbnail-img: ""
date:       2021-11-11 11:10
author:     "dreamume"
tags: 		[number]
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



序为n的Farey系列 $ \\Im_ {n} $是在0和1之间不可约的分数递增序列，其分母不超过n。则h / k 属于 $ \\Im_ {n} $如果

$ 0 \\le h \\le k \\le n, \\qquad (h, k) = 1 $

0和1之间包含 $ \\frac{0}{1}, \\frac{1}{1} $。例如，$ \\Im_ {5} $为

$ \\frac{0}{1}, \\frac{1}{5}, \\frac{1}{4}, \\frac{1}{3}, \\frac{2}{5}, \\frac{1}{2}, \\frac{3}{5}, \\frac{2}{3}, \\frac{3}{4}, \\frac{4}{5}, \\frac{1}{1} $

**定理** 如果 $ h / k, h^{\\prime} / k^{\\prime} $是 $ \\Im_ {n} $中两个连续的项，则 

$ kh^{\\prime} - hk^{\\prime} = 1 $

**定理** 如果 $ h / k, h^{\\prime \\prime} / k^{\\prime \\prime}, h^{\\prime} / k^{\\prime} $是 $ \\Im_ {n} $中三个连续的项，则

$ \\frac{h^{\\prime \\prime}}{k^{\\prime \\prime}} = \\frac{h + h^{\\prime}}{k + k^{\\prime}} $

**定理** 如果 $ h / k, h^{\\prime} / k^{\\prime} $是 $ \\Im_ {n} $中两个连续的项，则

$ k + k^{\\prime} > n $

则它们的中位数

$ \\frac{h + h^{\\prime}}{k + k^{\\prime}} $

在区间

$ (\\frac{h}{k}, \\frac{h^{\\prime}}{k^{\\prime}}) $

**定理** 如果n > 1，则 $ \\Im_ {n} $中连续两项没有相同的分母

