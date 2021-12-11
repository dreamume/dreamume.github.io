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
