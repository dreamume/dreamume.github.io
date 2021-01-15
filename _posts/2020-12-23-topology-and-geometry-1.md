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
    3.  [Subspaces](#org0d82477)


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

**定义** 一个在两个拓扑空间上的函数 $ f : X \\to Y $被称为一个homeomorphism如果 $ f^{-1}: Y \\to X $存在（f是一一对应且onto的）且f和 $ f^{-1} $都是连续的。记号 $ X \\approx Y $表示X与Y是homoemorphic的

**定义** 如果X是一个拓扑空间且 $ \\mathbf{B} $是X的子集的集合，则 $ \\mathbf{B} $被称为X拓扑的一个基如果开集是 $ \\mathbf{B} $的成员的并（特别地， $ \\mathbf{B} $的成员是开的）。一个X的子集的集合 $ \\mathbf{S} $被称为X拓扑的子基如果集合 $ \\mathbf{S} $的成员的有限交的集合 $ \\mathbf{B} $是一个基

注意任意集合X的子集的任意集合 $ \\mathbf{S} $是X上某些拓扑的子基，即开集的拓扑为 $ \\mathbf{S} $的成员的有限交的任意并（空集和全集X通常为集合的空集合的交是全集且集合的空集合的并是空集）。这样，为定义拓扑，它充分说明某些集合的集合是一个子基，该结果的拓扑为称为被这个子基生成的拓扑

在测量空间中 $ \\epsilon- $球的集合，对所有 $ \\epsilon > 0 $，是一个基，所以是$ \\epsilon- $球的集合，$ \\epsilon = 1, \\frac{1}{2}, \\frac{1}{3}, \\ldots $

这是拓扑空间的一些例子：

1. (Trivial topology) 任意集合X只有空集和全集是开的
2. （离散拓扑）任意集合X，所有子集是开的
3. 任意集合X，其开集为那些其补为有限的X的子集，及空集（即闭集为有限的集合与X本身）
4. $ X = \\omega \\cup \\{ \\omega \\} $，开集为 $ \\omega $所有子集及有限集的补（这里，$ \\omega $记为自然数集合）
5. 设X为任意偏序集，对 $ \\alpha \\in X $考虑单边间隔 $ \\{ \\beta \\in X \| \\alpha < \\beta \\} 和 \\{ \\beta \\in X \| \\alpha > \\beta \\} $。X上的“顺序拓扑”是由这些间隔产生的拓扑。“强顺序拓扑“由这些间隔及有限集合的补产生的拓扑
6. 设 $ X = I \\times I $, I 是单位间隔[0, 1]，给定“字典序”，例如，$ (x,y) < (s,t) \\leftrightarrow x < s $ 或 (x = s且y < t)。设X对这个序有顺序拓扑
7. 设X实数线及被半开间隔[x, y)产生的拓扑，这被称为半开间隔拓扑
8. 设 $ X = \\Omega \\cup \\{ \\Omega \\} $为序数集合包含至少不可数序 $ \\Omega $；见定理 B.28。记它为顺序拓扑

**定义** 一个拓扑空间被称为first countable如果每个点有一个可数邻居基

**定义** 一个拓扑空间被称为second countable如果它的拓扑有一个可数基

注意所有的度量空间是first countable的，一些度量空间不是second countable，例如，空间包含任意不可数集合其度量 dist(x, y) = 1如果 $ x \\ne y $，且dist(x, x) = 0（离散拓扑）

欧几里得空间是second countable因为 $ \\epsilon $-球，$ \\epsilon $有理数，所有有理数坐标的点容易看到是一个基

**定义** 一个序列函数 $ f_ {1}, f_ {2}, \\ldots $从一个拓扑空间X到度量空间Y被称为统一收敛到一个函数：$ f: X \\to Y $，如果对每个 $ \\epsilon > 0 $，有一个数n使得 $ i > n \\Rightarrow dist(f_ {i}(x), f(x)) < \\epsilon $对所有 $ x \\in X $

**定理** 如果一个连续函数序列 $ f_ {1}, f_ {2}, \\ldots $从一个拓扑空间X到度量空间Y统一收敛到一个函数 $ f: X \\to Y $，则f是连续的

**定义** 一个函数 $ f: X \\to Y $在拓扑空间之间被称为开的如果f(U)在Y中是开的对所有开集 $ U \\subset X $，它被称为闭的如果f(C)在Y中是闭的对所有闭集 $ C \\subset X $

**定义** 如果X是一个集合且一些条件给定在X的子集上，其对任意特殊子集可能或不能保持，则如果有一个拓扑T其开集满足条件，且使得对任意拓扑 $ T' $，其开集满足条件，则T开集也是$ T' $开集（例如，$ T \\subset T' $），则T被称为最小（或最弱或最粗的）拓扑满足条件。如果对任意拓扑 $ T' $其开集满足条件，任意 $ T' $开集也是开的，则T被称为最大（最强或最好）拓扑满足条件

术语弱和强是很老的术语，然而，它们用在一些地方表示在一般拓扑中相反的意思。因此，术语粗和好被引入来纠正该混乱。最小和最大也是一样的原因被引入。它们在数学上对拓扑及开集集合更精确，我们一般更愿意用后者

例如，如果 $ f: X \\to Y $是一个函数且X是一个拓扑空间，则有一个Y上最大拓扑使f连续，该拓扑有开集 $ \\{ V \\subset Y \| f^{-1}(V)在X中是开的 \\} $。同样有一个最小的拓扑

如果一个拓扑是满足某些给定条件的最大的拓扑则通常对给定拓扑有另外的条件是满足新条件最小的拓扑。例如，在Y上的拓扑，如前段例子中，是最小的拓扑满足条件“对所有空间Z和所有函数 $ g: Y \\to Z, g \\circ f 连续 \\Rightarrow g连续 $“，这样讨论是否一个给定拓扑是弱或强的意义不大，除非定义条件是指定的


<a id="org0d82477"></a>

## Subspaces

**定义** 如果X是一个拓扑空间且 $ A \\subset X $则A上的相关拓扑或子空间拓扑是A和X的开集的交的集合，对这个拓扑，A被称为X的子空间

**命题** 如果Y是X的一个子空间则 $ A \\subset Y $在Y中是闭的 $ \\leftrightarrow A = Y \\cap B $，B是X的某个闭子集

**命题** 如果X是一个拓扑空间且 $ A \\subset X $则有一个最大的开集U使得 $ U \\subset A $，这个集合被称为X中A的内部且被记为int(A)

**命题** 如果X是一个拓扑空间且 $ A \\subset X $则有一个最小的闭集F使得 $ A \\subset F \\subset X $，这个集合被称为X中A的闭且被记为 $ \\bar{A} $

如果我们需要指明闭集所在的空间（X），我们将使用记号 $ \\bar{A}^{X} $

**命题** 如果 $ A \\subset Y \\subset X $则 $ \\bar{A}^{Y} = \\bar{A}^{X} \\cap Y $，这样，如果Y是在X中闭的，则 $ \\bar{A}^{Y} = \\bar{A}^{X} $

**定义** 如果X是一个拓扑空间且 $ A \\subset X $则A的边界或边沿被定义为 $ \\partial A = dbry(A) = \\bar{A} \\cap \\overline{X - A} $

**命题** 如果 $ Y \\subset X $则Y与X的一个基的成员的交集集合是Y相关拓扑的一个基

**命题** 如果X, Y, Z是拓扑空间且Y是X的子空间且Z是Y的子空间，则Z是X的子空间

**命题** 如果X是一个度量空间且 $ A \\subset X $则 $ \\bar{A} $是A的点序列在X上的极限的集合

**定义** 一个拓扑空间X的子集A被称为在X中稠密的如果 $ \\bar{A} = X $，一个子集A被称为在X中无处稠密如果 $ int(\\bar{A}) = \\emptyset $
