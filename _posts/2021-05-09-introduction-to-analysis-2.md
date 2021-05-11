---
layout:     post
title:      "解析概論(Chapter 2) by 高木貞治"
subtitle:   "微分法"
thumbnail-img: ""
date:       2021-05-09 14:10
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

1.  [微分法](#orgf3ab5b6)
    1.  [微分方法](#orgb8fc619)
    2.  [复合函数的微分](#org58e77c9)


<a id="orgf3ab5b6"></a>

# 微分法


<a id="orgb8fc619"></a>

## 微分方法

**定理** 连续性是微分可能性的必要条件

但是它不是充分条件

例子，$ f(x) = x \\sin{\\frac{1}{x}}, f(0) = 0 $的f(x)在0时的区间上连续，x = 0时却不能微分。实际上

$ \\frac{f(h) - f(0)}{h} = \\sin{\\frac{1}{h}} $

当 $ h \\to 0 $时，极限不存在

上述函数在x = 0这一点是特异点，Weierstras（1872）作出了区间各点都不能微分的连续函数的例子时，震惊了当时的数学界


<a id="org58e77c9"></a>

## 复合函数的微分

**定理** f(x) $ \\varphi(t) $微分存在，则 $ F(t) = f(\\varphi(t)) $微分存在

$ F^{\\prime} (t) = f^{\\prime}(x) \\cdot \\varphi^{\\prime}(t) $

即

$ \\frac{dy}{dt} = \\frac{dy}{dx} \\cdot \\frac{dx}{dt} $

这是复合函数的微分法

**证明** t的变动为 $ \\Delta t $，x的变动为 $ \\Delta x $，这样y的变动为 $ \\Delta y $

$ \\frac{\\Delta y }{\\Delta t} = \\frac{\\Delta y}{\\Delta x} \\cdot \\frac{\\Delta x}{\\Delta t} $

当 $ \\Delta t \\to 0 $时

$ \\frac{\\Delta x}{\\Delta t} \\to \\frac{dx}{dt} $

同时当 $ \\Delta x \\to 0 $时

$ \\frac{\\Delta y}{\\Delta x} \\to \\frac{dy}{dx} $

所以

$ \\frac{\\Delta y}{\\Delta t} \\to \\frac{dy}{dx} \\cdot \\frac{dx}{dt} $

这样

$ F^{\\prime}(t) = f^{\\prime}(x)\\varphi^{\\prime}(t) $

注意上述证明方法的问题

x为独立变量，$ \\Delta x $任意的话需要 $ \\Delta x \\ne 0 $，上面的情况是x是t的函数值，$ \\Delta t $的值引起 $ \\Delta x = 0$的情况是有的。这样的话，之前的证明写法有不合理的地方，变量 $ \\Delta x, \\Delta y $的写法要做修改如下：

$ \\Delta y = f^{\\prime}(x) \\Delta x + \\epsilon \\Delta x, \\quad \\Delta x = \\varphi^{\\prime}(t)\\Delta t + \\epsilon^{\\prime} \\Delta t $

当 $ \\Delta t \\to 0 $时， $ \\epsilon^{\\prime} \\to 0 $，有 $ \\Delta x \\to 0 $，但 $ \\Delta t \\ne 0 $时，$ \\Delta x = 0 $的情况也有。$ \\Delta x = 0 $时 $ \\epsilon = 0 $定义为 $ \\Delta t \\to 0 $时 $ \\epsilon \\to 0 $，这样

$ \\begin{aligned} \\Delta t &= (f^{\\prime}(x) + \\epsilon)(\\varphi^{\\prime}(t) + \\epsilon^{\\prime}) \\Delta t \\\\ &= f^{\\prime}(x)\\varphi^{\\prime}(t) \\cdot \\Delta t + [\\epsilon \\varphi^{\\prime}(t) + \\epsilon^{\\prime} f^{\\prime}(x) + \\epsilon \\epsilon^{\\prime}] \\Delta t $

右边括弧中的用 $ \\epsilon^{\\prime \\prime} $表达，则

$ \\Delta y = f^{\\prime}(x) \\varphi^{\\prime}(t) \\Delta t + \\epsilon^{\\prime \\prime} \\Delta t, \\qaud \\epsilon^{\\prime \\prime} = \\epsilon \\varphi^{\\prime}(t) + \\epsilon^{\\prime} f^{\\prime}(x) + \\epsilon \\epsilon^{\\prime} $

当 $ \\Delta t \\to 0 $时 $ \\epsilon^{\\prime \\prime} \\to 0 $，则

$ dy = f^{\\prime}(x) \\varphi^{\\prime}(t) dt $

这样结果为

$ dy = f^{\\prime}(x)dx $

同样，y为x的函数，x为t的函数，t为u的函数时，微分为

$ \\frac{dy}{du} = \\frac{dy}{dx} \\frac{dx}{dt} \\frac{dt}{du} $
