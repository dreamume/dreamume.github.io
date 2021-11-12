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
