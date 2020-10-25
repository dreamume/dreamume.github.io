---
layout:     post
title:      "Calculus on manifolds(Chapter 1) by Spivak"
subtitle:   "Functions on Euclidean Space"
thumbnail-img: ""
date:       2020-10-25 09:00
author:     "dreamume"
tags: 		[calculus]
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

1.  [Functions on Euclidean Space](#org73ef655)
    1.  [NORM和INNER PRODUCT](#org511b687)
    2.  [SUBSETS OF EUCLIDEAN SPACE](#org3861630)
    3.  [FUNCTIONS AND CONTINUITY](#org3337c7e)


<a id="org73ef655"></a>

# Functions on Euclidean Space


<a id="org511b687"></a>

## NORM和INNER PRODUCT

在向量空间定义向量x的长度，我们通常记为norm \|x\|，$ \|x\|=\\sqrt{\\left(x^{1}\\right)^{2}+\\cdots+\\left(x^{n}\\right)^{2}} $

向量x和y的inner product记为<x,y>, $ \\langle x, y\\rangle=\\frac{\|x+y\|^{2}-\|x-y\|^{2}}{4} $


<a id="org3861630"></a>

## SUBSETS OF EUCLIDEAN SPACE

一个集合A被称为是紧的，仅当每个开覆盖 $ \\Theta $ 包含有限个开集合能覆盖A。


<a id="org3337c7e"></a>

## FUNCTIONS AND CONTINUITY

定理：如果 $ f: A \\rightarrow \\mathbf{R}^{m} $ 连续，$ A \\subset \\mathbf{R}^{n} $ 且 A是紧的，则 $ f(A) \\subset \\mathbf{R}^{m} $ 也是紧的。

如果 $ f: A \\rightarrow \\mathbf{R}^{m} $ 有界，$ a \\in A $ ，$ \\delta>0 $ ，有 $ \\begin{equation} \\begin{aligned} M(a, f, \\delta) &=\\sup \\{f(x): x \\in A \\text { and }\|x-a\|<\\delta\\} \\\\ m(a, f, \\delta) &=\\inf \\{f(x): x \\in A \\text { and }\|x-a\|<\\delta\\} \\end{aligned} \\end{equation} $

在a点的震荡函数o(f, a)定义为 $ o(f, a) = \\lim _{\\delta \\rightarrow 0}[M(a, f, \\delta)-m(a, f, \\delta)] $

定理：有界函数f在a点连续当且仅当o(f, a) = 0

