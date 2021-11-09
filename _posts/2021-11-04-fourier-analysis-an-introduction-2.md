---
layout:     post
title:      "Fourier analysis an introduction(Chapter 2) by Stein"
subtitle:   "Basic Properties of Fourier Series"
thumbnail-img: ""
date:       2021-11-04 17:00
author:     "dreamume"
tags: 		[analysis]
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



在本章中，我们开始我们傅立叶级数的严谨地学习。我们设置舞台引入主题的主要目标，且然后公式化我们之前接触到的一些基本问题

我们第一个结果为布置问题的唯一性：两个带相同傅立叶系数的函数必须相等吗？事实上，一个简单地争论显示如果两个函数是连续的，则它们相等

接下来，我们更近地观察傅立叶级数的部分和。使用傅立叶系数公式，我们有关键观察这些和可方便的写成积分：

$ \\frac{1}{2 \\pi} \\int D_ {N}(x - y)f(y)dy $

$ \\{D_ {N}\\} $是一族汉森称为Dirichlet核。以上表达式是带函数 $ D_ {N} $的f的复杂阐述。一般地，给定一族函数 $ \\{K_ {n}\\} $，我们看极限当n趋于无穷时

$ \\frac{1}{2 \\pi} \\int K_ {n}(x - y)f(y)dy $

我们发现如果家族 $ \\{K_ {n}\\} $满足好核的三个重要属性，则上式趋于f(x)当 $ n \\to \\infty $（至少当f连续时）。这样，家族 $ \\{K_ {n}\\} $是一个大约估计。不幸地是，Dirichlet核 $ D_ {N} $不属于好核分类，其显示傅立叶级数的收敛问题是琐碎的

除了追求问题的收敛，我们考虑几个其他的方法求函数傅立叶级数的和。第一个方法，其包含部分和的平均，其属于好核，且是Fejer的重要定理。从这里，我们推演事实一个圆上的连续函数可被三角多项式统一估计。第二，我们也用Abel求傅立叶级数的和且其属于好核的家族。在这个情况中，其结果导致磁盘的稳定状态热力问题的Dirichlet问题的一个解

**问题的例子和想法**

我们开始我们应该考虑的函数类型的简单描述。因为f的傅立叶系数被定义为

$ a_ {n} = \\frac{1}{L} \\int^{L}_ {0}f(x)e^{-2 \\pi inx/L} dx, \\qquad \\text{for } n \\in \\mathbb{Z} $

f是[0, L]的复数值，它将需要在f上放置一些积分条件。我们将因此假设（本书后面）所有函数至少是黎曼可积的。有时它将被阐述聚焦我们的注意力在函数关于更规范上，即函数处理某个连续性或微分属性。如下，我们列出几类一般性增序的函数。我们强调我们不将一般性限制在实数函数上，相反我们将总是允许函数在复数上取值。更进一步，我们有时认为我们的函数被定义在一个圆上而不是一个间隔

**全连续函数**

复数值函数f在线段[0, L]上每点都连续。一个典型的连续函数如下图(a)。我们要注意之后连续函数在圆上满足额外的条件f(0) = f(L)

**分段连续函数**

在[0, L]上函数有有限个不连续不连续点。一个这样的函数如下图(b)

![img](../img/example_of_continuous_and_piecewise_continuous_functions.png)

**黎曼可积函数**

这是我们将考虑的最一般化的函数类。这样的函数有界，但有无穷多个不连续点。我们回忆积分的定义。一个在[0, L]上的实值函数f是黎曼可积的如果它有界且如果对任意 $ \\epsilon > 0 $，有一个在[0, L]上小的分割 $ 0 = x_ {0} < x_ {1} < \\cdots < x_ {N-1} < x_ {N} = L $，使得如果 $ \\mathcal{U}, \\mathcal{L} $，为这个分割的上和和下和，即

$ \\mathcal{U} = \\sum^{N}_ {j=1} [ \\operatorname{sup}_ {x_ {j-1} \\le x \\le x_ {j} f(x)](x_ {j} - x_ {j - 1}) $

$ \\mathcal{L} = \\sum^{N}_ {j=1} [ \\operatorname{inf}_ {x_ {j-1} \\le x \\le x_ {j} f(x)](x_ {j} - x_ {j - 1}) $

则我们有 $ \\mathcal{U} - \\mathcal{L} < \\epsilon $。最后，我们说一个复数值函数是可积的如果它的实部和虚部是可积的
