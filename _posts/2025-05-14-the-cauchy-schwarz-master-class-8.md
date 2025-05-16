---
layout:     post
title:      "The Cauchy-Schwarz master class(Chapter 8) by Steele"
subtitle:   "The Ladder of Power Means"
thumbnail-img: ""
date:       2025-05-14 19:00
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

1.  [The Geometric Mean as a Limit](#orgcc3bd4f)
2.  [Power Mean Bound for the Geometric Mean](#org9538d8a)
3.  [Power Mean Inequality](#orgff37b2c)


<a id="orgcc3bd4f"></a>

# The Geometric Mean as a Limit

对非负实数 $ x_ {k}, k = 1, 2, \\ldots, n $，和非负重量值 $ p_ {k}, k = 1, 2, \\ldots, n $ 且 $ p_ {1} + p_ {2} + \\cdots + p_ {n} = 1 $，其有极限

$ \\lim_ {t \\to 0} \\{ \\sum^{n}_ {k=1}p_ {k}x^{t}_ {k} \\}^{\\frac{1}{t}} = \\prod^{n}_ {k=1}x^{p_ {k}}_ {k} $


<a id="org9538d8a"></a>

# Power Mean Bound for the Geometric Mean

对任意非负重量值 $ p_ {k}, k = 1, 2, \\ldots, n $ 且 $ p_ {1} + p_ {2} + \\cdots + p_ {n} = 1 $ 且对任意非负实数 $ x_ {k}, k = 1, 2, \\ldots, n $，有边界

$ \\prod^{n}_ {k=1}x^{p_ {k}}_ {k} \\le \\{ \\sum^{n}_ {k=1}p_ {k}x^{t}_ {k} \\}^{\\frac{1}{t}} \\quad \\forall t > 0 $


<a id="orgff37b2c"></a>

# Power Mean Inequality

正重量值 $ p_ {k}, k = 1, 2, \\ldots, n $ 有 $ p_ {1} + p_ {2} + \\cdots + p_ {n} = 1 $ 且对非负实数 $ x_ {k}, k = 1, 2, \\ldots, n $，映射 $ t \\mapsto M_ {t} $ 在 $ \\mathbb{R} $ 上是非减函数。则对 $ - \\infty < s < t < \\infty $ 有

$ \\{ \\sum^{n}_ {k=1}p_ {k}x^{s}_ {k} \\}^{\\frac{1}{s}} \\le \\{ \\sum^{n}_ {k=1}p_ {k}x^{t}_ {k} \\}^{\\frac{1}{t}} $

当且仅当 $ x_ {1} = x_ {2} = \\cdots = x_ {n} $ 时等式才成立
