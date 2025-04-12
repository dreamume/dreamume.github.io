---
layout:     post
title:      "The Cauchy-Schwarz master class(Chapter 5) by Steele"
subtitle:   "Consequences of Order"
thumbnail-img: ""
date:       2025-04-10 19:45
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

1.  [Chebyshev's Order Inequality](#org7b05037)
2.  [The Rearrangement Inequality](#orgae7df62)
3.  [Nonlinear Rearrangement Inequality](#org4763c78)

对所有非负实数 $ a_ {k}, b_ {k}, k = 1,2, \\ldots, n, 0 < m \\le \\frac{a_ {k}}{b_ {k}} \\le M < \\infty $，我们有如下边界

$ \\left( \\sum^{n}_ {k=1} a^{2}_ {k} \\right)^{\\frac{1}{2}} \\left( \\sum^{n}_ {k=1} b^{2}_ {k} \\right)^{\\frac{1}{2}} \\le \\frac{A}{G} \\sum^{n}_ {k=1}a_ {k}b_ {k} $

其中 $ A = \\frac{(m+M)}{2}, G = \\sqrt{mM} $


<a id="org7b05037"></a>

# Chebyshev's Order Inequality

假设 $ f : \\mathbb{R} \\to \\mathbb{R}, g: \\mathbb{R} \\to \\mathbb{R} $ 为非递减且假设 $ p_ {j} \\ge 0, j = 1,2, \\ldots, n $，且满足 $ p_ {1} + p_ {2} + \\cdots + p_ {n} = 1 $。则对于任意非递减序列 $ x_ {1} \\le x_ {2} \\le \\cdots \\le x_ {n} $，有不等式

$ \\{ \\sum^{n}_ {k=1}f(x_ {k})p_ {k} \\}\\{ \\sum^{n}_ {k=1}g(x_ {k})p_ {k} \\} \\le \\sum^{n}_ {k=1}f(x_ {k})g(x_ {k})p_ {k} $

该式子用概率论语言来说，则如果 X 是一个随机变量其有 $ P(X = x_ {k}) = p_ {k}, k = 1,2,\\ldots,n $，则其有关期望的不等式如下：

$ E[f(X)]E[g(X)] \\le E[f(X)g(X)] $


<a id="orgae7df62"></a>

# The Rearrangement Inequality

对每个有序实数列对 $ - \\infty < a_ {1} \\le a_ {2} \\le \\cdots \\le a_ {n} < \\infty, - \\infty < b_ {1} \\le b_ {2} \\le \\cdots \\le b_ {n} \\le \\infty $

且对每个排列 $ \\sigma: [n] \\to [n] $，有

$ \\sum^{n}_ {k=1}a_ {k}b_ {n-k+1} \\le \\sum^{n}_ {k=1}a_ {k}b_ {\\sigma(k)} \\le \\sum^{n}_ {k=1}a_ {k}b_ {k} $


<a id="org4763c78"></a>

# Nonlinear Rearrangement Inequality

设 $ f_ {1}, f_ {2}, \\ldots, f_ {n} $ 是从区间 I 到 $ \\mathbb{R} $ 的函数，有 $ f_ {k+1}(x) - f_ {k}(x) , 1 \\le k \\le n $ 是非递减的，设 $ b_ {1} \\le b_ {2} \\le \\cdots \\le b_ {n} $ 为区间 I 中一个有序数列，则对每个排列 $ \\sigma: [n] \\to [n] $，有如下边界

$ \\sum^{n}_ {k=1}f_ {k}(b_ {n-k+1}) \\le \\sum^{n}_ {k=1}f_ {k}(b_ {\\sigma(k)}) \\le \\sum^{n}_ {k=1}f_ {k}(b_ {k}) $

