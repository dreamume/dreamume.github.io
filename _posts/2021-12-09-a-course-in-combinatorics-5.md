---
layout:     post
title:      "A Course in Combinatorics(Chapter 5) by J. H. van Lint"
subtitle:   "Systems of distinct representatives"
thumbnail-img: ""
date:       2021-12-09 08:10
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



我们首先给出两个不同的定理公式作为P. Hall's marriage theorem。我们给出一个构造证明和一个计数证明。如果A是一个图的顶点的子集，则记为 $ \\Gamma(A) $，集合 $ \\cup_ {a \\in A} \\Gamma(a) $。考虑一个两分图G有顶点集合 $ X \\cup Y $。一个G中的匹配为一个边集的子集 $ E_ {1} $使得在 $ E_ {1} $中没有顶点邻接超过一条边。一个从X到Y的完全匹配是一个匹配使得X中每个顶点在 $ E_ {1} $中有一条边邻接。如果X和Y中的顶点认为是男孩和女孩，且一条边代表一端的人对另一端友好，则一个完全的匹配代表在X中一个可能的结婚对象

**定理** 对G中从X到Y有一个完全匹配的充分必要条件为 $ \| \\Gamma(A) \| \\ge \| A \|, \\forall A \\subset X $

证明：(i)对充分条件来说这是明显的

(ii) 假设 $ \| \\Gamma(A) \| \\ge \| A \|, \\forall A \\subset X $。设 $ \| X \| = n $，m < n，且假设我们有一个匹配M有m条边。我们将显示一个更大的匹配存在

记M的边为红色其他边为蓝色。设 $ x_ {0} \\in X $为一个不邻接匹配边的顶点。我们声称存在一个简单的路径（奇数长度）开始于 $ x_ {0} $且是一条蓝边，使用红蓝交替的边，且终止于一条蓝边其末点是不邻接匹配边的点y。如果我们找到这样的一个路径p，我们就完成了因为我们通过删除p的红色边且用p的蓝色边替换就获得了一个m+1的匹配。即我们交换p的边颜色

因为 $ \| \\Gamma(\\{x_ {0}\\}) \| \\ge 1 $，有一个顶点 $ y_ {1} $邻接 $ x_ {0} $（明显地通过一个蓝边因为 $ x_ {0} $不邻接任意红边）。如果 $ y_ {1} $也不邻接任意红边，我们就有了需要的路径（长度为1）；如果 $ y_ {1} $邻接一条红边，设 $ x_ {1} $为该红边的另一个顶点。递归地，定义 $ x_ {0}, x_ {1}, \\ldots $和 $ y_ {1}, y_ {2}, \\dots $。如果 $ x_ {0}, x_ {1}, \\ldots, x_ {k} $和 $ y_ {1}, \\ldots, y_ {k} $被定义，则因为 $ \| \\Gamma( \\{x_ {0}, x_ {1}, \\ldots, x_ {k}\\}) \| \\ge k + 1 $，存在一个顶点 $ y_ {k+1} $，不同于 $ y_ {1}, \\ldots, y_ {k} $，邻接 $ \\{x_ {0}, x_ {1}, \\ldots, x_ {k} \\} $中至少一个顶点。如果 $ y_ {k+1} $不邻接一条红边，停止；否则，设 $ x_ {k+1} $为该红边的另一个顶点

当过程终止是，我们构建了路径p通过开始于 $ y_ {k+1} $且一条蓝边连接它，为 $ x_ {i_ {1}}, i_ {1} < k + 1 $。然后添加红边 $ \\{x_ {i_ {1}}, y_ {i_ {1}} $。通过构建，$ y_ {i_ {1}} $被某个 $ x_ {i_ {2}}, i_ {2} < i_ {1} $的一条蓝边连接。则添加红边 $ \\{x_ {i_ {2}}, y_ {i_ {2}} $。继续这个过程直到到达 $ x_ {0} $

**引理** 对 $ n \\ge 1 $，设 $ f_ {n}: \\mathbb{Z}^{n} \\to \\mathbb{N} $定义为

$ f_ {n}(a_ {0},a_ {1}, \\ldots, a_ {n-1}) := F_ {n}(m_ {0}, m_ {1}, \\ldots, m_ {n-1}) $

如果 $ (m_ {0}, \\ldots, m_ {n-1}) $是n元组 $ (a_ {0}, \\ldots, a_ {n-1}) $的一个非减重排序。则 $ f_ {n} $是对每个变量 $ a_ {i} $是非减的

证明：设

$ m_ {0} \\le \\cdots \\le m_ {k-1} \\le a_ {i} = m_ {k} \\le m_ {k+1} \\le \\cdots \\le m_ {l} \\le m_ {l+1} \\le \\cdots \\le m_ {n-1} $

为 $ (a_ {0}, \\ldots, a_ {n-1}) $的一个非减重排序。如果 $ a^{\\prime}_ {i} \\ge a_ {i} $且

$ m_ {0} \\le \\cdots \\le m_ {k-1} \\le m_ {k+1} \\le \\cdots \\le m_ {l} \\le a^{\\prime}_ {i} \\le m_ {l+1} \\le \\cdots \\le m_ {n-1} $

是 $ (a_ {0}, \\ldots, a_ {i-1}, a^{\\prime}_ {i}, a_ {i+1}, \\ldots, a_ {n-1}) $的一个非减重排序则

$ \\frac{f_ {n}(a_ {0}, \\ldots, a_ {i-1}, a^{\\prime}_ {i}, a_ {i+1}, \\ldots, a_ {n-1})}{f_ {n}(a_ {0}, \\ldots, a_ {n-1})} = \\\\ \\frac{(m_ {k+1} - k)_ {* }}{(a_ {i} - k)_ {* }} \\cdot \\frac{(a^{\\prime}_ {i} - l)_ {* }}{(m_ {l} - l)_ {* }} \\prod^{l-1}_ {j=k+1} \\frac{(m_ {j+1} - j)_ {* }}{(m_ {j} - j)_ {* }} $

且它 $ \\ge 1 $因为 $ a_ {i} \\le m_ {k+1}, a^{\\prime}_ {i} \\ge m_ {l}, m_ {j+1} \\ge m_ {j}, j = k+1, \\ldots, l-1 $

我们现在有了Hall定理的第二个形式，我们记 $ N(A_ {0}, \\ldots, A_ {n-1}) $ 为 $ (A_ {0}, \\ldots, A_ {n-1}) $ SDR的个数

**定理** 设 $ (A_ {0}, \\ldots, A_ {n-1}) $为集合S的一系列子集。设 $ m_ {i} := \| A_ {i} \| (i = 0, \\ldots, n-1) $且设 $ m_ {0} \\le m_ {1} \\le \\cdots \\le m_ {n-1} $

如果序列有属性H，则

$ N(A_ {0}, \\ldots, A_ {n-1}) \\ge F_ {n}(m_ {0}, \\ldots, m_ {n-1}) $

证明：使用归纳法。当n = 1时明显是成立的，我们区分两种情况

情况1，没有critical block。这种情况下，我们选择 $ A_ {0} $的任意元素a作为它的代表且然后从其他集合中删除a。这样的集合，我们称为 $ A_ {1}(a), \\ldots, A_ {n-1}(a) $，且对这些集合H属性依然成立。通过归纳假设和引理，我们发现

$ \\begin{aligned} N(A_ {0}, \\ldots, A_ {n-1}) &\\ge \\sum_ {a \\in A_ {0}} f_ {n-1}(\| A_ {1}(a) \|, \\ldots, \| A_ {n-1}(a) \|) \\\\ &\\ge \\sum_ {a \\in A_ {0}} f_ {n-1}(m_ {1} - 1, \\ldots, m_ {n-1} - 1) \\\\ &= m_ {0}f_ {n-1}(m_ {1} - 1, \\ldots, m_ {n-1} - 1) \\\\ &= F_ {n}(m_ {0}, m_ {1}, \\ldots, m_ {n-1}) \\end{aligned} $

情况2，有一个critical block $ (A_ {\\upsilon_ {0}}, \\ldots, A_ {\\upsilon_ {k-1}}), \\upsilon_ {0} < \\cdots < \\upsilon_ {k-1}, 0 < k < n $。在这种情况下，我们从所有其他集合 $ A_ {i} $中删除 $ A_ {\\upsilon_ {0}} \\cup \\cdots \\cup A_ {\\upsilon_ {k-1}} $的所有元素，生成 $ A^{\\prime}_ {\\mu_ {0}}, \\ldots, A^{\\prime}_ {\\mu_ {l-1}}, \\{\\upsilon_ {0}, \\ldots, \\upsilon_ {k-1}, \\mu_ {0}, \\ldots, \\mu_ {l-1} \\} = \\{0, 1, \\ldots, n-1\\}, k + l = n $

现在 $ (A_ {\\upsilon_ {0}}, \\ldots, A_ {\\upsilon_ {k-1}}), (A^{\\prime}_ {\\mu_ {0}}, \\ldots, A^{\\prime}_ {\\mu_ {l-1}}) $满足属性H且两个序列的SDR不相交。因此通过归纳假设和引理，我们有

$ \\begin{aligned} N(A_ {0}, \\ldots, A_ {n-1}) &= N(A_ {\\upsilon_ {0}}, \\ldots, A_ {\\upsilon_ {k-1}}) N(A^{\\prime}_ {\\mu_ {0}}, \\ldots, A^{\\prime}_ {\\mu_ {l-1}}) \\\\ &\\ge f_ {k}(m_ {\\upsilon_ {0}}, \\ldots, m_ {\\upsilon_ {k-1}}) f_ {l}(\| A^{\\prime}_ {\\mu_ {0}} \|, \\ldots, \| A^{\\prime}_ {\\mu_ {l-1}}) \\\\ &\\ge f_ {k}(m_ {\\upsilon_ {0}}, \\ldots, m_ {\\mu_ {\\upsilon_ {k-1}}}) f_ {l}(\| A^{\\prime}_ {\\mu_ {0}} \|, \\ldots, \| A^{\\prime}_ {\\mu_ {l-1}} \|) \\\\ &\\ge f_ {k}(m_ {\\upsilon_ {0}}, \\ldots, m_ {\\upsilon_ {k-1}}) f_ {l}(m_ {\\mu_ {0}} - k, \\ldots, m_ {\\mu_ {l-1}} - k) \\\\ &\\ge f_ {k}(m_ {0}, \\ldots, m_ {k-1}) f_ {l}(m_ {\\mu_ {0}} - k, \\ldots, m_ {\\mu_ {l-1}} - k) \\end{aligned} $

现在我们标注

$ m_ {\\upsilon_ {k-1}} \\le \| A_ {\\upsilon_ {0}} \\cup \\cdots \\cup A_ {\\upsilon_ {k-1}} \| = k $

且因此我们有

$ (m_ {r} - r)_ {* } = 1 $ 如果 $ k \\le r \\le \\upsilon_ {k-1} $

且

$ (m_ {\\mu_ {i}} - k - i)_ {* } = 1 $ 如果 $ \\mu_ {i} \\le \\upsilon_ {k-1} $

这意味着

$ f_ {k}(m_ {0}, \\ldots, m_ {k-1}) = \\prod_ {0 \\le i \\le \\upsilon_ {k-1}} (m_ {i} - i)_ {* } $

$ f_ {l}(m_ {\\mu_ {0}} - k, \\ldots, m_ {\\mu_ {l-1}} - k) = \\prod_ {\\upsilon_ {k-1} < j < n} (m_ {j} - j)_ {* } $

这样得证

**定理** 包含A的所有1的A的线的最小个数等于两两不在一条线上的A的1的最大个数

证明 设m为包含A的所有1的A的线的最小个数，M为两两不在一条线上的1的最大个数。明显的，$ m \\ge M $。设包含r行s列(r + s = m)的线的最小覆盖。不失一般性，它们是头r行和头s列。我们现在定义集合 $ A_ {i}, 1 \\le i \\le r, A_ {i} := \\{j > s: a_ {ij} = 1\\} $。如果某个 $ A_ {i} $的k元组包含小于k个元素，依然覆盖所有的1。因为这是不可能的，我们看到 $ A_ {i} $的满足H属性。这样 $ A_ {i} $有一个SDR。这意味着有r个1，在头r行和非头s列中，两两互不在一条线上。相似地，有s个1，在头s列和非头r行中，两两互不在一条线上。这说明 $ M \\ge r + s = m $，则得证

**定理** 设 $ A = (a_ {ij}) $为一个 $ n \\times n $矩阵，条目为非负整数，使得A的每一行和列有和1。则A是和为l的排序矩阵

证明：定义 $ A_ {i}, 1 \\le i \\le n, A_ {i} := \\{j: a_ {ij} > 0\\} $。对任意 $ A_ {i} $的k元组，A的对应行的和是kl。因为A的每列有和l，在选中行中的非零元素必须至少在k列。因此 $ A_ {i} $满足H属性。$ A_ {i} $的一个SDR对应矩阵 $ P = (p_ {ij}) $的一个排序使得 $ a_ {ij} > 0 $如果 $ p_ {ij} = 1 $。定理通过归纳法可得

**定理** 如果存在一个匹配 $ M_ {1} $ 覆盖X的一个子集 $ X_ {0} $且存在一个匹配 $ M_ {2} $覆盖Y的一个子集 $ Y_ {0} $，则存在一个匹配 $ M_ {3} $覆盖 $ X_ {0} \\cup Y_ {0} $

证明：考虑 $ M_ {1} $的边为红色边，$ M_ {2} $的边为蓝色边。如果一条边属于 $ M_ {1}, M_ {2} $，则它是紫色的

一个所有顶点度数最多为2的连接图容易看出为下面中的一个：一个有限路径图（允许长度为0，当部分为一个顶点而没有边），一个有限多边形，一个有限两分路径图。图H，其顶点为G的顶点，边为 $ M_ {1} \\cup M_ {2} $有属性每个顶点度数最多为2，这样它的连通部分为以上类型。这些部分的边，除了包含紫边和其两个顶点的部分，为交替的红蓝色。特别地，所有的多边形有偶数长度。$ X_ {0} \\cup Y_ {0} $的每个顶点在这些部分中的之一中

对匹配 $ M_ {3} $，我们将选择所有紫色边，且H的每个其他部分的所有红色边或蓝色边。从循环和无限两分路径中，它是没问题的；选择所有红色或蓝色边，且它们将覆盖部分的所有顶点。对奇数长度的路径和无限一分路径，选所有红色或蓝色边取决于第一条边是否为红色或蓝色。这样，选择的边将覆盖部分的所有顶点

我们更深一步考虑偶数长度的有限路径P，其有顶点 $ \\upsilon_ {0}, \\upsilon_ {1}, \\ldots, \\upsilon_ {k} $。有奇数个顶点且它们交替在X和Y中，这样 $ \\upsilon_ {0}, \\upsilon_ {k} $同时在X中或Y中。如果它们在X中，选择P中所有红色边（$ M_ {1} $）并把它们放入 $ M_ {3} $；如果都在Y中，则选择P的所有蓝边并放入 $ M_ {3} $。只有路径的一个末点没有被选择的边覆盖

考虑 $ \\upsilon_ {0}, \\upsilon_ {k} \\in X $的情况。如果P的第一条边为红色，则最后一条为蓝色且它有 $ \\upsilon_ {k} \\notin X_ {0} $因为没有 $ M_ {1} $的边覆盖 $ \\upsilon_ {k} $。这样P的红边依然覆盖 $ X_ {0}, Y_ {0} $的所有边。第一条边为蓝边的情况相似

对 $ X_ {0} = X, Y_ {0} = Y $的情况，且当图G是完全两分的，覆盖 $ X_ {0} $ 或 $ Y_ {0} $的匹配对应可被解释为单射 $ X \\to Y $ 或 $ Y \\to X $
