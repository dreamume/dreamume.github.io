---
layout:     post
title:      "The Cauchy-Schwarz master class(Chapter 2) by Steele"
subtitle:   "Cauchy's Second Inequality: The AM-GM Bound"
thumbnail-img: ""
date:       2020-11-26 19:00
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



对非负实数 $ a_ {1}, a_ {2}, \\ldots, a_ {n} $ 和每个正实数序列 $ p_ {1}, p_ {2}, \\ldots, p_ {n} $，该序列和为1，有

$ \\begin{equation} a_ {1}^{p_ {1}} a_ {2}^{p_ {2}} \\ldots a_ {n}^{p_ {n}} \\leq p_ {1}a_ {1} + p_ {2}a_ {2} + \\cdots + p_ {n}a_ {n} \\end{equation} $

证明：我们利用公式 $ x \\leq e^{x-1} \\qquad for \\, all \\, x \\in R $，有

$ \\begin{equation} a_ {k} \\leq e^{a_ {k} - 1} \\quad and \\quad a_ {k}^{p_ {k}} \\leq e^{p_ {k}a_ {k} - p_ {k}} \\end{equation} $

则有 $ a_ {1}^{p_ {1}} a_ {2}^{p_ {2}} \\ldots a_ {n}^{p_ {n}} = exp\\left(\\{\\sum_ {k=1}^{n}p_ {k}a_ {k} \\} - 1 \\right) $

然后我们考虑引入新变量 $ \\alpha_ {k}, k = 1,2,\\ldots, n $，使得

$ \\begin{equation} \\alpha_ {k} = \\frac{a_ {k}}{A} \\qquad where \\, A = p_ {1}a_ {1} + p_ {2}a_ {2} + \\cdots + p_ {n}a_ {n} \\end{equation} $

然后我们得到 $ \\left(\\frac{a_ {1}}{A}\\right)^{p_ {1}} \\left(\\frac{a_ {2}}{A}\\right)^{p_ {2}} \\cdots \\left(\\frac{a_ {n}}{A}\\right)^{p_ {n}} \\leq exp\\left(\\{\\sum_ {k=1}^{n}p_ {k} \\frac{a_ {k}}{A} \\} - 1\\right) = 1 $

则得证。

