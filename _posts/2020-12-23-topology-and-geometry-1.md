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
    4.  [Connectivity and Components](#org5da5401)
    5.  [Separation Axioms](#orgf392415)
    6.  [Nets (Moore-Smith Convergence)](#orgbf02f66)
    7.  [Compactness](#org838373f)
    8.  [Products](#orgdbaaa36)
    9.  [再次Metric空间](#org8384420)


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


<a id="org5da5401"></a>

## Connectivity and Components

**定义** 一个拓扑空间X被称为连通的如果它不是两个非空开集的不可交并

**定义** 一个拓扑空间X的一个子集A被称为clopen如果它在X中即是开也是闭的

**命题** 一个拓扑空间X是连通的 $ \\Leftrightarrow $它的clopen子集只有X和 $ \\varnothing $

**定义** 一个离散值映射是一个映射（连续的）从拓扑空间X到一个离散空间D

**命题** 一个拓扑空间X是连通的 $ \\Leftrightarrow $X上每个离散值映射是一个常量

证明：如果X是连通的且 $ d: X \\to D $是一个离散值映射且如果 $ y \\in D $在d的范围中，则 $ d^{-1}(y) $是clopen且非空的，且必须等于X，这样d是只有值y的常数

相反地，如果X不是连通的则 $ X = U \\cup V $，对某个不相交clopen集U和V，则映射 $ d: X \\to {0, 1} $，0在U上，1在V上是一个非常量离散值映射

**命题** 如果 $ f: X \\to Y $是连续的且X是连通的，则f(X)是连通的

证明：设 $ d: f(X) \\to D $是一个离散值映射。则 $ d \\circ f $是一个在X上的离散值映射且因此必须是常数。但这意味着d是常数，因此f(X)是连续的

**命题** 如果 $ \\{ Y_ {i} \\} $是拓扑空间X中连通集的集合且如果没有两个 $ Y_ {i} $是不相交的，则 $ \\cup Y_ {i} $是连通的

证明：设 $ d: \\cup Y_ {i} \\to D $ 是离散值映射。设p、q为任意 $ \\cup Y_ {i} $上两个点。假设 $ p \\in Y_ {i} $且 $ q \\in Y_ {j} $且 $ r \\in Y_ {i} \\cap Y_ {j} $。则因为d在每个 $ Y_ {i} $上必须是常数我们有d(p) = d(r) = d(q)。但p和q是完全任意的，则d是一个常数

**推论** 关系“p和q属于一个X的连通子集“是一个相等关系

**定义** 上述推论中的相等关系的相等类型被称为X的部件

**命题** 空间X的部件是连通的且是闭的。每个连通集合包含在一个部件里。（这样部件为“最大连通子集“）部件要么为相等要么不相交，且填满X

证明：最后的陈述连接着一个事实，即部件为相等关系的相等类型。通过定义，X的部件包含p是包含p的所有连通集合的并，且根据之前命题来说它是连通的。这也意味着一个连通集合在一个部件中，该部件是闭的连接一个事实即连通集合的闭是连通的

**命题** 陈述“对每个X上离散值映射d(p) = d(q)“是一个相等关系

**定义** 上述命题中的相等类型关系被称为X的quasi-componennts

**命题** 一个空间X的Quasi-components是闭的。每个连通集合包含在一个quasi-component中。（特别地，每个部件包含在一个quasi-component中），Quasi-components要么相等要么不相交，且充满X

证明：如果 $ p \\in X $则quasi-component包含

$ \\begin{equation} \\{ q \\in X \| d(q) = d(p) \\text{ 对所有离散值映射d} \\} \\end{equation} $

但

$ \\begin{equation} \\cap \\{ d^{-1}(d(p)) \| d 一个离散值映射 \\} \\end{equation} $

其是一个闭集的交集且因此是闭的


<a id="orgf392415"></a>

## Separation Axioms

**定义** 分割公理：

( $ T_ {0} $) 一个拓扑空间X被称为一个 $ T_ {0}- $空间如果对任意两个点 $ x \\ne y $有一个开集包含其中一个但另一个不包含

( $ T_ {1} $) 一个拓扑空间X被称为一个 $ T_ {1}- $空间如果对任意两个点 $ x \\ne y $有一个开集包含x但不包含y，另一个开集包含y但不包含x

( $ T_ {2} $) 一个拓扑空间X被称为一个 $ T_ {2}- $空间或hausdorff如果对任意两个点 $ x \\ne y $有不相交开集U和V有 $ x \\in U, y \\in V $

( $ T_ {3} $) 一个 $ T_ {1}- $空间X被称为一个 $ T_ {3}- $空间或regular如果对任意点x和不包含x的闭集F有一个不相交开集U和V有 $ x \\in U, F \\in V $

( $ T_ {4} $) 一个 $ T_ {1}- $空间X被称为一个 $ T_ {4}- $空间或正常的如果对任意两个不相交闭集F和G有不相交开集U和V有 $ F \\subset U, G \\subset V $

公理 $ T_ {0} $简单描述点可被它们所在的开集区分

公理 $ T_ {1} $同样描述单点集合是闭集，因为如果我们对一个点x，对每个不同的点y我们使 $ U_ {y} $为一个开集包含y但不包含x，则 $ X - \\{x\\} = \\cup U_ {y} $是开集的并且是开的。相反地，如果 $ \\{ x \\} $是闭的则开集 $ X - \\{ x \\} $为开集包含任意其他点

公理 $ T_ {2} $是这些公理里最重要的

**命题** 一个Hausdorff空间是规范的 $ \\Leftrightarrow $任意点的闭邻居关系形成该点的一个邻居关系基

证明：假设X是规范的，设 $ x \\in V $，V是开的，且让C = X - V。通过规则性有一个开集U、W，有 $ x \\in U, C \\subset W，且 U \\cap W = \\varnothing $。则 X - W是闭的，且我们有 $ X - W \\subset X - C = V $，这样任意x的邻居关系V包含一个x的闭邻居关系 X - W

相反地，假设每个点有一个闭邻居关系基。设 $ x \\notin C $，C是闭的，且让V = X - C。通过假设，有一个开集U有 $ \\bar{U} \\subset V = X - C 且 x \\in U $，则 $ C \\subset X - \\bar{U}且 U \\cap (X - \\bar{U}) = \\varnothing $。这样X是规范的

**推论** 一个规范空间的子空间是规范的

证明：如果 $ A \\subset X $是一个子空间，在X中交一个点 $ a \\in A $的一个闭邻居关系基为A且你得到在A中a的一个闭邻居关系


<a id="orgbf02f66"></a>

## Nets (Moore-Smith Convergence)

在度量空间中函数的连续性可被表达为序列的收敛。这在一般的拓扑空间中不行。然而，有一个序列的一般化方法可以起作用且允许证明跟度量空间中使用序列的证明相似。这对直观有很大帮助。序列的一般化被称为一个net，虽然我们将使用这个概念证明一些重要的结论，但这些结果将不会用在本书的主要部分中

**定义** 一个直接的集合D是一个偏序集合使得对任意两个元素 $ \\alpha, \\beta $，有一个 $ \\tau \\in D, \\tau \\ge \\alpha, \\tau \\ge \\beta $

**定义** 一个拓扑空间X中的net是一个直接的集合D，有一个函数 $ \\Phi : D \\to X $

注意一个序列是一个简单的net基于自然数作为索引集

**定义** 如果 $ \\Phi: D \\to X $是拓扑空间X上的一个net且 $ A \\subset X $则我们说 $ \\Phi $在A上是频繁的如果对任意 $ \\alpha \\in D $有一个 $ \\beta \\ge \\alpha $使得 $ \\Phi(\\beta) \\in A $，这被称为最终在A中如果有一个 $ \\alpha \\in D $使得 $ \\Phi(\\beta) \\in A, \\forall \\beta \\ge \\alpha $

**定义** 一个net $ \\Phi: D \\to X $在一个拓扑空间中被称为收敛到 $ x \\in X $如果对x的每个邻居关系 $ U \\subset X $，$ \\Phi $最终在U中

注意如果一个net $ \\Phi $最终在两个集合U和V中则它最终在 $ U \\cap V $中。同样，如果 $ U \\cap V = \\varnothing $是不可能的。这证明半个如下事实。剩下的证明构建一个net，该net是典型的net在一般化拓扑空间中

**命题** 一个拓扑空间X是Hausdorff的 $ \\Leftrightarrow $任意收敛的net的任意两个限制是相等的（这可以说是在这样一个空间的一个net的限制）

证明：$ \\Rightarrow $可由之前的讨论得到。这样假设X不是Hausdorff的，$ x, y \\in X $为两个点不能被开集分割，考虑直集其元素为开集的偏序对 $ \\alpha = < U, V >, x \\in U, y \\in V $，顺序 $ < U, V > \\ge < A, B > \\Leftrightarrow (U \\subset A且V \\subset B) $。对任意 $ \\alpha = < U, V > $，设 $ \\Phi(\\alpha) $为某些在 $ U \\cap V $中的点。这定义了一个net $ \\Phi $我们声称其收敛到x和y

为说明这个，设W为x的任意邻居关系。我们声称 $ \\Phi $最终在W。事实上，对任意包含y的开集V和一个开集U，$ x \\in U \\subset W $且设 $ \\alpha = <U, V> $。如果 $ \\beta = <A, B> \\ge \\alpha $则 $ A \\subset U且B \\subset V $这样 $ \\Phi(\\beta) \\in A \\cap B \\subset U \\subset W $，这样 $ \\Phi $收敛到x。相似的，它也收敛到y

接下来我们显示net是描述连续性的充分条件

**命题** 一个函数 $ f: X \\to Y $在两个拓扑空间上是连续的 $ \\Leftrightarrow $对X中每个net $ \\Phi $收敛到 $ x \\in X $，Y中net $ f \\circ \\Phi $收敛到f(x)

证明：首先假设f是连续的且设 $ \\Phi $为X中的一个net收敛到x。设V为Y中任意开集包含f(x)且设 $ U = f^{-1}(V) $，其是x的一个邻居关系。通过收敛的定义，$ \\Phi $最终在U中，这样 $ f \\circ \\Phi $最终在V中，且收敛到f(x)

相反地，假设f不连续，则有一个开集 $ V \\in Y $使得 $ K = f^{-1}(V) $不是开的。设 $ x \\in K - int(K) $，考虑直集包含x的开邻居关系，例如，$ A \\le B $表示 $ A \\supset B $。对任意这样的x的邻居关系，A不能完全在K中，这样我们可选择一个点 $ w_ {A} \\in A - K $。定义net $ \\Phi $设 $ \\Phi(A) = w_ {A} $。如果N是x的任意邻居关系且如果 $ B \\ge N $（例如，$ B \\subset U $）则 $ \\Phi(B) = w_ {B} \\in B - K \\subset U $，则 $ \\Phi $最终在N中。这样 $ \\Phi $收敛到x。然而 $ (f \\circ \\Phi)(A) \\notin V, \\forall A $，这样 $ f \\circ \\Phi $最终不在V中，这样不收敛到f(x)

给定一个特殊的net $ \\Phi: D \\to X $设 $ x_ {\\alpha} = \\Phi(\\alpha), \\alpha \\in D $，则通常说 $ \\{ x_ {\\alpha} \\} $为问题中的net。这个记号使net的讨论跟序列的相似，例如，上面命题的条件可描述为

$ \\begin{equation} f(\\lim x_ {\\alpha}) = \\lim (f(x_ {\\alpha})) \\end{equation} $

**命题** 如果 $ A \\subset X $则 $ \\bar{A} $邻接A中net极限集合，其在X中收敛

证明：如果 $ x \\in \\bar{A} $则x的任意开邻居关系必须与A相交。这样我们可基于一个net在这个邻居关系集合上，顺序为包含且有这样的点 $ x_ {U} \\in U \\cap A $。这很明显收敛到x。相反地，如果 $ \\{ x_ {\\alpha} \\} $是A中任意net的点，其收敛到一个点 $ x \\in X $，则，通过定义，这个net最终在任意给定的x的邻居关系中。这样x的任意邻居关系包含A中一个点且 $ x \\in \\bar{A} $

在普通的序列中，子序列可被认为由两种不同的方式形成：(1)通过丢弃序列中的元素并重排列，或(2)组成序列，通过函数 $ Z^{+} \\to X $，用一个函数 $ h: Z^{+} \\to Z^{+} $，使得 $ i > j \\Rightarrow h(i) > h(j) $。第一种不适合一般空间中的net，对第二种，最后的h单调性条件比通常使用的子序列要强。修改它导致更一般的记号“subnet“

**定义** 如果D和$ D' $为直集且 $ h: D' \\to D $是一个函数，则h被称为final如果 $ \\forall \\delta \\in D, \\exists \\delta' \\in D' \\in (\\alpha' \\ge \\delta' \\Rightarrow h(\\alpha') \\ge \\delta) $

**定义** 一个net的子net $ \\mu: D \\to X $，是 $ \\mu $的组合 $ \\mu \\circ h $及一个final函数 $ h: D' \\to D $

**命题** 一个net $ \\{ x_ {\\alpha} \\} $在一个给定点 $ x \\in X $上的每个邻居关系中是频繁的 $ \\Leftrightarrow $它是一个收敛到x的子net

证明：考虑直集 $ D' $包含有序对 $ (\\alpha, U), \\alpha \\in D $，U是x的一个邻居关系，且 $ x_ {\\alpha} \\in U $，通过D顺序顺序化且包括。如果 $ (\\alpha, U) $和 $ (\\beta, V) $在 $ D' $中，则因为 $ \\{ x_ {\\alpha} \\} $在 $ U \\cap V $是频繁的，有一个 $ \\gamma \\ge \\alpha, \\beta, x_ {\\gamma} \\in U \\cap V $。这样 $ (\\gamma, U \\cap V) \\in D' $且 $ (\\gamma, U \\cap V) \\ge (\\alpha, U), (\\beta, V) $，显示 $ D' $是直的。通过 $ (\\alpha, U) \\mapsto \\alpha $映射 $ D' \\to D $。对任意 $ \\delta \\in D $，我们有 $ (\\delta, X) \\in D' $。现在 $ (\\alpha, U) \\ge (\\delta, X) $意味着 $ \\alpha \\ge \\delta $，意味着 $ D' \\to D $是final的，且这样 $ \\{ x_ {(\\alpha, U)} \\} $是 $ \\{ x_ {\\alpha} \\} $的子net。我们称它收敛到x。设N为x的任意邻居关系，通过假设，有某个 $ x_ {\\beta} \\in N $。如果 $ (\\alpha, U) \\ge (\\beta, N) $则 $ x_ {(\\alpha, U)} = x_ {\\alpha} \\in U \\subset N $。相反地，$ \\{ x_ {(\\alpha, U)} \\} $最终在N中

接下来我们处理没有序列信息的net的强大概念

**定义** 一个在集合X上的net被称为universal如果对任意 $ A \\subset X $，net要么最终在A中或最终在X - A中

**命题** 在X中的一个universal net的组合有一个函数 $ f: X \\to Y $是Y中一个universal net

证明：由定义如果 $ A \\subset Y $则net最终要么在 $ f^{-1}(A) 或 X - f^{-1}(A) $中，但 $ X - f^{-1}(A) = f^{-1}(Y - A) $且它跟随组合net最终要么在A或Y - A中

除了一些无趣的例子，unniverse net的定义可能看起来很强以至于读者可能怀疑universal net的存在，然而

**定理** 每个net有一个universe 子net

证明：设 $ \\{ x_ {\\alpha} \| \\alpha \\in P \\} $为X中一个net，考虑X中所有子集的收集C使得:

(1) $ A \\in C \\Rightarrow \\{ x_ {\\alpha} \\} $在A中是频繁的，且

(2) $ A, B \\in C \\Rightarrow A \\cap B \\in C $

例如，$ C = \\{ X \\} $是这样一个收集。顺序化包含所有这样收集C的族。任意简单这样收集的顺序化集合的并是一个收集，例如，满足(1)和(2)。通过最大化原理，有一个最大的这样的收集 $ C_ {0} $

设 $ P_ {0} = \\{ (A, \\alpha) \\in C_ {0} \\times P \| x_ {\\alpha} \\in A \\} $且顺序化 $ P_ {0} $通过

$ \\begin{equation} (B, \\beta) \\ge (A, \\alpha) \\Leftrightarrow B \\subset A且 \\beta \\ge \\alpha \\end{equation} $

这给定了$ P_ {0} $上的一个偏序使 $ P_ {0} $为一个直集。映射 $ P_ {0} \\to P $通过使 $ (A, \\alpha) $ 到 $ \\alpha $。这明显是final的且这样定义一个子net我们记为 $ \\{ x_ {(A, \\alpha)} \\} $。我们声称这个子net是universal的

假设S是X的任意子集使得 $ \\{ x_ {(A, \\alpha)} \\} $在S中是频繁的，则对任意 $ (A, \\alpha) \\in P_ {0} $，有一个 $ P_ {0} 中(B, \\beta) \\ge (A, \\alpha) $有 $ x_ {\\beta} = x_ {(B, \\beta)} \\in S $。则 $ B \\subset A, \\beta \\ge \\alpha $，且 $ x_ {\\beta} \\in B $。这样 $ x_ {\\beta} \\in S \\cap B \\subset S \\cap A $。对任意 $ A \\in C_ {0} $我们有 $ \\{ x_ {\\alpha} \\} $在 $ S \\cap A $中是频繁的。对 $ A \\in C_ {0} $我们可把S和所有 $ S \\cap A $的集合扔到 $ C_ {0} $中且条件(1)和(2)将仍然保持。通过最大化，我们必须有 $ S \\in C_ {0} $。如果 $ \\{ x_ {(A, \\alpha)} \\} $ 也频繁在X - S中则X - S也在 $ C_ {0} $中，且这样 $ \\varnothing = S \\cap (X - S) $也在 $ C_ {0} $中，通过(2)，这与(1)不符。这样我们知道 $ \\{ x_ {(A, \\alpha)} \\} $在X - S中不是频繁的，这样最终是在S中

我们已显示如果 $ \\{ x_ {(A, \\alpha)} \\} $在集合S中是频繁的，则，事实上，它最终在S中。这意味着 $ \\{ x_ {(A, \\alpha)} \\} $是universal的

注意这个证明在最大化原理的伪装下使用了选择公理。事实上，它可显示上面的定理与选择公理是相当的

如下事实从定义中可直接得到

**命题** 一个universal net的子net是universal的


<a id="org838373f"></a>

## Compactness

**定义** 一个拓扑空间X的覆盖是集合的收集其并为X。它是开覆盖的如果集合是开的。一个子覆盖是该收集的子集覆盖该空间

如果 $ A \\subset X $，为方便起见，我们有时使用“覆盖A"来表示X的子集的收集，其并包含A

**定义** 一个拓扑空间X被称为是紧的如果每个X的开覆盖有一个有限的子覆盖

**定义** 一个集合的收集C有有限的交属性如果任意有限子收集的交非空

**定理** 一个拓扑空间是紧的 $ \\Leftrightarrow $对X的有有限交属性的每个闭子集的收集，整个收集的交非空

**定理** 如果X是一个Hausdorff空间，则X的任意紧子集是闭的

证明：设 $ A \\subset X $为紧的且假设 $ x \\in X - A $。对 $ a \\in A $设 $ a \\in U_ {a} $且 $ x \\in V_ {a} $为开集且 $ U_ {a} \\cap V_ {a} = \\varnothing $。现在 $ A = \\cup (U_ {a} \\cap A ) $，这意味着，由A的紧性，有 $ a_ {1}, a_ {2}, \\ldots, a_ {n} \\in A $，使得 $ A \\subset U_ {a1} \\cup \\cdots \\cup U_ {an} = U $。但 $ x \\in V_ {a1} \\cap \\cdots \\cap V_ {an} = V $，这是开的，且 $ U \\cap V = \\varnothing $。这样 $ x \\in V \\subset X - U \\subset X - A $且V是开的。因为对任意 $ x \\in X - A $这是真的，我们有X - A是开的，且这样A是闭的

**定理** 如果X是紧的且 $ f: X \\to Y $是连续的，则f(X)是紧的

证明：我们可以用f(X)取代Y且假设f是onto的。对任意Y的开覆盖查看它的集合的反像且应用X的紧性质

**定理** 如果X是紧的，且 $ A \\subset X $是闭的，则A是紧的

证明：在X中用开集覆盖A，通过开集X - A且应用X的紧性质

**定理** 如果X是紧的且Y是Hausdorff的且 $ f: X \\to Y $是连续的，one-one,且onto，则f是homeomorphism

证明：我们已可证 $ f^{-1} $是连续的，即f是一个闭映射。但如果 $ A \\subset X $是闭的，则A是紧的，这样f(A)是紧的，因此f(A)是闭的

**定理** 单位间隔 I = [0, 1]是紧的

证明：设 $ \\mathcal{U} $为I的一个开覆盖，设

$ \\begin{equation} S = \\{ s \\in I \| [0, s]被 \\mathcal{U} 的一个有限子收集覆盖 \\end{equation} $

设b为S的最小上界。明显S必须为一个间隔形如S = [0, b)或S = [0, b]。在前一种形式中，考虑一个集合 $ U \\in \\mathcal{U} $包含点b。该集合必须包含一个间隔形如[a, b]。但然后我们可扔掉U假设[0, a]的有限覆盖来获得[0, b]的有限覆盖。专业我们必须有S = [0, b]对某个 $ b \\in [0, 1] $。但如果b < 1，则对某个c > b，有一个[0, c]的有限覆盖，跟b的选择矛盾。这样b = 1且我们找到了想要的[0, 1]的有限覆盖

**定理** 在一个紧空间上的实值映射假设有一个最大值

证明：如果 $ f: X \\to R $是连续的且X是紧的则f(X)是紧的，这样f(X)是闭且有界的。这样sup(f(X))存在，有限且属于f(X)因为f(X)是闭的

**定理** 一个紧的Hausdorff空间是normal的

证明：假设X是紧Hausdorff的。我们将首先显示X是regular的。假设C是一个闭子集且 $ x \\notin C $，因为X是Hausdorff的，对任意点 $ y \\in C $有一个开集 $ U_ {y}和 V_ {y}, x \\in U_ {y}, y \\in V_ {y}, U_ {y} \\cap V_ {y} == \\varnothing $。因为C是闭的，它是紧的，且 $ V_ {y} $覆盖它。这样有点 $ y_ {1}, \\ldots, y_ {n} $，使得 $ C \\subset V_ {y_ {1}} \\cup \\cdots \\cup V_ {y_ {n}} $。如果我们设 $ U = U_ {y_ {1}} \\cap \\cdots \\cap U_ {y_ {n}} $且 $ V = V_ {y_ {1}} \\cup \\cdots \\cup V_ {y_ {n}} $则 $ x \\in U, C \\subset V 且 U \\cap V = \\varnothing $，则X是regular的，剩下的证明相似

**定义** 一个拓扑空间之间的映射 $ f: X \\to Y $被称为proper的如果 $ f^{-1}(C) $对Y的每个紧子集C是紧的

**定理** 如果 $ f: X \\to Y $是一个闭映射且 $ f^{-1}(y) $对每个 $ y \\in Y $是紧的，则f是proper的

证明：设 $ C \\subset Y $为紧的且设 $ \\{ U_ {\\alpha} \| \\alpha \\in A \\} $为一个开集的收集其并包含 $ f^{-1}(C) $。对任意 $ y \\in C $有一个有限子集 $ A_ {y} \\in A $使得

$ \\begin{equation} f^{-1}(y) \\subset \\cup \\{ U_ {\\alpha} \| \\alpha \\in A_ {y} \\} \\end{equation} $

设

$ \\begin{equation} W_ {y} = \\cup \\{ U_ {\\alpha} \| \\alpha \\in A_ {y} \\} \\end{equation} $

且

$ \\begin{equation} V_ {y} = Y - f(X - W_ {y}) \\end{equation} $

其是开的。注意 $ f^{-1}(V_ {y}) \\subset W_ {y} 且y \\in V_ {y} $。因为C是紧的且被 $ V_ {y} $覆盖，有点 $ y_ {1}, \\ldots, y_ {n} $使得 $ C \\subset V_ {y_ {1}} \\cup \\cdots \\cup V_ {y_ {n}} $。这样

$ \\begin{equation} \\begin{aligned} f^{-1}(C) \\subset & f^{-1}(V_ {y_ {1}}) \\cup \\cdots \\cup f^{-1}(V_ {y_ {n}}) \\subset W_ {y_ {1}} \\cup \\cdots \\cup W_ {y_ {n}} \\\\ = & \\cup \\{ U_ {\\alpha} \| \\alpha \\in A_ {y_ {i}}; i = 1, 2, \\ldots, n \\} \\end{aligned} \\end{equation} $

是一个有限并

**定理** 对一个拓扑空间X如下描述等效：

(1) X是紧的

(2) 带有限交属性的每个X的闭子集的收集有一个非空的交集

(3) X中每个universal net是收敛的

(4) X中每个net有一个收敛的subnet

证明：我们已处理(1)和(2)的相等性，对(1) $ \\Rightarrow $ (3)假设 $ \\{ x_ {\\alpha} \\} $是一个universe net其不收敛，则给定 $ x \\in X $，有一个x的开邻居关系 $ U_ {x} $使得 $ x_ {\\alpha} $最终不在 $ U_ {x} $中，则由universe的定义 $ x_ {\\alpha} $最终在 $ X - U_ {\\alpha} $中。即有一个索引 $ \\beta_ {x} $使得 $ \\alpha \\ge \\beta_ {x} \\Rightarrow x_ {\\alpha} \\notin U_ {x} $。通过 $ U_ {x_ {1}} \\cup \\cdots \\cup U_ {x_ {n}} $，设 $ \\forall i, \\alpha \\ge \\beta_ {x_ {i}} $，则 $ \\forall i, x_ {\\alpha} \\notin U_ {x_ {i}} $，这意味着 $ x_ {\\alpha} \\notin X $，悖论

(3) $ \\Rightarrow $ (4)是明显的因为每个net有一个universe子net

(4) $ \\Rightarrow $ (2)，设 $ F = \\{ C \\} $为带有限交属性的闭集的收集，我们可抛出在所有有限交中且假设F在有限交下是闭的。则F，排序为 $ C \\ge C' \\Leftrightarrow C \\subset C' $，是直的。对每个 $ C \\in F $设 $ x_ {c} \\in C $，定义一个net。假设，有一个收敛子net，给定为一个final映射 $ f : D \\to F $。这样，对 $ \\alpha \\in D, f(\\alpha) \\in F且x_ {f(\\alpha)} \\in f(\\alpha) $。假设 $ x_ {f(\\alpha)} \\to x $。设 $ C \\in F $。则有一个 $ \\beta \\in D \\in \\alpha \\ge \\beta \\Rightarrow f(\\alpha) \\subset C $，且这样 $ x_ {f(\\alpha)} \\in f(\\alpha) \\subset C $。因为C是闭的则 $ x \\in C $。这样 $ x \\in \\cap\\{ C \\in F \\} $，得到(2)


<a id="orgdbaaa36"></a>

## Products

设X和Y为拓扑空间。则我们可定义一个拓扑（称为乘积拓扑）在 $ X \\times Y $上，把 $ U \\times V $集合的收集作为子基，当 $ U \\subset X, V \\subset Y $为开集。因为

$ U_ {1} \\times V_ {1} \\cap U_ {2} \\times V_ {2} = (U_ {1} \\cap U_ {2}) \\times (V_ {1} \\cap V_ {2}) $

这事实上是一个基。因此开集精确地为这样的矩形的并

相似地，我们可定义一个乘积拓扑在有限乘积 $ X_ {1} \\times X_ {2} \\times \\cdots \\times X_ {n} $拓扑空间

对一个无限乘积 $ \\times \\{X_ {\\alpha} \| \\alpha \\in A \\} $，我们定义乘积拓扑为当 $ U_ {\\alpha} $为开集一个包含 $ \\times \\{U_ {\\alpha} \| \\alpha \\in A\\} $的基的集合上的拓扑且当我们需要对所有 $ U_ {\\alpha} = X_ {\\alpha} $，只有有限个 $ \\alpha $不同时。注意形如 $ U_ {\\alpha} \\times \\times \\{X_ {\\beta} \| \\beta \\neq \\alpha\\} $的集合的收集是乘积拓扑的一个子基。该拓扑也称为Tychonoff拓扑

**命题** 映射 $ \\pi_ {X}: X \\times Y \\to X, \\pi_ {Y}: X \\times Y \\to Y $为连续，且乘积拓扑是对之成立的最小拓扑。对无穷乘积也类似

证明：之前描述的子基包含这些集合必须是开集，对映射是连续的，且命题刚好做出了表达

**命题** 如果X是紧的则映射 $ \\pi_ {Y}: X \\times Y \\to Y $是闭集

证明：设 $ C \\subset X \\times Y $为闭集。我们显示 $ Y - \\pi_ {Y}(C) $是开集。设 $ y \\notin \\pi_ {Y}(C) $，例如，$ <x, y> \\notin C, \\forall x \\in X $。则对任意 $ x \\in X $，有开集 $ U_ {x} \\subset X, V_ {x} \\subset Y $使得 $ x \\in U_ {x}, (U_ {x} \\times V_ {x}) \\cap C = \\emptyset $

因为X是紧的，有点 $ x_ {1}, \\ldots, x_ {n} \\in X $使得 $ U_ {x_ {1}} \\cup \\cdots U_ {x_ {n}} = X $。设 $ V = V_ {x_ {1}} \\cap \\cdots \\cap V_ {x_ {n}} $。则

$ (X \\times V) \\cap C = (U_ {x_ {1}} \\cup \\cdots \\cup U_ {x_ {n}}) \\times (V_ {x_ {1}} \\cap \\cdots \\cap V_ {x_ {n}}) \\cap C = \\emptyset $

这样，$ y \\in V \\subset Y - \\pi_ {Y}(C) $且V是开集。因为y是$ Y - \\pi_ {Y}(C) $上任意一点，它使得该集合是开集，且这样它的补集 $ \\pi_ {Y}(C) $是闭集

**推论** 如果X是紧的则 $ \\pi_ {Y}: X \\times Y \\to Y $是适合的

**推论** 如果X和Y为紧的，则 $ X \\times Y $为紧的

**推论（有限乘积的Tychonoff定理）** 如果$ X_ {i} $是紧的，则 $ X_ {1} \\times \\cdots \\times X_ {n} $是紧的

**推论** 方块 $ I^{n} \\subset R^{n} $是紧的

**推论** $ R^{n} $的子空间是紧的 $ \\Leftrightarrow $ 它是闭的且有界

证明 设X为子空间

（ $ \\Rightarrow $）因为X是紧的，它是闭的。用在原点半径为k, $ k = 1, 2, \\ldots $的开球覆盖X，因为有这样的，通过假设，一个有限的覆盖，X必须在这些开球中的一个，因此它是有界的

（ $ \\Leftarrow $）如果X是闭且有边界的，则它在以原点半径为k的某些球里，该球包含 $ [-k, k] \\times \\cdots \\times [-k, k] $区域，因此是紧的。这样X是一个紧集的闭子集且因此是一个子空间

**命题** 一个在乘积空间 $ X = \\times X_ {\\alpha} $的net覆盖点 $ (\\ldots, x_ {\\alpha}, \\ldots) \\Leftrightarrow $ 它是每个映射 $ \\pi_ {\\alpha}: X \\to X_ {\\alpha} $收敛到 $ x_ {\\alpha} $的组合

**定理（Tychonoff）** 紧空间的一个任意收集的乘积是紧的

证明 设 $ X = \\times X_ {\\alpha}, X_ {\\alpha} $是紧的。设 $ f: D \\to X $为X中的一个universal net。则组合 $ \\pi_ {\\alpha} \\circ f $也是一个universal net。因此它的组合覆盖，通过之前的定理证明。但这意味着原始的net覆盖点其第$ \\alpha $个坐标是 $ x_ {\\alpha} $且这样X是紧的

如果X是一个空间且A是一个集合，A的乘积拷贝X通常被记为 $ X^{A} $且被认为是函数的空间：$ f: A \\to X $。这样，有如下形式

**命题** 一个net $ \\{ f_ {\\alpha} \\} $在 $ X^{A} $中覆盖 $ f \\in X^{A} \\Leftrightarrow \\forall x \\in X, f_ {\\alpha}(x) \\to f(x) $，特别地，$ \\lim{(f_ {\\alpha}(x))} = (\\lim{f_ {\\alpha}})(x) $

**定义** 如果X和Y是空间，则它们的拓扑和或不相交并X + Y是集合 $ X \\times \\{0\\} \\cup Y \\times \\{1\\} $，其拓扑使得 $ X \\times \\{0\\}, Y \\times \\{1\\} $闭的且包含 $ X \\to X + Y $的$ x \\mapsto (x, 0) $和 $ Y \\to X + Y $的 $ y \\mapsto (y, 1) $同构到它们的像。更一般地，如果 $ \\{X_ {\\alpha} \| \\alpha \\in A \\} $是空间的一个索引家族则它们的拓扑和 $ +_ {\\alpha} X_ {\\alpha} $是 $ \\cup \\{X_ {\\alpha} \\times \\{ \\alpha \\} \| \\alpha \\in A \\} $给出拓扑使得每个 $ X_ {\\alpha} \\times \\{\\alpha\\} $闭且每个包含 $ X_ {\\beta} \\to +_ {\\alpha}X_ {\\alpha} $的 $ x \\mapsto (x, \\beta) $是它的象 $ X_ {\\beta} \\times \\{\\beta\\} $的一个同构


<a id="org8384420"></a>

## 再次Metric空间

在本节中，我们讨论一个metric空间完备的中心概念，直观地说，序列应该收敛。我们也显示在拓扑空间上，对给定的拓扑在空间上存在一个度量的某些拓扑条件

**定义** 一个度量空间上的柯西序列是一个序列 $ x_ {1}, x_ {2}, x_ {3}, \\ldots $使得 $ \\forall \\epsilon > 0, \\exists N > 0 \\in n, m > N \\Rightarrow dist(x_ {n}, x_ {m}) < \\epsilon $

**定义** 一个度量空间X被称为是完备的如果X中每个柯西序列在X中收敛

**定义** 一个度量空间X是总边界的，如果对每个 $ \\epsilon > 0 $，X可被有限个 $ \\epsilon - $球覆盖

**定理** 在一个度量空间X中如下条件相当

(1) X是紧的

(2) X中每个序列有一个收敛的子序列

(3) X是完备的且有总边界

证明。(1) $ \\Rightarrow $ (2)。设 $ \\{x_ {n}\\} $为一个序列。假设x不是一个子序列的极限。则有一个x的开的邻居关系 $ U_ {x} $包含 $ x_ {n} $，n为一个有限数。因为X可被有限个 $ U_ {x} $覆盖，这跟n是无穷大索引矛盾

(2) $ \\Rightarrow $ (3)。设 $ \\{x _{n} \\} $为一个柯西序列。它从(2)有对某个 $ x \\in X $有某个子序列 $ x_ {n_ {j}} \\to x $。三角不等式意味着 $ x_ {n} \\to x $且因此X是完备的。现在假设X不被有限个 $ \\epsilon - $球覆盖。则可选择点 $ x_ {1}, x_ {2}, \\ldots $使得 $ dist(x_ {i}, x_ {j}) > \\epsilon $，对所有j < i。则任意这些点的两个之间的距离大于 $ \\epsilon $。这样的序列没有收敛的子序列，这跟(2)矛盾。这样，事实上，X必须为总有序的

(3) $ \\Rightarrow $ (2)。设 $ \\{x_ {n} \\} $ 为X中任意一个序列。因为X被假设为总有界的，它可被有限个1球覆盖。这样这些1球中的一个，记为 $ B_ {1} $，对一个无限数n包含 $ x_ {n} $。接着，X，且因此 $ B_ {1} $，可被有限个 $ \\frac{1}{2} $球覆盖，这样记 $ B_ {2} $，必须使得 $ B_ {1} \\cap B_ {2} $包含 $ x_ {n} $，对无限数n。继续这样的操作我们可找到，对 $ n = 1, 2, 3 \\ldots $，一个 $ (1 / n) $球 $ B_ {n} $使得 $ B_ {1} \\cap B_ {2} \\cap \\cdots \\cap B_ {n} $包含 $ x_ {i} $，i为一个无限数。这样，我们可选择一个子序列 $ \\{ x_ {n_ {i}} \\} $使得 $ x_ {n_ {i}} \\in B_ {1} \\cap \\cdots \\cap B_ {i} $，对所有i。如果i < j，则它有 $ x_ {n_ {i}}, x_ {n_ {j}} $都在 $ B_ {1} $中，且因此 $ dist(x_ {n_ {i}}, x_ {n_ {j}}) < 1 / i $。这意味着该序列是柯西的且这样它必须收敛
