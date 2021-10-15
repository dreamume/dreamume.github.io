---
layout:     post
title:      "A Course in Algebra(Chapter 3) by Vinberg"
subtitle:   "Elements of Polynomial Algebra"
thumbnail-img: ""
date:       2021-01-23 08:00
author:     "dreamume"
tags: 		[algebra]
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

1.  [Fundamental Theorem of Algebra of Complex Numbers](#org9669ceb)
2.  [Factorization in Euclidean Domains](#org8222f14)
3.  [对称多项式](#org250fd7e)

polynomial的和和乘积及polynomial和数的乘积依然是polynomial，这意味着polynomials在一个实变量的所有函数上的代数形成了一个子代数。该子代数被称为polynomial在R上的代数并记为R[x]


<a id="org9669ceb"></a>

# Fundamental Theorem of Algebra of Complex Numbers

**引理 3.31（D'Alembert's Lemma）** 设 $ f \\in C[z] $为正度数的多项式且 $ f(z_ {0}) \\ne 0 $，则在任意的 $ z_ {0} $邻居关系中，存在z使得 $ \| f(z) \| < \| f(z_ {0}) \| $

证明：表达f为一个 $ z - z_ {0} $的多项式且除以 $ f(z_ {0}) $，一些参数可能为0，一般地我们有

$ \\begin{equation} \\frac{f(z)}{f(z_ {0})} = 1 + c_ {p} (z - z_ {0})^{p} + c_ {p+1}(z - z_ {0})^{p+1} + \\cdots + c_ {n}(z - z_ {0})^{n} \\qquad (c_ {p} \\ne 0) \\end{equation} $

我们需要证明存在一个z使得

$ \\begin{equation} \| \\frac{f(z)}{f(z_ {0})} \| < 1 \\end{equation} $

证明的想法是我们选择z非常靠近 $ z_ {0} $，不管是否不等式，现在只依赖之前等式的头两项

让我们看这样的z形式 $ z = z_ {0} + tz_ {1}, t \\in (0, 1) 且 z_ {1} $是一个复数满足条件 $ c_ {p}z_ {1}^{p} = -1 $

我们现在有

$ \\begin{equation} \\frac{f(z)}{f(z_ {0})} = 1 - t^{p} + t^{p+1} \\varphi(t) \\end{equation} $

$ \\varphi $是一个n - p - 1次方的（复数系数）的多项式。如果C是 $ \\varphi $系数的最大绝对值，则

$ \\begin{equation} \| \\varphi(t) \| \\le A = (n - p)C \\end{equation} $

因此

$ \\begin{equation} \| \\frac{f(z)}{f(z_ {0})} \| \\le 1 - t^{p} + At^{p+1} = 1 - t^{p}(1 - At) < 1 \\end{equation} $

对 $ t < \\frac{1}{A} $


<a id="org8222f14"></a>

# Factorization in Euclidean Domains

**定义** 一个带单位元的交换结合环和非零除数被称为一个integral domain

**定义** 设A为一个integral domain而不是一个域，我们称A为Euclidean如果存在一个函数

$ \\begin{equation} N: A \\ \\{ 0 \\} \\to Z_ {+} \\end{equation} $

（称为一个norm）满足如下条件：

(i) $ N(ab) \\ge N(a) $且等式成立当且仅当b可逆

(ii) 对任意 $ a, b \\in A, b \\ne 0 $，存在 $ q,r \\in A $使得a = qb + r且要么r = 0要么N(r) < N(b)


<a id="org250fd7e"></a>

# 对称多项式

**定义** 一个多项式 $ f \\in K[x_ {1}, x_ {2}, \\ldots, x_ {n}] $被称为对称的如果它对变量任意重排结果一致

**例子** 如下对称多项式被称为基本对称多项式

$ \\sigma_ {1} = x_ {1} + x_ {2} + \\cdots + x_ {n} $

$ \\sigma_ {2} = x_ {1}x_ {2} + x_ {1}x_ {3} + \\cdots + x_ {n-1}x_ {n} $

$ \\ldots \\ldots \\ldots \\ldots \\ldots \\ldots \\ldots \\ldots $

$ \\sigma_ {k} = \\sum_ {i_ {1} < i_ {2} < \\cdots < i_ {k}}x_ {i_ {1}}x_ {i_ {2}} \\cdots x_ {i_ {k}} $

$ \\ldots \\ldots \\ldots \\ldots \\ldots \\ldots \\ldots \\ldots $

$ \\sigma_ {n} = x_ {1}x_ {2} \\cdots x_ {n} $
