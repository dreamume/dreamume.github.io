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

1.  [Polya's Coaching and Carleman's Inequality](#org0beded2)

对非负实数 $ a_ {1}, a_ {2}, \\ldots, a_ {n} $ 和每个正实数序列 $ p_ {1}, p_ {2}, \\ldots, p_ {n} $，该序列和为1，有

$ \\begin{equation} a_ {1}^{p_ {1}} a_ {2}^{p_ {2}} \\ldots a_ {n}^{p_ {n}} \\leq p_ {1}a_ {1} + p_ {2}a_ {2} + \\cdots + p_ {n}a_ {n} \\end{equation} $

证明：我们利用公式 $ x \\leq e^{x-1} \\qquad for \\, all \\, x \\in R $，有

$ \\begin{equation} a_ {k} \\leq e^{a_ {k} - 1} \\quad and \\quad a_ {k}^{p_ {k}} \\leq e^{p_ {k}a_ {k} - p_ {k}} \\end{equation} $

则有 $ a_ {1}^{p_ {1}} a_ {2}^{p_ {2}} \\ldots a_ {n}^{p_ {n}} = exp\\left(\\{\\sum_ {k=1}^{n}p_ {k}a_ {k} \\} - 1 \\right) $

然后我们考虑引入新变量 $ \\alpha_ {k}, k = 1,2,\\ldots, n $，使得

$ \\begin{equation} \\alpha_ {k} = \\frac{a_ {k}}{A} \\qquad where \\, A = p_ {1}a_ {1} + p_ {2}a_ {2} + \\cdots + p_ {n}a_ {n} \\end{equation} $

然后我们得到 $ \\left(\\frac{a_ {1}}{A}\\right)^{p_ {1}} \\left(\\frac{a_ {2}}{A}\\right)^{p_ {2}} \\cdots \\left(\\frac{a_ {n}}{A}\\right)^{p_ {n}} \\leq exp\\left(\\{\\sum_ {k=1}^{n}p_ {k} \\frac{a_ {k}}{A} \\} - 1\\right) = 1 $

则得证。


<a id="org0beded2"></a>

# Polya's Coaching and Carleman's Inequality

**Carleman's Inequality** 对每个正实数序列 $ a_ {1}, a_ {2}, \\ldots $，有

$ \\begin(equation} \\sum_ {k=1}^{\\infty} \\left( a_ {1} a_ {2} \\cdots a_ {k} \\right)^{\\frac{1}{k}} \\leq e \\sum_ {k=1}^{\\infty}a_ {k} \\end{equation} $

证明：这里我们构造一序列因子c<sub>k</sub> ，有

$ \\begin{equation} \\begin{aligned} \\sum_ {k=1}^{\\infty}\\left(a_ {1} a_ {2} \\cdots a_ {k}\\right)^{\\frac{1}{k}} &= \\sum_ {k=1}^{\\infty}\\frac{\\left(a_ {1}c_ {1}a_ {2}c_ {2} \\codts a_ {k}c_ {k}\\right)^{\\frac{1}{k}}}{\\left(c_ {1}c_ {2} \\cdots c_ {k}\\right)^{\\frac{1}{k}}} \\\\ &\\leq \\sum_ {k=1}^{\\infty} \\sum_ {k=1}{\\infty}\\frac{a_ {1}c_ {1} + a_ {2}c_ {2} + \\cdots + a_ {k}c_ {k}}{k\\left(c_ {1}c_ {2} \\cdots c_ {k}\\right)^{\\frac{1}{k}}} \\\\ &=\\sum_ {k=1}^{\\infty}a_ {k}c_ {k}\\sum_ {j=k}^{\\infty}\\frac{1}{j\\left(c_ {1}c_ {2} \\cdots c_ {j}\\right)^{\\frac{1}{j}}} \\end{aligned} \\end{equation} $

我们可以精心选择这样的c<sub>k</sub> ，$ k = 1, 2, \\ldots $，使得其和有界

$ \\begin{equation} s_ {k} = c_ {k} \\sum_ {j=k}^{\\infty}\\frac{1}{j\\left(c_ {1} c_ {2} \\cdots c_ {j}\\right)^{\\frac{1}{j}}} \\qquad k = 1, 2, \\ldots \\end{equation} $

于是我们取这样的c<sub>k</sub> ，使得

$ \\begin{equation} \\left( c_ {1} c_ {2} \\cdots c_ {j}\\right)^{\\frac{1}{j}} = j + 1 \\qquad for \\, j = 1, 2, \\ldots \\end{equation} $

这样我们有

$ \\begin{equation} s_ {k} = c_ {k} \\sum_ {j=k}^{\\infty}\\frac{1}{j \\left(c_ {1}c_ {2} \\codts c_ {j}\\right)^{\\fac{1}{j}}} = c_ {k} \\sm_ {j=k}^{\\infty}\\frac{1}{j\\left(j + 1\\right)} = \\frac{c_ {k}}{k} \\end{equation} $

通过如下等式：

$ \\begin{equation} c_ {1} c_ {2} \\cdots c_ {j-1} = j^{j-1} \\quad and \\quad c_ {1} c_ {2} \\cdots c_ {j} = \\left(j+1\\right)^{j} \\end{equation} $

我们可以推出：

$ \\begin{equation} c_ {j} = \\frac{\\left(j+1\\right)^{j}}{j^{j-1}} = j \\left(1 + \\frac{1}{j}\\right)^{j} \\end{equation} $

这样我们就得到：

$ \\begin{equation} \\sum_ {k=1}^{\\infty}\\left(a_ {1} a_ {2} \\cdots a_ {k}\\right)^{\\frac{1}{k}} \\leq \\sum_ {k=1}^{\\infty}\\left(1 + \\frac{1}{k}\\right)^{k} a_ {k} \\leq e \\sum_ {k=1}^{\\infty}a_ {k} \\end{equation} $
