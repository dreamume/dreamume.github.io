---
layout:     post
title:      "Linear  Algebra(Chapter 2) by Hoffman"
subtitle:   "Vector Spaces"
thumbnail-img: ""
date:       2020-10-31 10:00
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

1.  [Vector Spaces](#orgf089874)


<a id="orgf089874"></a>

# Vector Spaces

定义：一个向量空间（或线性空间）包含如下：

1.  一个域F的标量
2.  一个对象集合V，称为向量
3.  一个规则（或操作），称为向量加法，对于每一对V中的向量 $ &alpha;, &beta; $ ，向量 $ &alpha; + &beta; $ 也在V中，有：
    1.  加法可交换， $ \\alpha + \\beta = \\beta + \\alpha $
    2.  加法可结合， $ \\alpha + ( \\beta + \\gamma ) = ( \\alpha + \\beta ) + \\gamma $
    3.  V中有一个向量0，称为零向量，对任意 $ \\alpha \\in V, \\alpha + 0 = \\alpha $
    4.  对任意向量 $ \\alpha, \\text{存在唯一一个向量} - \\alpha \\in V, \\alpha + (-\\alpha) = 0 $
4.  一个规则（或操作）称为标量乘法，对于每个标量c和向量 $ \\alpha \\in V $ ，称为c 和 $ \\alpha $ 的乘积：
    1.  对任意 $ \\alpha \\in V, 1 \\alpha = \\alpha $
    2.  $ ( c_{1} c_{2} ) \\alpha = c_{1} (c_{2} \\alpha) $
    3.  $ c (\\alpha + \\beta) = c \\alpha + c \\beta $
    4.  $ (c_{1} + c_{2}) \\alpha = c_{1} \\alpha + c_{2} \\alpha $

