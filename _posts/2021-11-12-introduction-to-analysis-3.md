---
layout:     post
title:      "解析概論(Chapter 3) by 高木貞治"
subtitle:   "积分法"
thumbnail-img: ""
date:       2021-11-12 16:10
author:     "dreamume"
tags: 		[analysis]
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

1.  [古代的求积法](#org610e933)


<a id="org610e933"></a>

# 古代的求积法

特殊的曲面曲线的求积法自古就为人所知。阿基米德以计算球面及体积闻名，阿基米德还设计了如下的方法，用一根弦限制的抛物线碎片很好地计算出了面积

AB是抛物线的弦，OM是通过它中点的直径，那么抛物线和弦所围成的面积S是三角形OAB面积T的 $ \\frac{4}{3} $，即

$ S = \\frac{4}{3} T $

用现代的坐标法，OM为x轴，O处的切线为y轴，抛物线的方程式为 $ y^{2} = cx $，OM = a，AB的极点N为(-a, 0)，即O为NM的中点，弦AB与两端的切线形成的三角形NAB的面积是OAB的两倍

![img](../img/ancient_integral_method.png)

同样的关系对弦OA、OB也成立，上图 $ O_ {1}M_ {1} = \\frac{1}{2} N_ {1}M_ {1} = \\frac{1}{4} OM $。则 $ \\bigtriangleup O O^{\\prime}_ {1}B = \\frac{1}{4} \\bigtriangleup OBM $。现在 $ \\bigtriangleup OO_ {1}A, \\bigtriangleup OO^{\\prime}_ {1}B $的面积的和为 $ T_ {1} $

$ T_ {1} = \\frac{1}{4} T $

同样的弦 $ O_ {1}A, OO_ {1}, OO^{\\prime}_ {1}, O^{\\prime}_ {1}B $为底做同样的三角形，这样的面积的和 $ T_ {2} $

$ T_ {2} = \\frac{1}{4} T_ {1} = \\frac{1}{4^{2}} T $

继续这样的操作，可做出 $ T, T_ {1}, T_ {2}, \\ldots $，这样的面积统计得

$ S = T + \\frac{T}{4} + \\frac{T}{4^{2}} + \\cdots = T(1 + \\frac{1}{4} + \\frac{1}{4^{2}} + \\cdots) = \\frac{4}{3} T $

由于

$ T + T_ {1} + \\cdots + T_ {n-1} + T_ {n} < S < T + T_ {1} + \\cdots + T_ {n-1} + 2T_ {n} $

$ T(1 + \\frac{1}{4} + \\cdots + \\frac{1}{4^{n}}) < S < T(1 + \\frac{1}{4} + \\cdots + \\frac{1}{4^{n}} + \\frac{1}{4^{n}}) $

$ \\frac{4}{3}T(1 - \\frac{1}{4^{n+1}}) < S < \\frac{4}{3}T(1 - \\frac{1}{4^{n+1}}) + \\frac{T}{4^{n}} $

$ -\\frac{1}{3} \\cdot \\frac{T}{4^{n}} < S - \\frac{4}{3} T < \\frac{2}{3} \\cdot \\frac{T}{4^{n}} $

由于n任意，则S为 $ \\frac{4}{3} T $

这样的精确理论是希腊数学的特征之一，但在17、18世纪的近代早期数学，不得不去那里，甚至在19世纪中叶，它也被重建了。上面的阿基米德考察法在解析概论上很重要，所以让我详细说明一下。上面公式可得

$ \| S - \\frac{4}{3} T \| < \\frac{2T}{3} \\cdot \\frac{1}{4^{n}} $

这样 $ \| S - \\frac{4}{3} T \| = 0 $，从而 $ S = \\frac{4}{3} T $，这样S是T的定数，n是任意自然数。现在左边的定数写成 $ \\epsilon $，右边定数 $ \\frac{2}{3} T $用a表示，$ \\epsilon \\ge 0, a > 0, 4^{n} > n $，则

$ \\epsilon < \\frac{a}{n} $

这里 $ \\epsilon = 0 $的话，它基于以下原理

$ \\epsilon, a $为正数，$ n \\epsilon > a $成立的自然数n存在。如果我们赞同这个原则，我们从 $ \\epsilon > 0 $则有这样的n

$ \\epsilon < \\frac{a}{n}, \\text{ 从而} n \\epsilon < a $

这与阿基米德原则矛盾，则 $ \\epsilon > 0 $的假设不成立，然而 $ \\epsilon \\ge 0 $，则 $ \\epsilon = 0 $

阿基米德的原则包含在实数的连续性中，如果阿基米德原则不成立，则所有的自然数 $ n \\le \\frac{a}{\\epsilon} $。即所有的自然数的集合有界，从而这样的集合的上限为s，从而有自然数 $ s - 1 < n \\le s $，从而s < n + 1，n + 1也是自然数，这样矛盾，则不得不承认阿基米德原则
