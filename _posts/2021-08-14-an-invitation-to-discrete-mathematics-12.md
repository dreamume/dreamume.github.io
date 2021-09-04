---
layout:     post
title:      "An invitation to discrete mathematics(Chapter 12) by Matousek"
subtitle:   "Generating functions"
thumbnail-img: ""
date:       2021-08-14 17:00
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

1.  [多项式的组合应用](#orga50c1a3)
    1.  [例子](#org87a1fc9)
    2.  [命题](#org60a5acb)
    3.  [命题](#org7d40c22)
2.  [Fibonacci数和黄金分割](#org706c12a)
    1.  [一些递归的总结](#orge6e4b5a)

本章我们将呈现一个有用的计算技术。基本思想是考虑一个实数的无穷序列和它的某个连续函数，这被称为序列的生成函数。序列的问题可通过计算函数来解决


<a id="orga50c1a3"></a>

# 多项式的组合应用

我们如何计算多项式 $ p(x) = x + x^{2} + x^{3} + x^{4} $且 $ q(x) = x + x^{3} + x^{4} $。这里有一个简单的规则：用q(x)的每一项乘以p(x)的每一项，并把乘积相加。这样我们得到 $ p(x)q(x) = x^{8} + 2x^{7} + 2x^{6} + 3x^{5} + 2x^{4} + x^{3} + x^{2} $

我们现在问一个不同的问题。我们取某一项，比如 $ x^{5} $，我们想要知道它在p(x)q(x)中的系数，而不计算整个乘积。我们可选其一中小于等于5的项跟另一个中适合的项来得到系数

**一个组合平均的二进制定理** 二进制定理断言：

$ (1 + x)^{n} = {n \\choose 0} + {n \\choose 1}x + {n \\choose 2}x^{2} + \\cdots + {n \\choose n}x^{n} $


<a id="org87a1fc9"></a>

## 例子

对所有 $ n \\ge 1 $，我们有

$ \\sum^{n}_ {k = 0}k {n \\choose k} = n 2^{n-1} $

**证明** 很简单，从上面定理两边求导即得

**第3章定理的另一个证明** 我们想要证明

$ \\sum^{n}_ {i=0} {n \\choose 2}^{2} = {2n \\choose n} $

考虑等式

$ (1+x)^{n} (1+x)^{n} = (1+x)^{2n} $

右边 $ x^{n} $的系数是 $ {2n \\choose n} $，左边我们可根据二进制定理扩展 $ (1+x)^{n} $，则得到

$ \\sum^{n}_ {i=0} {n \\choose i}{n \\choose n - i} = {2n \\choose n} $

即得证


<a id="org60a5acb"></a>

## 命题

对组合应用程序，需要注意到对r为负整数，二项式系数 $ {r \\choose k}$ 可表达为 $ {r \\choose k} = (-1)^{k}{-r+k-1 \\choose k} = (-1)^{k} {-r+k-1 \\choose -r-1} $。因此对1 - x的负整数次方，我们有

$ \\frac{1}{(1-x)^{n}} = {n-1 \\choose n-1} + {n \\choose n - 1}x + {n + 1 \\choose n - 1}x^{2} + \\cdots + {n+k-1 \\choose n-1}x^{k} + \\cdots $

注意等式 $ \\frac{1}{1-x} = 1 + x + x^{2} + \\cdots $是n = 1时的特殊形式


<a id="org7d40c22"></a>

## 命题

对任意实数r和任意非负整数k，我们定义二项式系数 $ {r \\choose k} $为公式：

$ {r \\choose k} = \\frac{r(r-1)(r-2)\\cdots (r - k + 1)}{k!} $

（特别地，我们设 $ {r \\choose 0} $为1）。则函数 $ (1+x)^{r} $的生成函数的序列为 $ ({r \\choose 0}, {r \\choose 1}, {r \\choose 2}, \\ldots) $。系列 $ {r \\choose 0} + {r \\choose 1} x + {r \\choose 2} x^{2} + \\cdots $对所有 $ \| x \| < 1 $总是收敛


<a id="org706c12a"></a>

# Fibonacci数和黄金分割


<a id="orge6e4b5a"></a>

## 一些递归的总结

我们可找到一个系列 $ (y_ {0}, y_ {1}, y_ {2}, \\ldots) $的一般化形式满足等式

$ y_ {n+k} = a_ {k-1}y_ {n+k-1} + a_ {k-2}y_ {n+k-2} + \\cdots + a_ {1}y_ {n+1} + a_ {0}y_ {n} $

对所有 $ n = 0, 1, 2, \\ldots $，k是一个自然数且 $ a_ {0}, a_ {1}, \\ldots, a_ {k-1} $为实（或复）数。例如，对Fabonacci数我们将设置 $ k = 2, a_ {0} = a_ {1} = 1 $。让我们记所有系列 $ (y_ {0}, y_ {1}, y_ {2}, \\ldots) $的集合为 $ \\mathcal{Y} $满足上述等式（这样 $ \\mathcal{Y} $依赖于k和 $ a_ {0}, a_ {1}, \\ldots, a_ {k-1} $）。首先我们看一下术语

Eq是一个k度带常量系数的同构线性递归

-   一个递归或递归关系作为一个一般化记号表示解释一个系列的第n项和其前面几项的一个关系（通常是一个公式）
-   同构出现在名字中因为 $ (y_ {0}, y_ {1}, y_ {2}, \\ldots) \\in \\mathcal{Y} $则 $ (\\alpha y_ {0}, \\alpha y_ {1}, \\alpha y_ {2}, \\ldots) \\in \\mathcal{Y}, \\alpha $为任意实数。（在数学上，同构通常表示常量扩展）。另一方面，一个非同构递归的例子是 $ y_ {n+1} = y_ {n} + 1 $
- 线性表示 $ y_ {j} $的值总是出现在递归的第一次方且不是乘在一起。一个非线性递归的例子：$ y_ {n+2} = y_ {n+1}y_ {n} $
-   最后，常量系数表示 $ a_ {0}, a_ {1}, \\ldots, a_ {k-1} $为与n独立的固定数。也可以考虑一个递归如 $ y_ {n+1} = (n-1)y_ {n} $，系数是n的函数
