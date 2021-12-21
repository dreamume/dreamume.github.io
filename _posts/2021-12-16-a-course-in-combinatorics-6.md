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

**定理** 如果 $ A_ {1}, A_ {2}, \\ldots, A_ {m} $是 $ N := \\{1, 2, \\ldots, n \\} $的子集使得 $ A_ {i} $不是 $ A_ {j} $的子集，如果 $ i \\ne j $，则 $ m \\le {n \\choose {\\lfloor n / 2 \\rfloor} } $

证明：考虑N的子集的集合。 $ \\mathcal{A} := \\{A_ {1}, \\ldots, A_ {m}\\} $是这个集合中的一个antichain

集合中一个最大的chain $ \\mathcal{C} $将包含每个cardinality $ 0, 1, \\ldots, n $的一个子集，且开始于空集获得，然后任意单集（n个），然后任意2元子集包含单集（n-1个），然后任意3元子集包含2元集（n-2个），等。这样有n!个最大chain。相似地，有 $ k!(n-k)! $个最大chain包含给定N的k子集A

现在统计有序对 $ (A, \\mathcal{C}) $的数量使得 $ A \\in \\mathcal{A}, \\mathcal{C} $是一个最大chain，且 $ A \\in \\mathcal{C} $。因为每个最大chain $ \\mathcal{C} $包含最多一个antichain的一个元素，这个数目最多为n!。如果我们让 $ \\alpha_ {k} $记为 $ A \\in \\mathcal{A}, \| A \| = k $，这个数目是 $ \\sum^{n}_ {k=0} \\alpha_ {k} k! (n-k)! $。这样

$ \\sum^{n}_ {k=0} \\alpha_ {k}k!(n-k)! \\le n! $ 或 $ \\sum^{n}_ {k=0} \\frac{\\alpha_ {k}}{ {n \\choose k} } \\le 1 $

因为 $ {n \\choose k} $在 $ k = \\lfloor n / 2 \\rfloor $时最大且 $ \\sum \\alpha_ {k} = m $，则得证

如果我们让所有N的 $ \\lfloor n / 2 \\rfloor $子集为antichain则等式成立

我们现在考虑N的n元集合的子集的poset $ B_ {n} $，用之上的排序。N的i元子集的集合记为 $ \\mathcal{A}_ {i} $。我们定义 $ B_ {n} $中一个对称chain为一系列点 $ P_ {k}, P_ {k+1}, \\ldots, P_ {n-k} $使得 $ P_ {i} \\in \\mathcal{A}_ {i}, P_ {i} \\subseteq P_ {i+1}, i = k, k+1, \\ldots, n-k-1 $。我们描述一个算法分割 $ B_ {n} $为（不相交）对称chain

算法：开始于 $ B_ {1} $。通过归纳法，如果 $ B_ {n} $被分割成对称chain，则对每个这样的对称chain $ P_ {k}, \\ldots, P_ {n-k} $定义 $ B_ {n+1} $中两个对称chain。名为 $ P_ {k+1}, \\ldots, P_ {n-k} $和 $ P_ {k}, P_ {k} \\cup \\{n+1\\}, P_ {k+1} \\cup \\{n+1\\}, \\ldots, P_ {n-k} \\cup \\{n+1\\} $

**问题** 设 $ a_ {1}, a_ {2}, \\ldots, a_ {n^{2} +1} $为整数 $ 1, 2, \\ldots, n^{2} + 1 $的一个排序。显示Dilworth定理意味着有一个长度为n + 1的子序列是单调的

一个漂亮直接的证明如下。假设不存在n + 1项的增长子序列。定义 $ b_ {i} $为从 $ a_ {i} $项开始最长增长子系列的长度为 $ b_ {i} $。则通过鸽巢原理，在 $ b_ {i} $子序列中有至少n + 1项有相同的值。因为j < j且 $ b_ {i} = b_ {j} $意味着 $ a_ {i} > a_ {j} $，我们有一个n+1项的递减子序列

我们现在用本章的定理证明前一章的定理。我们考虑前一章定理中的二分图G。设 $ \| X \| = n, \| Y \| = n^{\\prime} \\ge n $。我们引入一个偏序集通过定义 $ x_ {i} < y_ {i} $当且仅当有一个从顶点 $ x_ {i} $到顶点 $ y_ {j} $的边。假设最大的antichain包含s个元素。设这个antichain为 $ \\{x_ {1}, \\ldots, x_ {h}, y_ {1}, \\ldots, y_ {k} \\}, h + k = s $。因为 $ \\Gamma(\\{x_ {1}, \\ldots, x_ {h} \\}) \\subseteq Y \\ \\{y_ {1}, \\ldots, y_ {k}\\} $，我们有 $ h \\le n^{\\prime} - k $。因此 $ s \\le n^{\\prime} $。偏序集是s个不相交chain的并。这将有一个大小为a的匹配，剩下X的n - a个元素和Y的 $ n^{\\prime - a} $个元素。因此 $ n + n^{\\prime} - a = s \\le n^{\\prime} $，例如，$ a \\ge n $，这意味着我们有一个完全的匹配

**定理** 设 $ \\mathcal{A} = \\{A_ {1}, \\ldots, A_ {m}\\} $为m个不同 $ \\{1, 2, \\ldots, n\\} $ k子集的一个收集，$ k \\le n / 2 $，及任意两个子集有非空的交。则 $ m \\le {n-1 \\choose k-1} $

证明：把整数1到n放到一个圆上且考虑圆上所有连续k元组的家族 $ \\mathcal{F} = \\{F_ {1}, \\ldots, F_ {n}\\} $，例如，$ F_ {i} $记为 $ \\{i, i+1, \\ldots, i + k - 1\\} $，其整数需要模n。我们观察 $ \| \\mathcal{A} \\cap \\mathcal{F} \| \\le k $因为如果某个 $ F_ {i} $等于 $ A_ {j} $，则最多集合 $ \\{l, l+1, \\ldots, l + k - 1\\}, \\{l - k, \\ldots, l - 1\\} (i < l < i + k) $之一在 $ \\mathcal{A} $中。相同的断言对从 $ \\mathcal{F} $通过应用一个排序 $ \\pi $到 $ \\{1, \\ldots, n\\} $中获得的 $ \\mathcal{F}^{\\pi} $成立。因此

$ \\sum := \\sum_ {\\pi \\in S_ {n}} \| \\mathcal{A} \\cap \\mathcal{F}^{\\pi} \| \\le k \\cdot n! $

我们现在统计该和通过固定 $ A_ {j} \\in \\mathcal{A}, F_ {i} \\in \\mathcal{F} $且观察有 $ k! (n-k)! $个排序 $ \\pi $使得 $ F^{\\pi}_ {i} = A_ {j} $。因此，$ \\sum = m \\cdot n \\cdot k!(n-k)! $。这证明了定理

**定理** 设 $ \\mathcal{A} = \\{A_ {1}, \\ldots, A_ {m}\\} $为 $ N := \\{1,2,\\ldots, n\\} $的m子集的一个收集使得 $ A_ {i} \\not \\subseteq A_ {j}, A_ {i} \\cap A_ {j} \\ne \\emptyset, \\forall i, i \\ne j, \| A_ {i} \| \\le k \\le n / 2 $。则 $ m \\le {n-1 \\choose k-1} $

证明：(i)如果所有的子集有大小k，则通过之前的定理可得证

(ii) 设 $ A_ {1}, \\ldots, A_ {s} $ 为最小cardinality的子集，$ l \\le \\frac{n}{2} - 1 $。考虑所有N的(l+1)子集包含 $ A_ {i}, 1 \\le i \\le s $中的一个或多个。明显这些不会在 $ \\mathcal{A} $中。每个 $ A_ {i}, 1 \\le i \\le s $集合，在n - l个 $ B_ {j} $中且每个 $ B_ {j} $包含最多 $ l + 1 \\le n - l $个 $ A_ {i} $。这样通过之前的定理，我们可选择s个不同的集合，记为 $ B_ {1}, \\ldots, B_ {s} $，使得 $ A_ {i} \\subseteq B_ {i} $。如果我们用 $ B_ {1}, \\ldots, B_ {s} $替换 $ A_ {1}, \\ldots, A_ {s} $，则新的收集 $ \\mathcal{A}^{\\prime} $满足定理条件且最小的cardinality的子集现在都有大小> l。通过归纳，我们可缩减到(i)

**定理** 设 $ \\mathcal{A} = \\{A_ {1}, \\ldots, A_ {m} \\} $是 $ \\{1,2,\\ldots,n\\} $的m个不同的子集的一个收集，$ \| A_ {i} \| \\le n / 2, i = 1, \\ldots, m $，其任意两个子集有非空的交，则

$ \\sum^{m}_ {i=1} \\frac{1}{ {n-1 \\choose \|A_ {i} \| - 1} } \\le 1 $

证明：设 $ \\pi $为 $ 1,2, \\ldots, n $的一个排序放在一个圆上且设 $ A_ {i} \\in \\pi $如果 $ A_ {i} $的元素在圆上连续。通过之前定理相同的讨论我们有如果 $ A_ {i} \\in \\pi $，则 $ A_ {j} \\in \\pi $对最多 $ \| A_ {i} \| $值个j

现在定义

$ f(\\pi, i) = \\left\\{ \\begin{array}{ll} \\frac{1}{\| A_ {i} \|}, & \\text{if } A_ {i} \\in \\pi \\\\ 0, & \\text{otherwise} \\end{array} \\right. $

由于 $ \\sum_ {\\pi \\in S_ {n}} \\sum^{m}_ {i=1} f(\\pi, i) \\le n! $，改变和的顺序，对一个固定的 $ A_ {i} $，圆上 $ \\pi $使得 $ A_ {i} \\in \\pi $的数目为 $ n \\cdot \| A_ {i} \| ! (n- \| A_ {i} \|) ! $，这样我们有

$ \\sum^{m}_ {i=1} \\frac{1}{\| A_ {i} \| } \\cdot n \\cdot \| A_ {i} \|! (n- \| A_ {i} \|)! \\le n! $

这样得到证明
