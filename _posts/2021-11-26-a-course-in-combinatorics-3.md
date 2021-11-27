---
layout:     post
title:      "A Course in Combinatorics(Chapter 3) by J. H. van Lint"
subtitle:   "Colorings of graphs and Ramsey's Theorem"
thumbnail-img: ""
date:       2021-11-26 06:10
author:     "dreamume"
tags: 		[discrete]
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

1.  [Colorings of graphs and Ramsey's theorem](#org634776c)


<a id="org634776c"></a>

# Colorings of graphs and Ramsey's theorem

**定理** 如果 $ K_ {n} $的边着上红色或蓝色，且 $ r_ {i}, i = 1, 2, \\ldots, n $，记为顶点i作为端点的红边个数。且如果 $ \\Delta $记为单色三角形的个数，则

$ \\Delta = {n \\choose 3} - \\frac{1}{2} \\sum^{n}_ {i=1} r_ {i}(n - 1 - r_ {i}) $

证明：$ K_ {n} $中每个三角形不是单色的话有两个顶点是红边和蓝边的交点。在第i个顶点上，两个这样的边可被选择有 $ r_ {i} (n - 1 - r_ {i}) $个，进而得证

**定理** 设 $ r \\ge 1 $且 $ q_ {i} \\ge r, i = 1, 2, \\ldots, s $。存在一个最小的正整数 $ N(q_ {1}, q_ {2}, \\ldots, q_ {s}; r) $有如下属性。设S为有n个元素的集合。假设所有 $ {n \\choose r} $ S的r子集被分割成一个互斥家族 $ T_ {1}, \\ldots, T_ {s} $（颜色）。则如果 $ n \\ge N(q_ {1}, q_ {2}, \\ldots, q_ {s}; r) $有一个i，$ 1 \\le i \\le s $，且一些 $ q_ {i} $S的子集，其每个r子集在 $ T_ {i} $中

证明：我们只给出s = 2时的证明。一般化情况只多了些记账步骤

(a) 定理对r = 1且N(p,q;1) = p + q - 1来说是真的

(b) 对任意r和 $ p \\ge r $，明显地N(p,r;r) = p且相似地N(r,q;r) = q, $ q \\ge r $

(c) 我们使用归纳法。假设定理对r - 1时是真的。我们现在看p + q，使用(b)。这样我们可定义 $ p_ {1} = N(p - 1, q; r), q_ {1} = N(p, q - 1; r) $。设S为有n个元素的集合，$ n \\ge 1 + N(p_ {1}, q_ {1}; r - 1) $。设S的r子集用两种颜色着色，分别为红色和蓝色。在 $ K_ {6} $的证明中，我们任意选S中的一个元素a。我们现在定义一个$ S^{\\prime} $的着色(r - 1)子集，$ S^{\\prime} := S \\ \\{a \\} $，给定 $ X \\subseteq S^{\\prime} $跟 $ X \\cup \\{a\\} $有相同的颜色。通过归纳 $ S^{\\prime} $要么包含一个大小为 $ p_ {1} $的子集A使得所有它的(r - 1)子集为红色或一个大小为 $ q_ {1} $的子集B使得所有它的(r - 1)子集为蓝色。不失一般性这里我们说第一种情况发生。因为A有 $ N(p - 1, q; r) $个元素，存在两种可能。第一是A有一个q元素的子集其所有r子集为蓝色。另一种是A有一个p - 1元素的子集 $ A^{\\prime} $其所有r-子集为红色。集合 $ A^{\\prime} \\cup \\{a \\} $也有这个属性因为 $ A^{\\prime} \\subseteq A $。这证明了定理且进一步我们显示

$ N(p,q;r) \\le N(N(p-1,q;r), N(p, q-1;r);r-1) + 1 $

上式的一个特殊情况发生在当我们回到两个颜色的一个图形着色(r = 2)时。使用(a)我们发现

$ N(p,q;2) \\le N(p-1,q;2) + N(p,q-1;2) $
