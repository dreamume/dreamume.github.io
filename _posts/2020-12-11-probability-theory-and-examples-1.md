---
layout:     post
title:      "Probability: Theory and Exmaples(Chapter 1) by Durrett"
subtitle:   "Measure Theory"
thumbnail-img: ""
date:       2020-12-11 01:00
author:     "dreamume"
tags: 		[probability]
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

1.  [Measure Theory](#org5966362)
    1.  [Probability Spaces](#orga94cfd0)


<a id="org5966362"></a>

# Measure Theory


<a id="orga94cfd0"></a>

## Probability Spaces

一个Probability space是一个3元组 $ \\left(\\Omega, \\mathcal{F}, P\\right), \\Omega $是输出的集合，$ \\mathcal{F} $是事件集合，$ P : \\mathcal{F} \\to [0, 1] $是一个事件概率函数。我们假设 $ \\mathcal{F} $是一个 $ \\sigma $域（或 $ \\sigma $代数），例如，一个 $ \\Omega $的子集的（非空）集合满足

(i) 如果 $ A \\in \\mathcal{F} $，则 $ A^{c} \\in \\mathcal{F} $，且

(ii) 如果 $ A_ {i} \\in \\mathcal{F} $ 是集合的可数序列则 $ \\cup_ {i}A_ {i} \\in \\mathcal{F} $

这里及如下的可数表示有限或可数无穷个。因为 $ \\cap_ {i}A_ {i} = \\left(\\cup_ {i}A_ {i}^{c}\\right)^{c} $，它说明一个 $ \\sigma $域在可数个交集下是闭合的。我们忽略定义最后的属性使它容易检查。

没有P的话，$ \\left(\\Omega, \\mathcal{F} \\right) $称为度量空间，例如，它是一个可以测量的空间。一个度量是一个非负可数加集函数；即一个函数 $ \\mu : \\mathcal{F} \\to R $，有

(i) $ \\forall A \\in \\mathcal{F}, \\mu\\left(A\\right) \\ge \\mu\\left(\\emptyset\\right) = 0 $，且

(ii) 如果 $ A_ {i} \\in \\mathcal{F} $是一个不相交集合的可数序列，则

$ \\begin{equation} \\mu\\left(\\cup_ {i}A_ {i}\\right) = \\sum_ {i}\\mu\\left(A_ {i}\\right) \\end{equation} $

如果 $ \\mu\\left(\\Omega\\right) = 1 $，我们称 $ \\mu $ 为一个概率测度。本书中，概率测度通常记为P

下面的结果给了我们后面需要的度量定义的一些结论。在所有的例子中，我们假设我们提到的集合在 $ \\mathcal{F} $中

**定理 1.1.1** 设 $ \\mu $为 $ \\left(\\Omega, \\mathcal{F}\\right) $上的一个测度

(i) 单调性，如果 $ A \\subset B 则 \\mu\\left(A\\right) \\le \\mu\\left(B\\right) $

(ii) 子加和，如果 $ A \\subset \\cup_ {m=1}^{\\infty} A_ {m} 则 \\mu\\left(A\\right) \\le \\sum_ {m=1}^{\\infty}\\mu\\left(A_ {m}\\right) $

(iii) 连续向下，如果 $ A_ {i} \\uparrow A $（例如，$ A_ {1} \\subset A_ {2} \\subset \\ldots $ 且 $ \\cup_ {i}A_ {i} = A $）则 $ \\mu\\left(A_ {i}\\right) \\uparrow \\mu\\left(A\\right) $

(iv) 连续向上，如果 $ A_ {i} \\downarrow A $（例如，$ A_ {1} \\supset A_ {2} \\supset \\ldots $ 且 $ \\cap_ {i}A_ {i} = A, \\mu\\left(A_ {1}\\right) < \\infty $）则 $ \\mu\\left(A_ {i}\\right) \\downarrow \\mu\\left(A\\right) $

例子 1.1.3 实数线上的度量。$ (\\mathbf{R}, \\mathcal{R}) $上的度量被定义为给定一个Stieltjes度量函数，有以下属性：

(i) F是非递减的

(ii) F是右连续的，例如 $ lim_ {y \\downarrow x} F\\left(y\\right) = F\\left(x\\right) $

**定理 1.1.4** 对于每个Stieltjes度量函数，有一个在 $ (\\mathbf{R}, \\mathcal{R}) $上唯一的度量 $ \\mu, \\mu\\left( (a, b]\\right) = F\\left(b\\right) - F\\left(a\\right) $

F(x) = x 该度量被称为Lebesgue度量

集合的集 $ \\mathbf{S} $为称为是一个semialgebra如果 (i) 它在交集下是闭合的，例如，$ S, T \\in \\mathbf{S} $ 意味着 $ S \\cap T \\in \\mathbf{S} $，且 (ii) 如果 $ S \\in \\mathbf{S} $则 $ S^{c} $是 $ \\mathbf{S} $中有限不相关集合的并。一个重要的semialgebra例子是

例子 1.1.5 $ \\mathbf{S}_ {d} = $ 空集加上如下形式的所有集合

$ \\begin{equation} (a_ {1}, b_ {1}] \\times \\cdots \\times (a_ {d}, b_ {d}] \\subset \\mathbf{R}^{d} \\qquad - \\infty \\le a_ {i} < b_ {i} \\le \\infty \\end{equation} $

**引理 1.1.7** 如果 $ \\mathcal{S} $ 是一个semialgebra则 $ \\bar{\\mathcal{S}} = \\{ \\mathcal{S}中有限不相交集合的并 \\} $是一个代数，称为由 $ \\mathcal{S} $产生的代数

代数 $ \\mathcal{A} $上的度量，我们表示为一个集合函数 $ \\mu $，

(i) $ \\forall A \\in \\mathcal{A}, \\mu\\left(A\\right) \\ge \\mu\\left(\\emptyset\\right) = 0 $，且

(ii) 如果 $ A_ {i} \\in \\mathcal{A} $是不相交的且它们的并在 $ \\mathcal{A} $中，则

$ \\begin{equation} \\mu\\left(\\cup_ {i=1}^{\\infty}A_ {i}\\right) = \\sum_ {i=1}^{\\infty}\\mu\\left(A_ {i}\\right) \\end{equation} $

$ \\mu $被称为是 $ \\sigma-finite $如果有一个集合序列 $ A_ {n} \\in \\mathcal{A} $，使得 $ \\mu\\left( A_ {n} \\right) < \\infty $ 且 $ \\cup_ {n}A_ {n} = \\Omega $。设 $ A'_ {1} = A_ {1} $且对 $ n \\ge 2 $，

$ \\begin{equation} A'_ {n} = \\cup_ {m=1}^{n}A_ {m} \\qquad 或 \\qquad A'_ {n} = A_ {n} \\cap \\left(\\cap_ {m=1}^{n-1}A_ {m}^{c}\\right) \\in \\mathcal{A} \\end{equation} $

我们可不失一般性假设 $ A_ {n} \\uparrow \\Omega $ 或 $ A_ {n} $是不相交的。

**定理 1.1.9** 设 $ \\mathcal{S} $为semialgebra且设 $ \\mu $定义在 $ \\mathcal{S} $上有 $ \\mu\\left(\\emptyset\\right) = 0 $。假设 (i) 如果 $ S \\in \\mathcal{S} $是一个有限集合 $ S_ {i} \\in \\mathcal{S} $的不相交并则 $ \\mu\\left(S\\right) = \\sum_ {i}\\mu\\left(S_ {i}\\right) $，且 (ii) 如果 $ S_ {i}, S \\in \\mathcal{S}, S = +_ {i \\ge 1}S_ {i} 则 \\mu\\left(S\\right) \\le \\sum_ {i \\ge 1}\\mu\\left(S_ {i}\\right) $。则 $ \\mu $ 有一个唯一的扩展 $ \\bar{\\mu} $是由 $ \\mathcal{S} $产生的代数 $ \\bar{\\mathcal{S}} $的一个度量。如果 $ \\bar{\\mu} $是sigma-finite则由一个唯一的扩展v是 $ \\sigma\\left(\\mathcal{S}\\right) $上的一个度量

在上面的(ii)中， $ i \\ge 1 $表示一个可数的并，普通下标i或j表示一个有限的并

**引理 1.1.10** 假设只有 (i) 满足，则

(a) 如果 $ A, B_ {i} \\in \\bar{\\mathcal{S}}, A = +_ {i=1}^{n}B_ {i},则 \\bar{\\mu}\\left(A\\right) = \\sum_ {i}\\bar{\\mu}\\left(B_ {i}\\right) $

(b) 如果 $ A, B_ {i} \\in \\bar{\\mathcal{S}}, A \\subset \\cup_ {i=1}^{n}B_ {i},则 \\bar{\\mu}\\left(A\\right) \\le \\sum_ {i}\\bar{\\mu}\\left(B_ {i}\\right) $

**$ R^{d} $上的度量** 我们下一个目标是证明定理 1.1.4对 $ R^{d} $上的版本。首先是在定义函数F上引入假设。同d = 1时相似，假设：

(i) 它是非递减的，例如，如果 $ x \\le y $（意思是 $ \\forall i, x_ {i} \\le y_ {i} $）则 $ F\\left(x\\right) \\le F\\left(y\\right) $

(ii) F是右连续的，例如，$ lim_ {y \\downarrow x} F\\left(y\\right) = F \\left(x\\right) $（这里 $ y \\downarrow x $表示每个 $ y_ {i} \\downarrow x_ {i} $）

(iii) 如果 $ x_ {n} \\downarrow - \\infty $，例如，每个坐标有 $ F\\left(x_ {n}\\right) \\downarrow 0 $，如果 $ x_ {n} \\uparrow - \\infty $，例如，每个坐标有 $ F\\left(x_ {n}\\right)  \\uparrow 1 $

考虑如下的F

$ \\begin{equation} F\\left(x_ {1}, x_ {2}\\right) = \\{ \\begin{array}{ll} 1 & \\text{ if } x_ {1}, x_ {2} \\ge 1 \\\\ \\frac{2}{3} & \\text{ if } x_ {1} \\ge 1 \\text{ and } 0 \\le x_ {2} < 1 \\\\ \\frac{2}{3} & \\text{ if } x_ {2} \\ge 1 \\text{ and } 0 \\le x_ {1} < 1 \\\\ 0 & otherwise \\end{array} \\right. \\end{equation} $

一点思考显示如下

$ \\begin{equation} \\begin{aligned} \\mu\\left((a_ {1}, b_ {1}] \\times (a_ {2}, b_ {2}]\\right) &= \\mu\\left((- \\infty, b_ {1}] \\times (- \\infty, b_ {2}]\\right) - \\mu \\left((- \\infty, a_ {1}] \\times (- \\infty, b_ {2}]\\right) \\\\ &- \\mu \\left((- \\infty, b_ {1}] \\times (- \\infty, a_ {2}]\\right) + \\mu\\left((- \\infty, a_ {1}] \\times (- \\infty, a_ {2}]\\right) \\\\ &= F\\left(b_ {1}, b_ {2}\\right) - F\\left(a_ {1}, b_ {2}\\right) - F\\left(b_ {1}, a_ {2}\\right) + F\\left(a_ {1}, a_ {2}\\right) \\end{aligned} \\end{equation} $

使 $ a_ {1} = a_ {2} = 1 - \\epsilon且 b_ {1} = b_ {2} = 1 且设 \\epsilon \\to 0 $我们看到

$ \\begin{equation} \\mu\\left(\\{1, 1\\}\\right) = 1 - \\frac{2}{3} - \\frac{2}{3} + 0 = - \\frac{1}{3} \\end{equation} $

相似的推理显示 $ \\mu\\left(\\{1, 0\\}\\right) = \\mu\\left(\\{0, 1\\}\\right) = \\frac{2}{3} $

为定义度量，创造F的第三个即最后的条件，设

$ \\begin{equation} A = (a_ {1}, b_ {1}] \\times \\cdots \\times (a_ {d}, b_ {d}] \\end{equation} $

$ \\begin{equation} V = \\{a_ {1}, b_ {1}\\} \\times \\cdots \\times \\{a_ {d}, b_ {d}\\} \\end{equation} $   

$ - \\infty < a_ {i} < b_ {i} < \\infty $。为强调 $ \\infty $是不允许的，我们称A为一个有限方块。则V = 方块A中的向量。如果 $ v \\in V $，设

$ \\begin{equation} \\operatorname{sgn}\\left(v\\right) = \\left(-1\\right)^{\\# \\text{ of a's in v}} \\end{equation} $

$ \\begin{equation} \\triangle_ {A}F = \\sum_ { v \\in V} \\operatorname{sgn}\\left(v\\right)F\\left(v\\right) \\end{equation} $

我们将设 $ \\mu\\left(A\\right) = \\triangle_ {A}F $，所以我们必须假设

(iv) $ \\triangle_ {A}F \\ge 0 $ 对所有方块A

**定理 1.1.11** 假设 $ F: \\mathbf{R}^{d} \\to [0, 1] $满足上述的(i) - (iv)。则有一个 $ \\left(\\mathbf{R}^{d}, \\mathcal{R}^{d} \\right) $上的唯一概率度量 $ \\mu $使得对所有方块 $ \\mu\\left(A\\right) = \\triangle_ {A}F $
