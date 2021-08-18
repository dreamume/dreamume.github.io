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
