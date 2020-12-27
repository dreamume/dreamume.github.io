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
    2.  [Distributions](#orgc14a0ba)


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

$ \\begin{equation} F\\left(x_ {1}, x_ {2}\\right) = \\left\\{ \\begin{array}{ll} 1 & \\text{ if } x_ {1}, x_ {2} \\ge 1 \\\\ \\frac{2}{3} & \\text{ if } x_ {1} \\ge 1 \\text{ and } 0 \\le x_ {2} < 1 \\\\ \\frac{2}{3} & \\text{ if } x_ {2} \\ge 1 \\text{ and } 0 \\le x_ {1} < 1 \\\\ 0 & \\text{ otherwise } \\end{array} \\right. \\end{equation} $

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

$ \\begin{equation} \\vartriangle_ {A}F = \\sum_ { v \\in V} \\operatorname{sgn}\\left(v\\right)F\\left(v\\right) \\end{equation} $

我们将设 $ \\mu\\left(A\\right) = \\vartriangle_ {A}F $，所以我们必须假设

(iv) $ \\vartriangle_ {A}F \\ge 0 $ 对所有方块A

**定理 1.1.11** 假设 $ F: \\mathbf{R}^{d} \\to [0, 1] $满足上述的(i) - (iv)。则有一个 $ \\left(\\mathbf{R}^{d}, \\mathcal{R}^{d} \\right) $上的唯一概率度量 $ \\mu $使得对所有方块 $ \\mu\\left(A\\right) = \\vartriangle_ {A}F $

**例子 1.1.12** 假设 $ F\\left(x\\right) = \\prod_ {i=1}^{d}F_ {i}\\left(x\\right), F_ {i} $满足定理1.1.4的(i)和(ii)。在这个情况下

$ \\begin{equation} \\vartriangle_ {A}F = \\prod_ {i=1}^{d} \\left(F_ {i}\\left(b_ {i}\\right) - F_ {i}\\left(a_ {i}\\right)\\right) \\end{equation} $

当 $ \\forall i, F_ {i}\\left(x\\right) = x $，这个度量被称为 $ R^{d} $上的Lebesgue度量

证明：对所有有限方块我们设 $ \\mu\\left(A\\right) = \\vartriangle_ {A}F $且使用单调性扩展定义 $ \\mathcal{S}_ {d} $。为检查定理1.1.9的(i)，称 $ A = +_ {k}B_ {k} $是A的一个规则子分割如果有一个序列 $ a_ {i} = \\alpha_ {i, 0} < \\alpha_ {i, 1} < \\cdots < \\alpha_ {i, n_ {i}} = b_ {i} $使得每个方块 $ B_ {k} $有形式

$ \\begin{equation} (\\alpha_ {1, j_ {1} - 1}, \\alpha_ {1, j_ {1}}] \\times \\cdots \\times (\\alpha_ {d, j_ {d} - 1}, \\alpha_ {d, j_ {d}}], 1 \\le j_ {i} \\le n_ {i} \\end{equation} $

容易看出对方块分割 $ \\lambda \\left(A\\right) = \\sum_ {k}\\lambda\\left(B_ {k}\\right) $。（首先考虑例子所有的终点是有限的且利用限制来获得一般例子）扩展这个结果到一般化的有限子分割 $ A = +_ {j}A_ {j} $，进一步分割得到一个规则的分割形式。

(ii)的证明根定理1.1.4里的基本一样。为简化我们设

$ \\begin{equation} \\left(x, y\\right) = \\left(x_ {1}, y_ {1}\\right) \\times \\cdots \\times \\left(x_ {d}, y_ {d}\\right) \\end{equation} $

$ \\begin{equation} (x, y] = (x_ {1}, y_ {1}] \\times \\cdots \\times (x_ {d}, y_ {d}] \\end{equation} $

$ \\begin{equation} [x, y] = [x_ {1}, y_ {1}] \\times \\cdots \\times [x_ {d}, y_ {d}] \\end{equation} $

$ x, y \\in R^{d} $。假设首先 $ - \\infty < a < b < \\infty $，不等式意味着每个部分是有限的，假设 $ (a, b] \\subset \\cup_ {i \\ge 1}(a^{i}, b^{i}], - \\infty < a^{i} < b^{i} < \\infty $。设 $ \\bar{1} = (1, \\ldots, 1), \\delta > 0 $使得

$ \\begin{equation} \\mu\\left((a + \\delta \\bar{1}, b]\\right) < \\mu\\left((a, b]\\right) + \\epsilon \\end{equation} $

带入 $ \\eta_ {i} $使得

$ \\begin{equation} \\mu\\left((a, b^{i} + \\eta_ {i} \\bar{1}]\\right) < \\mu\\left((a^{i}, b^{i}]\\right) + \\epsilon 2^{-i} \\end{equation} $

开放方块 $ \\left(a^{i}, b^{i} + \\eta_ {i} \\bar{1}\\right) $覆盖 $ [a + \\delta \\bar{1}, b] $，这样有一个有限子覆盖 $ \\left(\\alpha^{j}, \\beta^{j} \\right), 1 \\le j \\le J $。因为 $ (a + \\delta \\bar{1}, b] \\subset \\cup_ {i=1}^{J} (\\alpha^{j}, \\beta^{j}] $，(b)在引理1.1.10中意味着

$ \\begin{equation} \\mu\\left([a + \\delta \\bar{1}, b]\\right) \\le \\sum_ {j=1}^{J}\\mu\\left((\\alpha^{j}, \\beta^{j}]\\right) \\le \\sum_ {i=1}^{\\infty}\\mu\\left((a^{i}, b^{i} + \\eta_ {i}\\bar{1}]\\right) \\end{equation} $

这样，选择好 $ \\delta 和 \\eta_ {i} $，有

$ \\begin{equation} \\mu\\left((a, b]\\right) \\le 2 \\epsilon + \\sum_ {i=1}^{\\infty} \\mu\\left((a^{i}, b^{i}]\\right) \\end{equation} $

因为 $ \\epsilon $是任意的，我们已证明 $ - \\infty < a < b < \\infty $的结果。


<a id="orgc14a0ba"></a>

## Distributions

当我们定义随机变量在其上之后概率空间变得更有趣了。一个定义在 $ \\Omega $上的实值函数X为称为随机变量如果对每个Borel集 $ B \\subset R $我们有 $ X^{-1}\\left(B\\right) = \\{ \\omega: X\\left(\\omega\\right) \\in B\\} \\in \\mathcal{F} $。当我们需要强调 $ \\sigma $ -field，我们说X是 $ \\mathcal{F} $-measurable 或写成 $ X \\in \\mathcal{F} $。如果 $ \\Omega $是一个离散概率空间，则任意函数 $ X : \\Omega \\to \\mathbf{R} $是一个随机变量。一个有用的随机变量的例子为集合 $ A \\in \\mathcal{F} $的指导函数：

$ \\begin{equation} 1_ {A}\\left(\\omega\\right) = \\left\\{ \\begin{array}{ll} 1 & \\omega \\in A \\\\ 0 & \\omega \\notin A \\end{array} \\right. \\end{equation} $

该记号假设提醒你这个函数是A上的1。分析人士称这个对象为A的特征函数。在概率上，该术语使用有些不同

如果X是一个随机变量，则X引入R上一个概率测度称为它的分布，对Borel集合A设置 $ \\mu\\left(A\\right) = P\\left(X \\in A\\right) $。使用以上介绍的记号，右边可被写为 $ P\\left(X^{-1}\\left(A\\right)\\right) $。我们把 $ A \\in \\mathcal{R} $变为 $ X^{-1}\\left(A\\right) \\in \\mathcal{F} $且用P作用在该集合上。

为检测 $ \\mu $是一个概率度量我们观察到如果 $ A_ {i} $是不相交的则使用 $ \\mu $的定义；X落于联合中的事实当且仅当它落于 $ A_ {i} $中的一个；事实如果集合 $ A_ {i} \\in \\mathcal{R} $为不相交的则事件 $ \\{ X \\in A_ {i} \\} $是不相交的；且 $ \\mu $重定义；我们有

$ \\begin{equation} \\mu\\left(\\cup_ {i}A_ {i}\\right) = P\\left(X \\in \\cup_ {i}A_ {i}\\right) = P \\left(\\cup_ {i}\\{ X \\in A_ {i} \\}\\right) = \\sum_ {i}P\\left(X \\in A_ {i}\\right) = \\sum_ {i}\\mu\\left(A_ {i}\\right) \\end{equation} $

一个随机变量X的分布通常被描述为给定它的分布函数，$ F\\left(x\\right) = P\\left(X \\le x\\right) $

**定理 1.2.1** 任意分布函数F有如下属性：

(i) F是非递减的

(ii) $ \\lim_ {x \\to \\infty}F\\left(x\\right) = 1, \\lim_ {x \\to - \\infty}F\\left(x\\right) = 0 $

(iii) F是右连续的，例如，$ \\lim_ {y \\downarrow x}F\\left(y\\right) = F\\left(x\\right) $

(iv) 如果 $ F\\left(x-\\right) = \\lim_ {y \\uparrow x}F\\left(y\\right) 则 F\\left(x-\\right) = P\\left(X < x\\right) $

(v) $ P\\left(X = x\\right) = F\\left(x\\right) - F\\left(x-\\right) $

证明：为证明(i)，注意如果 $ x \\le y 则 \\{X \\le x\\} \\subset \\{X \\le y\\} $，且然后使用(i)在定理 1.1.1来得到 $ P\\left(X \\le x\\right) \\le P\\left(X \\le y\\right) $

为证明(ii)，我们观察到如果 $ x \\uparrow \\infty 则 \\{ X \\le x \\} \\uparrow \\Omega $，而如果 $ x \\downarrow - \\infty 则 \\{X \\le x\\} \\downarrow \\emptyset $且使用定理1.1.1的(iii)和(iv)

为证明(iii)，我们观察到如果 $ y \\downarrow x 则 \\{X \\le y\\} \\downarrow \\{ X \\le x \\} $

为证明(iv)，我们观察到如果 $ y \\uparrow x 则\\{X \\le y\\} \\uparrow \\{ X < x \\} $

对(v)，注意 $ P \\left(X = x\\right) = P\\left(X \\le x\\right) - P \\left(X < x\\right) $且使用(iii)和(iv)

**定理 1.2.2** 如果F满足定理1.2.1的(i)、(ii)和(iii)，则它是某个随机变量分布函数

证明：设 $ \\Omega = \\left(0, 1\\right), \\mathcal{F} = $ Borel集合，且P = Lebesgue测度，如果 $ \\omega \\in \\left(0, 1\\right) $，设

$ \\begin{equation} X\\left(\\omega\\right) = sup\\{y: F\\left(y\\right) < \\omega \\} \\end{equation} $

一旦我们显示

$ \\begin{equation} \\{ \\omega : X\\left(\\omega\\right) \\le x \\} = \\{ \\omega : \\omega \\le F\\left(x\\right) \\} \\end{equation} $

如果上式成立则即得证，因为 $ P\\left(\\omega: \\omega \\le F\\left(x\\right)\\right) = F\\left(x\\right) $

我们观察到如果 $ \\omega \\le F\\left(x\\right) 则 X\\left(\\omega\\right) \\le x $，因为 $ x \\notin \\{ y: F\\left(y\\right) < \\omega \\} $。如果 $ \\omega > F\\left(x\\right) $则因为F是右连续的，存在一个 $ \\epsilon > 0 使得 F\\left(x + \\epsilon\\right) < \\omega 且 X\\left(\\omega\\right) \\ge x + \\epsilon > x $

即使F可能不是1-1且onto的，我们将把X称为F的反且记它为 $ F^{-1} $。

如果X和Y在 $ \\left(\\mathbf{R}, \\mathcal{R} \\right) $上导入相同的分布 $ \\mu $，我们说X和Y在分布上相等。利用定理1.1.4，这个成立当且仅当X和Y有相同的分布函数，例如，$ \\forall x, P\\left(X \\le x\\right) = P\\left(Y \\le x \\right) $。这时我们会写成

$ \\begin{equation} X \\stackrel{d}{=} Y \\end{equation} $

但为了书写方便我们也使用 $ X =_ {d} Y $

当分布函数 $ F\\left(x\\right) = P\\left(X \\le x \\right) $有形如：

$ \\begin{equation} F\\left(x\\right) = \\int_ {- \\infty}^{x} f\\left(y\\right) dy \\end{equation} $

我们说X有密度函数f。为方便记忆公式，它通常可以认为f(x)为P(X = x)

$ \\begin{equation} P\\left(X = x\\right) = \\lim_ {\\epsilon \\to 0} \\int_ {x - \\epsilon}^{x + \\epsilon} f\\left(y\\right) dy = 0 \\end{equation} $

**例子 1.2.4** 速度 $ \\lambda $的指数分布。 $ f\\left(x\\right) = \\lambda e^{- \\lambda x}, x \\ge 0 $，否则为0。分布函数：

$ \\begin{equation} F\\left(x\\right) = \\left\\{ \\begin{array}{ll} 0 & x \\le 0 \\\\ 1 - e^{- \\lambda x} & x \\ge 0 \\end{array} \\right. \\end{equation} $

**例子 1.2.5** 标准正常分布

$ \\begin{equation} f\\left(x\\right) = \\left(2 \\pi\\right)^{- \\frac{1}{2}} exp\\left(\\frac{- x^{2}}{2}\\right) \\end{equation} $

在这个例子中，没有F(x)的闭合表达，但我们有如下边界对大x非常有用:
