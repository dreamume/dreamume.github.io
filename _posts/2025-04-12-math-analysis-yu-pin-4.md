---
layout:     post
title:      "Math Analysis(Chapter 4) by Yu Pin"
subtitle:   "Limit, Series, Cauchy Sequence, Convergence in Distance Space"
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
    1.  [1](#org65c1ff7)
    2.  [2](#orged8f069)


<a id="org1ce2a79"></a>

# 计算级数的例题


<a id="org65c1ff7"></a>

求 $ \\sum^{n}_ {n=1} \\arctan\\frac{1}{n^{2} + n + 1} $

我们需要利用等式：

$ \\arctan{a} - \\arctan{b} = \\arctan{\\left(\\frac{a-b}{1+ab}\\right)} $

于是我们有

$ \\arctan{\\left(\\frac{1}{n^{2}+n+1}\\right)} = \\arctan{(n+1)} - \\arctan{(n)} $

则

$ \\sum^{n}_ {n=1} \\arctan\\frac{1}{n^{2} + n + 1} = \\lim_ {\\n \\to \\infty}{(\\arctan{(n+1)} - \\arctan{1})} = \\frac{\\pi}{2} - \\frac{\\pi}{4} = \\frac{\\pi}{4} $


<a id="orged8f069"></a>

这里我们利用 weighted geometric series，其一般形式为：

$ \sum^{\\infty}_ {n=1}nx^{n} = \\frac{x}{(1-x)^{2}}, \\| x \\| < 1 $

这里，我们让 $ x = \\frac{1}{3} $，则有

$ \\sum^{\\infty}_ {n=1}\\frac{n}{3^{n}} = \\sum^{\\infty}_ {n=1}n\\left(\\frac{1}{3}\\right)^{n} = \\frac{\\frac{1}{3}}{(1 - \\frac{1}{3})^{2}} = \\frac{3}{4} $
