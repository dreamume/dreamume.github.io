---
layout:     post
title:      "The Cauchy-Schwarz master class(Chapter 9) by Steele"
subtitle:   "Holder's Inequality "
thumbnail-img: ""
date:       2025-06-29 11:00
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



对所有非负数 $ a_ {k}, b_ {k}, k = 1, 2, \\ldots, n $，有边界

$ \\sum^{n}_ {k=1}a_ {k}b_ {k} \\le \\left( \\sum^{n}_ {k=1}a^{p}_ {k}\\right)^{\\frac{1}{p} \\left( \\sum^{n}_ {k=1}b^{q}_ {k}\\right)^{\\frac{1}{q} $

其中 p > 1 且 q > 1 且满足关系

$ \\frac{1}{p} + \\frac{1}{q} = 1 $

且当存在一个常量 $ \\lambda \\in \\mathbb{R} $ 使得

$ \\lambda a^{\\frac{1}{p}}_ {k} = b^{\\frac{1}{q}}_ {k}, \\forall 1 \\le k \\le n $ 

时不等式的等号成立
