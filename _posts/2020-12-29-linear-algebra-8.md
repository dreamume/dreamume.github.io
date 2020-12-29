---
layout:     post
title:      "Linear Algebra(Chapter 8) by Hoffman"
subtitle:   "Inner Product Spaces"
thumbnail-img: ""
date:       2020-12-29 21:48
author:     "dreamume"
tags: 		[linear algebra]
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

1.  [Inner Products](#orgf9c15e0)


<a id="orgf9c15e0"></a>

# Inner Products

本章我们只考虑实数或复数向量空间。

**定义** 设F为实数或复数域，且V是F上的一个向量空间。一个V上的inner product是一个函数，赋值V中每个有序向量对 $ \\alpha, \\beta $一个F中常量 $ (\\alpha \| \\beta) $使得对V中所有 $ \\alpha, \\beta, \\gamma $ 和所有常量c

(a) $ (\\alpha + \\beta \| \\gamma ) = (\\alpha \| \\gamma) + (\\beta \| \\gamma) $

(b) $ (c \\alpha \| \\beta) = c(\\alpha \| \\beta) $

(c) $ (\\beta \| \\alpha) = \\overline{(\\alpha \| \\beta)} $，上横线表示复数conjugation

(d) $ (\\alpha \| \\alpha) > 0 如果 \\alpha \\ne 0 $

例子1，在 $ F^{n} $上有一个inner product我们称之为standard inner product。它定义为当 $ \\alpha = (x_ {1}, \\ldots, x_ {n})和 \\beta = (y_ {1}, \\ldots, y_ {n}) $时，

$ \\begin{equation} (\\alpha \| \\beta) = \\sum_ {j} x_ {j}\\bar{y}_ {j} \\end{equation} $

在实数域上，该standard inner product通常称为点积或常量积且被记为 $ \\alpha \\cdot \\beta $

例子3，设V为 $ F^{n \\times n} $，F上所有 $ n \\times n $矩阵的空间。则V根 $ F^{n^{2}} $同构。等式

$ \\begin{equation} (A \| B) = \\sum_ {j,k} A_ {j k} \\bar{B}_ {j k} \\end{equation} $

定义V上的一个inner product。更进一步，如果我们引入conjugate transpose 矩阵 $ B^{ * }, B_ {k j}^{ * } = \\bar{B}_ {j k}  $，我们表达 $ F^{ n \\times n} $上的trace函数的inner product：

$ \\begin{equation} (A \| B) = \\operatorname{tr}(AB^{ * }) = \\operatorname{tr}(B^{ * }A) \\end{equation} $

$ \\begin{equation} \\begin{aligned} \\operatorname{tr}(AB^{ * } ) &= \\sum_ {j}(AB^{ *})_ {j j} \\\\ &= \\sum_ {j} \\sum_ {k} A_ {j k}B_ {k j}^{ * } \\\\ &= \\sum_ {j} \\sum_ {k} A_ {j k}\\bar{B}_ {j k} \\end{aligned} \\end{equation} $

例子4 设 $ F^{n \\times 1} $为F上 $ n \\times 1 $矩阵空间，且设Q为F上 $ n \\times n $可逆矩阵，对在 $ F^{n \\times 1} $集合上的X, Y

$ \\begin{equation} (X \| Y) = Y^{ * }Q^{ * }QX \\end{equation} $

我们称它为 $ F^{ n \\times 1 } $上的standard inner product

假设V是有限维的，则 $ \\mathcal{B} = \\{\\alpha_ {1}, \\ldots, \\alpha_ {n} \\} $是V的一个有序基，且我们给定一个V上特殊的inner product，我们将显示这个inner product完全被值 $ G_ {j k} = (\\alpha_ {k} \| \\alpha_ {j}) $决定。如果 $ \\alpha = \\sum_ {k}x_ {k}\\alpha_ {k} 和 \\beta = \\sum_ {j}y_ {j} \\alpha_ {j} $，则

\\begin{equation} \\begin{aligned} (\\alpha \| \\beta) &= (\\sum_ {k}x_ {n}\\alpha_ {k} \| \\beta) \\\\ &= \\sum_ {k}x_ {k}(\\alpha_ {k} \| \\beta) \\\\ &= \\sum_ {k}x_ {k}\\sum_ {j}\\bar{y}_ {j} (\\alpha_ {k} \| \\alpha_ {j}) \\\\ &= \\sum_ {j, k}\\bar{y}_ {j} G_ {j k}x_ {k} \\\\ &= Y^{ * }GX \\end{aligned} \\end{equation} $

我们称G为在有序基 $ \\mathcal{B} $下inner product的矩阵
