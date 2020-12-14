---
layout:     post
title:      "Probability: Theory and Exmaples(Chapter 1) by Durrett"
subtitle:   "Measure Theory"
thumbnail-img: ""
date:       2020-12-11 01:00
author:     "dreamume"
tags: 		[probability]
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

1.  [Measure Theory](#org5966362)
    1.  [Probability Spaces](#orga94cfd0)


<a id="org5966362"></a>

# Measure Theory


<a id="orga94cfd0"></a>

## Probability Spaces

一个Probability space是一个3元组 $ \\left(\\Omega, \\mathcal{F}, P\\right), \\Omega $是输出的集合，$ \\mathcal{F} $是事件集合，$ P : \\mathcal{F} \\to [0, 1] $是一个事件概率函数。我们假设 $ \\mathcal{F} $是一个 $ \\sigma $域（或 $ \\sigma $代数），例如，一个 $ \\Omega $的子集的（非空）集合满足

(i) 如果 $ A \\in \\mathcal{F} $，则 $ A^{c} \\in \\mathcal{F} $，且

(ii) 如果 $ A_ {i} \\in \\mathcal{F} $ 是集合的可数序列则 $ \\cup_ {i}A_ {i} \\in \\mathcal{F} $

这里及如下的可数表示有限或可数无穷个。因为 $ \\cap_ {i}A_ {i} = \\left(\\cup_ {i}A_ {i}^{c}\\right)^{c} $，它说明一个 $ \\sigma $域在可数个交集下是闭合的。我们忽略定义最后的属性使它容易检查。

没有P的话，$ \\left(\\Omega, \\mathcal{F} \\right) $称为度量空间，例如，它是一个可以测量的空间。一个度量是一个非负可数加集函数；即一个函数 $ \\mu : \\mathcal{F} \\to R $，有

(i) $ \\forall A \\in \\mathcal{F}, \\mu\\left(A\\right) \\ge \\mu\\left(\\emptyset\\right) = 0 $，且

(ii) 如果 $ A_ {i} \\in \\mathcal{F} $是一个不相交集合的可数序列，则

$ \\begin{equation} \\mu\\left(\\cup_ {i}A_ {i}\\right) = \\sum_ {i}\\mu\\left(A_ {i}\\right) \\end{equation} $

如果 $ \\mu\\left(\\Omega\\right) = 1 $，我们称 $ \\mu $ 为一个概率测度。本书中，概率测度通常记为P

下面的结果给了我们后面需要的度量定义的一些结论。在所有的例子中，我们假设我们提到的集合在 $ \\mathcal{F} $中

**定理 1.1.1** 设 $ \\mu $为 $ \\left(\\Omega, \\mathcal{F}\\right) $上的一个测度

(i) 单调性，如果 $ A \\subset B 则 \\mu\\left(A\\right) \\le \\mu\\left(B\\right) $

(ii) 子加和，如果 $ A \\subset \\cup_ {m=1}^{\\infty} A_ {m} 则 \\mu\\left(A\\right) \\le \\sum_ {m=1}^{\\infty}\\mu\\left(A_ {m}\\right) $

(iii) 连续向下，如果 $ A_ {i} \\uparrow A $（例如，$ A_ {1} \\subset A_ {2} \\subset \\ldots $ 且 $ \\cup_ {i}A_ {i} = A $）则 $ \\mu\\left(A_ {i}\\right) \\uparrow \\mu\\left(A\\right) $

(iv) 连续向上，如果 $ A_ {i} \\downarrow A $（例如，$ A_ {1} \\supset A_ {2} \\supset \\ldots $ 且 $ \\cap_ {i}A_ {i} = A, \\mu\\left(A_ {1}\\right) < \\infty $）则 $ \\mu\\left(A_ {i}\\right) \\downarrow \\mu\\left(A\\right) $

例子 1.1.3 实数线上的度量。$ (\\mathbf{R}, \\mathcal{R}) $上的度量被定义为给定一个Stieltjes度量函数，有以下属性：

(i) F是非递减的

(ii) F是右连续的，例如 $ lim_ {y \\downarrow x} F\\left(y\\right) = F\\left(x\\right) $

**定理 1.1.4** 对于每个Stieltjes度量函数，有一个在 $ (\\mathbf{R}, \\mathcal{R}) $上唯一的度量 $ \\mu, \\mu\\left( (a, b]\\right) = F\\left(b\\right) - F\\left(a\\right) $

F(x) = x 该度量被称为Lebesgue度量

集合的集 $ \\mathbf{S} $为称为是一个semialgebra如果 (i) 它在交集下是闭合的，例如，$ S, T \\in \\mathbf{S} $ 意味着 $ S \\cap T \\in \\mathbf{S} $，且 (ii) 如果 $ S \\in \\mathbf{S} $则 $ S^{c} $是 $ \\mathbf{S} $中有限不相关集合的并。一个重要的semialgebra例子是

例子 1.1.5 $ \\mathbf{S}_ {d} = $ 空集加上如下形式的所有集合

$ \\begin{equation} (a_ {1}, b_ {1}] \\times \\cdots \\times (a_ {d}, b_ {d}] \\subset \\mathbf{R}^{d} \\qquad - \\infty \\le a_ {i} < b_ {i} \\le \\infty \\end{equation} $

**引理 1.1.7** 如果 $ \\mathcal{S} $ 是一个semialgebra则 $ \\bar{\\mathcal{S}} = \\{ \\mathcal{S}中有限不相交集合的并 \\} $是一个代数，称为由 $ \\mathcal{S} $产生的代数

代数 $ \\mathcal{A} $上的度量，我们表示为一个集合函数 $ \\mu $，

(i) $ \\forall A \\in \\mathcal{A}, \\mu\\left(A\\right) \\ge \\mu\\left(\\emptyset\\right) = 0 $，且

(ii) 如果 $ A_ {i} \\in \\mathcal{A} $是不相交的且它们的并在 $ \\mathcal{A} $中，则

$ \\begin{equation} \\mu\\left(\\cup_ {i=1}^{\\infty}A_ {i}\\right) = \\sum_ {i=1}^{\\infty}\\mu\\left(A_ {i}\\right) \\end{equation} $

$ \\mu $被称为是 $ \\sigma-finite $如果有一个集合序列 $ A_ {n} \\in \\mathcal{A} $，使得 $ \\mu\\left( A_ {n} \\right) < \\infty $ 且 $ \\cup_ {n}A_ {n} = \\Theta $。设 $ A'_ {1} = A_ {1} $且对 $ n \\ge 2 $，

$ \\begin{equation} A'_ {n} = \\cup_ {m=1}^{n}A_ {m} \\qquad 或 \\qquad A'_ {n} = A_ {n} \\cap \\left(\\cap_ {m=1}^{n-1}A_ {m}^{c}\\right) \\in \\mathcal{A} \\end{equation} $

我们可不失一般性假设 $ A_ {n} \\uparrow \\Theta $ 或 $ A_ {n} $是不相交的。
