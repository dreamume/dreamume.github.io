---
layout:     post
title:      "An invitation to discrete mathematics(Chapter 3) by Matousek"
subtitle:   "Combinatorial counting"
thumbnail-img: ""
date:       2020-11-21 19:00
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

1.  [Combinatorial counting](#org7ccbb93)
    1.  [二项式系数](#org9b21a7d)
    2.  [估计：简介](#orged53e4c)
    3.  [估计：阶乘函数](#org4911f9a)
    4.  [估计：二项式系数](#orgb7e13e8)
    5.  [Inclusion-exclusion principle](#org07e2e5c)


<a id="org7ccbb93"></a>

# Combinatorial counting


<a id="org9b21a7d"></a>

## 二项式系数

命题：

$ \\begin{equation} \\sum_ {i=0}^{n}\\left(\\begin{array}{c}n \\\\ i\\end{array}\\right)^{2}=\\left(\\begin{array}{c}2 n \\\\ n\\end{array}\\right) \\end{equation} $

证明：

该式左边可写成

$ \\begin{equation} \\sum_ {i=0}^{n}\\left(\\begin{array}{c}n \\\\ i\\end{array}\\right) \\left(\\begin{array}{c}n \\\\ n - i \\end{array}\\right) \\end{equation} $

可理解为2n个物品分成两组，每组n个物品，则按前一组取i个，后一组取n - i个，然后遍历组合即为2n个物品里取n个。

如果我们有m种物品，第i中物品有k<sub>i</sub> 个，$ k_ {1} + k_ {2} + \\ldots + k_ {m} = n $ ，则不同的组合有：

$ \\begin{equation} \\frac{n!}{k_ {1}! k_ {2}! \\ldots k_ {m}!} \\end{equation} $

该表达式通常写成：

$ \\begin{equation} \\left(\\begin{array}{c}n \\\\ k_ {1}, k_ {2}, \\ldots, k_ {m} \\end{array}\\right) \\end{equation} $

Multinomial theorem: 对任意实数 $ x_ {1}, x_ {2}, \\ldots, x_ {m} $ 和任意自然数 $ n \\geq 1 $ ，有如下等式：

$ \\begin{equation} \\left(x_ {1}+x_ {2}+\\cdots+x_ {m}\\right)^{n}=\\sum_ {k_ {1}+\\cdots+k_ {m}=n \\atop k_ {1}, \\ldots, k_ {m} \\geq 0}\\left(\\begin{array}{c}n \\\\ k_ {1}, k_ {2}, \\ldots, k_ {m}\\end{array}\\right) x_ {1}^{k_ {1}} x_ {2}^{k_ {2}} \\ldots x_ {m}^{k_ {m}} \\end{equation} $


<a id="orged53e4c"></a>

## 估计：简介

harmonic numbers:

$ \\begin{equation} H_ {n} = 1 + \\frac{1}{2} + \\frac{1}{3} + \\cdots + \\frac{1}{n} = \\sum_ {i=1}^{n}\\frac{1}{i} \\end{equation} $

为估计该值，我们把其元素分成k组，因此第k组 $ G_ {k} $ 包含 $ 2^{k-1} $ 个元素：

$ \\begin{equation} \\frac{1}{2^{k-1}}, \\frac{1}{2^{k-1} + 1}, \\frac{1}{2^{k-1} + 2}, \\cdots, \\frac{1}{2^{k} - 1} \\end{equation} $

这样该$ G_ {k} $组的和满足：

$ \\begin{equation} \\sum_ {x \\in G_ {k}}x \\leq \| G_ {k} \| max G_ {k} = 2^{k - 1} \\frac{1}{2^{k-1}} = 1 \\end{equation} $

$ \\begin{equation} \\sum_ {x \\in G_ {k}}x \\geq \| G_ {k} \| min G_ {k} > 2^{k - 1} \\frac{1}{2^{k}} = \\frac{1}{2} \\end{equation} $

因此：

$ \\begin{equation} H_ {n} = \\sum_ {i=1}^{n}\\frac{1}{i} \\leq \\sum_ {k=1}^{\\lfloor \\log_ {2} n \\rfloor + 1}1 \\leq \\log_{2} n + 1 \\end{equation} $

$ \\begin{equation} H_ {n} > \\sum_ {k=1}^{\\lfloor \\log_ {2} n \\rfloor}\\frac{1}{2} \\geq \\frac{1}{2} \\lfloor \\log_ {2} n \\rfloor \\end{equation} $


<a id="org4911f9a"></a>

## 估计：阶乘函数

为估计 $ n! $ 的大小，我们考虑，如果n为偶数，则 集合 $ \\{ 1, 2, \\ldots, n } $ 中 $ \\frac{n}{2} $ 个数最多为 $ \\frac{n}{2} $ ，且 $ \\frac{n}{2} $ 个数大于 $ \\frac{n}{2} $ 。因此，我们有

$ \\begin{equation} n ! \\geq \\prod_ {i=n / 2+1}^{n} i>\\prod_ {i=n / 2+1}^{n} \\frac{n}{2}=\\left(\\frac{n}{2}\\right)^{n / 2}=\\left(\\sqrt{\\frac{n}{2}}\\right)^{n} \\end{equation} $

$ \\begin{equation} n ! \\leq \\left( \\prod_ {i=1}^{\\frac{n}{2}} \\right) \\left( \\prod_ {i = \\frac{n}{2} + 1}^{n}n \\right) = \\frac{n^{n}}{2^{\\frac{n}{2}}} \\end{equation} $

如n为奇数，则对于 $ n \\geq 3 $ 的奇数也成立

定理：对任意 $ n \\geq 1 $ ，有

$ \\begin{equation} n^{\\frac{n}{2}} \\leq n ! \\leq \\left( \\frac{n+1}{2} \\right)^{n} \\end{equation} $

证明：

我们可以构造如下等式：

$ \\begin{equation} n ! = \\prod_ {i=1}^{n} \\sqrt{i \\left(n+1-i \\right) } \\end{equation} $

因

$ \\begin{equation} \\sqrt{i \\left(n+1-i \\right) } \\leq \\frac{i + n + 1 - i}{2} = \\frac{n+1}{2} \\end{equation} $

所以

$ \\begin{equation} n ! = \\prod_ {i=1}^{n} \\sqrt{ i \\left( n + 1 - i \\right) } \\leq \\prod_ {i=1}^{n}\\frac{n+1}{2} = \\left( \\frac{n+1}{2} \\right)^{n} \\end{equation} $

对下界，我们可以看到对所有 $ i = 1, 2, \\ldots, n, i \\left( n + 1 - i \\right) \\geq n $ ，因此有 $ n ! \\geq \\sqrt{n^{n}} = n^{\\frac{n}{2}} $

我们观察到这样一个事实，对任意实数x，有 $ 1 + x \\leq e^{x} $

定理：对任意 $ n \\geq 1 $ ，有

$ \\begin{equation} e \\left( \\frac{n}{e} \\right)^{n} \\leq n ! \\leq en \\left(\\frac{n}{e}\\right)^{n} \\end{equation} $

这里我们仅证明上界，利用归纳法，当n = 1时，可以验证不等式成立，假设n - 1也成立，我们来验证n的情况，我们有

$ \\begin{equation} n ! = n \\left(n - 1\\right) ! \\leq n e \\left(n - 1\\right) \\left( \\frac{n-1}{e}\\right)^{n-1} \\end{equation} $

我们把右边的式子转换为

$ \\begin{equation} \\left[ en \\left( \\frac{n}{e} \\right)^{n} \\right] \\left( \\frac{n-1}{n} \\right)^{n} e \\end{equation} $

由于

$ \\begin{equation} e \\left( \\frac{n-1}{n} \\right)^{n} = e \\left( 1 - \\frac{1}{n} \\right)^{n} \\leq e \\left( e^{- \\frac{1}{n}} \\right)^{n} = e e^{-1} = 1 \\end{equation} $

所以得证。

我们考虑一个更精确地估计，Stirling's formula: 如果我们定义函数

$ \\begin{equation} f(n) = \\sqrt{2 \\pi n} \\left( \\frac{n}{e} \\right)^{n} \\end{equation} $

我们有 $ \\begin{equation} \\lim_ {n \\to \\infty} \\frac{f(n)}{n !} = 1 \\end{equation} $


<a id="orgb7e13e8"></a>

## 估计：二项式系数

定理：对任意 $ n \\geq 1 $ 和 任意 $ 1 \\leq k \\leq n $ ，有

$ \\begin{equation} { n \\choose k } \\leq \\left( \\frac{en}{k} \\right)^{k} \\end{equation} $

证明：

事实上我们证明一个更强的不等式：

$ \\begin{equation} { n \\choose 0 } + { n \\choose 1 } + { n \\choose 2 } + \\cdots + { n \\choose k } \\leq \\left(\\frac{en}{k}\\right)^{k} \\end{equation} $

首先根据二项式定理，我们有

$ \\begin{equation} { n \\choose 0 } + { n \\choose 1 }x + { n \\choose 2 }x^{2} + \\cdots + { n \\choose n }x^{n} = \\left(1 + x\\right)^{n} \\end{equation} $

现在我们假设0 < x < 1，我们去掉右边的一些项，得到：

$ \\begin{equation} { n \\choose 0 } + { n \\choose 1 }x + \\cdots + { n \\choose k }x^{k} \\leq \\left(1 + x\\right)^{n} \\end{equation} $

不等式两边都除以 $ x^{k} $ ，得到

$ \\begin{equation} \\frac{1}{x^{k}}{ n \\choose 0 } + \\frac{1}{x^{k-1}}{ n \\choose 1 } + \\cdots + { n \\choose k } \\leq \\frac{\\left(1 + x\\right)^{n}}{x^{k}} \\end{equation} $

因x < 1，则有

$ \\begin{equation} { n \\choose 0 } + { n \\choose 1 } + \\cdots + { n \\choose k } \\leq \\frac{\\left(1 + x\\right)^{n}}{x^{k}} \\end{equation} $

我们再把 $ x = \\frac{k}{n} $ 带入：

$ \\begin{equation} { n \\choose 0 } + { n \\choose 1 } + \\cdots + { n \\choose k } \\leq \\left( 1 + \\frac{k}{n} \\right)^{n} \\left( \\frac{n}{k} \\right)^{k} \\end{equation} $

由于

$ \\begin{equation} \\left(1 + \\frac{k}{n} \\right)^{n} \\leq \\left(e^{\\frac{k}{n}} \\right)^{n} = e^{k}  \\end{equation} $

因此可得定理。

命题：对n为偶数，设$ n = 2m $，则对任意 $ m \\geq 1 $ ，我们有

$ \\begin{equation} \\frac{2^{2m}}{2 \\sqrt{m}} \\leq { 2m \\choose m } \\leq \\frac{2^{2m}}{\\sqrt{2m}} \\end{equation} $

证明：

我们考虑这样的数

$ \\begin{equation} P=\\frac{1 \\cdot 3 \\cdot 5 \\cdot \\ldots \\cdot(2 m-1)}{2 \\cdot 4 \\cdot 6 \\cdot \\ldots \\cdot 2 m} \\end{equation} $

因为

$ \\begin{equation} P=\\frac{1 \\cdot 3 \\cdot 5 \\cdot \\ldots \\cdot(2 m-1)}{2 \\cdot 4 \\cdot 6 \\cdot \\ldots \\cdot 2 m} \\cdot \\frac{2 \\cdot 4 \\cdot \\ldots(2 m)}{2 \\cdot 4 \\cdot \\ldots(2 m)}=\\frac{(2 m) !}{2^{2 m}(m !)^{2}} \\end{equation} $

我们得到

$ \\begin{equation} P = \\frac{1}{2^{2m}} { 2m \\choose m } \\end{equation} $

然后，我们想要证明：

$ \\begin{equation} \\frac{1}{2 \\sqrt{m}} \\leq P \\leq \\frac{1}{\\sqrt{2m}} \\end{equation} $

对上界，我们考虑乘积：

$ \\begin{equation} \\left( 1 - \\frac{1}{2^{2}} \\right) \\left(1 - \\frac{1}{4^{2}} \\right) \\ldots \\left(1 - \\frac{1}{\\left(2m\\right)^{2}} \\right) \\end{equation} $

该乘积可改写为：

$ \\begin{equation} \\left( \\frac{1 \\cdot 3}{2^{2}} \\right) \\left( \\frac{3 \\cdot 5}{4^{2}} \\right) \\ldots \\left( \\frac{\\left(2m-1\\right) \\left(2m+1\\right)}{\\left(2m\\right)^{2}} \\right) = \\left(2m+1\\right) P^{2} \\end{equation} $

因为乘积的值小于1，我们得到 $ \\left(2m+1\\right) P^{2} < 1 $，因此 $ P \\leq \\frac{1}{\\sqrt{2m}} $

对下界，我们考虑乘积

$ \\begin{equation} \\left( 1 - \\frac{1}{3^{2}} \\right) \\left(1 - \\frac{1}{5^{2}} \\right) \\ldots \\left(1 - \\frac{1}{\\left(2m-1\\right)^{2}} \\right) \\end{equation} $

我们把该乘积改写成：

$ \\begin{equation} \\left( \\frac{2 \\cdot 4}{3^{2}} \\right) \\left( \\frac{4 \\cdot 6}{5^{2}} \\right) \\ldots \\left( \\frac{\\left(2m-2\\right) \\left(2m\\right)}{\\left(2m-1\\right)^{2}} \\right) = \\frac{1}{2 \\cdot \\left(2m\\right) \\cdot P^{2}} \\end{equation} $

因此有 $ P \\geq \\frac{1}{2 \\sqrt{m}} $

使用Stirling's formula，我们可以获得更精确地估计：

$ \\begin{equation} { 2m \\choose m} \\sim \\frac{2^{2m}}{\\sqrt{\\pi m}} \\end{equation} $

质数定理：设 $ \\pi \\left(n\\right) $ 为不超过n的质数个数，则

$ \\begin{equation} \\pi \\left(n\\right) \\sim \\frac{n}{\\ln n} \\end{equation} $


<a id="org07e2e5c"></a>

## Inclusion-exclusion principle

