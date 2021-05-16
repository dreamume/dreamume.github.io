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
    3.  [用脊椎动物证明](#orgaa4f3ff)
    4.  [使用 $ Pr \\ddot{u} fer $代码证明](#org33f6fcc)
    5.  [用行列式证明](#org2ca32ce)


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


<a id="orgaa4f3ff"></a>

## 用脊椎动物证明

![img](../img/vertebrate_spanning_tree.png)

考虑一个完全图 $ K_ {n} $的伸展树，把一个顶点用圆圈标记，一个顶点用方框标记，如上图(a)。一个顶点可以即用圆圈标记也用方框标记。从 $ K_ {n} $的一些扩展树用这种方法得到的对象被称为脊椎动物。设 $ \\mathcal{V} $记为所有脊椎动物的集合

对每个给定的扩展树，我们可创建 $ n^{2} $个脊椎动物。因此所有扩展树的数量为 $ \| \\mathcal{V} \| / n^{2} $

**引理** 在所有脊椎动物集合 $ \\mathcal{V} $和所有顶点集合V到其自身的映射集合中存在一个双射F

因为n个元素集合到其自身的映射数量为 $ n^{n} $，因此伸展数的数目为 $ n^{n-2} $

**引理证明** 我们用上图的例子阐述了双射F的定义。我们开始如上图(a)脊椎动物W的绘制。圆圈和方块标记的顶点由唯一的路径连接，我们先以顶点标号的大小排列写下一行数字，然后我们从标记圆圈到标记方块的顺序写下一行数字：

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">3</th>
<th scope="col" class="org-right">4</th>
<th scope="col" class="org-right">7</th>
<th scope="col" class="org-right">8</th>
<th scope="col" class="org-right">9</th>
<th scope="col" class="org-right">14</th>
<th scope="col" class="org-right">15</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">8</td>
<td class="org-right">4</td>
<td class="org-right">14</td>
<td class="org-right">9</td>
<td class="org-right">3</td>
<td class="org-right">7</td>
<td class="org-right">15</td>
</tr>
</tbody>
</table>

我们定义一个辅助直接图P: 顶点集合包含上面的顶点，且我们对上一行的顶点向对应下一行的顶点做一个箭头（直边）。因为只有一个箭头指向一个顶点并指出一个顶点，图P是一个直接循环的不相交并（包含可能直接循环的孤立顶点）。我们也说该连接线定义了它的顶点的一个排列，且P包含该排列的循环。在我们的例子中，这些循环是(3, 8, 9), (4), (7, 14)和(15)

我们现在回头来看整个脊椎动物W，如果我们移除连接线的边，它分裂成几部分（各部分也是树）。我们连接各部分的边使得它们指向该部分中包含连接线中的顶点。我们现在定义顶点集合V的直接图：它的边为各部分的所有直接边，加上图形P的边。我们绘制图形P的循环，然后我们绘制每个顶点（原始是从连接线来）树悬挂在连接线的顶点上，如上图(b)

我们声称该直接图G是一个图的映射。使用该图G，我们可最终定义一个映射 $ f: \\{1, 2, \\ldots, n\\} \\to \\{1,2,\\ldots, n\\} $，对每个 $ i \\in V, f(i) = j $，在我们的例子中，我们获得映射 $ 1 \\mapsto 7, 2 \\mapsto 15, 3 \\mapsto 8, 4 \\mapsto 4, 5 \\mapsto 2, 6 \\mapsto 5, 7 \\mapsto 14, 8 \\mapsto 9, 9 \\mapsto 3, 10 \\mapsto 4, \\\\ 11 \\mapsto 10, 12 \\mapsto 4, 13 \\mapsto 12, 14 \\mapsto 7, 15 \\mapsto 15, 16 \\mapsto 7, 17 \\mapsto 16, 18 \\mapsto 1, 19 \\mapsto 8 $。这样， 每个脊椎动物W确定一个映射F(W)

仍然要证明原始的脊椎动物W可用上述映射f重建，且每个映射可从某个脊椎动物获得


<a id="org33f6fcc"></a>

## 使用 $ Pr \\ddot{u} fer $代码证明

![img](../img/spanning_tree_with_code_and_reconstruction.png)

考虑一个伸展树，如上图(a)是一个8个顶点的例子。我们解释如何构建一个序列 $ p = P(T) = (p_ {1}, p_ {2}, \\ldots, p_ {n-2}) $，被称为树T的 $ Pr \\ddot{u} fer $代码。基本思想是一个个移除T的叶子直到树被缩减为一条边。我们将构建一个树的辅助序列 $ T_ {0} = T, T_ {1}, T_ {2}, \\ldots, T_ {n-2} = K_ {2} $，且同时生成序列p。假设树 $ T_ {i-1} $已经从某些i（初始化时我们有 $ T_ {0} = T $）构建。如我们所知，$ T_ {i-1} $有至少一个叶子（例如，一个度数为1的顶点）。我们拿走 $ T_ {i-1} $中最小的叶子（回忆T的顶点为数$ 1, 2, \\ldots, n $），且我们通过从 $ T_ {i-1} $移除该叶子及其边来形成 $ T_ {i} $。同时，我们也定义第i项，$ p_ {i} $，作为从 $ T_ {i-1} $移除的邻居叶子作为构建序列。注意，我们不记录叶子而是记录它的邻居！通过持续这么做 $ i = 1,2, \\ldots, n - 2$，我们定义整个序列p = P(T)

现在我们看如何从序列 $ p = (p_ {1}, p_ {2}, \\ldots, p_ {n-2}) $重构原来的树 $ T = P^{-1}(p) $。更确切地，我们给定一个规则从给定的序列p创建一个伸展树，且我们用这种方式从某些伸展树得到p然后我们还能还原该树T。这将显示树的序列编码对应了一个双射

让我们假设一个给定序列p从某个伸展树T通过上述构建获得。设 $ \\mathcal{l}_ {1} $记为T第一个被移除的叶子。我们如何从序列p中选择 $ \\mathcal{l}_ {1} $呢？$ \\mathcal{l}_ {1} $不能发生在序列p的任意地方，进一步不包含在集合 $ \\{p_ {1}, p_ {2}, \\ldots, p_ {n-2} \\} $上的任意顶点则为树 $ T_ {0} $的叶子，否则我们会移除它导致出现一个悬着的叶子，且它将出现在序列p中。根据移除叶子的规则，$ \\mathcal{l}_ {1} $必须为集合 $ \\{1, 2, \\ldots, n \\} \\ \\{ p_ {1}, p_ {2}, \\ldots, p_ {n-2} \\} $中最小元素。现在我们可绘制顶点 $ \\mathcal{l}_ {1} $和 $ p_ {1} $且通过一条边连接它们，如上图(b)

进一步，我们继续这样处理。从T的第一步到第i - 1步中移除T中的叶子 $ \\mathcal{l}_ {1}, \\mathcal{l}_ {2}, \\ldots, \\mathcal{l}_ {i-1} $。我们通过顶点 $ p_ {i} $的边连接 $ \\mathcal{l}_ {i} $；如果 $ \\mathcal{l}_ {i} $还没被绘制，$ p_ {i} $也相似。构建的前5步描述在上图(b)中。第6步，我们将绘制边$ \\{1, 5\\} $

在n - 2步后，我们已绘制伸展树T的n - 2条边，在p的构建中所有边被移除。它得到最后剩下的边，其一个顶点为 $ p_ {n-2} $，例如，最后叶子的邻居撕裂，另一个顶点是不在叶子 $ \\mathcal{l}_ {1}, \\ldots, \\mathcal{l}_ {n-2} $和不同于 $p_ {n-2} $。在上图中，是边 $ \\{ 1, 8 \\} $

这里完成了构建过程的描述，但证明还没完。容易检查对任意输入序列p，算法执行且返回某个带n - 1条边的 $ K_ {n} $子图形G，且我们知道如果p通过编码某个伸展树T的方式获得，则G = T。仍然要证明(1) G总是一棵树，且(2)应用到G的编码总是原来的p

设 $ G_ {i} = (\\{1, 2, \\ldots, n\\}, \\{e_ {i}, e_ {i+1}, \\ldots, e_ {n-1} \\}), e_ {1}, e_ {2}, \\ldots, e_ {n-1} $为G的边，顺序通过编码算法产生。可以检查边 $ e_ {i+1}, \\ldots, e_ {n-1} $不会连接顶点 $ \\mathcal{l}_ {i} $，因此 $ \\mathcal{l}_ {i} $在 $ G_ {i} $中是一个叶子。这样G是一颗树，且$ G_ {i} $是树加上i + 1个孤立顶点

对(2)，可以检查 $ \\mathcal{l}_ {i} $是 $ G_ {i} $中最小的叶子，$ i \\le i \\le n - 2 $。通过 $ \\mathcal{l}_ {i} $的定义，一个更小的叶子只发生在 $ \\mathcal{l}_ {1}, \\ldots, \\mathcal{l}_ {i-1} $或 $ \\{p_ {i}, \\ldots, p_ {n-2} \\} $中。第一组在问题之外，因为 $ \\mathcal{l}_ {1}, \\ldots, \\mathcal{l}_ {i-1} $在 $ G_ {i} $中是孤立的。让我们考虑一个顶点 $ p_ {k}, i \\le k \\le n - 2 $，在图 $ G_ {k} $中，$ p_ {k} $是叶子 $ \\mathcal{l}_ {k} $的邻居，且它还有另一个邻居因为它在$ G_ {k+1} $的单个连接部分中至少有两个顶点


<a id="org2ca32ce"></a>

## 用行列式证明

