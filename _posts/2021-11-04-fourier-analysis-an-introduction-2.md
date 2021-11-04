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

