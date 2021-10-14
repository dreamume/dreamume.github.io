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
