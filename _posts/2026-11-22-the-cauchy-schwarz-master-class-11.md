---
layout:     post
title:      "The Cauchy-Schwarz master class(Chapter 11) by Steele"
subtitle:   "Hardy's Inequality and the Flop"
thumbnail-img: ""
date:       2026-11-22 16:27
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



Hardy's Inequality: 每个 $ f: (0, T) \\to \\mathbb{R} $ 的积分函数满足不等式：

$ \\int^{T}_ {0} \\{ \\frac{1}{x} \\int^{x}_ {0} f(u)du \\}^{2} dx \\le 4 \\int^{T}_ {0} f^{2}(x) dx $
