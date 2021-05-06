---
layout:     post
title:      "An invitation to discrete mathematics(Chapter 8) by Matousek"
subtitle:   "The number of spanning trees"
thumbnail-img: ""
date:       2021-05-07 06:40
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

1.  [结果](#org4f39a9a)
    1.  [定理（Cayley公式）](#orgfb9c108)
    2.  [A proof via score](#org6c78265)
        1.  [命题](#org6275426)


<a id="org4f39a9a"></a>

# 结果

对一个给定的图形G，设T(G)记为G的所有伸展树的个数，我们有 $ T(K_ {3}) = 3 $。在本章中，我们呈现如下结果的几个证明：


<a id="orgfb9c108"></a>

## 定理（Cayley公式）

对每个 $ n \\ge 2 $，$ T(K_ {n}) $的个数，例如，给定n个顶点的树的个数，为 $ n^{n-2} $


<a id="org6c78265"></a>

## A proof via score


<a id="org6275426"></a>

### 命题

设 $ d_ {1}, d_ {2}, \\ldots, d_ {n} $为正整数，其和为2n - 2，则对 $ i = 1, 2, \\ldots, n $的顶点i有度数为 $ d_ {i} $的图形 $ K_ {n} $的伸展树的个数为

$ \\frac{(n - 2)!}{(d_ {1} - 1)! (d_ {2} - 1)! \\cdots (d_ {n} - 1)! } $

**证明** 使用归纳法。对n = 1, 2，命题显然成立，所以设n > 2，因为 $ d_ {i} $的和小于2n，存在一个i，其 $ d_ {i} = 1 $。我们现在假设 $ d_ {n} = 1 $

设 $ \\mathcal{T} $为 $ K_ {n} $的所有伸展树的集合。分类 $ \\mathcal{T} $的树为n - 1个组 $ \\mathcal{T}_ {1}, \\ldots, \\mathcal{T}_ {n - 1} $: 集合 $ \\mathcal{T}_ {j} $包含所有顶点n连接到顶点j的 $ \\mathcal{T} $的树。接着，我们考虑 $ \\mathcal{T}_ {j} $中的树，且我们删除顶点n及它的度数。我们获得一个 $ K_ {n-1} $的伸展树，其顶点i的度数为 $ d_ {i}, i \\ne j $和 $ d_ {j} - 1, i = j $。容易看到这样我们获得一个集合 $ \\mathcal{T}_ {j} $到 $ K_ {n-1} $的所有伸展树的集合 $ \\mathcal{T}^{\\prime}_ {j} $的双射，顶点为 $ d_ {1}, d_ {2}, \\ldots, d_ {j-1}, d_ {j} - 1, d_ {j+1}, \\ldots, d_ {n-1} $

通过归纳假设，我们有

$ \\begin{aligned} \| \\mathcal{T}_ {j} \| &= \| \\mathcal{T}^{\\prime}_ {j} \| = \\frac{(n-3)!}{(d_ {1} - 1)! \\cdots (d_ {j-1} - 1)! (d_ {j} - 2)!(d_ {j+1} - 1)! \\cdots (d_ {n-1} - 1)!} \\\\ &= \\frac{(n-3)! (d_ {j} - 1)}{(d_ {1} - 1)! (d_ {2} - 1)! \\cdots (d_ {n-1} - 1)!} \\end{aligned} $

当 $ d_ {j} = 1 $时该公式也成立，它使得在顶点j没有伸展树，$ d_ {j} - 1 = 0 $

因此，顶点度数为 $ d_ {1}, d_ {2}, \\ldots, d_ {n}, d_ {n} = 1 $的n个顶点的伸展树个数为

$ \\begin{aligned} \| \\mathcal{T} \| &= \\sum^{n}_ {j=1} \| \\mathcal{T}_ {j} \| = \\sum^{n-1}_ {j=1} \\frac{(n-3)! (d_ {j} - 1)}{(d_ {1} - 1)! (d_ {2} - 1)! \\cdots (d_ {n-1} - 1)!} \\\\ &= \\left(\\sum^{n-1}_ {j=1}(d_ {j} - 1)\\right) \\frac{(n-3)!}{(d_ {1} - 1)!(d_ {2} - 1)! \\cdots (d_ {n-1} - 1)!} \\\\ &= \\frac{(n-2)(n-3)!}{(d_ {1} - 1)! (d_ {2} - 1)! \\cdots (d_ {n-1} - 1)!} \\end{aligned} $

我们加上所有可能scores的伸展树，得到

$ \\begin{aligned} T\\left(K_{n}\\right) &=\\sum_{d_{1}, d_{2}, \\ldots, d_{n} \\geq 1 \\atop d_{1}+d_{2}+\\cdots+d_{n}=2 n-2} \\frac{(n-2) !}{\\left(d_{1}-1\\right) !\\left(d_{2}-1\\right) ! \\cdots\\left(d_{n}-1\\right) !} \\\\ &=\\sum_{k_{1}+k_{2}+\\cdots+k_{n}=n-2}{k_{1}, \\ldots, k_{n} \\geq 0} \\frac{(n-2) !}{k_{1} ! k_{2} ! \\cdots k_{n} !} \\\\ &=(\\underbrace{1+1+\\cdots+1}_{n \\times})^{n-2}=n^{n-2} . \\end{aligned} $
