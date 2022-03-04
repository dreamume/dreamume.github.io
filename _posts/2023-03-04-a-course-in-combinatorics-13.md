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
