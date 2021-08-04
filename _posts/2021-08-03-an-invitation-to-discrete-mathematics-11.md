---
layout:     post
title:      "An invitation to discrete mathematics(Chapter 11) by Matousek"
subtitle:   "Order from disorder: Ramsey's theorem"
thumbnail-img: ""
date:       2021-08-03 07:00
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

1.  [6个人的聚会](#org12b5603)
    1.  [定理](#org82b7db9)


<a id="org12b5603"></a>

# 6个人的聚会

我们现在看一个6个人聚会的例子。设G为一个图形，我们引入如下的记号：$ \\omega(G) $记为一个完全子图的最大顶点数，且 $ \\alpha(G) $为G中一个独立集合的最大顶点数，即集合中两个顶点之间没有被一条边连接


<a id="org82b7db9"></a>

## 定理

设G为一个至少6个顶点的图，则 $ \\alpha(G) \\ge 3 $ 或 $ \\omega(G) \\ge 3 $

**证明** 让我们任意选择G中一个顶点且让我们把它记为u。设 $ A \\subseteq V(G) \\ \\{u\\} $为不连接到u的顶点集合；形式为 $ A = \\{v \\in V(G): v \\ne u, \\{u, v\\} \\notin E(G) \\} $。设 $ B = V(G) \\ A \\ \\{u \\} $ 包含连接到u的顶点。因为 $ \| V(G) \| \\ge 6 $，A、B集合中必须至少有一个有3个元素。我们现在区分两种情况

1.  $ \| A \| \\ge 3 $。设A包含顶点x, y, z。如果每两个形成G的一条边，则 $ \\{x, y, z\\} $确定为一个三角形，例如，一个完全子图显示 $ \\omega(G) \\ge 3 $。否则，如果，例如，$ \\{x, y\\} \\notin E(G) $，则 $ \\{x, y, z \\} $在G中是一个独立集合，且这样 $ \\alpha(G) \\ge 3 $
2.  $ \| B \| \\ge 3 $。我们继续分析：要么B中没有没有顶点对是G的边，则 $ \\alpha(G) \\ge 3 $，否则存在顶点 $ x,y \\in B $形成G的一条边。第二种情况集合 $ \\{u, x, y \\} $引入一个G的完全子图，且因此 $ \\omega(G) \\ge 3 $

注意我们需要区分多少情况来区分证明6个顶点图形的定理。在上面定理的证明中我们使用了一个特殊的情况，$ t = 2, n_ {1} = n_ {2} = 3 $，和如下著名的定理


<a id="org57f3471"></a>

## 定理（鸽笼定理）

设 $ n_ {1}, n_ {2}, \\ldots, n_ {t} $为自然数，设X为至少 $ 1 + \\sum^{t}_ {i=1} (n_ {i} - 1) $个元素的集合，且设 $ X_ {1}, X_ {2}, \\ldots, X_ {t} $为不相交集合形成X的分区。则存在i使得 $ X_ {i} $有至少 $ n_ {i} $个元素


<a id="org6856fa2"></a>

# 对图形的Ramsey定理


<a id="org2061e07"></a>

## 定理（对图形的Ramsey定理）

设图形G有至少 $ {k + \\ell - 2 \\choose k - 1} $个顶点，则 $ \\omega(G) \\ge k $ 或 $ \\alpha(G) \\ge \\ell $

让我们记定理的条件对k和 $ \\ell $是对称的，因为 $ {k + \\ell + 2 \\choose k - 1} = { k + \\ell - 2 \\choose \\ell - 1} $

如果我们在定理中用 $ k = \\ell = 3 $替代，我们获得每个有 $ {4 \\choose 2} = 6 $个顶点的图形G满足 $ \\omega(G) \\ge 3 $ 或 $ \\alpha(G) \\ge 3 $

**证明** 我们继续在 $ k + \\ell $上进行归纳。对 k = 1 或 $ \\ell = 1 $容易看到该表述是满足的（对k = 2或 $ \\ell = 2 $也是）
