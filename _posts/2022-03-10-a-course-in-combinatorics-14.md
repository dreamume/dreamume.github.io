---
layout:     post
title:      "A Course in Combinatorics(Chapter 14) by J. H. van Lint"
subtitle:   "Recursions and generating functions"
thumbnail-img: ""
date:       2022-03-10 21:00
author:     "dreamume"
tags: 		[discrete math]
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



许多组合统计问题带一个有参数n的$ a_ {n} $的解决方案，可被解决为找到一个 $ a_ {n} $的递归关系且然后解决该递归。有时候这通过引入一个普通生成函数

$ f(x) := \\sum_ {n \\ge 0}a_ {n}x^{n} $

或一个指数生成函数

$ f(x) := \\sum_ {n \\ge 0}a _{n} \\frac{x^{n}}{n!} $

且使用递归来找到一个等式或一个f(x)的导函数，且解决该等式。我们将展示一些技巧

**例子 14.1** 作为一个介绍，考虑例子10.1。设 $ \\pi $为一个derangement $ \\{1,2,\\ldots,n+1\\} $。对 $ \\pi(n + 1) $有n个选择。如果 $ \\pi(n + 1) = i $且 $ \\pi(i) = n + 1 $ 则 $ \\pi $也是也是集合 $ \\{1,2,\\ldots, n\\} \\backslash \\{i\\} $的一个dearrangement。如果 $ \\pi(n + 1) = i $且 $ \\pi(i) \\ne n + 1 = \\pi(j) $，则用i位的替代 $ \\pi(j) $得到一个集合 $ \\{1,2,\\ldots,n\\} $的dearrangement。因此

$ d_ {n+1} = n(d_ {n} + d_ {n-1}) $

这也是10.3的一个结果。设D(x)为序列 $ d_ {0} = 1, d_ {1} = 0, d_ {2}, \\ldots $的指数生成函数，我们可发现

$ (1 - x) D^{\\prime}(x) = x D(x) $

且从这我们发现 $ D(x) = e^{-x} / (1 - x) $且(10.2)

在许多情况下，我们使用生成函数只作为订阅设备，且我们的加法、乘法操作（甚至替换和求导）会做形式化地解释。它可能给出一个形式化指数系列（代数对象）的完整严谨的理论和我们在附录2中给出一个这个理论的一个简介。在多数情况下，容易验证这些操作是合理的。如果我们使用的系列是收敛的，则我们可使用所有分析中适合的知识来考虑这些系列
