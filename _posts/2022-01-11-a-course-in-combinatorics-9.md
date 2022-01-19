---
layout:     post
title:      "A Course in Combinatorics(Chapter 9) by J. H. van Lint"
subtitle:   "Two (0,1,*) problems: addressing for graphs and a hash-coding scheme"
thumbnail-img: ""
date:       2022-01-11 18:10
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



  如下问题源于通讯定理。对一个电话网络，终端A和B之间的一个连接在每个方向上在消息流之前建立。对一个计算机网络它想要可能发送一个消息从A到B不需要知道B知道一个消息在它的道路上。想法是让消息被B的某些地址处理使得在网络的每个节点可确定一个决定消息需要处理的方向

  一个自然的事情是尝试给出图形G的每个顶点一个二进制地址，称为 $ \\{0, 1\\}^{k} $，在这样的方法上图形中两个顶点的距离等于地址的被称为Hamming的距离，例如，地址不同的位置数。这相等于视G为一个超立方体 $ H_ {k} $的引导子图形，其 $ V(H_ {k}) := \\{0, 1\\}^{k} $且k元组是邻接的当它们只在一个坐标上不同时。例子 $ G = K_ {3} $已经显示这是不可能的。我们现在引入一个新的字母 $ \\{ 0, 1, * \\} $且从这个字母中取n元形成地址。两个地址的距离是定义为当数字的位置一个为0一个为1时这样的位置数。对一个图形G的一个地址，我们需要G中任意两个顶点的距离等于它们地址的距离。我们记N(G)为n的最小值，其存在G的一个地址比为长度n

  对一棵树我们可用没有星的如下操作。我们使用归纳法。对一个两顶点的树，我们有一个长度为1的地址。假设我们可用k个顶点处理树。如果 $ x_ {0}, x_ {1}, \\ldots, x_ {k} $是树T的顶点且 $ x_ {0} $一个单价顶点，则考虑通过删除树的 $ x_ {0} $顶点获得的一个地址方案。设 $ \\mathbf{x}_ {i} $为 $ x_ {i} $的地址且假设 $ x_ {0} $连接 $ x_ {1} $。我们改变所有地址为 $ (0, \\mathbf{x}_ {i}), 1 \\le i \\le k $，且给出 $ x_ {0} $地址 $ (1, \\mathbf{x}_ {1}) $。明显地现在这是T的一个地址。这样对一个树，我们有 $ N(T) \\le \| V(T) \| - 1 $

  作为第二个例子，考虑 $ K_ {m} $。在大小为m - 1的单位矩阵中，我们替换对角线之上的0为星且添加一个零行。任意两行现在有距离1且因此 $ N(K_ {m}) \\le m - 1 $

  作为第三个例子，我们考虑如下图

  ![img](../img/example_addressing_for_graphs_and_a_hash_coding_scheme.png)

  一个可能的（非优化）的地址方案是

  $ \\begin{array}{ccccccc} 1 & & 1 & 1 & 1 & * & * \\\\ 2 & & 1 & 0 & * & 1 & * \\\\ 3 & & * & 0 & 0 & 0 & 1 \\\\ 4 & & 0 & 0 & 1 & * & * \\\\ 5 & & 0 & 0 & 0 & 0 & 0 \\end{array} $

  我们现在显示一个图地址和quadratic形式的一个对应。考虑上上图的图形G且上面给定的地址方案。对地址方案的第一列，我们赋予乘积 $ (x_ {1} + x_ {2})(x_ {4} + x_ {5}) $。这里 $ x_ {i} $在第一、对应第二，因子如果i的地址有1，对应0，在第一列。如果我们对每列做同样的事且添加项，我们获得一个quadratic形式 $ \\sum d_ {ij}x_ {i}x_ {j}, d_ {ij} $是G中顶点i和j的距离。这样G的一个地址方案对应quadratic形式 $ \\sum d_ {ij}x_ {i}x_ {j} $作为n乘积的和

  $ (x_ {i_ {1}} + \\cdots + x_ {i_ {k}})(x_ {j_ {1}} + \\cdots + x_ {j_ {l}}) $

  使得没有 $ x_ {i} $在两个因式中。变量数为 $ \| V(G) \| $

  **定理9.1** 设 $ n_ {+} $，对应的 $ n_ {-} $，为图形G的距离矩阵 $ (d_ {ij}) $的特征值的正及负的个数。则 $ N(G) \\ge max \\{n_ {+}, n_ {-} \\} $

  证明：上面提到的每个二项式形式可被表达为 $ \\frac{1}{2} \\mathbf{x}^{T} A \\mathbf{x}, \\mathbf{x} := (x_ {1}, x_ {2}, \\ldots, x_ {n}) $且A有条目 $ a_ {ij} = 1 $，如果项 $ x_ {i}x_ {j} $发生在二项式形式否则0。这样一个矩阵有rank 2且trace 0。因此它有一个正的和一个负的特征值。因为 $ (d_ {ij}) $是矩阵对应二项式形式的和，它可最多有n个正（负）特征值

  **定理9.2** $ N(K_ {m}) = m - 1 $

  证明：我们已看到 $ N(K_ {m}) \\le m - 1 $。因为J - I，大小为m，是 $ K_ {m} $的距离矩阵且J - I的特征值为m - 1个1或-1，从定理9.1可得到结果

  **定理9.3** 如果T是n个顶点的一棵树，则N(T) = n - 1

  证明：我们首先计算T的距离矩阵 $ (d_ {ij}) $的行列式。我们编号顶点 $ p_ {1}, \\ldots, p_ {n} $使得 $ p_ {n} $是邻接 $ p_ {n-1} $的一个端点。在距离矩阵中，我们从行n剪去行n - 1，且对列也相似操作。则在新的最后行和列的所有条目为1除了对角线元素为-2。现在重编号顶点 $ p_ {1}, \\ldots, p_ {n-1} $使得新顶点 $ p_ {n-1} $是邻接 $ p_ {n-2} $的 $ T \\ \\{p_ {n}\\} $中一个点。重复这个过程，在n - 1步之后，我们有行列式

  $ \\begin{array}{\|ccccc\|} 0 & 1 & 1 & \\ldots & 1 \\\\ 1 & -2 & 0 & \\ldots & 0 \\\\ 1 & 0 & -2 & \\ldots & 0 \\\\ \\vdots & \\vdots & \\vdots & \\ddots & \\vdots \\\\ 1 & 0 & 0 & \\ldots & -2 \\end{array} $

  从这我们发现可标记的结果在n个顶点的一棵树的距离矩阵的行列式 $ D_ {n} $满足

  $ D_ {n} = (-1)^{n-1} (n-1)2^{n-2} $

  例如，它只依赖 $ \| V(T) \| $。如果我们根据之前描述的过程编号顶点，则距离矩阵的左上角的 $ k \\times k $原理镜像是k个顶点上一个子树的距离矩阵。因此序列 $ 1, D_ {1}, D_ {2}, \\ldots, D_ {n}, D_ {k} $是 $ k \\times k $镜像的行列式，等于

  $ 1, 0, -1, 4, -12, \\ldots, (-1)^{n-1}(n-1)2^{n-2} $

  如果我们考虑0的符号为正，则该序列只有一个连续两个相同符号的项。通过二项式形式的一个基本定理这意味着对应的二项式形式有索引1，且因此 $ (d_ {ij}) $有一个正特征值

  对所有（连通的）图形G有 $ N(G) \\le \| V(G) \| - 1 $，这个已被P.Winkler在1983年证明。为了描述地址方案，我们需要一些准备，考虑下图

  ![img](../img/example_for_describing_addressing.png)

  我们取一个顶点 $ x_ {0} $，则通过宽度优先搜索构建一个伸展树T，且通过一个深度优先搜索编号顶点。结果显示在上图右图，$ E(G) \\ E(T) $的边为点线

  设 $ n := \| V(G) \| - 1 $。我们需要几个定义

  对 $ i \\le n $，我们定义

  $ P(i) := \\{j: x_ {j} $ 是T中在从 $ x_ {0} $到 $ x_ {i} $的路径中}

  例如，P(6) = {0, 3, 4, 6}。设

  $ i \\triangle j := max(P(i) \\cap P(j)) $

  我们描述一般情形如下图

  ![img](../img/example_of_cap_definition_in_addressing_problem.png)

  注意在图中，我们有i < j 当且仅当k < l

  对 $ i \\le n $，我们定义

  $ i^{\\prime} := max(P(i) \\ \\{i\\}) $

  例如在上上图中，$ 7^{\\prime} = 3 $，定义

  $ i \\sim j \\Leftrightarrow P(i) \\subseteq P(j) \\, or \\, P(j) \\subseteq P(i) $

  我们定义G中的距离，对应T，为 $ d_ {G} $及 $ d_ {T} $

  差异函数c(i, j)现在定义为

  $ c(i, j) := d_ {T}(x_ {i}, x_ {j}) - d_ {G}(x_ {i}, x_ {j}) $

  例如，在上上图中，c(6, 9) = 4
