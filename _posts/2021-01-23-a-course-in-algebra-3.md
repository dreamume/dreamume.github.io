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
4.  [Cubic Equations](#orgf02219b)

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

如果一个多项式

$ f = a_ {0}x^{n} + a_ {1}x^{n-1} + \\cdots + a_ {n-1}x + a_ {n} $

因式为线性项，则它可被写为

$ f = a_ {0}(x - c_ {1})(x - c_ {2}) \\cdots (x - c_ {n}) $

$ c_ {1}, c_ {2}, \\ldots, c_ {n} $为f的根。通过观察系数我们获得如下Viete公式

$ \\begin{array}{l} c_ {1}+c_ {2}+\\cdots+c_ {n}=-\\frac{a_ {1}}{a_ {0}} \\\\ c_ {1} c_ {2}+c_ {1} c_ {3}+\\cdots+c_ {n-1} c_ {n}=\\frac{a_ {2}}{a_ {0}} \\\\ \\ldots \\ldots \\ldots \\ldots \\ldots \\ldots \\ldots . . \\\\ \\sum_ {i_ {1}<i_ {2}<\\cdots<i_ {k}} c_ {i_ {1}} c_ {i_ {2}} \\cdots c_ {i_ {k}}=(-1)^{k} \\frac{a_ {k}}{a_ {0}} \\\\ \\ldots \\ldots \\ldots \\ldots \\ldots \\ldots \\ldots . \\\\ c_ {1} c_ {2} \\cdots c_ {n}=(-1)^{n} \\frac{a_ {n}}{a_ {0}}\\end{array} $


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

**标注** 等式 $ l_ {1} + l_ {2} + \\cdots + l_ {n} = k_ {1} $显示monomial $ X^{l_ {1}}_ {1} X^{l_ {2}}_ {2} \\cdots X^{l_ {n}}_ {n} $的总度数为u在 $ x_ {1} $的度数

**定理的证明** 设 $ f \\in K[x_ {1}, x_ {2}, \\ldots, x_ {n}] $ 为一个对称多项式。我们需要找到 $ F \\in K[X_ {1}, X_ {2}, \\ldots, X_ {n}] $使得

$ F(\\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n}) = f $

如果f = 0，则我们可用F = 0。否则， 设 $ u_ {1} = ax^{k_ {1}}_ {1} x^{k_ {2}}_ {2} \\cdots x^{k_ {n}}_ {n} $为f的leading monomial。根据引理，存在一个monomial $ F_ {1} \\in K[X_ {1}, X_ {2}, \\ldots, X_ {n}] $使得多项式 $ F_ {1}(\\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n}) $的leading monomial为 $ u_ {1} $。考虑对称多项式

$ f_ {1} = f - F_ {1}(\\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n}) $

如果 $ f_ {1} = 0 $，我们可用 $ F = F_ {1} $。否则，设 $ u_ {2} $为 $ f_ {1} $的leading monomial。明显地，它小于 $ u_ {1} $。存在一个monomial $ F_ {2} \\in K[X_ {1}, X_ {2}, \\ldots, X_ {n}] $使得 $ F_ {2}(\\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n}) $的leading monomial为 $ u_ {2} $。考虑对称多项式

$ f_ {2} = f_ {1} - F_ {2}(\\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n}) $

如果 $ f_ {2} = 0 $，则我们可用 $ F = F_ {1} + F_ {2} $。否则，继续以上步骤，我们获得一系列对称多项式 $ f, f_ {1}, f_ {2}, \\ldots $，其leading monomial满足如下不等式

$ u_ {1} \\succ u_ {2} \\succ \\cdots $

根据引理，任意monomial $ u_ {m} $的任意变量的指数不超过这个monomial的 $ x_ {1} $的指数，即不超过 $ k_ {1} $。因此，只存在有限多个 $ u_ {m} $中可能的变量指数的收集，且这样我们描述的算法将在某个时候停止。这意味着对某个M，$ f_ {M} = 0 $。则我们可取 $ F = F_ {1} + F_ {2} + \\cdots + F_ {M} $

剩下是证明多项式F是唯一的。假设F和G是多项式使得

$ F(\\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n}) = G(\\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n}) $

考虑H = F - G，则

$ H(\\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n}) = 0 $

我们需要证明H = 0。假设不是这样，设 $ H_ {1}, H_ {2}, \\ldots, H_ {s} $为H的所有非零项。记 $ \\omega_ {i}, i = 1, 2, \\ldots, s $为多项式的leading monomial

$ H_ {i}(\\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n}) \\in K[x_ {1}, x_ {2}, \\ldots, x_ {n}] $

通过引理，monomial $ \\omega_ {1}, \\omega_ {2}, \\ldots, \\omega_ {s} $不会互相成比例。考虑它们中最大的，假设是 $ \\omega_ {1} $。通过构建，$ \\omega_ {1} $ 比所有 $ H_ {1}(\\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n}) $的其他monomial和多项式 $ H_ {i}(\\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n}), i = 2, \\ldots, s $的所有monomial都大。这样

$ H_ {1}(\\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n}) + H_ {2}(\\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n}) + \\cdots + H_ {s}(\\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n}) \\\\ = H(\\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n}) $

monomial $ \\omega_ {1} $不会出现。因此，该和非零，这和我们的假设矛盾

**例子** 我们表达多项式

$ f = s_ {3} = x^{3}_ {1} + x^{3}_ {2} + \\cdot + x^{3}_ {n} $

作为$ \\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n} $的多项式。我们的计算收集在如下表格中

$ \\begin{array}{\|c\|c\|c\|c\|}\\hline m & u_ {m} & F_ {m}\\left(\\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n}\\right) & f_ {m} \\\\ \\hline 1 & x_ {1}^{3} & \\sigma_ {1}^{3}=\\sum_ {i} x_ {i}^{3}+3 \\sum_ {i \\neq j} x_ {i}^{2} x_ {j} & -3 \\sum_ {i \\neq j} x_ {i}^{2} x_ {j} \\\\ & & +6 \\sum_ {i<j<k} x_ {i} x_ {j} x_ {k} & -6 \\sum_ {i<j<k} x_ {i} x_ {j} x_ {k} \\\\ \\hline 2 & -3 x_ {1}^{2} x_ {2} & -3 \\sigma_ {1} \\sigma_ {2}=-3 \\sum_ {i \\neq j} x_ {i}^{2} x_ {j} & 3 \\sum_ {i<j<k} x_ {i} x_ {j} x_ {k} \\\\ & & -9 \\sum_ {i<j<k} x_ {i} x_ {j} x_ {k} & \\\\ \\hline 3 & 3 x_ {1} x_ {2} x_ {3} & 3 \\sigma_ {3}=3 \\sum_ {i<j<k} x_ {i} x_ {j} x_ {k} & 0 \\\\ \\hline \\end{array} $

因此

$ s_ {3} = \\sigma^{3}_ {1} - 3 \\sigma_ {1} \\sigma_ {2} + 3 \\sigma_ {3} $

设 $ f \\in K[x_ {1}, x_ {2}, \\ldots, x_ {n}] $为一个对称多项式且 $ F \\in K[X_ {1}, X_ {2}, \\ldots, X_ {n}] $为

$ f = F(\\sigma_ {1}, \\sigma_ {2}, \\ldots, \\sigma_ {n}) $

现在，设 $ c_ {1}, c_ {2}, \\ldots, c_ {n} $为如下代数等式的根：

$ a_ {0}x^{n} + a_ {1}x^{n-1} + \\cdots + a_ {n-1}x + a_ {n} = 0, \\qquad a_ {0} \\ne 0 $

则

$ f(c_ {1}, c_ {2}, \\ldots, c_ {n}) = F(-\\frac{a_ {1}}{a_ {0}}, \\frac{a_ {2}}{a_ {0}}, \\ldots, (-1)^{n} \\frac{a_ {n}}{a_ {0}}) $

*标注* 设 $ \\operatorname{deg}_ {x_ {1}} f = k $。则 $ \\operatorname{deg} F = k $。用 $ a^{k}_ {0} $乘以上式，我们获得右边度数为k的 $ a_ {0}, a_ {1}, a_ {2}, \\ldots, a_ {n} $的同构多项式

*例子* 设 $ c_ {1}, c_ {2}, c_ {3}, c_ {4} $为如下等式的根

$ x^{4} + px^{2} + qx + r = 0 $

我们将找到第三度数的等式其根为

$ d_ {1} = c_ {1}c_ {2} + c_ {3}c_ {4}, \\qquad d_ {2} = c_ {1}c_ {3} + c_ {2}c_ {4}, \\qquad d_ {3} = c_ {1}c_ {4} + c_ {2}c_ {3} $

它有形式

$ y^{3} + a_ {1}y^{2} + a_ {2}y + a_ {3} = 0 $

根据Viete公式

$ a_ {1} = -(d_ {1} + d_ {2} + d_ {3}), \\qquad a_ {2} = d_ {1}d_ {2} + d_ {1}d_ {3} + d_ {2}d_ {3}, \\qquad a_ {3} = -d_ {1}d_ {2}d_ {3} $

我们有 $ d_ {i} = h_ {i}(c_ {1}, c_ {2}, c_ {3}, c_ {4})$，则

$ h_ {1} + h_ {2} + h_ {3} = \\sigma_ {2} $

$ h_ {1}h_ {2} + h_ {1}h_ {3} + h_ {2}h_ {3} = \\sum_ {i \\ne j,k, j < k}x^{2}_ {i}x_ {j} x_ {k} = \\sigma_ {1} \\sigma_ {3} - 4 \\sigma_ {4} $

$ h_ {1}h_ {2}h_ {3} = \\sigma^{2}_ {1} \\sigma_ {4} + \\sigma^{2}_ {3} - 4 \\sigma_ {2}\\sigma_ {4} $

Viete公式给出

$ \\sigma_ {1}(c_ {1}, c_ {2}, c_ {3}, c_ {4}) = 0 $

$ \\sigma_ {2}(c_ {1}, c_ {2}, c_ {3}, c_ {4}) = p $

$ \\sigma_ {3}(c_ {1}, c_ {2}, c_ {3}, c_ {4}) = -q $

$ \\sigma_ {4}(c_ {1}, c_ {2}, c_ {3}, c_ {4}) = r $

因此

$ a_ {1} = -p, \\qquad a_ {2} = -4r, \\qquad a_ {3} = 4pr - q^{2} $

例如，我们的等式有形式

$ y^{3} - py^{2} - 4ry + (4pr - q^{2}) = 0 $


<a id="orgf02219b"></a>

# Cubic Equations

在解决一个二次方等式时，discriminant扮演了一个主要的角色。

让我们解释二次多项式$ D(\\varphi) $ discriminant的意义

$ \\varphi = a_ {0}x^{2} + a_ {1}x + a_ {2} \\in C[x] $

设$ c_ {1}, c_ {2} $为它的根。则

$ D(\\varphi) = a^{2}_ {1} - 4a_ {0}a_ {2} = a^{2}_ {0} [(\\frac{a_ {1}}{a_ {0}})^{2} - \\frac{4a_ {2}}{a_ {0}}] = a^{2}_ {0}[(c_ {1} + c_ {2})^{2} - 4c_ {1}c_ {2}] = a^{2}_ {0}(c_ {1} - c_ {2})^{2} $

$ a_ {0}, a_ {1}, a_ {2} \\in \\mathbb{R} $，这个公式解释了discriminant和根的属性的连接。有3个可能性：

(i) $ c_ {1}, c_ {2} \\in \\mathbb{R}, c_ {1} \\ne c_ {2} $；则 $ c_ {1} - c_ {2} $是非零实数且 $ D(\\varphi) > 0 $

(ii) $ c_ {1} = c_ {2} \\in \\mathbb{R} $；则 $ c_ {1} - c_ {2} = 0, D(\\varphi) = 0 $

(iii) $ c_ {1} = \\bar{c}_ {2} \\notin \\mathbb{R} $；则 $ c_ {1} - c_ {2} $是非零虚数且 $ D(\\varphi) < 0 $

更重要的是，这个公式显示如何确定任意多项式的discriminant

$ \\varphi = a_ {0}x^{n} + a_ {1}x^{n-1} + \\cdots + a_ {n-1}x + a_ {n} \\in K[x], \\qquad a_ {0} \\ne 0 $

假设首先多项式 $ \\varphi $有n个根 $ c_ {1}, c_ {2}, \\ldots, c_ {n} \\in K $。我们定义它的discriminant $ D(\\varphi) $通过公式

$ D(\\varphi) = a^{2n-2}_ {0} \\prod_ {i > j}(c_ {i} - c_ {j})^{2} $

（$ a_ {0} $的指数不重要，它将之后变得清晰为什么我们选择这个）

即，$ D(\\varphi) $是 $ a^{2n-2}_ {0} $的一个乘积且对称多项式的值

$ f = \\prod_ {i > j}(x_ {i} - x_ {j})^{2} $

用 $ \\varphi $的根计算。通过 $ \\varphi $的系数表达 $ D(\\varphi) $。因为

$ \\operatorname{deg}_ {x_ {1}}f = 2n - 2 $

该表达式将为 $ a_ {0}, a_ {1}, \\ldots, a_ {n} $的同质多项式 $ \\Delta $的度2n-2

$ D(\\varphi) = \\Delta(a_ {0}, a_ {1}, \\ldots, a_ {n}) $

为了找到 $ \\Delta $，我们不需要知道多项式 $ \\varphi $在K中确实有n个根

**标注** 因为f有整数系数，$ \\Delta $也有整数系数

**标注** 它可显示对任意度数为n的多项式 $ \\varphi \\in K[x] $，存在一个域K的扩展L，$ \\varphi $有n个根。以上描述过程对计算discriminant不依赖多项式 $ \\varphi $上的域。这样，公式对 $ D(\\varphi) $有效如果我们在L中有 $ \\varphi $的根 $ c_ {1}, c_ {2}, \\ldots, c_ {n} $

discriminant的定义清晰地意味着多项式 $ \\varphi \\in \\mathbb{C}[x] $有多重根当且仅当 $ D(\\varphi) = 0 $。这显示有多重根是一个特殊的情况：如果随机选择多项式的系数，它有多重根的概率为0

现在，让 $ \\varphi $为一个cubic多项式，有实系数。让 $ c_ {1}, c_ {2}, c_ {3} $为它的复数根，则

$ D(\\varphi) = a^{4}_ {0}(c_ {1} - c_ {2})^{2}(c_ {1} - c_ {3})^{2}(c_ {2}-c_ {3})^{2} $

有三种可能性；

(i) $ c_ {1}, c_ {2}, c_ {3} $为不同的实数；则 $ D(\\varphi) > 0 $

(ii) $ c_ {1}, c_ {2}, c_ {3} \\in \\mathbb{R}, c_ {2} = c_ {3}$；则 $ D(\\varphi) = 0 $

(iii) $ c_ {1} \\in \\mathbb{R}, c_ {2} = \\bar{c}_ {3} \\notin \\mathbb{R} $；则

$ \\begin{aligned} D(\\varphi) &= a^{4}_ {0}[(c_ {1} - c_ {2})(c_ {1} - \\bar{c}_ {2}]^{2} (c_ {2} - \\bar{c}_ {2})^{2} \\\\ &= a^{4}_ {0} \| c_ {1} - c_ {2} \|^{4} (c_ {2} - \\bar{c}_ {2})^{2} < 0 \\end{aligned} $

这样，我们得到和二次方多项式相同的结论：多项式 $ \\varphi $的所有根是实数当且仅当 $ D(\\varphi) \\ge 0 $

**练习** 设 $ \\varphi $为一个任意度数的实系数多项式，假设它没有多重复数根。证明

$ \\operatorname{sign}D(\\varphi) = (-1)^{t} $

t是 $ \\varphi $的共轭复数根的对数

我们将直接通过它的系数表达一个cubic等式的discriminant。首先，让我们做一些基本的观察简化我们的计算

任意多项式可被处理为头系数为1.这不会改变它的根。进一步，任意头系数为1的多项式

$ \\varphi = x^{n} + a_ {1}x^{n-1} + x_ {2}x^{n-2} + \\cdots + a_ {n-1}x + a_ {n} $

在零特征的域里（更一般地，域里的特征不能被n整除）可被转换为这样形式的多项式

$ \\psi = y^{n} + b_ {2}y^{n-2} + \\cdots + b_ {n-1}y + b_ {n} $

通过替换

$ x = y - \\frac{a_ {1}}{n} $

这里 $ y^{n-1} $的系数为0。这种类型的多项式被称为depressed。当n = 2时，这导致其为二次方多项式的根，当n > 2时，等式看上去更简单些

现在我们找depressed cubic多项式的discriminant

$ \\varphi = x^{3} + px + q $

使用之前的例子，我们表达对称多项式

$ f = (x_ {1} - x_ {2})^{2} (x_ {1} - x_ {3})^{2} (x_ {2} - x_ {3})^{2} $

为基本对称函数 $ \\sigma_ {1}, \\sigma_ {2}, \\sigma_ {3} $。多项式f是跟度数6同质。它的头项为 $ x^{4}_ {1}x^{2}_ {2} $。下表包含对称多项式的所有可能头项，其可发生在之前定理证明的过程中。右边列包含对应基本对称多项式的乘积：

$ \\begin{array}{\|ccc\|c\|}\\hline 4 & 2 & 0 & \\sigma_ {1}^{2} \\sigma_ {2}^{2} \\\\ 4 & 1 & 1 & \\sigma_ {1}^{3} \\sigma_ {3} \\\\ 3 & 3 & 0 & \\sigma_ {2}^{3} \\\\ 3 & 2 & 1 & \\sigma_ {1} \\sigma_ {2} \\sigma_ {3} \\\\ 2 & 2 & 2 & \\sigma_ {3}^{2} \\\\ \\hline\\end{array} $

我们看到

$ f = \\sigma^{2}_ {1} \\sigma^{2}_ {2} + a \\sigma^{3}_ {1}\\sigma_ {3} + b \\sigma^{3}_ {2} + c \\sigma_ {1}\\sigma_ {2}\\sigma_ {3} + d \\sigma^{2}_ {3} $

为计算 $ D(\\varphi) $，我们需要用如下替代：

$ \\sigma_ {1} = 0, \\qquad \\sigma_ {2} = p, \\qquad \\sigma_ {3} = -q $

因此，系数a和c不影响最后的结果且我们不需要找到它们

为找到b和d，让我们从下表的左边列赋值给变量 $ x_ {1}, x_ {2}, x_ {3} $，最右边列包含结果等式

$ \\begin{array}{\|ccc\|ccc\|c\|c\|} \\hline x_ {1} & x_ {2} & x_ {3} & \\sigma_ {1} & \\sigma_ {2} & \\sigma_ {3} & f & \\\\ \\hline 1 & -1 & 0 & 0 & -1 & 0 & 4 & -b = 4 \\\\ 2 & -1 & -1 & 0 & -3 & 2 & 0 & -27b + 4d = 0 \\\\ \\hline \\end{array} $

则，b = -4, d = -27，且

$ D(\\varphi) = -4p^{3} -27q^{2} $

**例子** 这个多项式有几个实数根

$ \\varphi = x^{3} - 0.3x^{2} - 4.3x + 3.9 $

通过替换

$ y = x - 0.1 $

我们获得depressed多项式

$ \\psi = y^{3} - 4.33y + 3.468 $

现在

$ D(\\varphi) = D(\\psi) = 4 \\cdot 4.33^{3} - 27 \\cdot 3.468^{2} = 0.0013 > 0 $

因此，多项式 $ \\varphi $有3个不同的实数根

**标注** 一个一般化cubic等式的discriminant

$ \\varphi = a_ {0}x^{3} + a_ {1}x^{2} + a_ {2}x + a_ {3} $

为

$ D(\\varphi) = a^{2}_ {1}a^{2}_ {2} - 4a^{3}_ {1}a_ {3} - 4a_ {0}a^{3}_ {2} + 18a_ {0}a_ {1}a_ {2}a_ {3} - 27 a^{2}_ {0}a^{2}_ {3} $

我们将解释如何解决一个cubic等式

假设基本域K包含一个非平凡（例如，不为1）统一的cubic根。记为 $ \\omega $。则1，$ \\omega, \\omega^{-1} $为所有统一的cubic根

$ \\omega + \\omega^{-1} = -1 $

考虑线性多项式

$ h_ {1} = x_ {1} + \\omega x_ {2} + \\omega^{-1} x_ {3}, \\qquad h_ {2} = x_ {1} + \\omega^{-1}x_ {2} + \\omega x_ {3} $

当 $ x_ {2}, x_ {3} $交换时它们交换。当 $ x_ {1}, x_ {2} $交换时，$ h_ {1} $ 变成 $ \\omega h_ {2} $且 $ h_ {2} $变成 $ \\omega^{-1} h_ {1} $。有如下多项式

$ f = h^{3}_ {1} + h^{3}_ {2}, \\qquad g = h_ {1}h_ {2} $

为对称的。我们可表达它们通过基本对称多项式

$ f = 2\\sigma^{3}_ {1} - 9\\sigma_ {1}\\sigma_ {2} + 27 \\sigma_ {3}, \\qquad g = \\sigma^{2}_ {1} - 3 \\sigma_ {2} $

现在让 $ c_ {1}, c_ {2}, c_ {3} $为多项式的根

$ d_ {1} = c_ {1} + \\omega c_ {2} + \\omega^{-1}c_ {3}, \\qquad d_ {2} = c_ {1} + \\omega^{-1}c_ {2} + \\omega c_ {3} $

以上意味着

$ d^{3}_ {1} + d^{3}_ {2} = -27q, \\qquad d_ {1}d_ {2} = -3p $

因此

$ d^{3}_ {1}d^{3}_ {2} = -27p^{3} $

因此，$ d^{3}_ {1}, d^{3}_ {2} $为如下二次多项式的根

$ x^{2} + 27qx - 27p^{3} = 0 $

通过解它，我们找到

$ d^{3}_ {1} = 27(-\\frac{q}{2} + \\sqrt{\\frac{p^{3}}{27} + \\frac{q^{2}}{4}}) $

$ d^{3}_ {2} = 27(-\\frac{q}{2} - \\sqrt{\\frac{p^{3}}{27} + \\frac{q^{2}}{4}}) $

根据之前的等式discriminant求解，得到等式

$ c_ {1} + c_ {2} + c_ {3} = 0 $

$ c_ {1} + \\omega c_ {2} + \\omega^{-1} c_ {3} = d_ {1} $

$ c_ {1} + \\omega^{-1}c_ {2} + \\omega c_ {3} = d_ {2} $

我们获得

$ c_ {1} = \\frac{1}{3}(d_ {1} + d_ {2}) $

因为根的顺序是任意选择的，该公式事实上是三个根的乘积。我们获得

$ d_ {1}d_ {2} = -3p $

因此，我们得到如下公式

$ c_ {1,2,3} = \\sqrt[3]{- \\frac{q}{2} + \\sqrt{\\frac{p^{3}}{27} + \\frac{q^{2}}{4}}} + \\sqrt[3]{- \\frac{q}{2} - \\sqrt{\\frac{p^{3}}{27} + \\frac{q^{2}}{4}}} $

称为Cardano公式
