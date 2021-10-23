---
layout:     post
title:      "An invitation to discrete mathematics(Chapter 13) by Matousek"
subtitle:   "Applications of linear algebra"
thumbnail-img: ""
date:       2021-10-08 08:50
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

1.  [Block designs](#orge454f95)
    1.  [定理（集成条件）](#org6940849)
    2.  [例子（Steiner triple系统）](#orgab112db)
    3.  [定理（Wilson定理）](#orgb40ff78)
2.  [Fisher不等式](#org213207c)
    1.  [定理（Fisher不等式）](#org1cc5c46)
3.  [覆盖完全二分图](#org8a1682e)
    1.  [定理（Graham-Pollak定理）](#org5c7eb2d)
4.  [图的循环空间](#org1c1e864)
    1.  [定义（边的偶数集）](#orgd93f163)
    2.  [引理](#org9cca52d)
    3.  [定理（循环空间定理）](#org41d11cc)


<a id="orge454f95"></a>

# Block designs

这里我们考虑非常常规的有限集合系统，称为块设计。有限映射平面是这个概念的一个特殊情况但块设计的一般记号不再有几何动机

设V为一个有限集合且设 $ \\mathcal{B} $为集合V的一个子集系统。为了强调集合系统 $ \\mathcal{B} $在集合V上，我们写成一个有序对 $ (V, \\mathcal{B}) $。如果所有的集合 $ B \\in \\mathcal{B} $有相同的cardinality k，我们说 $ (V, \\mathcal{B}) $是k统一的

**定义** 设v, k, t和 $ \\lambda $为整数。我们假设 $ v > k > t \\ge 1 $且$ \\lambda \\ge 1 $。一个类型 $ t - (v, k, \\lambda) $的块设计是一个集合系统 $ (V, \\mathcal{B}) $满足如下条件：

(1) V有v个元素

(2) 每个集合 $ B \\in \\mathcal{B} $有k个元素。$ \\mathcal{B} $的集合被称为块

(3) 集合V的每t元素子集包含在 $ \\mathcal{B} $的 $ \\lambda $个块中

这里有一些基本的例子阐释这些定义

**例子** 设V为一个有限集合且k为一个整数。我们把 $ \\mathcal{B} = {V \\choose k} $( $ \\mathcal{B} $包含V的所有k元素子集）。$ (V, \\mathcal{B} ) $被称为平凡的块设计

容易检查 $ (V, \\mathcal{B}) $是一个 $ t- (v, k, \\lambda) $块设计，$ t \\in \\{1, 2, \\ldots, k\\} $可任意选择，$ v = \| V \| $且$ \\lambda = {v - t \\choose k - t} $。（V的任意t元素子集包含在 $ {v-t \\choose k-t} $个块 $ B \\in \\mathcal{B} $中)

**例子** 设V为序为n的映射平面的点集，且设 $ \\mathcal{B} $记为它的线的集合。这样一个 $ (V, \\mathcal{B}) $是一个类型 $ 2-(n^{2}+n+1, n+1,1) $的块设计。相反地，它能显示类型 $ 2-(n^{2}+n+1, n+1, 1), n \\ge 2 $的任意块设计是一个序为n的映射平面

**例子** 设 $ V = \\{0, 1, 2, 3, 4, 5\\} $且设 $ \\mathcal{B} $包含如下三元组：$ \\{0, 1, 2\\}, \\{0, 2, 3\\}, \\{0, 3, 4\\}, \\{0, 4, 5\\}, \\{0, 1, 5\\}, \\{1, 2, 4\\}, \\{2, 3, 5\\}, \\{1, 3, 4\\}, \\{2, 4, 5\\}, \\{1, 3, 5\\} $。则$ (V, \\mathcal{B}) $是一个2-(6,3,2)块设计

这个块设计也可用一种更结构化的方式被定义。考虑一个循环，顶点为 $ 1, 2, \\ldots, 5 $且另一个顶点为0。系统 $ \\mathcal{B} $包含所有顶点的三元组包含循环的一条边；如下图

![img](../img/example_of_block_design_definition_with_structure_manner.png)

这些例子应该调用正确的印象块设计形成某种类型的规则。通常它不容易构建一个给定类型的块设计，且这个整个领域的基本问题是该问题的存在

**基本问题** 对给定数 $ v, k, \\lambda, t $，决定是否一个类型 $ t-(v, k, \\lambda) $的块设计是否存在

这里我们引入代数均值的一些必要的条件

这个简单介绍的最后，让我们提及块设计引起和用在数理统计的设计实验中。这个动机也影响了以上引入的记号

想象我们想要访问几个处理某个植物（为抑制它的昆虫寄生虫）的不同方法。有v类处理用来比较。我们将用一系列实验比较这些处理，且每个实验我们可应用k类处理；这给定实验的技术条件。每个实验将形成测试处理的一个块。我们可原理上测试所有可能的k元组，或块；对处理，在域实验的情形下，测试的平凡方法（这里命名平凡块设计）是远多于k和v的小值。为这个原因，统计开始使用实验设计，其不能测试所有可能的k元组但只有某些选择的块。这可能导致错误，因为实验不完整；某些可能的块没有考虑，且因此某些可能的处理间相互影响被忽视。为了补偿这个测试的不完整性，我们需要至少每个处理对在相同数量的实验块中一起出现。这样一系列实验的方案是一种 $ 2-(v, k, \\lambda) $的块设计。如果我们需要处理的每个三元组出现在相同的数量，$ \\lambda $，我们获得一个类型为 $ 3-(v, k, \\lambda) $的块设计，等等

各种块设计以不同的特色名称出现：例如，平衡不完整块设计（BIBD）设计类型 $ 2-(v, k, \\lambda) $，Steiner系统($ \\lambda = 1 $)，tactical configurations (t > 2)等等

**集成条件** 一个类型为 $ t-(v, k, \\lambda) $的块设计在每个集合上不存在是明显的，例如，对v的所有值。例如，一个 $ 1-(v, k, 1) $的设计是k元素集合的一个分区，且因此v可被k整除。另外，更少的平凡例子从映射平面的情况中获得，v被线的大小唯一确定。如下定理描述最重要类的一个类型为 $ t-(v, k, \\lambda) $块设计存在的必要条件


<a id="org6940849"></a>

## 定理（集成条件）

假设一个类型为 $ t-(v, k, \\lambda) $的块设计存在，然后如下分式必须为整数：

$ \\lambda \\frac{v(v-1)\\ldots (v-t+1)}{k(k-1) \\ldots (k-t+1)}, \\lambda \\frac{(v-1)\\ldots (v-t+1)}{(k-1) \\ldots (k -t +1)}, \\ldots, \\lambda \\frac{v-t+1}{k-t+1} $

**证明** 这是一个双统计的应用程序。设 $ (V, \\mathcal{B}) $为一个类型为 $ t-(v, k, \\lambda) $的块设计。固定一个整数s ($ 0 \\le s \\le t $)且一个s元素的集合 $ S \\subseteq V $。让我们统计数N的对 $ (T, B) $有 $ S \\subseteq T \\in {V \\choose t}, T \\subseteq B \\in \\mathcal{B} $:

![img](../img/example_integrality_conditions.png)

另一方面，T可被取为 $ {v -s \\choose t-s} $种方法，且每个T是一个 $ \\lambda $个块 $ B \\in \\mathcal{B} $的子集；因此 $ N = \\lambda {v-s \\choose t-s} $

另一方面，设M为包含集合S的块数。因为每个包含S的块B包含 $ {k-s \\choose t-s} $个t元素集合T，$ S \\subseteq T $，我们也有 $ N = M {k-s \\choose t-s} $。因此

$ M = \\lambda \\frac{{v-s \\choose t-s}}{{k-s \\choose t-s}} = \\lambda \\frac{(v-s) \\ldots (v-t+1)}{(k-s)\\ldots (k-t+1)} $

这样右边的分式应该为一个整数


<a id="orgab112db"></a>

## 例子（Steiner triple系统）

第一个非平凡的类型为 $ t-(v, k, \\lambda) $的块设计的例子是t = 2, $ \\lambda = 1 $, k = 3。这是一个三元系统每对点包含一个三元组。即，它是把完全图通过边不相连三角进行覆盖的方法

在这样的例子中，集成条件需要

$ \\frac{v(v-1)}{6} \\qquad \\frac{v-1}{2} $

为整数。对此，容易得出要么 $ v \\equiv 1 \\, (mod \\, 6) $ 或 $ v \\equiv 3 \\, (mod \\, 6) $。因此v为 $ 3, 7, 9, 13, 15, 19, 21, 25, 27, \\ldots $。对所有这样的v值，一个类型为 $ 2-(v, 3,1) $的块设计存在。对v = 7，一个Steiner triple系统是一个序为2的映射平面（Fano平面）。对v = 9，我们有如下的Steiner系统

![img](../img/example_steiner_triple_system_for_v_7.png)

这可视为一个affine平面，其是序为3的映射平面去掉一条线和所有它的点

**平衡不完全块设计** 对t = 2（例如，如果我们需要从 $ \\mathcal{B} $中每对有 $ \\lambda $对），集成条件如下：

$ \\lambda v(v - 1) \\equiv 0 \\qquad (mod \\, k(k-1)) $

$ \\lambda (v-1) \\equiv 0 \\qquad (mod \\, k-1) $

这些条件一般不再是充分的。但如下的困难和重要的结果保持：


<a id="orgb40ff78"></a>

## 定理（Wilson定理）

对任意数 $ k \\ge 1, \\lambda \\ge 1 $的选择，存在一个数 $ v_ {0}(k, \\lambda) $使得对所有 $ v \\ge v_ {0}(k, \\lambda) $满足上面的集成条件，一个类型为$ 2-(v, k, \\lambda) $的块设计存在

即集成条件对t = 2是充分的如果ground集合足够大。定理没有说小值的v：例如，类型 $ 2-(k^{2}+k+1, k+1, 1) $的块设计的存在，例如，有限映射平面

我们已提及这个定理的完整性，且我们没有进一步在这里证明


<a id="org213207c"></a>

# Fisher不等式

英国统计学家R. A. Fisher是块设计理论的奠基人之一。虽然块设计的例子已出现很长时间了（Steiner triple系统大约100年），Fisher是第一个在统计领域确定一般定义和它的重要性。他也发现了一些必要条件限制块设计的存在


<a id="org1cc5c46"></a>

## 定理（Fisher不等式）

设 $ (V, \\mathcal{B}) $为一个类型为 $ 2-(v, k, \\lambda), v > k $的块设计，则 $ \| \\mathcal{B} \| \\ge \| V \| $。因此，v处理的块测试需要至少v个实验

注意 $ \| \\mathcal{B} \| = \| V \| $的块设计是存在的（例如，有限映射平面），且，Fisher不等式是优化的，如下示例展示了它的力量

**例子** Fisher不等式意味着没有类型为2-(16, 6, 1)的块设计。根据之前的定理，在这种块设计中块的数量必须为 $ \\frac{16 \\cdot 15}{6 \\cdot 5} = 8 < 16 $。同时，对这种参数的选择集成条件是满足的：我们已经检查块的数量是集成的，且数量 $ r = \\frac{15}{5} = 3 $是一个整数。读者可检查类型为2-(21, 6, 1)和2-(25, 10, 3)的块设计也被Fisher不等式排除了，虽然它们也满足集成条件

Fisher不等式可通过一个基本的线性代数标志性的应用程序证明，这是由印度数学家R. C. Bose发现的。在我们开始证明之前，让我们引入集合系统 $ (V, \\mathcal{B}) $的发生矩阵；这跟图形的发生矩阵相似。让我们记集合V的元素为 $ x_ {1}, x_ {2}, \\ldots, x_ {v}, \\mathcal{B} $的集合为 $ B_ {1}, B_ {2}, \\ldots, B_ {b} $。我们定义一个 $ v \\times b $的矩阵 $ A = (a_ {ij}) $，行代表V的点，列代表 $ \\mathcal{B} $的集合，公式

$ a_ {ij} = \\left\\{ \\begin{array}{ll} 1 & \\text{ if } x_ {i} \\in B_ {j} \\\\ 0 & \\text{ otherwise} \\end{array} \\right. $

矩阵A被称为集合系统 $ (V, \\mathcal{B}) $的发生矩阵

**Fisher不等式的证明** 对一个给定的块设计 $ (V, \\mathcal{B}) $，考虑它的发生矩阵 $ A = (a_ {ij}) $。矩阵A的转置 $ A^{T} $，有大小 $ b \\times v $，且因此矩阵乘积 $ AA^{T} $有大小 $ v \\times v $。我们显示矩阵 $ M = AA^{T} $有一个简单的形式

让我们考虑M中的一个条目 $ m_ {ij} $。通过矩阵乘法的定义，我们有

$ m_ {ij} = \\sum^{b}_ {k=1}a_ {ik}a_ {jk} $

这样，条目 $ m_ {ij} $表达集合 $ B_ {k} $包含 $ x_ {i}, x_ {j} $的数目。通过块设计的定义，$ m_ {ij} $只能有两个可能值：

$ m_ {ij} = \\left\\{ \\begin{array}{ll} \\lambda & \\text{for } i \\ne j \\\\ \\lambda \\frac{\\upsilon - 1}{k-1} & \\text{for } i = j \\end{array} \\right. $

数 $ \\lambda \\cdot \\frac{\\upsilon - 1}{k - 1} $在之前的内容中记为r，且这样矩阵M是

$ \\left( \\begin{array}{cccc} r & \\lambda & \\ldots & \\lambda \\\\ \\lambda & r & \\ldots & \\lambda \\\\ \\vdots & \\vdots & \\ddots & \\vdots \\\\ \\lambda & \\lambda & \\ldots & r \\end{array} \\right) $

我们想要显示该矩阵是nonsingular的，即他的行列式非零。元素行操作给出

$ \\begin{aligned} \\operatorname{det} M &= \\operatorname{det} \\left( \\begin{array}{cccc} r + (\\upsilon - 1)\\lambda & r + (\\upsilon-1) \\lambda & \\ldots & r + (\\upsilon-1)\\lambda \\\\ \\lambda & r & \\ldots & \\lambda \\\\ \\vdots & \\vdots & \\ddots & \\vdots \\\\ \\lambda & \\lambda & \\ldots & r \\end{array} \\right) \\\\ &= (r + (\\upsilon - 1) \\lambda) \\operatorname{det} \\left( \\begin{array}{cccc} 1 & 1 & \\ldots & 1 \\\\ \\lambda & r & \\ldots & \\lambda \\\\ \\vdots & \\vdots & \\ddots & \\vdots \\\\ \\lambda & \\lambda & \\ldots & r \\end{array} \\right) \\\\ &= (r + (\\upsilon -1)\\lambda) \\operatorname{det} \\left( \\begin{array}{cccc} 1 & 1 & \\ldots & 1 \\\\ 0 & r - \\lambda & \\ldots & 0 \\\\ \\vdots & \\vdots & \\ddots & \\vdots \\\\ 0 & 0 & \\ldots & r - \\lambda \\end{array} \\right) \\\\ &= (r + (\\upsilon - 1) \\lambda) \\cdot (r - \\lambda)^{\\upsilon - 1} \\end{aligned} $

我们现在回忆 $ r = \\lambda \\cdot \\frac{\\upsilon - 1}{k-1} $。明显地，$ r + (\\upsilon - 1) \\lambda \\ne 0 $，且因此 $ \\upsilon > k $，我们也有 $ r > \\lambda $，且这样 $ \\operatorname{det} M \\ne 0 $。因此，矩阵M有 $ rank^{2} \\upsilon $。但如果我们有 $ b < \\upsilon $则$ A, A^{T} $的rank必须严格小于 $ \\upsilon $，且因此矩阵 $ M = AA^{T} $有 $ rank < \\upsilon $。我们有 $ b \\ge \\upsilon $。这完成了Fisher不等式的证明

这个矩阵rank的应用程序变成许多相似的组合数学的基础证明


<a id="org8a1682e"></a>

# 覆盖完全二分图

如下问题为通信问题作为动机

**问题** 一个完全图 $ K_ {n} $的边的集合应该表达为m完全二分图的边集合的不相交并。m = m(n)的最小值的可能性是什么？

一个可能的表达 $ E(K_ {n}) $作为n - 1的完全二分图的边的集合的不相交并使用类型 $ K_ {1, n_ {i}} $的图。这里是一个n = 5的不相交覆盖的例子：

![img](../img/disjoint_covering_bipartite_graph_n_5.png)

为产生对任意n的一个不相交覆盖，假设 $ E(K_ {n-1}) $已经被使用n-2星表达。在图形 $ K_ {n} $中，考虑一个顶点，且覆盖所有边包含一个星 $ K_ {1, n-1} $的边集合的顶点。然后它依然覆盖$ K_ {n-1} $的图形对称的所有边，且我们可这么做

显然我们不能做得更好，比如通过使用一些颜色类别很大的完全二分图

但Graham和Pollack发现一个巧妙的方法显示没有更好的不相交覆盖可存在


<a id="org5c7eb2d"></a>

## 定理（Graham-Pollak定理）

我们有m(n) > n - 1

**证明** 假设完全二分图 $ B_ {1}, B_ {2}, \\ldots, B_ {m} $不相交地覆盖$ K_ {n} $的所有边，例如，我们有 $ V(B_ {k}) \\subseteq V(K_ {n}) = \\{1, 2, \\ldots, n\\} $和 $ E(K_ {n}) = E(B_ {1}) \\dot{\\cup} E(B_ {2}) \\dot{\\cup} \\cdots \\dot{\\cup} E(B_ {m}) $。设 $ X_ {k} $和 $ Y_ {k} $为 $ B_ {k} $的颜色分类；这意味着 $ B_ {k} $的边都在 $ X_ {k} $和 $ Y_ {k} $之间

对每个图 $ B_ {k} $，我们给出一个 $ n \\times n $的矩阵 $ A_ {k} $，其元素为

$ a^{(k)}_ {ij} = \\left\\{ \\begin{array}{ll} 1 & \\text{if } i \\in X_ {k} \\text{ and } j \\in Y_ {k} \\\\ 0 & otherwise \\end{array} \\right. $

$ A_ {k} $的定义像图形 $ B_ {k} $的邻接矩阵，除了 $ A_ {k} $是不对称的 - 图形 $ B_ {k} $的每条边只贡献一个1。例如，对子图

![img](../img/example_of_bipartite_graph_for_graham_pollak_theory.png)

矩阵 $ A_ {k} $为

$ \\left\\{ \\begin{array}{cccccc} 0 & 0 & 0 & 1 & 1 & 1 \\\\ 0 & 0 & 0 & 1 & 1 & 1 \\\\ 0 & 0 & 0 & 0 & 0 & 0 \\\\ 0 & 0 & 0 & 0 & 0 & 0 \\\\ 0 & 0 & 0 & 0 & 0 & 0 \\\\ 0 & 0 & 0 & 0 & 0 & 0 \\end{array} \\right\\} $

我们声称每个矩阵 $ A_ {k} $有rank 1。这是因为所有 $ A_ {k} $的非零行为相同的向量

让我们现在考虑矩阵 $ A = A_ {1} + A_ {2} + \\cdots + A_ {m} $。每条边 $ \\{i, j\\} $只属于一个图形 $ B_ {k} $，且因此对每个 $ i \\ne j $，我们有要么 $ a_ {ij} = 1, a_ {ji} = 0 $或 $ a_ {ij} = 0, a_ {ji} = 1 $。$ a_ {ii} = 0 $。这样我们得到 $ A + A^{T} = J_ {n} - I_ {n}, J_ {n} $是 $ n \\times n $的矩阵，其元素都是1，$ I_ {n} $是 $ n \\times n $的单位矩阵。我们现在想要显示这样的矩阵rank至少为n - 1。一旦我们知道这个，我们获得 $ n - 1\\le r(A) \\le r(A_ {1}) + \\cdots + r(A_ {m}) = m $，因为对任意两个矩阵 $ M_ {1}, M_ {2} $（相同的形状），我们有 $ r(M_ {1} + M_ {1}) \\le r(M_ {1}) + r(M_ {2}) $

让我们假设 $ r(A) \\le n - 2 $。如果我们添加一个额外的行包含所有1，则 $ (n+1) \\times n $矩阵仍然是 $ rank \\le n - 1 $，且因此存在一个列的非平凡线性组合为零向量。即，存在一个列向量 $ x \\in R^{n}, x \\ne (0, 0, \\ldots, 0)^{T} $，使得Ax = 0且 $ \\sum^{n}_ {i=1} x_ {i} = 0 $

从最后提及的等式，我们得到 $ J_ {n} x = 0 $，我们计算

$ \\begin{aligned} x^{T}(A + A^{T})x &= x^{T}(J_ {n} - I_ {n})x = x^{T}(J_ {n}x) - x^{T}(I_ {n}x) \\\\ &= 0 - x^{T}x = - \\sum^{n}_ {i=1} x^{2}_ {i} < 0 \\end{aligned} $

另一方面，我们有

$ x^{T}(A^{T} + A)x = (x^{T}A^{T})x + x^{T}(Ax) = 0 \\cdot x + x \\cdot 0 = 0 $

这样矛盾，因此 $ r(A) = n - 1 $且定理得证


<a id="org1c1e864"></a>

# 图的循环空间

设G = (V, E)为一个无向图。设符号 $ \\mathcal{K}_ {G} $记为所有循环的集合，在G中所有可能的长度（更确切地说，所有子图为循环的集合）。明显该集合应为一个复杂的记号用一个书法字母表示因为它非常大。例如，完全图 $ K_ {n} $有

$ \| \\mathcal{K}_ {K_ {n}} \| = \\sum^{n}_ {k=3} {n \\choose k} \\cdot \\frac{(k-1)!}{2} $

且对完全二分图 $ K_ {n, n} $我们有

$ \| \\mathcal{K}_ {K_ {n, n}} \| = \\sum^{n}_ {k=2} {n \\choose k}^{2} \\cdot \\frac{k! (k-1)!}{2} $

另一方面，我们可注意 $ \\mathcal{K}_ {G} = \\emptyset $当且仅当G是一个森林（树的不相交并）

似乎集合 $ \\mathcal{K}_ {G} $没有合适的结构。在本章节，我们引入一个合适的循环记号的一般化，其扩展所有循环的集合到一个更大的带一个非常简单结构的集合，称为一个向量空间的结构。原始是来自于电子电路问题


<a id="orgd93f163"></a>

## 定义（边的偶数集）

设G = (V, E)为一个无向图。一个集合 $ E^{\\prime} \\subseteq E $被称为偶的如果图 $ (V, E^{\\prime}) $的所有顶点的度数是偶的

例如，空集和一个任意循环的边集为偶集

结果，可用边集对应一个循环


<a id="org9cca52d"></a>

## 引理

一个集合 $ E^{\\prime} $的边是偶的当且仅当不相交循环对 $ E_ {1}, E_ {2}, \\ldots, E_ {t} $存在使得 $ E^{\\prime} = E_ {1} \\dot{\\cup} E_ {2} \\dot{\\cup} \\cdots \\dot{\\cup} E_ {t} $

**证明** 如果 $ E^{\\prime} $是一个非空偶集合则图形 $ (V, E^{\\prime}) $不是一个森林且因此它包含一些循环，$ E_ {1} $。集合 $ E^{\\prime} \\ E_ {1} $也是偶的，且这样我们可继续这样操作 $ E^{\\prime} $

我们现在代数地描述在一个给定图形G = (V, E)中所有偶集合的边的家族的结构。我们记G的边为 $ e_ {1}, e_ {2}, \\ldots, e_ {m} $，且对每个集合 $ A \\subseteq E $，我们赋值它的特征向量 $ \\mathcal{v}_ {A} = (v_ {1}, v_ {2}, \\ldots, v_ {m}) $定义为

$ \\upsilon_ {i} = \\left \\{ \\begin{array}{cc} 1 & \\text{if }e_ {i} \\in A \\\\ 0 & otherwise \\end{array} \\right. $

向量被添加且乘以模2（即1 + 1 = 0）。设 $ A, B \\subseteq E $为偶集合。则读者应该能够检查

$ \\mathcal{v}_ {A} + \\mathcal{v}_ {B} = \\mathcal{v}_ {C} $

$ C = (A \\cup B) \\ (A \\cap B) $是集合A和B的对称差

设符号 $ \\mathcal{E} $记为G中所有边的偶集合的特征向量的集合。对一个更简单的公式，我们需要一般化一个伸展树的记号：对一个任意、可能不相连的一个伸展森林，图形G我们理解G的任意子图 $ (V(G), \\bar{E}) $不包含循环和包含最大该属性（例如，添加任意G的边到 $ \\bar{E} $创造一个循环）。对一个连通图G，该定义和伸展树的定义冲突。对一个非连通图我们获得一个森林包含所有部分为伸展树


<a id="org41d11cc"></a>

## 定理（循环空间定理）

(1) 对任意图形G，集合 $ \\mathcal{E} $是一个在两元素域GF(2)上的向量空间。该向量空间的维度是 $ \| E \| - \| V \| + k $，k是图形G部分的数量

(2) 固定图形G的一个任意伸展森林 $ T = (V, E^{\\prime}) $，且对每条边 $ e \\in E \\ E^{\\prime} $，设 $ C_ {e} $记为唯一的循环包含在图形 $ (V, E^{\\prime} \\cup \\{e\\}) $。则循环 $ C_ {e} $的特征向量，形成 $ \\mathcal{E} $的一个基

在这个定理中，符号GF(2)代表2元素域包含数0和1，对算术操作执行模2操作。字母GF来自于"Galios field"，其是有限域的一个传统术语。一个GF(2)上的向量空间简单意味着如果两个偶集合的特征向量相加模2操作后我们又获得一个偶集合的特征向量

循环 $ C_ {e} $被称为一个基本循环（对给定的伸展数，其被边e确定）
