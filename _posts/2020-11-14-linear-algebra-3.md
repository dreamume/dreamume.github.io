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
2.  [Linear Functionals](#org74ca3f4)
3.  [The Double Dual](#orgcef566a)
4.  [线性变换的transpose](#orgb5ce838)

定义：设V和W为域F上的向量空间，一个从V到W的线性变换为一个从V到W的函数T，有

$ \\begin{equation} \\mathrm{T}(\\mathrm{c} \\alpha+\\beta)=\\mathrm{c}(\\mathrm{T} \\alpha)+\\mathrm{T} \\beta \\end{equation} $

对V中所有α和β及F中所有标量c。


<a id="orgd13b3aa"></a>

# 转换的矩阵表示

设V为域F上的n维向量空间，W为域F上的m维向量空间。设 $ \\mathbb{B}=\\left\\{\\alpha_ {1}, \\ldots, \\alpha_ {n}\\right\\} $ 为V的一个基，$ \\mathbb{B}^{'}=\\left\\{\\beta_ {1}, \\ldots, \\beta_ {m}\\right\\} $ 为W的基。如果T是任意从V到W的线性变换，则T被向量 $ \\alpha_ {j} $ 决定，有：

$ \\begin{equation} T \\alpha_ {j}=\\sum_ {i=1}^{m} A_ {i j} \\beta_ {i} \\end{equation} $

m x n矩阵A被称为T对于基 $ \\mathbb{B} $ 和 $ \\mathbb{B}^{'} $ 的矩阵

定义：设A和B为域F上的n x n 矩阵。我们说在域F上B跟A相似仅当有一个域F上的n x n可逆矩阵P，使得 $ B = P^{-1}AP $


<a id="org74ca3f4"></a>

# Linear Functionals

如果V是域F上的向量空间，一个线性变换f从V到域F上的常量被称为V上的linear functional

如果V是向量空间，则V上的所有linear functionals集合形成一个向量空间，我们记为空间 $ V^{*} $ ，并称它为V的dual space:

$ \\begin{equation} V^{*} = L(V, F) \\end{equation} $

如果V是有限维的，则有 $ dim V^{*} = dim V $

设 $ \\mathbb{B} = \\left\\{\\alpha_ {1}, \\ldots, \\alpha_ {n} \\right\\} $ 为V的基，则在V上存在（对每个i）有一个唯一的linear functional $ f_ {i} $ ，有

$ f_ {i}\\left(\\alpha_ {j}\\right)=\\delta_ {i j} $

这样我们从 $ \\mathbb{B} $ 中获得V上n个不同linear functionals $ f_ {1}, \\ldots, f_ {n} $ 的集合。这些functionals也是线性无关的。假设

$ \\begin{equation} f = \\sum_ {i = 1}^{n} c_ {i} f_ {i} \\end{equation} $

则

$ \\begin{equation} \\begin{aligned} f\\left(\\alpha_ {j}\\right) &=\\sum_ {i=1}^{n} c_ {i} f_ {i}\\left(\\alpha_ {j}\\right) \\\\ &=\\sum_ {i=1}^{n} c_ {i} \\delta_ {i j} \\\\ &=c_ {j} \\end{aligned} \\end{equation} $

我们知道 $ V^{* } $ 也是n维的，则 $ \\mathbb{B}^{* } = \\left\\{ f_ {1}, \\ldots, f_ {n} \\right\\} $ 是 $ V^{* } $ 的一个基，被称为 $ \\mathbb{B} $ 的dual basis

定理：设V为域F上的有限维向量空间，设 $ \\mathbb{B} = \\left\\{ \\alpha_ {1}, \\ldots, \\alpha_ {n} \\right\\} $ 为V的一个基，则存在唯一的一个dual basis $ \\mathbb{B}^{*} = \\left\\{ f_ {1}, \\ldots, f_ {n} \\right\\} $ ，使得 $ f_ {i}(\\alpha_ {j}) = \\delta_ {i j} $ 。对V上的每个linear functional f，我们有

$ \\begin{equation} f = \\sum_ {i = 1}^{n} f(\\alpha_ {i}) f_ {i} \\end{equation} $

且对V上的每个向量，我们有

$ \\begin{equation} \\alpha = \\sum_ {i = 1}^{n} f_ {i}(\\alpha) \\alpha_ {i} \\end{equation} $

一个n维向量空间，其n - 1维子空间被称为hyperspace

定义：如果V是域F上的向量空间，S是V的一个子集，the annihilator of S被称为V上linear functionals f的集合 $ S^{0} $ ，使得 $ \\forall \\alpha \\in S, f(\\alpha) = 0 $

定理：设V为域F上的有限维向量空间，W为V的子空间，则 $ dim W + dim W^{0} = dim V $


<a id="orgcef566a"></a>

# The Double Dual

定理：设V为域F上的有限维向量空间，对任意向量 $ \\alpha \\in V $ ，定义

$ \\begin{equation} L_ {\\alpha} \\left( f \\right) = f \\left( \\alpha \\right), \\quad \\quad f \\quad in \\quad V^{*} \\end{equation} $

映射 $ \\alpha \\longrightarrow L_ {\\alpha} $ 为V到 $ V^{**} $ 上的同构

这显示了映射 $ \\alpha \\longrightarrow L_ {\\alpha} $ 为V到 $ V^{**} $ 上到线性变换，该变换是non-singular的，$ L_ {\\alpha} = 0 $ 当且仅当 $ \\alpha = 0 $ ，且有

$ \\begin{equation} dim V^{** } = dim V^{* } = dim V \\end{equation} $


<a id="orgb5ce838"></a>

# 线性变换的transpose

假设我们有两个域F上的向量空间V和W，和一个从V到W的线性变换T。则T导入了一个从 $ W^{ * } $ 到 $ V^{ * } $ 的线性变换，假设g为W上的linear functional，设

$ \\begin{equation} \\forall \\alpha \\in V, \\quad f \\left( \\alpha \\right) = g \\left( T \\alpha \\right) \\end{equation} $

f为从V到F的函数，因为T和g都是线性的，则f也是线性的。这样T提供了一个规则 $ T^{t} $ 使得 $ f = T^{t} g $。$ T^{t} $  也是从 $ W^{ * } $ 到 $ V^{ * } $ 的一个线性变换。

**定理** 设V和W为域F上的向量空间，对每个从V到W的线性变换T，有一个唯一的从 $ W^{ * } $ 到 $ V^{ * } $ 的线性变换 $ T^{t} $ ， 使得

$ \\begin{equation} \\forall g \\, in \\, W^{ * } \\, and \\, \\alpha \\, in \\, V, \\quad \\left( T^{t} g \\right) \\left( \\alpha \\right) = g \\left( T \\alpha \\right) \\end{equation} $

我们称 $ T^{t} $ 为T的transpose，也被称为the adjoint of T

**定理** 设V和W为域F上的向量空间，设T为从V到W上的线性变换， $ T^{t} $ 的null space为T的范围的annihilator。如果V和W都是有限维的，则

(i) $ rank \\left( T^{t} \\right) = rank \\left( T \\right) $

(ii) $ T^{t} $ 的范围是T的null space的annihilator

**定理** 设V和W为域F上的有限维向量空间，设 $ \\mathbb{B} $ 为V上有序基及 $ \\mathbb{B}^{ * } $ 为dual basis，设 $ \\mathbb{B}' $ 为W的有序基，及 $ \\mathbb{B}'^{*} $ 为dual basis，设T为从V到W上的线性变换，A是关于 $ \\mathbb{B}, \\mathbb{B}' $ 的T的矩阵，B为关于 $ \\mathbb{B}'^{ * }, \\mathbb{B}^{ * } $ 的 $ T^{t} $ 的矩阵，则 $ B_ {i j} = A_ {j i} $

证明：设

$ \\begin{equation} \\mathbb{B} = \\{ \\alpha_ {1}, \\ldots, \\alpha_ {n} \\}, \\qquad \\mathbb{B}' = \\{ \\beta_ {1}, \\ldots, \\beta_ {m} \\}, \\end{equation} $

$ \\begin{equation} \\mathbb{B}^{ * } = \\{ f_ {1}, \\ldots, f_ {n} \\}, \\qquad \\mathbb{B}'^{ * } = \\{ g_ {1}, \\ldots, g_ {m} \\} \\end{equation} $

根据定义，

$ \\begin{equation} T \\alpha_ {j} = \\sum_ {i=1}^{m}A_ {i j}\\beta_ {i}, \\qquad j = 1, \\ldots, n \\end{equation} $

$ \\begin{equation} T^{t}g_ {j} = \\sum_ {i=1}^{n}B_ {i j}f_ {i}, \\qquad j = 1, \\ldots, m \\end{equation} $

另一方面，

$ \\begin{eqnarray} \\left( T^{t} g_ {j} \\right) \\left( \\alpha_ {i} \\right) & = & g_ {j} \\left(T \\alpha_ {i} \\right) \\nonumber \\\\
& = & g_ {j} \\left( \\sum_ {k = i}^{m}A_ {k i}\\beta_ {k} \\right) \\nonumber \\\\
& = & \\sum_ {k=1}^{m}A_ {k i}g_ {j}\\left( \\beta_ {k} \\right) \\nonumber \\\\
& = & \\sum_ {k=1}^{m}A_ {k i}\\delta_ {j k} \\nonumber \\\\
& = & A_ {j i} \\end{eqnarray} $

对任意V上的linear functional f 有

$ \\begin{equation} f = \\sum_ {i=1}^{m}f\\left(\\alpha_ {i} \\right)f_ {i} \\end{equation} $

如果我们应用该式到functional $ f = T^{t}g_ {j} $ 且 $ \\left(T^{t}g_ {j}\\right)\\left( \\alpha_ {i} \\right) = A_ {j i} $，我们有

$ \\begin{equation} T^{t}g_ {j} = \\sum_ {i=1}^{n}A_ {j i}f_ {i} \\end{equation} $

则可得到 $ B_ {i j} = A_ {j i} $

**定义** 如果A为域F上的m x n矩阵，则transpose of A为n x m矩阵 $ A^{t} $ ，使得 $ A_ {i j}^{t} = A_ {j i} $
