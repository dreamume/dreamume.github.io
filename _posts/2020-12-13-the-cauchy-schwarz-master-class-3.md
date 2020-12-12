---
layout:     post
title:      "The Cauchy-Schwarz master class(Chapter 3) by Steele"
subtitle:   "Lagrange's Identity and Minkowski's Conjecture"
thumbnail-img: ""
date:       2020-12-13 02:00
author:     "dreamume"
tags: 		[elementary]
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

1.  [PASSAGE TO A MORE GENERAL IDENTITY](#orgd139ef4)

对于等式 $ \\left(a_ {1}^{2} + a_ {2}^{2}\\right) \\left(b_ {1}^{2} + b_ {2}^{2}\\right) = \\left(a_ {1}b_ {1} + a_ {2}b_ {2}\\right)^{2} + \\left(a_ {1}b_ {2} - a_ {2}b_ {1}\\right)^{2} $，当

$ \\begin{equation} a_ {1} = \\lambda b_ {1} 且 a_ {2} = \\lambda b_ {2} \\qquad 对某些实数 \\lambda \\end{equation} $

时，$ \\left(a_ {1}b_ {2} - a_ {2}b_ {1}\\right)^{2} = 0 $。


<a id="orgd139ef4"></a>

# PASSAGE TO A MORE GENERAL IDENTITY

对于更一般化的公式，我们设 $ Q_ {n} $为

$ \\begin{equation} \\left(a_ {1}^{2} + a_ {2}^{2} + \\cdots + a_ {n}^{2}\\right) \\left(b_ {1}^{2} + b_ {2}^{2} + \\cdots + b_ {n}^{2}\\right) - \\left(a_ {1}b_ {1} + a_ {2}b_ {2} + \\cdots + a_ {n}b_ {n}\\right)^{2} \\end{equation} $

我们可简化重写为

$ \\begin{equation} Q_ {n} = \\sum_ {i=1}^{n} \\sum_ {j=1}^{n}a_ {i}^{2}b_ {j}^{2} - \\sum_ {i=1}^{n} \\sum_ {j=1}^{n}a_ {i}b_ {i}a_ {j}b_ {j} \\end{equation} $

为使得等式更有对称性，我们再重写为

$ \\begin{equation} Q_ {n} = \\frac{1}{2}\\sum_ {i=1}^{n} \\sum_ {j=1}^{n}\\left(a_ {i}^{2}b_ {j}^{2} + a_ {j}^{2}b_ {i}^{2}\\right) - \\sum_ {i=1}^{n} \\sum_ {j=1}^{n}a_ {i}b_ {i}a_ {j}b_ {j} \\end{equation} $

我们分解一下，有

$ \\begin{equation} Q_ {n} = \\frac{1}{2}\\sum_ {i=1}^{n} \\sum_ {j=1}^{n} \\left\\{ a_ {i}^{2}b_ {j}^{2} - 2a_ {i}b_ {j}a_ {j}b_ {i} + a_ {j}^{2}b_ {i}^{2} \\right\\} = \\frac{1}{2}\\sum_ {i=1}^{n} \\sum_ {j=1}^{n} \\left(a_ {i}b_ {j} - a_ {j}b_ {i}\\right)^{2} \\end{equation} $

整理之后我们得到Lagrange's Identity:

$ \\begin{equation} \\left(\\sum_ {i=1}^{n}a_ {i}b_ {i}\\right)^{2} = \\sum_ {i=1}^{n}a_ {i}^{2} \\sum_ {i=1}^{n}b_ {i}^{2} - \\frac{1}{2}\\sum_ {i=1}^{n} \\sum_ {j=1}^{n}\\left(a_ {i}b_ {j} - a_ {j}b_ {i}\\right)^{2} \\end{equation} $
