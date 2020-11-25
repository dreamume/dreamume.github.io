---
layout:     post
title:      "Linear Algebra(Chapter 4) by Hoffman"
subtitle:   "Polynomials"
thumbnail-img: ""
date:       2020-11-24 17:00
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

1.  [Algebras](#org42f2702)
2.  [The algebra of Polynomials](#orgefd9580)


<a id="org42f2702"></a>

# Algebras

**定义** 设F为一个域，一个域F上的线性代数为F上的一个线性空间 $ \\mathbb{Q} $，及一个加操作称为向量乘法，对每个向量 $ \\alpha, \\beta $ in $ \\mathbb{Q} $，一个 $ \\mathbb{Q} $ 里的向量 $ \\alpha \\beta $称为 $ \\alpha $ 和 $ \\beta $的乘积，且有

(a) 乘法是可结合的， $ \\alpha \\left( \\beta \\gamma \\right) = \\left( \\alpha \\beta \\right) \\gamma $

(b) 乘法与加法结合， $ \\alpha \\left( \\beta + \\gamma \\right) = \\alpha \\beta + \\alpha \\gamma \\quad and \\quad \\left( \\alpha + \\beta \\right) \\gamma = \\alpha \\gamma + \\beta \\gamma $

(c) 对每个F中常数c，有 $ c \\left( \\alpha \\beta \\right) = \\left( c \\alpha \\right) \\beta = \\alpha \\left( c \\beta \\right) $

如果有一个 $ \\mathbb{Q} $ 上的元素1，使得 $ \\forall \\alpha \\in \\mathbb{Q} \\, , \\, 1 \\alpha = \\alpha 1 = \\alpha $，我们称 $ \\mathbb{Q} $ 为F上带单位值的线性代数，并称1为 $ \\mathbb{Q} $的单位值。如果 $ \\forall \\alpha, \\beta \\in \\mathbb{Q}, \\, \\alpha \\beta = \\beta \\alpha $，则称代数 $ \\mathbb{Q} $为可交换的。


<a id="orgefd9580"></a>

# The algebra of Polynomials

**定义** 设F[x]为向量 $ 1, x, x^{2}, \\ldots $ 扩展的 $ F^{\\infty} $ 的子空间，F[x]的元素被称为F上的polynomial

**定理** 设f和g为F上非零polynomials，则

(i) fg是一个非零polynomial

(ii) deg(fg) = deg f + deg g

(iii) fg是一个monic polynomial当且仅当f和g都是nomic polynomials

(iv) fg是一个常量polynomial当且仅当f和g都是常量polynomials

(v) 如果 $ f + g \\neq 0, \\quad deg\\left(f + g\\right) \\leq max\\left( deg f, deg g \\right) $
