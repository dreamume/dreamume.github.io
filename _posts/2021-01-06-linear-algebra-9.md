---
layout:     post
title:      "Linear Algebra(Chapter 9) by Hoffman"
subtitle:   "Operators on Inner Product Spaces"
thumbnail-img: ""
date:       2021-01-06 08:38
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

1.  [Forms on Inner Product Spaces](#org33aee2c)


<a id="org33aee2c"></a>

# Forms on Inner Product Spaces

**定义** 一个在实数或复数向量空间V上的（sesqui-linear）form是一个 $ V \\times V $的函数使得

(a) $ f(c\\alpha + \\beta, \\gamma) = cf(\\alpha, \\gamma) + f(\\beta, \\gamma) $

(b) $ f(\\alpha, c\\beta + \\gamma) = \\bar{c}f(\\alpha, \\beta) + f(\\alpha, \\gamma) $

对所有V中的 $ \\alpha, \\beta, \\gamma $及所有常量c

当为实数时，$ f(\\alpha, \\beta) $对每个参数该函数都是线性的，即f是一个bilinear form

**定理 1** 设V为一个有限维内积空间且f为V上一个form，则V上有唯一一个线性算子T使得

$ \\begin{equation} f(\\alpha, \\beta) = (T\\alpha \| \\beta) \\end{equation} $

对V中所有 $ \\alpha, \\beta $，且映射 $ f \\to T $是forms空间在L(V, V)上的同构

**推论** 等式 $ (f \| g) = \\operatorname{tr}(T_ {f}T_ {g}^{ * } $定义了一个在forms空间上的内积有属性

$ \\begin{equation} (f \| g) = \\sum_ {j,k}f(\\alpha_ {k}, \\alpha_ {j})\\overline{g(\\alpha_ {k}, \\alpha_ {j})} \\end{equation} $

对V上每个标准正交基 $ \\{ \\alpha_ {1}, \\ldots, \\alpha_ {n} \\} $

**定义** 如果f是一个form且 $ \\mathcal{B} = \\{\\alpha_ {1}, \\ldots, \\alpha_{n} \\} $是V的一个任意有序基，矩阵A $ A_ {j k} = f(\\alpha_ {k}, \\alpha_ {j}) $被称为在有序基 $ \\mathcal{B} $上f的矩阵

**定理 2** 设f是在有限维复数内积空间V上的一个form，则有一个V的标准正交基使得f的矩阵是上三角的

**定义** 一个在实数或复数向量空间V上的form f被称为Hermitian如果

$ \\begin{equation} f(\\alpha, \\beta) = \\overline{f(\\beta, \\alpha)} \\end{equation} $

对V中所有 $ \\alpha, \\beta $

**定理 3** 设V为一个复数向量空间且f是V上一个form使得 $ f(\\alpha, \\alpha) $对每个 $ \\alpha $是实数，则f是Hermitian的

**推论** 设T为复数有限维内积空间V上的一个线性算子，则T是self-adjoint当且仅当 $ (T \\alpha \| \\alpha) $对V中每个 $ \\alpha $是实数

**定理 4(Principal Axis Theorem)** 对有限维内积空间V上的每个Hermitian form f有一个V上的标准正交基使得f为一个实数元素的对角矩阵

**推论** 使用上述条件，有

$ \\begin{equation} f(\\sum_ {j}x_ {j}\\alpha_ {j}, \\sum_ {k}y_ {k}\\alpha_ {k}) = \\sum_ {j}c_ {j}x_ {j}\\bar{y}_ {j} \\end{equation} $
