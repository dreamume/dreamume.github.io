---
layout:     post
title:      "A Course in Combinatorics(Chapter 13) by J. H. van Lint"
subtitle:   "Elementary counting; Stirling numbers"
thumbnail-img: ""
date:       2022-03-04 13:00
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



下面几个章节将专注于统计技术和一些特殊的组合统计问题。我们开始一些常用的基本方法。考虑从 $ \\{1, 2, \\ldots, n\\} $到 $ \\{1, 2, \\ldots, k\\} $的映射。它们总共的数量为$ k^{n} $。在之前的例子中我们学习了映射需要是满射的情况。如果映射是单射，则它们的数是如下因子

$ (k)_ {n} := k(k-1) \\ldots (k-n+1) = k! / (k-n)! $

我们现在考虑一个相似的问题。n个被映射的对象相同但像不同。我们形式化如下。我们有n个不同的球将放入k个盒子中，记为 $ 1, 2, \\ldots, k $。有多少种不同的放法？可用如下的技巧找到答案。想象球被染成蓝色且排列到它们想要放入的盒子前。则在两个连续的盒子间插入一个红球。我们得到一个n + k - 1个球排列，k-1个红球，这样问题的答案为 $ {n+k-1 \\choose k-1} $。我们形式化为一个定理

**定理13.1** 等式的解决方案数

$ x_ {1} + x_ {2} + \\cdots + x_ {k} = n $

为非负整数 $ {n+k-1 \\choose k-1} $

证明：解释 $ x_ {i} $为在第i个盒子中的球数

**推论** 以上等式正整数的解决方案为 $ {n-1 \\choose k-1} $

证明：用 $ y_ {i} := x_ {i} - 1 $替代。则 $ \\sum y_ {i} = n - k $，再用以上定理即可得证

**例子 13.1** 模拟之前10.6例子，我们考虑从整数 $ 1, 2, \\ldots, n $选择r个整数使得选择出的整数没有连续的。设 $ x_ {1} < x_ {2} < \\cdots < x_ {r} $为这样的序列。则 $ x_ {1} \\ge 1, x_ {2} - x_ {1} \\ge 2, \\ldots, x_ {r} - x_ {r-1} \\ge 2 $。定义

$ y_ {1} := x_ {1}, y_ {i} := x_ {i} - x_ {i-1} - 1, 2 \\le i \\le r, y_ {r+1} := n - x_ {r} + 1 $

则 $ y_ {i} $为正整数且 $ \\sum^{r+1}_ {i=1} y_ {i} = n - r + 2 $。这样通过之前的定理，我们得到 $ {n-r+1 \\choose r} $

**例子 13.3** 我们希望分割 $ \\{1, 2, \\ldots, n\\} $为 $ b_ {1} $个大小为1的子集，$ b_ {2} $个大小为2的子集，$ \\ldots $，$ b_ {k} $个大小为k的子集。这样 $ \\sum^{k}_ {i=1}i b_ {i} = n $。进一步，相同cardinality的子集可被排序，这样解决方案为

$ \\frac{n!}{b_ {1}! \\ldots b_ {k}! (1!)^{b_ {1}} (2!)^{b_ {2}} \\ldots (k!)^{b_ {k}}} $

**例子 13.4** 设A遍历$ \\{1,2,\\ldots,n\\} $所有的子集。计算 $ S = \\sum \| A \| $。因为大小为i的子集有 $ {n \\choose i} $，我们必须计算 $ \\sum^{n}_ {i=0}i {n \\choose i} $。通过求导 $ (1 + x)^{n} $，我们发现

$ \\sum^{n}_ {i=1}i {n \\choose i} x^{i-1} = n(1 + x)^{n-1} $ 

且取x = 1得到答案 $ S = n \\cdot 2^{n-1} $。如果我们花多一点时间思考，则该答案是明显的。一个集合A和它的补总共含有n个元素且它们有 $ 2^{n-1} $个这样的对

**例子 13.5** 在第10章我们看到一些包含二项式系数公式的例子，其用组合证明比直接证明更容易。熟悉的关系

$ \\sum^{n}_ {k=0} {n \\choose k}^{2} = {2n \\choose n} $

是另一个例子。当然我们可通过确定在 $ (1+x)^{n} (1+x)^{n} $中 $ x^{n} $的系数来计算且使用组合公式。然而，该式的每边只统计从n个红球和n个蓝球中选择n个球的方法

我们考虑一个更复杂的例子。多少个序列 $ A_ {1}, \\ldots, A_ {k}, A_ {i} \\subseteq \\{1,2,\\ldots, n\\}, 1 \\le i \\le k, \\cup^{k}_ {i=1}A_ {i} = \\{1,2,\\ldots,n\\} $？因为我们希望避免j，$ 1 \\le j \\le n $，不是 $ A_ {i} $的并中的元素，我们尝试使用包含排除方法。如果我们从 $ \\{1,2,\\ldots,n\\} $中选择i个元素且考虑所有序列 $ A_ {1}, \\ldots, A_ {k} $不包含任何这些i个元素，则我们有 $ (2^{n-i})^{k} $个序列。通过之前的定理，问题的答案是

$ \\sum^{n}_ {i=0} (-1)^{i} {n \\choose i} 2^{(n-i)k} = (2^{k}-1)^{n} $

如果我们描述一个系列 $ A_ {1}, \\ldots, A_ {k} $为一个(0, 1)的大小为 $ k \\times n $的矩阵，子集的特征函数作为它的行，则序列的条件描述A没有全为零的列。这样有 $ (2^{k} - 1)^{n} $个这样的矩阵
