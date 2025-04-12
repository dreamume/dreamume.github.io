---
layout:     post
title:      "Math Analysis(Chapter 4) by Yu Pin"
subtitle:   "极限，级数，Cauchy 列，距离空间中的收敛"
thumbnail-img: ""
date:       2025-04-12 16:50
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

1.  [计算级数的例题](#org1ce2a79)


<a id="org1ce2a79"></a>

# 计算级数的例题

求 $ \\sum^{n}_ {n=1} \\arctan\\frac{1}{n^{2} + n + 1} $

我们需要利用等式：

$ \\arctan{a} - \\arctan{b} = \\arctan{\\left(\\frac{a-b}{1+ab}\\right)} $

于是我们有

$ \\arctan{\\left(\\frac{1}{n^{2}+n+1}\\right)} = \\arctan{(n+1)} - \\arctan{(n)} $

则

$ \\sum^{n}_ {n=1} \\arctan\\frac{1}{n^{2} + n + 1} = \\lim_ {\\n \\to \\infty}{(\\arctan{(n+1)} - \\arctan{1})} = \\frac{\\pi}{2} - \\frac{\\pi}{4} = \\frac{\\pi}{4} $
