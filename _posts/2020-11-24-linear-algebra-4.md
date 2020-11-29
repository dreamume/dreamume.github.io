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
3.  [Lagrange Interpolation](#org002fa21)
4.  [Polynomial Ideals](#org53cf227)
5.  [The Prime Factorization of a Polynomial](#org82b7e7e)


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


<a id="org002fa21"></a>

# Lagrange Interpolation

本节我们将假设F为固定域且 $ t_ {0}, t_ {1}, \\ldots, t_ {n} $ 为n + 1个F上不同元素。设V为F[x]的子空间包含所有小于等于n的polynomials，且设 $ L_ {i} $为从V到F的函数，定义为：

$ \\begin{equation} L_ {i}\\left(f \\right) = f \\left(t_ {i} \\right), \\qquad 0 \\leq i \\leq n\\end{equation} $

每个 $ L_ {i} $ 为V上的linear functional，$ L_ {0}, L_ {1}, \\ldots, L_ {n} $的集合为V<sup>\*</sup> 的基。

$ \\{ L_ {0}, L_ {1}, \\ldots, L_ {n} \\} $为以 $ \\{ P_ {0}, P_ {1}, \\ldots, P_ {n} \\} $ 为基的V的dual。则最多有一个这样的基，如果其存在则：

$ \\begin{equation} L_ {j}\\left(P_ {i}\\right) = P_ {i}\\left(t_ {j}\\right) = \\delta_ {i j} \\end{equation} $

则Polymonials

$ \\begin{equation} \\begin{aligned} P_ {i} &= \\frac{\\left(x - t_ {0}\\right) \\cdots \\left(x - t_ {i-1}\\right)\\left(x - t_ {i+1}\\right) \\cdots \\left(x - t_ {n} \\right)}{\\left(t_ {i} - t_ {0}\\right) \\cdots \\left(t_ {i} - t_ {i-1}\\right)\\left(t_ {i} - t_ {i+1}\\right) \\cdots \\left(t_ {i} - t_ {n}\\right)} \\\\ &= \\prod_ {j \\neq i}\\left(\\frac{x - t_ {j}}{t_ {i} - t_ {j}}\\right) \\end{aligned} \\end{equation} $

如果 $ f = \\sum_ {i}c_ {i}P_ {i} $，则对每个j，$ f\\left(t_ {j} \\right) = \\sum_ {i}c_ {i}P_ {i}\\left(t_ {j}\\right) = c_ {j} $

这样对每个V中的f，有

$ \\begin{equation} f = \\sum_ {i=0}^{n}f\\left(t_ {i}\\right)P_ {i} \\end{equation} $

该表达式被称为拉格朗日插值公式。

设 $ f = x^{i} $ 我们得到 $ x^{j} = \\sum_ {i=0}^{n}\\left(t_ {i}\\right)^{j}P_ {i} $

如果f是F上的任意polymonial，记  $ f^{ \\backsim } $ 为从F到F的polynomial函数映射F中每个t到f(t)。但可能对两个polynomials f 和 g，$ f \\neq g $，有 $ f^{ \\backsim } = g^{ \\backsim } $。幸运地是，这种情况只发生在域F只有有限个不同元素上。为精确描述polynomials和polynomial函数之间的关系。我们需要定义两个polynomial函数乘积。如果f，g是F上的polynomials，$ f^{ \\backsim } $ 和 $ g^{ \\backsim } $的乘积是从F到F的函数 $ f^{ \\backsim } g^{ \\backsim } $：

$ \\begin{equation} \\left(f^{ \\backsim }g^{ \\backsim }\\right)\\left(t\\right) = f^{ \\backsim }\\left(t\\right) g^{ \\backsim }\\left(t\\right), \\qquad t \\, in \\, F \\end{equation} $

因 $ \\left(fg\\right)\\left(t\\right) = f\\left(t\\right) g\\left(t\\right) $，对F中每个t，有

$ \\begin{equation} \\left(fg\\right)^{ \\backsim }\\left(t\\right) = f^{ \\backsim }\\left(t\\right) g^{ \\backsim }\\left(t\\right) \\end{equation} $

这样 $ f^{ \\backsim }g^{ \\backsim } = \\left(fg\\right)^{ \\backsim } $，也是一个polynomial函数。

**定义** 设F为一个域且设 $ \\mathbb{Q} $ 和 $ \\mathbb{Q}^{ \\backsim } $为F上的linear algebras。algebra $ \\mathbb{Q} $ 和 $ \\mathbb{Q}^{ \\backsim } $被称为同构的如果有一个 $ \\mathbb{Q} $ 到 $ \\mathbb{Q}^{ \\backsim } $ 的一对一映射 $ \\alpha \\to \\alpha^{ \\backsim } $，使得

(a) $ \\begin{equation} \\left(c\\alpha + d\\beta\\right)^{ \\backsim } = c\\alpha^{ \\backsim } + d\\beta^{ \\backsim } \\end{equation} $

(b) $ \\begin{equation} \\left(\\alpha \\beta\\right)^{ \\backsim } = \\alpha^{ \\backsim } \\beta^{ \\backsim } \\end{equation} $

对所有 $ \\alpha, \\beta \\, in \\, \\mathbb{Q} $ 及F上所有常量c，d。映射 $ \\alpha \\to \\alpha^{ \\backsim } $ 被称为 $ \\mathbb{Q} $ 到 $ \\mathbb{Q}^{ \\backsim } $上的同构。

**定理** 如果F是一个域包含无穷多个不同的元素，则映射 $ f \\to f^{ \\backsim } $是F上algebra of polynomials到F上algebra of polynomial函数的同构。


<a id="org53cf227"></a>

# Polynomial Ideals

如果c是polynomialf的一个根，则multiplicity of c为最大的正整数r使得 $ \\left( x - c \\right)^{r} $ 能被f整除。

**定义** 设F为一个域，一个F[x]中的ideal是F[x]的子空间M，使得fg属于M，f在F[x]中，g在M中。

例5，如果F是一个域且d是F上的一个polynomial，则集合M = dF[x]，对任意F[x]中的f，所有d的multiples df是一个ideal。因M为非空，M实际上包含d，如果f, g属于F[x]且c是一个常量，则

$ \\begin{equation} c \\left(df\\right) - dg = d \\left( cf - g\\right) \\end{equation} $

属于M，这样M是一个子空间。最后M也包含 $ \\left(df\\right)g = d\\left(fg\\right) $。ideal M被称为由d产生的principal ideal


<a id="org82b7e7e"></a>

# The Prime Factorization of a Polynomial

**定义** 设F为一个域，一个F[x]上的polynomial f被称为F上可约的如果F[x]上存在degree $ \\geq 1 $ 的polynomials g，h，使得f = gh，否则，f被称为在F上不可约的。一个F上非常数不可约polynomial被称为F上质polynomial，我们有时候称为F[x]上的一个质数。
