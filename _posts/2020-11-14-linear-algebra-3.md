---
layout:     post
title:      "Linear Algebra(Chapter 3) by Hoffman"
subtitle:   "Linear Transformations"
thumbnail-img: ""
date:       2020-11-14 17:00
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

1.  [转换的矩阵表示](#orgd13b3aa)

定义：设V和W为域F上的向量空间，一个从V到W的线性变换为一个从V到W的函数T，有

$ \\begin{equation} \\mathrm{T}(\\mathrm{c} \\alpha+\\beta)=\\mathrm{c}(\\mathrm{T} \\alpha)+\\mathrm{T} \\beta \\end{equation} $

对V中所有α和β及F中所有标量c。


<a id="orgd13b3aa"></a>

# 转换的矩阵表示

设V为域F上的n维向量空间，W为域F上的m维向量空间。设 $ \\mathbb{B}=\\left\\{\\alpha_ {1}, \\ldots, \\alpha_ {n}\\right\\} $ 为V的一个基，$ \\mathbb{B}^{'}=\\left\\{\\beta_ {1}, \\ldots, \\beta_ {m}\\right\\} $ 为W的基。如果T是任意从V到W的线性变换，则T被向量 $ \\alpha_ {j} $ 决定，有：

$ \\begin{equation} T \\alpha_ {j}=\\sum_ {i=1}^{m} A_ {i j} \\beta_ {i} \\end{equation} $

m x n矩阵A被称为T对于基 $ \\mathbb{B} $ 和 $ \\mathbb{B}^{'} $ 的矩阵

定义：设A和B为域F上的n x n 矩阵。我们说在域F上B跟A相似仅当有一个域F上的n x n可逆矩阵P，使得 $ B = P^{-1}AP $
