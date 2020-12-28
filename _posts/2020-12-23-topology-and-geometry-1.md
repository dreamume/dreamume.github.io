---
layout:     post
title:      "Topology and geometry(Chapter 1) by Bredon"
subtitle:   "General Topology"
thumbnail-img: ""
date:       2020-12-23 00:30
author:     "dreamume"
tags: 		[topology]
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

1.  [General Topology](#org8fd57c5)
    1.  [Metric Spaces](#orgb8cdb49)
    2.  [Topological Spaces](#orgc07d561)


<a id="org8fd57c5"></a>

# General Topology


<a id="orgb8cdb49"></a>

## Metric Spaces

**定义** 一个度量空间是一个集合X及一个函数

$ \\begin{equation} dist: X \\times X \\to R \\end{equation} $

称为一个度量，使得如下三个规则满足：

(1) （正定性） $ dist\\left(x, y\\right) \\ge 0, 当等号成立时 $，x = y

(2) （对称性） dist(x, y) = dist(y, x)；且

(3) （三角不等式） $ dist\\left(x, z\\right) \\le dist\\left(x, y\\right) + dist\\left(y, z\\right) $

在度量空间X中我们定义 $ \\epsilon $球， $ \\epsilon > 0 $，对于一个点 $ x \\in X $ 有

$ \\begin{equation} B_ {\\epsilon}\\left(x\\right) = \\{ y \\in X \| dist\\left(x, y\\right) < \\epsilon \\} \\end{equation} $

一个子集 $ U \\subset X $被称为是开的，如果对每个点 $ x \\in U $，有一个 $ \\epsilon $球把x在U中完全包含。一个子集被称为闭的，如果它的补是开的。

**命题** 一个函数 $ f: X \\to Y $在度量空间中是连续的 $ \\Leftrightarrow f^{-1}\\left(U\\right) $ 对每个Y中的开子集U在X中是开的

证明：如果f是连续的且 $ U \\subset Y $是开的且 $ f\\left(x\\right) \\in U $，则有一个 $ \\epsilon > 0 使得 B_ {\\epsilon} \\left(f\\left(x\\right)\\right) \\subset U $。因为连续性，则有一个 $ \\delta > 0 $使得f映射x的 $ \\delta $-球到 $ B_ {\\epsilon}\\left(f\\left(x\\right)\\right) $。这意味着 $ B_ {\\delta}\\left(x\\right) \\subset f^{-1}\\left(U\\right) $。这意味着 $ f^{-1}\\left(U\\right) $是开的

相反地，假设f(x) = y且给定 $ \\epsilon > 0 $。通过假设，$ f^{-1}\\left(B_ {\\epsilon}\\left(y\\right)\\right) $是开的且含有x。因此，通过开集的定义，有一个 $ \\delta > 0使得 B_ {\\delta}\\left(x\\right) \\subset f^{-1}\\left(B_ {\\epsilon}\\left(y\\right)\\right) $。如果 $ dist\\left(x, x'\\right) < \\delta 则 f\\left(x'\\right) \\in B_ {\\epsilon}\\left(y\\right) $，且这样 $ dist\\left(f\\left(x\\right), f\\left(x'\\right)\\right) < \\epsilon $，即通过 $ \\epsilon - \\delta $语言证明了连续性

其他的度量有：

$ \\begin{equation} dist_ {2}\\left(x, y\\right) = \\sum_ {i=1}^{n} \| x_ {i} - y_ {i} \| \\end{equation} $

$ \\begin{equation} dist_ {3}\\left(x, y\\right) = max\\left( \| x_ {i} - y_ {i} \| \\right) \\end{equation} $

**命题** 如果 $ dist_ {1} 和 dist_ {2} $是相同集合X上的度量满足假设，对任意点 $ x \\in X 和 \\epsilon > 0 有一个 \\delta > 0 $使得

$ \\begin{equation} dist_ {1}\\left(x, y\\right) < \\delta \\Rightarrow dist_ {2}\\left(x, y\\right) < \\epsilon \\end{equation} $

$ \\begin{equation} dist_ {2}\\left(x, y\\right) < \\delta \\Rightarrow dist_ {1}\\left(x, y\\right) < \\epsilon \\end{equation} $

则这些度量在X上定义了相同的开集


<a id="orgc07d561"></a>

## Topological Spaces

**定义** 一个拓扑空间是一个集合X及X的子集合称为开集使得：

(1) 两个开集的交集是开的

(2) 任意开集的并是开的，且

(3) 空集 $ \\varnothing $ 和整个空间X是开的

拓扑空间比度量空间更一般化且它们和度量空间的不同的范围比度量空间和欧几里得空间的子空间要广。例如，可能谈到度量空间中序列点的收敛跟实数序列差别很小。函数的连续性在度量空集中可被描述为序列的收敛。也可以谈论序列的收敛在一般的拓扑空间但不再适合描述连续性。这样小心地练习一般拓扑空集理论是有必要的。

拓扑空间比度量空间更一般化且它们和度量空间的不同的范围比度量空间和欧几里得空间的子空间要广。例如，可能谈到度量空间中序列点的收敛跟实数序列差别很小。函数的连续性在度量空集中可被描述为序列的收敛。也可以谈论序列的收敛在一般的拓扑空间但不再适合描述连续性。这样小心地练习一般拓扑空集理论是有必要的。

假设X和Y是拓扑空间且 $ f: X \\to Y $是一个函数，则f被称为连续的如果 $ f^{-1}\\left(U\\right) $对每个开集 $ U \\subset Y $是开的

因为闭集为开集的补且反向映射保留补集（例如，$ f^{-1}\\left(Y - B\\right) = X - f^{-1}\\left(B\\right) $），则一个函数 $ f: X \\to Y $是连续的 $ \\Leftrightarrow f^{-1}\\left(F\\right) $对每个闭集 $ F \\subset Y $也是闭的

**定义** 如果X是一个拓扑空间且 $ x \\in X $则一个集合N被称为在X中的x的邻居关系如果有一个开集 $ U \\subset N, x \\in U $

注意邻居关系不需要是一个开集，虽然通常认为邻居关系是“小”的，它不需要：整个空间X是它的每个点的邻居关系

注意X中x的任意两个邻居关系的交集是x的邻居关系

**定义** 如果X是一个拓扑空间且 $ x \\in X $则一个包含x的X子集合的集合 $ B_ {x} $被称为X中在x点的邻居关系基础如果X中x的每个邻居关系包含 $ B_ {x} $的一些元素且 $ B_ {x} $的每个元素是x的一个邻居关系

邻居关系有时方便证明函数是连续的

**定义** 一个函数 $ f : X \\to Y $在拓扑空间中被称为在x点连续，$ x \\in X $，如果，给定Y中任意f(x)的邻居关系N，有一个X中x的邻居关系M使得 $ f(M) \\in N $

因为 $ f(f^{-1}(N)) \\in N $，这如同说 $ f^{-1}(N) $是x的一个邻居关系，对每个f(x)的邻居关系N。明显地，这只需要检查N属于f(x)的一些邻居关系

**命题** 一个函数 $ f: X \\to Y $在拓扑空间中是连续的 $ \\Leftrightarrow $ 在每个 $ x \\in X $的点它都是连续的

证明：假设f是连续的，则 $ f^{-1}(U) $是开的对每个开集 $ U \\in Y $。设N是Y中f(x)的一个邻居关系且设U为一个开集使得 $ f(x) \\in U \\subset N $被邻居关系的定义保障。则 $ x \\in f^{-1}(U) \\subset f^{-1}(N) 且 f^{-1}(U) $是开的。它使得 $ f^{-1}(N) $ 是x的一个邻居关系，则f在x点连续

相反地，假设f在每个点连续且设 $ U \\subset Y $为一个开集，对任意 $ x \\in f^{-1}(U)，f^{-1}(U) $是x的一个邻居关系。则存在X中的一个开集 $ V_ {x}, x \\in V_ {x} \\subset f^{-1}(U) $。因此 $ f^{-1}(U) $是x在 $ f^{-1}(U) $范围上的集合 $ V_ {x} $的并，因为任意开集集合的并是开的，则 $ f^{-1}(U) $是开的。但U是Y中任意开集合且因此f是连续的
