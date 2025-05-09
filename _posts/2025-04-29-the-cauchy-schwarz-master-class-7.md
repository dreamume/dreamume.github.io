---
layout:     post
title:      "The Cauchy-Schwarz master class(Chapter 7) by Steele"
subtitle:   "Integral Intermezzo"
thumbnail-img: ""
date:       2025-04-29 23:00
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

1.  [A Continuum of Compromise](#orgbbe10cf)
2.  [Doing Better Than Schwarz](#orge2dd950)
3.  [Jensen's Inequality: An Integral Version](#orgf45d7b4)
4.  [A Centered Version of Schwarz's Inequality](#orgd29b684)


<a id="orgbbe10cf"></a>

# A Continuum of Compromise

对一个积分 $ f: \\mathbb{R} \\to \\mathbb{R} $，有边界

$ \\int^{\\infty}_ {-\\infty} \|f(x)\| dx \\le 8^{\\frac{1}{2}} \\left(\\int^{\\infty}_ {- \\infty} \| xf(x) \|^{2} dx\\right)^{\\frac{1}{4}} \\left(\\int^{\\infty}_ {- \\infty} \| f(x) \|^{2} dx\\right)^{\\frac{1}{4}} $


<a id="orge2dd950"></a>

# Doing Better Than Schwarz

如果 $ f: [0, \\infty) \\to [0, \\infty) $ 是一个连续非增函数，在 $ (0, \\infty) $ 上可积分，则对任何一对参数 $ 0 < \\alpha, \\beta < \\infty $，积分

$ I = \\int^{\\infty}_ {0} x^{\\alpha + \\beta} f(x) dx $

满足如下边界

$ I^{2} \\le \\{ 1 - \\left( \\frac{\\alpha - \\beta}{\\alpha + \\beta + 1} \\right)^{2} \\} \\int^{\\infty}_ {0}x^{2 \\alpha} f(x)dx \\int^{\\infty}_ {0} x^{2 \\beta} f(x)dx $


<a id="orgf45d7b4"></a>

# Jensen's Inequality: An Integral Version

对每个区间 $ I \\subset \\mathbb{R} $ 且每个凸函数 $ \\Phi : I \\to \\mathbb{R} $，有边界

$ \\Phi \\left( \\int_ {D}h(x)w(x)dx \\right) \\le \\int_ {D}\\Phi(h(x))w(x)dx $

对每个 $ h: D \\to I $ 且每个重量函数 $ w: D \\to [0, \\infty) $ 使得 $ \\int_ {D}w(x)dx = 1 $


<a id="orgd29b684"></a>

# A Centered Version of Schwarz's Inequality

如果 $ w(x) \\ge 0, \\forall x \\in \\mathbb{R} $ 且如果 w 在 $ \\mathbb{R} $ 上的积分为 1，则一个合适的可积分的重量平均函数 $ f: \\mathbb{R} \\to \\mathbb{R} $ 用公式定义如下

$ A(f) = \\int^{\\infty}_ {- \\infty}f(x)w(x)dx $ 

对函数 f 和 g，有如下边界：

$ \\{ A(fg) - A(f)A(g) \\}^{2} \\le \\{ A(f^{2}) - A^{2}(f)\\}\\{A(g^{2}) - A^{2}(g)\\} $
