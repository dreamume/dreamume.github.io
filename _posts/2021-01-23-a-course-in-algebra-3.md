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

**问题** 多项式 $ s_ {2} = x^{2}_ {1} + x^{2}_ {2} + \\cdots + x^{2}_ {n} $是对称的，则

$ s_ {2} = \\sigma^{2}_ {1} - 2 \\sigma_ {2} $

这样，代数等式 $ x^{n} + a_ {1}x^{n-1} + a_ {2}x^{n-2} + \\cdots + a_ {n-1}x + a_ {n} = 0 $的根的平方的和为 $ a^{2}_ {1} - 2a_ {2} $

明显地，对称多项式的和和乘积也是也是对称多项式。即对称多项式形成所有多项式代数的一个子代数

因此，如果 $ F \\in K[X_ {1}, X_ {2}, \\cdots, X_ {m}] $是一个m个变量的多项式且 $ f_ {1}, f_ {2}, \\ldots, f_ {m} \\in K[x_ {1}, x_ {2}, \\ldots, x_ {m}] $为对称多项式，则 $ F(f_ {1}, f_ {2}, \\ldots, f_ {m}) $是变量 $ x_ {1}, x_ {2}, \\ldots, x_ {n} $的对称多项式。自然会问是否存在对错多项式 $ f_ {1}, f_ {2}, \\ldots, f_ {m} $使得任意对称多项式可通过上述表达。它们是存在的，基本对称多项式 $ \\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n} $即是

**定理** 任意对称多项式可唯一的表达为基本对称多项式的多项式

**引理** 设 $ u = ax^{k_ {1}}_ {1} x^{k_ {2}}_ {2} \\cdots x^{k_ {n}}_ {n} $为一个对称多项式f的leading monomial，则

$ k_ {1} \\ge k_ {2} \\ge \\cdots \\ge k_ {n} $

**引理** 对任意mononmial $ u = x^{k_ {1}}_ {1} x^{k_ {2}}_ {2} \\cdots x^{k_ {n}}_ {n} $满足上式，则存在非负整数 $ l_ {1}, l_ {2}, \\ldots, l_ {n} $使得对称多项式乘积 $ \\sigma^{l_ {1}}_ {1} \\sigma^{l_ {2}}_ {2} \\cdots \\sigma^{l_ {n}}_ {n} $的leading monomial为u。该条件唯一决定数 $ l_ {1}, l_ {2}, \\ldots, l_ {n} $

**证明** $ \\sigma_ {k} $的leading monomial为 $ x_ {1}x_ {2} \\cdots x_ {k} $，通过之前的命题，$ \\sigma^{l_ {1}}_ {1} \\sigma^{l_ {2}}_ {2} \\cdots \\sigma^{l_ {n}}_ {n} $的leading mononmial为

$ x^{l_ {1}}_ {1} (x_ {1}x_ {2})^{l_ {2}} \\cdots (x_ {1}x_ {2}\\cdots x_ {n})^{l_ {n}} = x^{l_ {1} + l_ {2} + \\cdots + l_ {n}}_ {1} + x^{l_ {2} + \\cdots + l_ {n}}_ {2} \\cdots x^{l_ {n}}_ {n} $

设它等于monomial u，我们获得如下线性等式系统

$ \\left\\{\\begin{array}{r}l_{1}+l_{2}+\\cdots+l_{n}=k_{1} \\\\ l_{2}+\\cdots+l_{n}=k_{2} \\\\ \\cdots \\ldots \\ldots \\ldots \\\\ l_{n}=k_{n}\\end{array}\\right. $

则该系统有唯一的解

$ l_ {i} = k_ {i} - k_ {i+1}, \\qquad i = 1,2,\\ldots,n-1 \\qquad l_ {n} = k_ {n} $
