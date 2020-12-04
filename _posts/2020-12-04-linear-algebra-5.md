---
layout:     post
title:      "Linear Algebra(Chapter 5) by Hoffman"
subtitle:   "Determinants"
thumbnail-img: ""
date:       2020-12-04 17:00
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

1.  [Modules](#orge434519)


<a id="orge434519"></a>

# Modules

如果K是带单位元的交换环，K上的module是一个代数系统，其行为跟向量空间相似。精确地说，V是K上的一个module（或K-module），如果

1.  V是一个交换群，V上有一个加法使得 $ \\left( \\alpha + \\beta \\right) \\to \\alpha + \\beta $
2.  有一个乘法使得 $ \\alpha \\in V, c \\in K, \\left(c, \\alpha\\right) \\to c\\alpha $，有
    
    $ \\begin{equation} \\left( c_ {1} + c_ {2}\\right) \\alpha = c_ {1}\\alpha + c_ {2}\\alpha \\end{equation} $
    
    $ \\begin{equation} c\\left( \\alpha_ {1} + \\alpha_ {2}\\right) = c\\alpha_ {1} + c\\alpha_ {2} \\end{equation} $
    
    $ \\begin{equation} \\left( c_ {1} c_ {2}\\right) \\alpha = c_ {1} \\left(c_ {2}\\alpha \\right) \\end{equation} $
    
    $ \\begin{equation} 1 \\alpha = \\alpha \\end{equation} $

**定义** K-module V被称为一个free module，如果它有一个基。如果V有有限个基包含n个元素，则V被称为一个free K-module with n generators

