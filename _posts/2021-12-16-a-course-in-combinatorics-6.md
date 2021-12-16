---
layout:     post
title:      "A Course in Combinatorics(Chapter 6) by J. H. van Lint"
subtitle:   "Dilworth's theorem and extremal set theory"
thumbnail-img: ""
date:       2021-12-16 12:10
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



**定理** 设P为一个偏序有限集合。包含P的所有元素的不相交chain的最小数m等于P的antichain元素中的最大个数M

证明：(i) $ m \\ge M $时是明显的

(ii) 我们使用归纳法。如果 $ \| P \| = 0 $，则不用证明。设C为P中一个最大chain。如果 $ P \\ C $中每个antichain包含最多 $ M - 1 $个元素，则得证。这样假设 $ \\{a_ {1}, \\ldots, a_ {M}\\} $是 $ P \\ C $中的一个antichain。现在定义 $ S^{-} := \\{ x \\in P: \\exists_ {i} [x \\le a_ {i}]\\} $，且相似的定义 $ S^{+} $。因为C是一个最大chain，C中最大的元素不在 $ S^{-} $，且因此通过归纳假设，定理对 $ S^{-} $成立。因此 $ S^{-} $是M个不相交chain $ S^{-}_ {1}, \\ldots, S^{-}_ {M}, a_ {i} \\in S^{-}_ {i} $的并。假设 $ x \\in S^{-}_ {i}, x > a_ {i} $。因为有一个j使得 $ x \\le a_ {j} $，我们有 $ a_ {i} < a_ {j} $，矛盾。这显示 $ a_ {i} $是chain $ S^{-}_ {i}, i = 1, \\ldots, m $的最大元素。对 $ S^{+} $地处理相似。这样得证

