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

  设c(n, k)记为$ \\pi \\in S_ {n} $带k个循环的排列数（该数被称为无符号第一种类型的Stirling数）。进一步定义c(0, 0) = 1和c(n, k) = 0如果$ n \\le k$ 或 $ k \\le 0, (n, k) \\ne (0, 0) $。第一种类型Stirling数s(n, k)被定义为

$ s(n, k) := (-1)^{n-k} c(n, k) $

**定理 13.2** 数c(n, k)满足递归关系

$ c(n, k) = (n-1)c(n-1, k) + c(n-1, k-1) $

证明：如果 $ \\pi $是 $_ {n-1} $中带k个循环的一个排序，则有n - 1个位置我们可插入整数n来生成一个 $ \\pi^{\\prime} \\in S_ {n} $带k个循环的一个排列。我们也可邻接(n)作为一个循环到任意带k - 1个循环的$ S_ {n-1} $排列中。这统计了等式的右边

**定理 13.3** 对$ n \\ge 0 $我们有

$ \\sum^{n}_ {k=0} c(n, k)x^{k} = x(x+1) \\ldots (x+n-1) $

且

$ \\sum^{n}_ {k=0} s(n, k)x^{k} = (x)_ {n} $

证明：写上上式的右边为

$ F_ {n}(x) = \\sum^{n}_ {k=0}b(n, k)x^{k} $

b(0, 0) = 1，定义b(n, k) := 0如果 $ n \\le 0 $或 $ k \\le 0, (n,k) \\ne (0,0) $。因为

$ \\begin{aligned} F_ {n}(x) &= (x + n - 1)F_ {n-1}(x) \\\\ &= \\sum^{n}_ {k=1} b(n-1, k-1) x^{k} + (n-1) \\sum^{n-1}_ {k=0} b(n-1, k) x^{k} \\end{aligned} $

我们看到数b(n, k)满足和c(n, k)相同的递归关系，因为数对 $ n \\le 0 $或 $ k \\le 0 $时相同，则对所有n和k都相同

我们现在定义第二类Stirling数：记为P(n, k)，把一个n个元素集合分成k个非空子集的所有划分的集合，则

$ S(n, k) := \| P(n, k) \| $

**定理 13.4** 第二类Stirling数满足关系

$ S(n, k) = kS(n-1, k) + S(n-1, k-1) $

证明：证明了定理13.3的相同。一个集合 $ \\{1,2,\\ldots,n-1\\} $的分区可通过n加入一个分区或作为 $ \\{n \\} $的一个新分区

我们定义Bell数B(n)为一个n个元素集合的总分区数，例如

$ B(n) := \\sum^{n}_ {k=1}S(n, k), \\qquad (n \\ge 1) $

**定理 13.5** 对 $ n \\ge 0 $我们有

$ x^{n} = \\sum^{n}_ {k=0} S(n, k)(x)_ {k} $

证明：我们首先标记从一个n元素集合到k元素集合的满射数为 $ k! S(n,k) $（一个分区块是k集合元素的反转像）。这样通过例子10.2，我们有

$ S(n, k) = \\frac{1}{k!} \\sum^{k}_ {i=0} (-1)^{i} {k \\choose i} (k-i)^{n} = \\frac{1}{k!} \\sum^{k}_ {i=0} (-1)^{k-i} {k \\choose i} i^{n} $

现在让x为一个整数，有 $ x^{n} $个映射从n个元素集合 $ N := \\{1,2,\\ldots, n\\} $到x元素集合 $ \\{1,2,\\ldots, x\\} $。对 $ \\{1,2,\\ldots, x\\} $的任意k元素集合Y，有 $ k! S(n, k) $个从N到Y的满射。这样我们找到

$ x^{n} = \\sum^{n}_ {k=0} {x \\choose k} k! S(n, k) = \\sum^{n}_ {k=0} S(n, k) (x)_ {k} $
