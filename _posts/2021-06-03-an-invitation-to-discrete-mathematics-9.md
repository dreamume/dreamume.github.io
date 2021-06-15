---
layout:     post
title:      "An invitation to discrete mathematics(Chapter 9) by Matousek"
subtitle:   "Finite projective planes"
thumbnail-img: ""
date:       2021-06-03 09:00
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

1.  [定义和基本属性](#org26c438d)
    1.  [定义](#org00539b3)


<a id="org26c438d"></a>

# 定义和基本属性

finite projective plane是带某些属性的有限集合的子集的系统


<a id="org00539b3"></a>

## 定义

设X为一个有限集，且设 $ \\mathcal{L} $为X的子集的系统。二元组 $ (X, \\mathcal{L}) $被称为finite projective plane，如果它满足如下公理：

(P0) 存在一个4元素集合 $ F \\subseteq X $使得对每个集合 $ L \\in \\mathcal{L}, \| L \\cap F \| \\le 2 $

(P1) 任意两个不同的集合 $ L_ {1}, L_ {2} \\in \\mathcal{L} $ 相交只有一个元素，例如，$ \| L_ {1} \\cap L_ {2} \| = 1 $

(P2) 对任意两个不同的元素 $ x_ {1}, x_ {2} \\in X $，只存在一个集合 $ L \\in \\mathcal{L} $ 使得 $ x_ {1} \\in L, x_ {2} \\in L $

如果 $ (X, \\mathcal{L}) $是一个finite projective plane，我们X的元素为点，$ \\mathcal{L} $的集合为线。如果 $ x \\in X $是一个点而 $ L \\in \\mathcal{L} $是一条线，我们说“点x在线L上“或“线L穿过点x“

如果我们用这种新语言表达公里(P0) - (P2)，他们开始跟几何陈述相似。公里(P1)说任意两个不同的线只相交于一个点，公理(P2)告诉我们只有一条线穿过两个不同的点。公理(P0)需要4个点存在使得没有3个点共线

如果 $ a, b \\in X $为finite projective plane上两个不同的点，包含a和b的唯一的线 $ L \\in \\mathcal{L} $被记为符号 $ \\bar{ab} $。如果 $ L, L^{\\prime} \\in \\mathcal{L} $为不同的线，$ L_ {1} \\cap L_ {2} $的唯一点被称为它们的交

我们依然还欠读者一个projective plane中projective的解释。首先，我们应该显示什么是projective转换。考虑两个3维欧几里得空间中的平面 $ \\rho $ 和 $ \\sigma $和一个不在这两个平面中的点c，且从点c映射 $ \\rho $中的每个点到平面 $ \\sigma $。这定义了一个映射，称为从 $ \\rho $到 $ \\sigma $的projective转换。如果 $ x \\in \\rho $是一个点使得线段cx平行于平面 $ \\sigma $，则在欧几里得几何中，x的像是未定义的。但如果我们补充 $ \\rho $和 $ \\sigma $一个无穷远的线使得它们变成projective planes，则这个projective转换是这两个projective planes间的双射。如果 $ \\rho $和 $ \\sigma $被考虑为同一平面的拷贝，我们认为这个映射是projective plane到其自身的双射。projective plane是一个适当的域可做projective几何，一个考虑projective几何适当的域和保留projective转换的配置的几何分支。例如，projective转换映射conic部分（圆、椭圆、抛物线和双曲线）到conic部分，但一个椭圆可被转换为一个双曲线，等，且一个conic部分的伟大统一理论可在projective几何中建立

实际projective plane的finite projective plane的相似用来作为各种记号的动机，且通常也为目的（我们可绘制几何图像）。在真实projective plane上的几何考虑和使用公理(P0) - (P2)只运用在finite projective planes上。不要忘记一个finite projective plane只是一个带(P0) - (P2)属性的有限集合系统，因此其他几何记号不能自动转换到它身上。例如，在finite projective plane上没有距离，因此它没有圆的明确定义。另一个重要的不同是在通常的几何平面上，每条线的点可被该线自然排序，但在finite projective plane上没有这样的排序

![img](../img/the_fano_plane.png)

**例子** 一个有限projective plane最小可能的例子是7个点和7条线，每条线有3个点，且它称为Fano plane。如上图。这些点被标记为1-7，且每条线上的3个点被一个线段连接，这些连接线被标签为a-g

![img](../img/weekly_schedule_for_location_plano_bar.png)

Fano plane虽然小，但是一个有用的数学对象，且它也作为各种谜题或一些高级问题的解决方案出现，比如如下这个。7个警察被转换到第87区域的各个区，一个好的时机是让他们互相观察在西南C Drive的Plano Bar，这里是一个简单甚至乏味地值班因为酒吧的顾客通常是计算机罪犯，数字钱币伪造者或类似的人。需要一个3人移动小组，一周1天服务。如何安排每周调度使得7人中的每两人会值班一周？Fano plane提供了好的解决方案（点对应警察，移动对应线，以某种顺序排列）。每个人有相同编号的移动，没有人会超过连续两天，但另一方面，每个移动有一个人在前一天也在并知道发生了什么。我们不知道这样的调度在实际中会被警方使用，但例如，一些摩托循环赛会根据基于affine plane的order four来组织

**命题** 设 $ (X, \\mathcal{L}) $为一个finite projective plane。则所有它的线有相同数量的点；即 $ \\forall L, L^{\\prime} \\in \\mathcal{L}, \| L \| = \| L^{\\prime} \| $

**证明** 任意选择两条线 $ L, L^{\\prime} \\in \\mathcal{L} $，首先我们证明一个辅助声明：存在一个点 $ z \\in X $不在 $ L, L^{\\prime} $上

证明辅助声明。选择一个集合 $ F \\subseteq X $作为公理(P0)，我们有 $ \| L \\cap F \| \\le 2 $且 $ \| L^{\\prime} \\cap F \| \\le 2 $。如果F不在 $ L \\cup L^{\\prime} $中则得证。唯一剩下的可能性是L交F于两点（称为a,b）且 $ L^{\\prime} $交F于两点（记为c,d）。则我们考虑线 $ L_ {1} = \\overline{ac} $和 $ L_ {2} = \\overline{bd} $，设z为 $ L_ {1} $和 $ L_ {2} $的交点

如下几何图形显示了该情形：

![img](../img/two_lines_in_a_finite_projective_plane.png)

当然，我们不得不非常小心只使用(P0) - (P2)，而不是图形中的额外信息。在许多方面，finite projective plane跟几何（欧几里得）平面很不同

我们断言 $ z \\notin L \\cup L^{\\prime} $。线L和 $ L_ {1} $交于一点，名为a，且这样如果 $ z \\in L $，我们得到z = a。但这是不可能的因为线 $ L_ {2} $会包含点z = a, b和d，F中的3个点。这被条件P0禁止。因此 $ z \\notin L $，且相似地我们可得到 $ z \\notin L^{\\prime} $。这完成了辅助声明的证明

现在我们显示线L和 $ L^{\\prime} $有相同的大小。我们定义一个映射 $ \\varphi: L \\to L^{\\prime} $；它是一个双射。我们固定一个点 $ z \\notin L \\cup L^{\\prime} $且定义点 $ x \\in L $的象 $ \\varphi(x) $作为线 $ \\overline{zx} $和 $ L^{\\prime} $的交，如下图所示：

![img](../img/proof_proposition_of_finite_projective_plane.png)

通过公理(P1)和(P2)，点 $ \\varphi(x) $是定义的。接着，我们检查 $ \\varphi $是双射。如果 $ y \\in L^{\\prime} $是一个任意点，我们考虑线 $ \\bar{zy} $，且设x为和线L的交点，则线 $ \\bar{zy} $和 $ \\bar{zx} $共线，因此我们有 $ y = \\varphi(x) $，则映射 $ \\varphi $是一个双射且 $ \| L \| = \| L^{\\prime} \| $

**定义（projective plane的序）** finite projective plane $ (X, \\mathcal{L}) $的序是 $ \| L \| - 1 $。$ L \\in \\mathcal{L} $是一条线（根据证明过的命题，序不依赖线的选择）

例如，Fano plane有序2（线有三个点），且它是唯一的序为2的projective plane

**命题** 设$ (X, \\mathcal{L}) $为一个序为n的projective plane，则我们有

(i) 只有n + 1条线穿过X中的每个点

(ii) $ \| X \| = n^{2} + n + 1 $

(iii) $ \| \\mathcal{L} \| = n^{2} + n + 1 $

**证明(i)** 考虑一个任意点 $ x \\in X $。首先我们观察到存在一条线不包含x。即如果F是4点配置如(P0)，且 $ a,b,c \\in F $为不同于x的点，则至少线 $ \\overline{ab} $ 和 $ \\overline{ac} $有一条线不包含x

固定这样的一条线L，$ x \\notin L $。对每个点 $ y \\in L $，我们考虑线 $ \\overline{xy} $；有n + 1条线通过x点。另一方面，任意包含x的线交L在某点 $ y \\in L $且因此它有n + 1条线穿过x

**证明(ii)** 我们选择某条线 $ L = \\{ x_ {0}, x_ {1}, x_ {2}, \\ldots, x_ {n} \\} \\in \\mathcal{L} $且一个点 $ a \\notin L $，如下图所示：

![img](../img/basic_property_in_finite_projective_plane.png)

设 $ L_ {i} $记为线 $ \\overline{a x_ {i}}, i = 0, 1, \\ldots, n $。根据(P1)，任意两条线，$ L_ {i} $和 $ L_ {j} $，交于一个点，为点a。线 $ L_ {0}, L_ {1}, \\ldots, L_ {n} $每个除了a还有n个点，且因此它们一共包含 $ (n + 1)n + 1 = n^{2} + n + 1 $个不同的点。它也显示对任意点 $ x \\in X \\ \\{a\\} $位于某条线 $ L_ {i} $上。通过(P1)，线 $ \\overline{ax} $交线于点 $ x_ {i} $，且通过(P2)，线 $ \\overline{ax} $必须和L相交。这证明了(ii)

我们现在忽略(iii)的证明。在续集中，我们将学习一个重要的原理，且从它我们看到(iii)立马得到证明

![img](../img/fano_plane_and_its_incidence_graph.png)

**Duality** duality的意思在projective planes中是“交换点和线的角色“。为了精确地公式化，我们先引入finite projective plane的发生图形。事实上，发生图形可被一个集合X的子集的任意系统 $ \\mathcal{S} $定义。发生图形是一个顶点集合 $ X \\cup \\mathcal{S} $的二分图，每个集合 $ S \\in \\mathcal{S} $被一条边连接到所有点 $ x \\in S $。结果每个点 $ x \\in X $连接到包含它的所有集合。简单地说，我们可说发生图形的每条边对应成员关系 $ \\in $。Fano plane的发生图形如上图；点被对应点和线的标签标签（结果的图形是漂亮且重要的图形，虽然在我们的绘制中比较丑陋，它甚至有个名字：the Heawood graph）

给定一个finite projective plane $ (X, \\mathcal{L}), (X, \\mathcal{L}) $的dual通过$ (X, \\mathcal{L}) $的发生图形获得且解释为线是点的顶点，顶点为点的集合。在上图中，我们可上下翻转该图形。因为 $ \\mathcal{L} $现在被认为是一个点集，对 $ \\forall x \\in X $，线的集合 $ \\{ L \\in \\mathcal{L}: x \\in L \\} $被解释为一条线。在上图例子中，dual的点为 $ \\{a, b, \\ldots, g\\} $，dual的线为 $ \\{a, c, e \\} $（对Fano plane中点1），$ \\{a, d, g\\} $（对点2），等等

**命题** finite projective plane的dual也是一个finite projective plane

**证明** 设 $ (X, \\mathcal{L}) $为一个finite projective plane。$ (X, \\mathcal{L}) $的dual是一对 $ (\\mathcal{L}, \\Lambda), \\Lambda $是一个 $ \\mathcal{L} $子集的系统，每个子集对应X中的某个点（注意不同的点为 $ \\mathcal{L} $不同的子集，因为两个点只共享一条线）

我们需要验证 $ (\\mathcal{L}, \\Lambda) $的条件(P0) - (P2)。我们以P0开始。如果这个条件转换为原始集合系统 $ (X, \\mathcal{L}) $的语言，它意味着我们需要找到4条线 $ L_ {1}, L_ {2}, L_ {3}, L_ {4} \\in \\mathcal{L} $使得不会有3条线共一个点。让我们考虑一个4点配置 $ F = \\{a, b, c, d\\} \\subseteq X $作为条件(P0)，且定义 $ L_ {1} = \\overline{ab}, L_ {2} = \\overline{cd}, L_ {3} = \\overline{ad}, L_ {4} = \\overline{bc} $。如果我们看这4条线的任意3条，任意两条共享F中的一个点，且该点不包含在第3条上。因此$ L_ {1}, \\ldots, L_ {4} $中的任意3条线只有空的交集，这样我们确认了dual集合系统的条件(P0)的验证

dual $ (\\mathcal{L}, \\Lambda) $的条件(P1)需要：如果 $ x, x^{\\prime} \\in X $为两个不同点，则存在只有一条线 $ L \\in \\mathcal{L} $包含x和 $ x^{\\prime} $。这就是$ (X, \\mathcal{L}) $需要的条件(P2)，我们发现dual的(P2)是原始projective plane $ (X, \\mathcal{L}) $的(P1)的结果

现在我们称finite projective plane的dual为dual projective plane。dual projective plane有和projective plane相同的序

一般地，如果我们有关于序为n的finite projective plane的一些有效的陈述，且如果我们交换点和线，我们也能获得一个有效地陈述。例如，如果原始陈述说“线 $ L_ {1}, L_ {2} $交于点x“，我们可在dual中说“点 $ x_ {1}, x_ {2} $被线L连接“
