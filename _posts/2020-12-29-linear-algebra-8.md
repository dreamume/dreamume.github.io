---
layout:     post
title:      "Linear Algebra(Chapter 8) by Hoffman"
subtitle:   "Inner Product Spaces"
thumbnail-img: ""
date:       2020-12-29 21:48
author:     "dreamume"
tags: 		[linear algebra]
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

1.  [Inner Products](#orgf9c15e0)
2.  [Inner Product Spaces](#org39befc0)


<a id="orgf9c15e0"></a>

# Inner Products

本章我们只考虑实数或复数向量空间。

**定义** 设F为实数或复数域，且V是F上的一个向量空间。一个V上的inner product是一个函数，赋值V中每个有序向量对 $ \\alpha, \\beta $一个F中常量 $ (\\alpha \| \\beta) $使得对V中所有 $ \\alpha, \\beta, \\gamma $ 和所有常量c

(a) $ (\\alpha + \\beta \| \\gamma ) = (\\alpha \| \\gamma) + (\\beta \| \\gamma) $

(b) $ (c \\alpha \| \\beta) = c(\\alpha \| \\beta) $

(c) $ (\\beta \| \\alpha) = \\overline{(\\alpha \| \\beta)} $，上横线表示复数conjugation

(d) $ (\\alpha \| \\alpha) > 0 如果 \\alpha \\ne 0 $

例子1，在 $ F^{n} $上有一个inner product我们称之为standard inner product。它定义为当 $ \\alpha = (x_ {1}, \\ldots, x_ {n})和 \\beta = (y_ {1}, \\ldots, y_ {n}) $时，

$ \\begin{equation} (\\alpha \| \\beta) = \\sum_ {j} x_ {j}\\bar{y}_ {j} \\end{equation} $

在实数域上，该standard inner product通常称为点积或常量积且被记为 $ \\alpha \\cdot \\beta $

例子3，设V为 $ F^{n \\times n} $，F上所有 $ n \\times n $矩阵的空间。则V根 $ F^{n^{2}} $同构。等式

$ \\begin{equation} (A \| B) = \\sum_ {j,k} A_ {j k} \\bar{B}_ {j k} \\end{equation} $

定义V上的一个inner product。更进一步，如果我们引入conjugate transpose 矩阵 $ B^{ * }, B_ {k j}^{ * } = \\bar{B}_ {j k}  $，我们表达 $ F^{ n \\times n} $上的trace函数的inner product：

$ \\begin{equation} (A \| B) = \\operatorname{tr}(AB^{ * }) = \\operatorname{tr}(B^{ * }A) \\end{equation} $

$ \\begin{equation} \\begin{aligned} \\operatorname{tr}(AB^{ * } ) &= \\sum_ {j}(AB^{ *})_ {j j} \\\\ &= \\sum_ {j} \\sum_ {k} A_ {j k}B_ {k j}^{ * } \\\\ &= \\sum_ {j} \\sum_ {k} A_ {j k}\\bar{B}_ {j k} \\end{aligned} \\end{equation} $

例子4 设 $ F^{n \\times 1} $为F上 $ n \\times 1 $矩阵空间，且设Q为F上 $ n \\times n $可逆矩阵，对在 $ F^{n \\times 1} $集合上的X, Y

$ \\begin{equation} (X \| Y) = Y^{ * }Q^{ * }QX \\end{equation} $

我们称它为 $ F^{ n \\times 1 } $上的standard inner product

假设V是有限维的，则 $ \\mathcal{B} = \\{\\alpha_ {1}, \\ldots, \\alpha_ {n} \\} $是V的一个有序基，且我们给定一个V上特殊的inner product，我们将显示这个inner product完全被值 $ G_ {j k} = (\\alpha_ {k} \| \\alpha_ {j}) $决定。如果 $ \\alpha = \\sum_ {k}x_ {k}\\alpha_ {k} 和 \\beta = \\sum_ {j}y_ {j} \\alpha_ {j} $，则

\\begin{equation} \\begin{aligned} (\\alpha \| \\beta) &= (\\sum_ {k}x_ {n}\\alpha_ {k} \| \\beta) \\\\ &= \\sum_ {k}x_ {k}(\\alpha_ {k} \| \\beta) \\\\ &= \\sum_ {k}x_ {k}\\sum_ {j}\\bar{y}_ {j} (\\alpha_ {k} \| \\alpha_ {j}) \\\\ &= \\sum_ {j, k}\\bar{y}_ {j} G_ {j k}x_ {k} \\\\ &= Y^{ * }GX \\end{aligned} \\end{equation} $

我们称G为在有序基 $ \\mathcal{B} $下inner product的矩阵


<a id="org39befc0"></a>

# Inner Product Spaces

**定义** 一个内积空间是一个实数或复数向量空间，及其上一个指定的内积

一个有限维实数内积空间通常称为欧几里得空间。一个复数内积空间通常称为unitary空间

**定理 1** 如果V是一个内积空间，则对V中任意向量 $ \\alpha, \\beta $和任意常数c

(i) $ \|\|c \\alpha \| \| = \|c\| \|\|\\alpha \|\| $

(ii) $ \| \| \\alpha \| \| > 0 \\text{ for } \\alpha \\ne 0 $

(iii) $ \| (\\alpha \| \\beta) \| \\le \| \| \\alpha \| \| \| \| \\beta \| \| $

(iv) $ \| \| \\alpha + \\beta \| \| \\le \| \| \\alpha \| \| + \| \| \\beta \| \| $

例子7，应用Cauchy-Schwarz不等式到内积，我们有

(a) $ \\begin{equation} \| \\sum x_ {k}\\bar{y}_ {k} \| \\le (\\sum \|x_ {k}\|^{2})^{\\frac{1}{2}} (\\sum \|y_ {k}\|^{2})^{\\frac{1}{2}} \\end{equation} $

(b) $ \\begin{equation} \| x_ {1}y_ {1} - x_ {2}y_ {1} - x_ {1}y_ {2} + 4x_ {2}y_ {2} \| \\le ((x_ {1} - x_ {2})^{2} + 3x_ {2}^{2})^{\\frac{1}{2}} ((y_ {1} - y_ {2})^{2} + 3y_ {2}^{2})^{\\frac{1}{2}} \\end{equation} $

(c) $ \\begin{equation} \| \\operatorname{tr} (AB^{ * }) \| \\le (\\operatorname{tr}(AA^{ * }))^{\\frac{1}{2}} (\\operatorname{tr}(BB^{ * }))^{\\frac{1}{2}} \\end{equation} $

(d) $ \\begin{equation} \| \\int_ {0}^{1} f(x)\\overline{g(x)} dx \| \\le \\left(\\int_ {0}^{1} \| f(x) \|^{2} dx\\right)^{\\frac{1}{2}} \\left(\\int_ {0}^{1} \| g(x) \|^{2} dx\\right)^{\\frac{1}{2}} \\end{equation} $

**定义** 设 $ \\alpha 和 \\beta $为内积空间上的向量，则 $ \\alpha $正交 $ \\beta 仅当 (\\alpha \| \\beta) = 0 $。如果S是V中向量集合，S被称为一个正交集提供所有不同正交向量对。一个标准正交集合是正交集合S中所有 $ \| \| \\alpha \| \| = 1 $的向量

**定理 2** 正交集的非零向量是线性无关的

**推论** 如果一个向量 $ \\beta $是正交非零向量序列 $ \\alpha_ {1}, \\ldots, \\alpha_ {m} $的线性组合，则 $ \\beta $是一个特别的线性组合

$ \\begin{equation} \\beta = \\sum_ {k=1}^{m} \\frac{(\\beta \| \\alpha_ {k})}{\|\| \\alpha_ {k} \|\|^{2}} \\alpha_ {k} \\end{equation} $

**定理 3** 设V为一个内积空间且设 $ \\beta_ {1}, \\ldots, \\beta_ {n} $为V上任意无关向量，则可构造V中正交向量 $ \\alpha_ {1}, \\ldots, \\alpha_ {n} $使得对每个 $ k = 1, 2, \\ldots, n $，集合 $ \\{ \\alpha_ {1}, \\ldots, \\alpha_ {k} $是由 $ \\beta_ {1}, \\ldots, \\beta_ {k} $扩展的子空间的一个基

证明：向量 $ \\alpha_ {1}, \\ldots, \\alpha_ {n} $可通过Gram-Schmidt正交过程构建，首先设 $ \\alpha_ {1} = \\beta_ {1} $，假设 $ \\alpha_ {1}, \\ldots, \\alpha_ {m} (1 \\le m < n) $被选中使得对每个k， $ \\{ \\alpha_ {1}, \\ldots, \\alpha_ {k} \\}, 1 \\le k \\le m $是由 $ \\beta_ {1}, \\ldots, \\beta_ {k} $扩展的V的子空间的一个正交基，设

$ \\begin{equation} \\alpha_ {m+1} = \\beta_ {m+1} - \\sum_ {k=1}^{m} \\frac{(\\beta_ {m+1} \| \\alpha_ {k})}{\|\| \\alpha_ {k} \|\|^{2}} \\alpha_ {k} \\end{equation} $

如果 $ 1 \\le j \\le m $，则

$ \\begin{equation} \\begin{aligned} (\\alpha_ {m+1} \| \\alpha_ {j}) &= (\\beta_ {m+1} \| \\alpha_ {j}) - \\sum_ {k=1}^{m} \\frac{(\\beta_ {m+1} \| \\alpha_ {k})}{\|\| \\alpha_ {k} \|\|^{2}} (\\alpha_ {k} \| \\alpha_ {j}) \\\\ &= (\\beta_ {m+1} \| \\alpha_ {j}) - (\\beta_ {m+1} \| \\alpha_ {j}) \\\\ &= 0 \\end{aligned} \\end{equation} $

因此 $ \\{ \\alpha_ {1}, \\ldots, \\alpha_ {m+1} \\} $是一个正交集合

**推论** 每个有限维内积空间有一个标准正交基

在内积空间W中向量到 $ \\beta $的最好估计是W中一个向量 $ \\alpha $使得

$ \\begin{equation} \| \| \\beta - \\alpha \| \| \\le \| \| \\beta - \\gamma \| \| \\end{equation} $

对W中每个向量 $ \\gamma $

**定理 4** 设W为内积空间V的一个子空间且设 $ \\beta $为V中一个向量

(i) W中向量 $ \\alpha $是W中到 $ \\beta $的最好估计当且仅当 $ \\beta - \\alpha $正交W中每个向量

(ii) 如果W中到 $ \\beta $的最好估计存在，它是唯一的

(iii) 如果W是有限维的且 $ \\{ \\alpha_ {1}, \\ldots, \\alpha_ {n} \\} $是W的任意标准正交基，则向量

$ \\begin{equation} \\alpha = \\sum_ {k} \\frac{(\\beta \| \\alpha_ {k})}{\|\| \\alpha_ {k} \|\|^{2}} \\alpha_ {k} \\end{equation} $

是W中向量唯一到 $ \\beta $的最好估计

**定义** 设V是一个内积空间且S是V中任意向量集合，S的正交补是V中集合 $ S^{\\perp} $中的所有向量，与S中的每个向量正交

**定义** 如果定理4中的向量 $ \\alpha $存在则被称为在W上 $ \\beta $的正交映射。如果V中每个向量在W中有一个正交映射，对V中每个向量赋予映射到W上它的正交映射被称为在V在W上的正交映射

**推论** 设V为一个内积空间，W为一个有限维子空间，且E是V在W上的正交映射，则映射

$ \\begin{equation} \\beta \\to \\beta - E \\beta \\end{equation} $

是V到 $ W^{\\perp} $的正交映射

**定理 5** 设W为内积空间V的一个有限维子空间且设E为V到W的正交映射，则E是V到W的幂等线性转换，$ W^{\\perp} $是E的null space，且

$ \\begin{equation} V = W \\oplus W^{\\perp} \\end{equation} $

**推论** 在理论条件下，I - E是V到 $ W^{\\perp} $上的正交映射，它是V到 $ W^{\\perp} $的幂等线性转换，其null space是W

**推论** 设 $ \\{ \\alpha_ {1}, \\ldots, \\alpha_ {n} \\} $为内积空间V上的非零向量的正交集，则

$ \\begin{equation} \\sum_ {k} \\frac{\|(\\beta \| \\alpha_ {k}) \|^{2}}{\|\| \\alpha_ {k} \|\|^{2}} \\le \|\| \\beta\|\|^{2} \\end{equation} $

等式成立当且仅当

$ \\begin{equation} \\beta = \\sum_ {k}\\frac{(\\beta \| \\alpha_ {k})}{\|\| \\alpha_ {k} \|\|^{2}} \\alpha_ {k} \\end{equation} $
