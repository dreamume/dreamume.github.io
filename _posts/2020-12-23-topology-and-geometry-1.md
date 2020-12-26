---
layout:     post
title:      "Topology and geometry(Chapter 1) by Bredon"
subtitle:   "General Topology"
thumbnail-img: ""
date:       2020-12-23 00:30
author:     "dreamume"
tags: 		[topology]
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

1.  [General Topology](#org8fd57c5)
    1.  [Metric Spaces](#orgb8cdb49)


<a id="org8fd57c5"></a>

# General Topology


<a id="orgb8cdb49"></a>

## Metric Spaces

**定义** 一个度量空间是一个集合X及一个函数

$ \\begin{equation} dist: X \\times X \\to R \\end{equation} $

称为一个度量，使得如下三个规则满足：

(1) （正定性） $ dist\\left(x, y\\right) \\ge 0, 当等号成立时 $，x = y

(2) （对称性） dist(x, y) = dist(y, x)；且

(3) （三角不等式） $ dist\\left(x, z\\right) \\le dist\\left(x, y\\right) + dist\\left(y, z\\right) $

在度量空间X中我们定义 $ \\epsilon $球， $ \\epsilon > 0 $，对于一个点 $ x \\in X $ 有

$ \\begin{equation} B_ {\\epsilon}\\left(x\\right) = \\{ y \\in X \| dist\\left(x, y\\right) < \\epsilon \\} \\end{equation} $

一个子集 $ U \\subset X $被称为是开的，如果对每个点 $ x \\in U $，有一个 $ \\epsilon $球把x在U中完全包含。一个子集被称为闭的，如果它的补是开的。

**命题** 一个函数 $ f: X \\to Y $在度量空间中是连续的 $ \\Leftrightarrow f^{-1}\\left(U\\right) $ 对每个Y中的开子集U在X中是开的

证明：如果f是连续的且 $ U \\subset Y $是开的且 $ f\\left(x\\right) \\in U $，则有一个 $ \\epsilon > 0 使得 B_ {\\epsilon} \\left(f\\left(x\\right)\\right) \\subset U $。因为连续性，则有一个 $ \\delta > 0 $使得f映射x的 $ \\delta $-球到 $ B_ {\\epsilon}\\left(f\\left(x\\right)\\right) $。这意味着 $ B_ {\\delta}\\left(x\\right) \\subset f^{-1}\\left(U\\right) $。这意味着 $ f^{-1}\\left(U\\right) $是开的

相反地，假设f(x) = y且给定 $ \\epsilon > 0 $。通过假设，$ f^{-1}\\left(B_ {\\epsilon}\\left(y\\right)\\right) $是开的且含有x。因此，通过开集的定义，有一个 $ \\delta > 0使得 B_ {\\delta}\\left(x\\right) \\subset f^{-1}\\left(B_ {\\epsilon}\\left(y\\right)\\right) $。如果 $ dist\\left(x, x'\\right) < \\delta 则 f\\left(x'\\right) \\in B_ {\\epsilon}\\left(y\\right) $，且这样 $ dist\\left(f\\left(x\\right), f\\left(x'\\right)\\right) < \\epsilon $，即通过 $ \\epsilon - \\delta $语言证明了连续性

其他的度量有：

$ \\begin{equation} dist_ {2}\\left(x, y\\right) = \\sum_ {i=1}^{n} \| x_ {i} - y_ {i} \| \\end{equation} $

$ \\begin{equation} dist_ {3}\\left(x, y\\right) = max\\left( \| x_ {i} - y_ {i} \| \\right) \\end{equation} $

**命题** 如果 $ dist_ {1} 和 dist_ {2} $是相同集合X上的度量满足假设，对任意点 $ x \\in X 和 \\epsilon > 0 有一个 \\delta > 0 $使得

$ \\begin{equation} dist_ {1}\\left(x, y\\right) < \\delta \\Rightarrow dist_ {2}\\left(x, y\\right) < \\epsilon \\end{equation} $

$ \\begin{equation} dist_ {2}\\left(x, y\\right) < \\delta \\Rightarrow dist_ {1}\\left(x, y\\right) < \\epsilon \\end{equation} $

则这些度量在X上定义了相同的开集
