---
layout:     post
title:      "An invitation to discrete mathematics(Chapter 4) by Matousek"
subtitle:   "Graphs: an introduction"
thumbnail-img: ""
date:       2020-12-10 14:00
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

1.  [subgraphs, components, adjacency matrix](#orgacd61fa)
2.  [Graph score](#org4fc6a3c)


<a id="orgacd61fa"></a>

# subgraphs, components, adjacency matrix

**命题** 设G = (V, E)是一个图，设顶点集合 $ V = \\{v_ {1}, v_ {2}, \\ldots, v_ {n} \\}, A = A_ {G} $为邻接矩阵。设 $ A^{k} $记为邻接矩阵的k次方，设 $ a_ {i j}^{\\left(k\\right)} $为矩阵 $ A^{k} $在(i, j)位置的元素。则 $ a_ {i j}^{\\left(k\\right)} $为图G中从点 $ v_ {i} $到 $ v_ {j} $路径长度为k的路径数。

**推论** 两个顶点的距离满足 $ d_ {G}\\left(v_ {i}, v_ {j}\\right) = min\\{k \\ge 0: a_ {i j}^{\\left(k\\right)} \\ne 0 \\} $


<a id="org4fc6a3c"></a>

# Graph score

**定理 4.3.3 (Score theorem)** 设 $ D = \\left(d_ {1}, d_ {2}, \\ldots, d_ {n} \\right) $为一个自然数序列，n > 1。假设 $ d_ {1} \\le d_ {2} \\le \\cdots \\le d_ {n} $，且设符号D'记为序列 $ \\left(d'_ {1}, \\ldots, d'_ {n-1}\\right) $，

$ \\begin{equation} d'_ {i} = \\left\\{\\begin{array}{ll}d_ {i} & \\text{ for } i < n - d_ {n} \\\\ d_ {i} - 1 & \\text{ for } i \\ge n - d_ {n} \\end{array} \\right. \\end{equation} $

例如，$ D = \\left(1, 1, 2, 2, 2, 3, 3\\right) $，我们有 $ D' = \\left(1, 1, 2, 1, 1, 2\\right) $。则D是一个graph score当且仅当D'是一个graph score

证明：假设D'是图G' = (V', E')的score，$ V' = \\{ v_ {1}, v_ {2}, \\ldots, v_ {n-1} \\} $且 $ deg_ {G}\\left(v_ {i}\\right) = d'_ {i}, i = 1, 2, \\ldots, n - 1 $。固定一个新的顶点 $ v_ {n} $，不同于 $ v_ {1}, \\ldots, v_ {n-1} $，且定义一个新的图G = (V, E)，有

$ \\begin{equation} V = V' \\cup \\{ v_ {n} \\} \\end{equation} $

$ \\begin{equation} E = E' \\cup \\{ \\{v_ {i}, v_ {n} \\}: i = n - d_ {n}, n - d_ {n} + 1, \\ldots, n - 1 \\} \\end{equation} $

用不那么形式化的语言表达，新顶点 $ v_ {n} $连接到图G'中 $ d_ {n} $个最后的顶点。明显地G有score D。

反过来证明比较困难，例如，如果D是一个score则D'是一个score。假设D是某个图的score，困难在于一般的，我们不能从反向的从D‘构造'，例如，移除最大degree的顶点，因为这样一个顶点可能连接到其他我们需要的顶点。

我们考虑顶点集合 $ \\{ v_ {1}, \\ldots, v_ {n} \\} $的所有图集合 $ \\mathcal{G} $，每个顶点 $ v_ {i} $的degree跟 $ d_ {i}, i = 1, 2, \\ldots, n $相等。我们证明如下：

**声明** 集合 $ mathcal{G} $包含一个图 $ G_ {0} $，其顶点 $ v_ {n} $邻接顶点 $ v_ {n-d_ {n}}, v_ {n - d_ {n} + 1}, \\ldots, v_ {n - 1} $，例如，这些是最后的 $ d_ {n} $个顶点。

有一个如声明所述的图 $ G_ {0} $，则它明显可得 $ G' = \\left(\\{ v_ {1}, \\ldots, v_ {n - 1} \\}, E'\\right), E' = \\{ e \\in E\\left(G_ {0}\\right): v_ {n} \\notin e \\} $，有score D'（例如，我们可移除 $ G_ {0} $里的顶点 $ v_ {n} $），且这证明了score定理。

如果 $ d_ {n} = n - 1 $，则 $ v_ {n} $连接所有其他顶点，则 $ \\mathcal{ G } $中的任意图都满足声明。假设 $ d_ {n} < n - 1 $且定义，对图 $ G \\in mathcal{G} $，一个数j(G)作为最大的索引 $ j \\in \\{1,2,\\ldots, n - 1 \\} $使得 $ \\{v_ {j}, v_ {n} \\} \\notin E\\left(G\\right) $。设 $ G_ {0} \\in \\mathcal{G} $为一个带j(G)最小可能值的图。我们证明 $ j\\left(G_ {0}\\right) = n - d_ {n} - 1 $，且从这可以看出 $ G_ {0} $满足声明。

为得出矛盾，让我们设 $ j = j\\left(G_ {0}\\right) > n - d_ {n} - 1 $。顶点 $ v_ {n} $连接 $ d_ {n} $个顶点，且最多 $ d_ {n} - 1 $个索引大于 $ v_ {j} $。因此存在某个索引 i < j使得 $ v_ {i} $邻接 $ v_ {n} $。这样我们有 $ \\{ v_ {j}, v_ {n} \\} \\notin E\\left(G_ {0}\\right), \\{ v_ {i}, v_ {n} \\} \\in E\\left(G_ {0}\\right) $。因为 $ deg_ {G_ {0}}\\left(v_ {i}\\right) \\le deg_ {G_ {0}}\\left(v_ {j}\\right) $，存在一个顶点 $ v_ {k} $邻接 $ v_ {j} $但不邻接 $ v_ {i} $。这样，我们考虑一个新图G' = (V, E')，有

$ \\begin{equation} E' = \\left(G\\left(G_ {0}\\right) \\ \\big\\{ \\{v_ {i}, v_ {n}\\}, \\{v_ {j}, v_ {k} \\}\\big\\}\\right) \\cup \\big\\{ \\{v_ {j}, v_ {n}\\}, \\{v_ {i}, v_ {k}\\}\\big\\} \\end{equation} $

容易得到图G'也有score D，且 $ j\\left(G'\\right) \\le j\\left(G_ {0}\\right) - 1 $，这和 $ G_ {0} $的选择矛盾。这证明了声明且因此定理4.3.3也得证。
