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

$ \\\begin{equation} \\&sum;\_ {i=0}<sup>n</sup>\\\left(\\\begin{array}{c}n \\\\\\\\ i\\\end{array}\\\right)<sup>2</sup>=\\\left(\\\begin{array}{c}2 n \\\\\\\\ n\\\end{array}\\\right) \\\end{equation} $

证明：

该式左边可写成

$ \\\begin{equation} \\&sum;\_ {i=0}<sup>n</sup>\\\left(\\\begin{array}{c}n \\\\\\\\ i\\\end{array}\\\right) \\\left(\\\begin{array}{c}n \\\\\\\\ n - i \\\end{array}\\\right) \\\end{equation} $

可理解为2n个物品分成两组，每组n个物品，则按前一组取i个，后一组取n - i个，然后遍历组合即为2n个物品里取n个。

如果我们有m种物品，第i中物品有k<sub>i</sub> 个，$ k\_ {1} + k\_ {2} + \\\ldots + k\_ {m} = n $ ，则不同的组合有：

$ \\\begin{equation} \\\frac{n!}{k\_ {1}! k\_ {2}! \\\ldots k\_ {m}!} \\\end{equation} $

该表达式通常写成：

$ \\\begin{equation} \\\left(\\\begin{array}{c}n \\\\\\\\ k\_ {1}, k\_ {2}, \\\ldots, k\_ {m} \\\end{array}\\\right) \\\end{equation} $

Multinomial theorem: 对任意实数 $ x\_ {1}, x\_ {2}, \\\ldots, x\_ {m} $ 和任意自然数 $ n \\&ge; 1 $ ，有如下等式：

$ \\\begin{equation} \\\left(x\_ {1}+x\_ {2}+\\&ctdot;+x\_ {m}\\\right)<sup>n</sup>=\\&sum;\_ {k\_ {1}+\\&ctdot;+k\_ {m}=n \\\atop k\_ {1}, \\\ldots, k\_ {m} \\&ge; 0}\\\left(\\\begin{array}{c}n \\\\\\\\ k\_ {1}, k\_ {2}, \\\ldots, k\_ {m}\\\end{array}\\\right) x\_ {1}<sup>k\_ {1}</sup> x\_ {2}<sup>k\_ {2}</sup> \\\ldots x\_ {m}<sup>k\_ {m}</sup> \\\end{equation} $


<a id="orged53e4c"></a>

## 估计：简介

harmonic numbers:

$ \\\begin{equation} H\_ {n} = 1 + \\\frac{1}{2} + \\\frac{1}{3} + \\&ctdot; + \\\frac{1}{n} = \\&sum;\_ {i=1}<sup>n</sup>\\\frac{1}{i} \\\end{equation} $

为估计该值，我们把其元素分成k组，因此第k组 $ G\_ {k} $ 包含 $ 2<sup>k-1</sup> $ 个元素：

$ \\\begin{equation} \\\frac{1}{2<sup>k-1</sup>}, \\\frac{1}{2<sup>k-1</sup> + 1}, \\\frac{1}{2<sup>k-1</sup> + 2}, \\&ctdot;, \\\frac{1}{2<sup>k</sup> - 1} \\\end{equation} $

这样该$ G\_ {k} $组的和满足：

$ \\\begin{equation} \\&sum;\_ {x \\&isin; G\_ {k}}x \\&le; \\| G\_ {k} \\| max G\_ {k} = 2<sup>k - 1</sup> \\\frac{1}{2<sup>k-1</sup>} = 1 \\\end{equation} $

$ \\\begin{equation} \\&sum;\_ {x \\&isin; G\_ {k}}x \\&ge; \\| G\_ {k} \\| min G\_ {k} > 2<sup>k - 1</sup> \\\frac{1}{2<sup>k</sup>} = \\\frac{1}{2} \\\end{equation} $

因此：

$ \\\begin{equation} H\_ {n} = \\&sum;\_ {i=1}<sup>n</sup>\\\frac{1}{i} \\&le; \\&sum;\_ {k=1}<sup>\\&lfloor; \\log\_ {2} n \\&rfloor; + 1</sup>1 \\&le; \\log<sub>2</sub> n + 1 \\\end{equation} $

$ \\\begin{equation} H\_ {n} > \\&sum;\_ {k=1}<sup>\\&lfloor; \\log\_ {2} n \\&rfloor;</sup>\\\frac{1}{2} \\&ge; \\\frac{1}{2} \\&lfloor; \\log\_ {2} n \\&rfloor; \\\end{equation} $


<a id="org4911f9a"></a>

## 估计：阶乘函数

为估计 $ n! $ 的大小，我们考虑，如果n为偶数，则 集合 $ \\\\{ 1, 2, \\\ldots, n } $ 中 $ \\\frac{n}{2} $ 个数最多为 $ \\\frac{n}{2} $ ，且 $ \\\frac{n}{2} $ 个数大于 $ \\\frac{n}{2} $ 。因此，我们有

$ \\\begin{equation} n ! \\&ge; \\&prod;\_ {i=n / 2+1}<sup>n</sup> i>\\&prod;\_ {i=n / 2+1}<sup>n</sup> \\\frac{n}{2}=\\\left(\\\frac{n}{2}\\\right)<sup>n / 2</sup>=\\\left(\\\sqrt{\\\frac{n}{2}}\\\right)<sup>n</sup> \\\end{equation} $

$ \\\begin{equation} n ! \\&le; \\\left( \\&prod;\_ {i=1}<sup>\\\frac{n}{2}</sup> \\\right) \\\left( \\&prod;\_ {i = \\\frac{n}{2} + 1}<sup>n</sup>n \\\right) = \\\frac{n<sup>n</sup>}{2<sup>\\\frac{n}{2}</sup>} \\\end{equation} $

如n为奇数，则对于 $ n \\&ge; 3 $ 的奇数也成立

定理：对任意 $ n \\&ge; 1 $ ，有

$ \\\begin{equation} n<sup>\\\frac{n}{2}</sup> \\&le; n ! \\&le; \\\left( \\\frac{n+1}{2} \\\right)<sup>n</sup> \\\end{equation} $

证明：

我们可以构造如下等式：

$ \\\begin{equation} n ! = \\&prod;\_ {i=1}<sup>n</sup> \\\sqrt{i \\left(n+1-i \\right) } \\\end{equation} $

因

$ \\\begin{equation} \\\sqrt{i \\left(n+1-i \\right) } \\&le; \\\frac{i + n + 1 - i}{2} = \\\frac{n+1}{2} \\\end{equation} $

所以

$ \\\begin{equation} n ! = \\&prod;\_ {i=1}<sup>n</sup> \\\sqrt{ i \\left( n + 1 - i \\right) } \\&le; \\&prod;\_ {i=1}<sup>n</sup>\\\frac{n+1}{2} = \\\left( \\\frac{n+1}{2} \\\right)<sup>n</sup> \\\end{equation} $

对下界，我们可以看到对所有 $ i = 1, 2, \\\ldots, n, i \\\left( n + 1 - i \\\right) \\&ge; n $ ，因此有 $ n ! \\&ge; \\\sqrt{n<sup>n</sup>} = n<sup>\\\frac{n}{2}</sup> $

我们观察到这样一个事实，对任意实数x，有 $ 1 + x \\&le; e<sup>x</sup> $

定理：对任意 $ n \\&ge; 1 $ ，有

$ \\\begin{equation} e \\\left( \\\frac{n}{e} \\\right)<sup>n</sup> \\&le; n ! \\&le; en \\\left(\\\frac{n}{e}\\\right)<sup>n</sup> \\\end{equation} $

这里我们仅证明上界，利用归纳法，当n = 1时，可以验证不等式成立，假设n - 1也成立，我们来验证n的情况，我们有

$ \\\begin{equation} n ! = n \\\left(n - 1\\\right) ! \\&le; n e \\\left(n - 1\\\right) \\\left( \\\frac{n-1}{e}\\\right)<sup>n-1</sup> \\\end{equation} $

我们把右边的式子转换为

$ \\\begin{equation} \\\left[ en \\\left( \\\frac{n}{e} \\\right)<sup>n</sup> \\\right] \\\left( \\\frac{n-1}{n} \\\right)<sup>n</sup> e \\\end{equation} $

由于

$ \\\begin{equation} e \\\left( \\\frac{n-1}{n} \\\right)<sup>n</sup> = e \\\left( 1 - \\\frac{1}{n} \\\right)<sup>n</sup> \\&le; e \\\left( e<sup>- \\\frac{1}{n}</sup> \\\right)<sup>n</sup> = e e<sup>-1</sup> = 1 \\\end{equation} $

所以得证。

我们考虑一个更精确地估计，Stirling's formula: 如果我们定义函数

$ \\\begin{equation} f(n) = \\\sqrt{2 \\pi n} \\\left( \\\frac{n}{e} \\\right)<sup>n</sup> \\\end{equation} $

我们有 $ \\\begin{equation} \\lim\_ {n \\&rarr; \\&infin;} \\\frac{f(n)}{n !} = 1 \\\end{equation} $


<a id="orgb7e13e8"></a>

## 估计：二项式系数

定理：对任意 $ n \\&ge; 1 $ 和 任意 $ 1 \\&le; k \\&le; n $ ，有

$ \\\begin{equation} { n \\\choose k } \\&le; \\\left( \\\frac{en}{k} \\\right)<sup>k</sup> \\\end{equation} $

证明：

事实上我们证明一个更强的不等式：

$ \\\begin{equation} { n \\\choose 0 } + { n \\\choose 1 } + { n \\\choose 2 } + \\&ctdot; + { n \\\choose k } \\&le; \\\left(\\\frac{en}{k}\\\right)<sup>k</sup> \\\end{equation} $

首先根据二项式定理，我们有

$ \\\begin{equation} { n \\\choose 0 } + { n \\\choose 1 }x + { n \\\choose 2 }x<sup>2</sup> + \\&ctdot; + { n \\\choose n }x<sup>n</sup> = \\\left(1 + x\\\right)<sup>n</sup> \\\end{equation} $

现在我们假设0 < x < 1，我们去掉右边的一些项，得到：

$ \\\begin{equation} { n \\\choose 0 } + { n \\\choose 1 }x + \\&ctdot; + { n \\\choose k }x<sup>k</sup> \\&le; \\\left(1 + x\\\right)<sup>n</sup> \\\end{equation} $

不等式两边都除以 $ x<sup>k</sup> $ ，得到

$ \\\begin{equation} \\\frac{1}{x<sup>k</sup>}{ n \\\choose 0 } + \\\frac{1}{x<sup>k-1</sup>}{ n \\\choose 1 } + \\&ctdot; + { n \\\choose k } \\&le; \\\frac{\\\left(1 + x\\\right)<sup>n</sup>}{x<sup>k</sup>} \\\end{equation} $

因x < 1，则有

$ \\\begin{equation} { n \\\choose 0 } + { n \\\choose 1 } + \\&ctdot; + { n \\\choose k } \\&le; \\\frac{\\\left(1 + x\\\right)<sup>n</sup>}{x<sup>k</sup>} \\\end{equation} $

我们再把 $ x = \\\frac{k}{n} $ 带入：

$ \\\begin{equation} { n \\\choose 0 } + { n \\\choose 1 } + \\&ctdot; + { n \\\choose k } \\&le; \\\left( 1 + \\\frac{k}{n} \\\right)<sup>n</sup> \\\left( \\\frac{n}{k} \\\right)<sup>k</sup> \\\end{equation} $

由于

$ \\\begin{equation} \\\left(1 + \\\frac{k}{n} \\\right)<sup>n</sup> \\&le; \\\left(e<sup>\\\frac{k}{n}</sup> \\\right)<sup>n</sup> = e<sup>k</sup>  \\\end{equation} $

因此可得定理。

命题：对n为偶数，设$ n = 2m $，则对任意 $ m \\&ge; 1 $ ，我们有

$ \\\begin{equation} \\\frac{2<sup>2m</sup>}{2 \\\sqrt{m}} \\&le; { 2m \\\choose m } \\&le; \\\frac{2<sup>2m</sup>}{\\\sqrt{2m}} \\\end{equation} $

证明：

我们考虑这样的数

$ \\\begin{equation} P=\\\frac{1 \\cdot 3 \\cdot 5 \\cdot \\ldots \\cdot(2 m-1)}{2 \\cdot 4 \\cdot 6 \\cdot \\ldots \\cdot 2 m} \\\end{equation} $

因为

$ \\\begin{equation} P=\\\frac{1 \\cdot 3 \\cdot 5 \\cdot \\ldots \\cdot(2 m-1)}{2 \\cdot 4 \\cdot 6 \\cdot \\ldots \\cdot 2 m} \\&sdot; \\\frac{2 \\cdot 4 \\cdot \\ldots(2 m)}{2 \\cdot 4 \\cdot \\ldots(2 m)}=\\\frac{(2 m) !}{2<sup>2 m</sup>(m !)<sup>2</sup>} \\\end{equation} $

我们得到

$ \\\begin{equation} P = \\\frac{1}{2<sup>2m</sup>} { 2m \\\choose m } \\\end{equation} $

然后，我们想要证明：

$ \\\begin{equation} \\\frac{1}{2 \\\sqrt{m}} \\&le; P \\&le; \\\frac{1}{\\\sqrt{2m}} \\\end{equation} $

对上界，我们考虑乘积：

$ \\\begin{equation} \\\left( 1 - \\\frac{1}{2<sup>2</sup>} \\\right) \\\left(1 - \\\frac{1}{4<sup>2</sup>} \\\right) \\\ldots \\\left(1 - \\\frac{1}{\\\left(2m\\\right)<sup>2</sup>} \\\right) \\\end{equation} $

该乘积可改写为：

$ \\\begin{equation} \\\left( \\\frac{1 \\cdot 3}{2<sup>2</sup>} \\\right) \\\left( \\\frac{3 \\cdot 5}{4<sup>2</sup>} \\\right) \\\ldots \\\left( \\\frac{\\left(2m-1\\right) \\left(2m+1\\right)}{\\\left(2m\\\right)<sup>2</sup>} \\\right) = \\\left(2m+1\\\right) P<sup>2</sup> \\\end{equation} $

因为乘积的值小于1，我们得到 $ \\\left(2m+1\\\right) P<sup>2</sup> < 1 $，因此 $ P &le; \\\frac{1}{\\\sqrt{2m}} $

对下界，我们考虑乘积

$ \\\begin{equation} \\\left( 1 - \\\frac{1}{3<sup>2</sup>} \\\right) \\\left(1 - \\\frac{1}{5<sup>2</sup>} \\\right) \\\ldots \\\left(1 - \\\frac{1}{\\\left(2m-1\\\right)<sup>2</sup>} \\\right) \\\end{equation} $

我们把该乘积改写成：

$ \\\begin{equation} \\\left( \\\frac{2 \\cdot 4}{3<sup>2</sup>} \\\right) \\\left( \\\frac{4 \\cdot 6}{5<sup>2</sup>} \\\right) \\\ldots \\\left( \\\frac{\\left(2m-2\\right) \\left(2m\\right)}{\\\left(2m-1\\\right)<sup>2</sup>} \\\right) = \\\frac{1}{2 \\&sdot; \\\left(2m\\\right) \\&sdot; P<sup>2</sup>} \\\end{equation} $

因此有 $ P \\&ge; \\\frac{1}{2 \\\sqrt{m}} $

使用Stirling's formula，我们可以获得更精确地估计：

$ \\\begin{equation} { 2m \\\choose m} \\&sim; \\\frac{2<sup>2m</sup>}{\\\sqrt{\\pi m}} \\\end{equation} $

质数定理：设 $ \\&pi; \\\left(n\\\right) 为不超过n的质数个数，则

$ \\\begin{equation} \\&pi; \\\left(n\\\right) \\&sim; \\\frac{n}{\\ln n} \\\end{equation} $


<a id="org07e2e5c"></a>

## Inclusion-exclusion principle

