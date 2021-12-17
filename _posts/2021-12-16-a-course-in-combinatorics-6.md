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

**定理** 设P为一个偏序集。如果P没有M + 1个元素的chain，则P是m个antichain的并

证明：对m = 1定理成立。设 $ m \\ge 2 $且假设m - 1时定理是真。设P为一个偏序集没有m + 1元素的chain。设M为P的最大元素的集合。M是一个antichain。假设 $ x_ {1} < x_ {2} < \\cdots < x_ {m} $是 $ P \\ M $中的一个chain。则这也是P中一个最大chain且因此我们有 $ x_ {m} \\in M $，矛盾。因此 $ P \\ M $中没有m个元素的chain。通过归纳假设，$ P \\ M $是m - 1个antichain的并，这证明了定理

**定理** 如果 $ A_ {1}, A_ {2}, \\ldots, A_ {m} $是 $ N := \\{1, 2, \\ldots, n \\} $的子集使得 $ A_ {i} $不是 $ A_ {j} $的子集，如果 $ i \\ne j $，则 $ m \\le {n \\choose \\lfloor n / 2 \\rfloor} $

证明：考虑N的子集的集合。 $ \\mathcal{A} := \\{A_ {1}, \\ldots, A_ {m}\\} $是这个集合中的一个antichain

集合中一个最大的chain $ \\mathcal{C} $将包含每个cardinality $ 0, 1, \\ldots, n $的一个子集，且开始于空集获得，然后任意单集（n个），然后任意2元子集包含单集（n-1个），然后任意3元子集包含2元集（n-2个），等。这样有n!个最大chain。相似地，有 $ k!(n-k)! $个最大chain包含给定N的k子集A

现在统计有序对 $ (A, \\mathcal{C}) $的数量使得 $ A \\in \\mathcal{A}, \\mathcal{C} $是一个最大chain，且 $ A \\in \\mathcal{C} $。因为每个最大chain $ \\mathcal{C} $包含最多一个antichain的一个元素，这个数目最多为n!。如果我们让 $ \\alpha_ {k} $记为 $ A \\in \\mathcal{A}, \| A \| = k $，这个数目是 $ \\sum^{n}_ {k=0} \\alpha_ {k} k! (n-k)! $。这样

$ \\sum^{n}_ {k=0} \\alpha_ {k}k!(n-k)! \\le n! $ 或 $ \\sum^{n}_ {k=0} \\frac{\\alpha_ {k}}{ {n \\choose k} } \\le 1 $

因为 $ {n \\choose k} $在 $ k = \\lfloor n / 2 \\rfloor $时最大且 $ \\sum \\alhpa_ {k} = m $，则得证

如果我们让所有N的 $ \\lfloor n / 2 \\rfloor $子集为antichain则等式成立

我们现在考虑N的n元集合的子集的poset $ B_ {n} $，用之上的排序。N的i元子集的集合记为 $ \\mathcal{A}_ {i} $。我们定义 $ B_ {n} $中一个对称chain为一系列点 $ P_ {k}, P_ {k+1}, \\ldots, P_ {n-k} $使得 $ P_ {i} \\in \\mathcal{A}_ {i}, P_ {i} \\subseteq P_ {i+1}, i = k, k+1, \\ldots, n-k-1 $。我们描述一个算法分割 $ B_ {n} $为（不相交）对称chain

算法：开始于 $ B_ {1} $。通过归纳法，如果 $ B_ {n} $被分割成对称chain，则对每个这样的对称chain $ P_ {k}, \\ldots, P_ {n-k} $定义 $ B_ {n+1} $中两个对称chain。名为 $ P_ {k+1}, \\ldots, P_ {n-k} $和 $ P_ {k}, P_ {k} \\cup \\{n+1\\}, P_ {k+1} \\cup \\{n+1\\}, \\ldots, P_ {n-k} \\cup \\{n+1\\} $

