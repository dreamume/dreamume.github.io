---
layout:     post
title:      "Linear Algebra(Chapter 6) by Hoffman"
subtitle:   "The Rational and Jordan Forms"
thumbnail-img: ""
date:       2020-12-12 19:00
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

1.  [Cyclic Suubspaces and Annihilators](#orgcee1036)


<a id="orgcee1036"></a>

# Cyclic Suubspaces and Annihilators

**定义** 如果 $ \\alpha $是V中任意向量，则$ \\alpha $产生的T-cyclic子空间是形如 $ g\\left(T\\right) \\alpha $的所有向量的子空间$ Z\\left(\\alhpa; T\\right), g \\in F[x] $。如果 $ Z\\left(\\alpha; T\\right) = V $，则 $ \\alpha $被称为T的一个cyclic向量

**定义** 如果 $ \\alpha $是V中任意向量，则$ \\alpha $的T-annihilator是ideal 在F[x]中的$ M\\left(\\alpha; T\\right) $包含域F上所有polynomials g使得 $ g\\left(T\\right) \\alpha = 0 $。产生这个ideal的唯一monic polynomial也被称为 $ \\alpha $的 T-annihilator

**定理 1** 设 $ \\alpha $为V上任意非零向量且设 $ p_ {\\alpha} $为 $ \\alpha $的T-annihilator

(i) $ p_ {\\alpha} $的degree与cyclic子空间 $ Z\\left(\\alpha; T\\right) 的维数相同

(ii)如果 $ p_ {\\alpha} $的degree为k，则向量 $ \\alpha, T\\alpha, T^{2}\\alpha, \\ldots, T^{k-1}\\alpha $形成 $ Z\\left(\\alpha; T\\right) $的一个基

(iii)如果U是由T引导的 $ Z\\left(\\alpha; T\\right) $上的线性算子，则U的minimal polynomial为 $ p_ {\\alpha} $

让我们看一下线性算子U在k维空间W上有一个cyclic向量 $ \\alpha $。通过定理1，向量 $ \\alpha, \\ldots, U^{k-1}\\alpha $形成空间W的一个基，且 $ \\alpha $ 的annihilator $ p_ {\\alpha} $是U的minimal polynomial（因此也是U的特征polynomial）。如果我们设 $ \\alpha_ {i} = U^{i-1} \\alpha, i = 1, \\ldots, k $，则U在有序基 $ \\mathcal{B} = \\{ \\alpha_ {1}, \\ldots, \\alpha_ {k} \\} $上的行为是

$ \\begin{equation} U_ {\\alpha_ {i}} = \\alpha_ {i+1}, \\qquad i = 1, \\ldots, k - 1 \\end{equation} $

$ \\begin{equation} U_ {\\alpha_ {k}} = -c_ {0}\\alpha_ {1} - c_ {1} \\alpha_{2} - \\cdots = c_ {k-1}\\alpha_ {k} \\end{equation} $

其中 $ p_ {\\alpha} = c_ {0} + c_ {1}x + \\cdots + c_ {k-1}x^{k-1} + x^{k} $。$ U_ {\\alpha_ {k}} $表达式根据 $ p_ {\\alpha}\\left(U\\right) \\alpha = 0 $有

$ \\begin{equation} U^{k} \\alpha + c_ {k-1}U^{k-1}\\alpha + \\cdots + c_ {1}U\\alpha + c_ {0} \\alpha = 0 \\end{equation} $

即U在有序基 $ \\mathcal{B} $下的矩阵为

$ \\begin{equation} \\left[ \\begin{array}{ccc} 0 & 0 & 0 & \\cdots & 0 & -c_ {0} \\\\ 1 & 0 & 0 & \\cdots & 0 & -c_ {1} \\\\ 0 & 1 & 0 & \\cdots & 0 & -c_ {2} \\\\ \\vdots & \\vdots & \\vdots & & \\vdots & \\vdots \\\\ 0 & 0 & 0 & \\cdots & 1 & -c_ {k - 1} \\end{equation} $

该矩阵被称为monic polynomial $ p_ {\\alpha} $的伴随矩阵

**定理 2** 如果U是有限维空间W上的线性算子，则U有一个cyclic向量当且仅当有一个W的有序基，则U以U的minimal polynomial的伴随矩阵的形式呈现

**推论** 如果A是一个monic polynomial p的伴随矩阵，则p是A的minimal和特征polynomial
