---
layout:     post
title:      "An invitation to discrete mathematics(Chapter 10) by Matousek"
subtitle:   "Probability by counting"
thumbnail-img: ""
date:       2021-07-15 09:00
author:     "dreamume"
tags: 		[discrete math]
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

1.  [统计证明](#org6e1a4a6)
    1.  [命题](#org0817386)
    2.  [问题](#org7e2a47f)
    3.  [定理](#orge96eef9)
    4.  [定理 $ m(3) \\&ge; 7 $](#org9b71866)


<a id="org6e1a4a6"></a>

# 统计证明


<a id="org0817386"></a>

## 命题

存在一个n个变量的布尔函数不能被任意少于 $ 2^{n} / \\log_ {2}{(n+8)} $个符号的公式定义。例如，对23个变量我们需要超过一百万个符号的公式

**证明** 所有n个变量的布尔函数的数量是 $ 2^{2^{n}} $，其n个变量公式的数量被最多m个符号写出的不超过 $ (n + 8)^{m} $个，因为公式中每m个位置可被n + 7个可能的符号填充，或可能是空白。这样，我们也统计了许多无意义的字符串符号，但一个初略的上限是有的。如果 $ 2^{2^{n}} > (n + 8)^{m} $，则存在一个布尔函数不能被最多m个符号表达。通过算法中的不等式，我们获得 $ m \\ge 2^{n} / \\log_ {2}{(n+8)} $


<a id="org7e2a47f"></a>

## 问题

假设 $ \\mathcal{M} $的每个集合都是k个元素。则 $ \\mathcal{M} $系统中不能两颜色着色的最小的个数m(k)是多少？

容看得到m(2) = 3，因为我们需要3条边来使图形不能两分。但对k = 3时问题要复杂很多。在之前的章节中，我们有一个7个3元组的系统不是两着色的，名为Fano plane，这样m(3) <= 7。事实上，m(3) = 7；为证明这个，我们需要显示所有6个或更少的3元组系统是可以两着色的。我们开始一个一般化陈述来给定一个k = 3的弱化边界。然后，对某些更大的效应，我们将改进k = 3的特殊情况的结果


<a id="orge96eef9"></a>

## 定理

我们有 $ m(k) \\ge 2^{k-1} $，例如，任意大小为k的系统集合元素个数小于 $ 2^{k-1} $是一个两着色的

**证明** 设 $ \\mathcal{M} $为某个集合X的k元素子集的系统，且设 $ \| \\mathcal{M} \| = m $。我们通过如下随机过程给X的每个点着上红色或白色。对每个点 $ x \\in X $，我们投一个硬币。如果我们得到头面我们把x着上白色否则我们着上红色

设 $ M \\in \\mathcal{M} $为考虑的系统中k元组之一。M中所有点在随机着色中获得相同颜色的概率是什么？所有k个点同时为白色的概率是 $ 2^{-k} $，且所有点同时为红色的概率为 $ 2^{-k} $。M不是同为一个颜色的概率为 $ 2 \\cdot 2^{-k} = 2^{1-k} $。因此 $ \\mathcal{M} $中m个集合至少一个是单色的概率是 $ m2^{1-k} $。如果该数字严格小于1，例如，如果 $ m < 2^{k-1} $，则我们随机着色是两着色对系统 $ \\mathcal{M} $是一个非零的概率。因此，至少一个两着色存在

对很大的k，函数m(k)增长$ 2^{k} $（更精确地，我们有 $ m(k) = \\Theta(2^{k}k^{1/3}) $且 $ m(k) = O(2^{k}k^{2}) $；）且这样定理给出一个非常好的主意，另一方面，对k = 3我们只给出估计 $ m(k) \\ge 4 $，我们使用两个技巧改进该边界


<a id="org9b71866"></a>

## 定理 $ m(3) \\ge 7 $

