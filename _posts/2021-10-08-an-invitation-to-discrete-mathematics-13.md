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
