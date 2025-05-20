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
    1.  [Some Special Means](#orgf40311f)
4.  [The Integral Analogs](#orgb05f110)


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

正重量值 $ p_ {k}, k = 1, 2, \\ldots, n $ 有 $ p_ {1} + p_ {2} + \\cdots + p_ {n} = 1 $ 且对非负实数 $ x_ {k}, k = 1, 2, \\ldots, n $，映射 $ t \\mapsto M_ {t}, M_ {t} = \\{ \\sum^{n}_ {k=1}p_ {k}x^{t}_ {k} \\}^{\\frac{1}{t}} $ 在 $ \\mathbb{R} $ 上是非减函数。则对 $ - \\infty < s < t < \\infty $ 有

$ \\{ \\sum^{n}_ {k=1}p_ {k}x^{s}_ {k} \\}^{\\frac{1}{s}} \\le \\{ \\sum^{n}_ {k=1}p_ {k}x^{t}_ {k} \\}^{\\frac{1}{t}} $

当且仅当 $ x_ {1} = x_ {2} = \\cdots = x_ {n} $ 时等式才成立


<a id="orgf40311f"></a>

## Some Special Means

当 t = -1，均值 $ M_ {-1} $ 被称为调和均值

$ M_ {-1} = M_ {-1}[x; p] = \\frac{1}{\\frac{p_ {1}}{x_ {1}} + \\frac{p_ {2}}{x_ {2}} + \\cdots + \\frac{p_ {n}}{x_ {n}}} $

特别的，我们有调和平均几何平均不等式

$ \\frac{1}{\\frac{p_ {1}}{x_ {1}} + \\frac{p_ {2}}{x_ {2}} + \\cdots + \\frac{p_ {n}}{x_ {n}}} \\le x^{p_ {1}}_ {1} x^{p_ {2}}_ {2} \\cdots x^{p_ {n}}_ {n} $

同时我们有调和平均算术平均不等式

$ \\frac{1}{\\frac{p_ {1}}{x_ {1}} + \\frac{p_ {2}}{x_ {2}} + \\cdots + \\frac{p_ {n}}{x_ {n}}} \\le p_ {1}x_ {1} p_ {2}x_ {2} \\cdots p_ {n}x_ {n} $


<a id="orgb05f110"></a>

# The Integral Analogs

设 $ D \\subset \\mathbb{R} $ 且我们考虑一个重量值函数 $ w : D \\to [0, \\infty) $ 满足

$ \\int_ {D} w(x)dx = 1 $ 且 $ w(x) > 0 \\quad \\quad \\forall x \\in D $

则对 $ f : D \\to [0, \\infty) $ 且 $ t \\in (- \\infty, 0) \\cup (0, \\infty) $ 我们用如下公式定义 f 的第 t 个中值

$ M_ {t} = M_ {t}[f; w] \\equiv \\{ \\int_ {D} f^{t}(x) w(x) dx\\}^{\\frac{1}{t}} $

同时对 $ M_ {0} $ 的特殊情况，我们定义其为

$ M_ {0}[f; w] \\equiv exp \\left( \\int_ {D} \\{ \\log{f(x)} \\} w(x)dx \\right) $

则我们有

$ M_ {s}[f; w] \\le M_ {t}[f; w] \\quad \\quad \\forall - \\infty < s < t < \\infty $
