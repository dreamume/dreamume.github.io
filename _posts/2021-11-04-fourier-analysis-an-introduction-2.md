---
layout:     post
title:      "Fourier analysis an introduction(Chapter 2) by Stein"
subtitle:   "Basic Properties of Fourier Series"
thumbnail-img: ""
date:       2021-11-04 17:00
author:     "dreamume"
tags: 		[analysis]
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

1.  [主要定义和一些例子](#org4a21d8f)

在本章中，我们开始我们傅立叶级数的严谨地学习。我们设置舞台引入主题的主要目标，且然后公式化我们之前接触到的一些基本问题

我们第一个结果为布置问题的唯一性：两个带相同傅立叶系数的函数必须相等吗？事实上，一个简单地争论显示如果两个函数是连续的，则它们相等

接下来，我们更近地观察傅立叶级数的部分和。使用傅立叶系数公式，我们有关键观察这些和可方便的写成积分：

$ \\frac{1}{2 \\pi} \\int D_ {N}(x - y)f(y)dy $

$ \\{D_ {N}\\} $是一族汉森称为Dirichlet核。以上表达式是带函数 $ D_ {N} $的f的复杂阐述。一般地，给定一族函数 $ \\{K_ {n}\\} $，我们看极限当n趋于无穷时

$ \\frac{1}{2 \\pi} \\int K_ {n}(x - y)f(y)dy $

我们发现如果家族 $ \\{K_ {n}\\} $满足好核的三个重要属性，则上式趋于f(x)当 $ n \\to \\infty $（至少当f连续时）。这样，家族 $ \\{K_ {n}\\} $是一个大约估计。不幸地是，Dirichlet核 $ D_ {N} $不属于好核分类，其显示傅立叶级数的收敛问题是琐碎的

除了追求问题的收敛，我们考虑几个其他的方法求函数傅立叶级数的和。第一个方法，其包含部分和的平均，其属于好核，且是Fejer的重要定理。从这里，我们推演事实一个圆上的连续函数可被三角多项式统一估计。第二，我们也用Abel求傅立叶级数的和且其属于好核的家族。在这个情况中，其结果导致磁盘的稳定状态热力问题的Dirichlet问题的一个解

**问题的例子和想法**

我们开始我们应该考虑的函数类型的简单描述。因为f的傅立叶系数被定义为

$ a_ {n} = \\frac{1}{L} \\int^{L}_ {0}f(x)e^{-2 \\pi inx/L} dx, \\qquad \\text{for } n \\in \\mathbb{Z} $

f是[0, L]的复数值，它将需要在f上放置一些积分条件。我们将因此假设（本书后面）所有函数至少是黎曼可积的。有时它将被阐述聚焦我们的注意力在函数关于更规范上，即函数处理某个连续性或微分属性。如下，我们列出几类一般性增序的函数。我们强调我们不将一般性限制在实数函数上，相反我们将总是允许函数在复数上取值。更进一步，我们有时认为我们的函数被定义在一个圆上而不是一个间隔

**全连续函数**

复数值函数f在线段[0, L]上每点都连续。一个典型的连续函数如下图(a)。我们要注意之后连续函数在圆上满足额外的条件f(0) = f(L)

**分段连续函数**

在[0, L]上函数有有限个不连续不连续点。一个这样的函数如下图(b)

![img](../img/example_of_continuous_and_piecewise_continuous_functions.png)

**黎曼可积函数**

这是我们将考虑的最一般化的函数类。这样的函数有界，但有无穷多个不连续点。我们回忆积分的定义。一个在[0, L]上的实值函数f是黎曼可积的如果它有界且如果对任意 $ \\epsilon > 0 $，有一个在[0, L]上小的分割 $ 0 = x_ {0} < x_ {1} < \\cdots < x_ {N-1} < x_ {N} = L $，使得如果 $ \\mathcal{U}, \\mathcal{L} $，为这个分割的上和和下和，即

$ \\mathcal{U} = \\sum^{N}_ {j=1} [ \\operatorname{sup}_ {x_ {j-1} \\le x \\le x_ {j}} f(x)] (x_ {j} - x_ {j - 1}) $

$ \\mathcal{L} = \\sum^{N}_ {j=1} [ \\operatorname{inf}_ {x_ {j-1} \\le x \\le x_ {j}} f(x)] (x_ {j} - x_ {j - 1}) $

则我们有 $ \\mathcal{U} - \\mathcal{L} < \\epsilon $。最后，我们说一个复数值函数是可积的如果它的实部和虚部是可积的

一个简单的在[0, 1]上可积函数的例子，有无限多个不连续点

$ f(x) = \\left \\{ \\begin{array}{ll} 1 & \\text{if } 1 / (n + 1) < x \\le 1 / n \\text{ 且n是奇数} \\\\ 0 & \\text{if } 1 / (n+1) < x \\le 1 / n \\text{且n是偶数} \\\\ 0 & \\text{if } x = 0 \\end{array} \\right. $

这个例子展示如下图。注意f在 x = 1 / n和x = 0时是不连续的

![img](../img/example_of_a_riemann_integrable_funnction.png)

在[0, 1]上含不连续的稠密点的可积函数的更精巧的例子描述在问题1。一般地，当可积函数有无穷多个不连续点，这些函数事实上被事实特征，更精确地，它们的不连续点不是太多，即可忽略不计，即一个可积函数不连续点的集合有度量0

从现在开始，我们将总是假设我们的函数是可积的，即使我们不直接陈述这个需求

**圆上的函数**

在$ \\mathbb{R} $ 上 $ 2 \\pi $周期函数之间像指数函数 $ e^{in \\theta} $有一个自然连接，函数在 $ 2 \\pi $周期长度间隔和在单位圆上的函数

在单位圆上的一个点有形式 $ e^{i \\theta} $，$ \\theta $是一个实数唯一加入 $ 2 \\pi $的整数倍。如果F是一个圆上的函数，则我们对每一个实数 $ \\theta $可定义

$ f(\\theta) = F(e^{i \\theta}) $

且观察这个定义，函数f是在 $ \\mathbb{R} $上周期为 $ 2 \\pi $的函数，即对所有 $ \\theta, f(\\theta + 2 \\pi) = f(\\theta) $。F的积分、连续和其他圆滑属性取决于f。例如，我们说F在圆上是可积的如果f在每个 $ 2 \\pi $间隔是可积的。F在圆上是连续的如果f在 $ \\mathbb{R} $上是连续的，也即是f在任意 $ 2 \\pi $的间隔上是连续的。更进一步，F是连续可微的如果f是连续可导的

因为f有 $ 2 \\pi $的周期，我们可限制它到任意 $ 2 \\pi $间隔，比如 $ [0, 2 \\pi] $ 或 $ [- \\pi, \\pi] $，且在圆上捕获初始化函数F。我们注意到f必须在间隔的末点有相同的值因为它们对应圆上相同的点。相反地，$ [0, 2 \\pi] $上的任意函数，$ f(0) = f(2 \\pi) $可被扩展为 $ \\mathbb{R} $上的一个周期函数，然后确定为圆上的一个函数。特别地，一个连续函数f在间隔 $ [0, 2 \\pi] $上对应于一个圆上的连续函数当且仅当 $ f(0) = f(2 \\pi) $

总之，$ \\mathbb{R} $上 $ 2 \\pi $周期的函数，且间隔长度为 $ 2 \\pi $的函数在它们的末点都有相同的值，为两个相同数学对象的相等描述，称为圆上的函数

在这个连接中，我们提及一个项目的记号使用。当我们的函数被定义为在线段上，我们通常使用x作为独立变量；然而，当我们考虑这些圆上的函数时，我们通常替代变量x为 $ \\theta $。如读者所注意到的，我们不严格执行这个规则的边界因为这个只是为了方便


<a id="org4a21d8f"></a>

# 主要定义和一些例子

我们现在开始精确定义傅立叶级数函数。重要的是找到函数原始定义的细节。如果f是一个积分函数在长度为L的间隔[a, b]上，则f的第n个傅立叶系数被定义为

$ \\hat{f}(n) = \\frac{1}{L} \\int^{b}_ {a} f(x)e^{-2 \\pi inx / L} dx, \\qquad n \\in \\mathbb{Z} $

f的傅立叶级数被形式化地给定为

$ \\sum^{\\infty}_ {n= - \\infty} \\hat{f}(n) e^{2 \\pi inx / L} $

我们将有时用 $ a_ {n} $表示f的傅立叶系数，且使用记号

$ f(x) \\sim \\sum^{\\infty}_ {n=- \\infty} a_ {n}e^{2 \\pi inx / L} $

来表示f的傅立叶级数

例如，如果f是在区间 $ [- \\pi, \\pi] $上的可积函数，则f的第n个傅立叶系数为

$ \\hat{f}(n) = a_ {n} = \\frac{1}{2 \\pi} \\int^{\\pi}_ {- \\pi} f( \\theta ) e^{- in \\theta} d \\theta, \\qquad n \\in \\mathbb{Z} $

f的傅立叶级数为

$ f(\\theta) \\sim \\sum^{\\infty}_ {n=- \\infty} a_ {n}e^{in \\theta} $

这里我们使用 $ \\theta $作为一个变量因为我们认为它范围从 $ - \\pi $到 $ \\pi $之间的一个角度

我们也考虑定义在一个圆上的函数的傅立叶系数和傅立叶级数。通过我们之前的讨论，我们可认为圆上的函数作为 $ \\mathbb{R} $上周期为 $ 2 \\pi $的函数。我们可限制函数f到任意长度为 $ 2 \\pi $的间隔，例如 $ [0, 2 \\pi], [- \\pi, \\pi] $，且计算它的傅立叶系数

最后，我们将有时考虑一个在给定[0, 1]上的函数g，则

$ \\hat{g}(n) = a_ {n} = \\int^{1}_ {0}g(x)e^{-2 \\pi inx}dx \\qquad and \\qquad g(x) \\sim \\sum^{\\infty}_ {n=- \\infty} a_ {n}e^{2 \\pi inx} $

这里我们使用x作为一个在0到1之间的一个变量

当然，如果f初始给定在 $ [0, 2 \\pi] $，则 $ g(x) = f(2 \\pi x) $定义在[0, 1]上且变量的改变显示f的第n个傅立叶系数等于g的第n个傅立叶系数

傅立叶级数是一个更大家族的一部分称为三角级数，通过定义，表达为形式 $ \\sum^{\\infty}_ {n=- \\infty} c_ {n}e^{2 \\pi inx/ L}, c_ {n} \\in \\mathbb{C} $。如果一个三角级数只包含有限多个非零项，即 $ c_ {n} = 0 $对所有大的 $ \| n \| $，它称为一个三角多项式；它的度是 $ \| n \| $的最大值，其 $ c_ {n} \\ne 0 $

f的傅立叶级数的第N个部分和，N为一个正整数，是一个三角多项式的特殊例子。它给定为

$ S_ {N}(f)(x) = \\sum^{N}_ {n=-N} \\hat{f}(n) e^{2 \\pi inx / L} $

注意通过定义，以上和是对称的因为n从-N到N，选择是自然的因为傅立叶级数的结果分解是sine和cosine的级数。结果，傅立叶级数的收敛将被理解为N趋于无穷时的这些对称和

事实上，使用傅立叶级数的部分和，我们可重形成第一章基本问题

问题：什么情况下当 $ N \\to \\infty, S_ {N}(f) $收敛？

在继续这个问题之前，我们回到一些简单的傅立叶级数的例子

例1 设 $ f(\\theta) = \\theta, -\\pi \\le \\theta \\le \\pi $。计算傅立叶系数需要部分简单的积分。首先，如果 $ n \\ne 0 $，则

$ \\begin{aligned} \\hat{f}(n) &= \\frac{1}{2 \\pi} \\int^{\\pi}_ {- \\pi} \\theta e^{-in \\theta} d \\theta \\\\ &= \\frac{1}{2 \\pi} [- \\frac{\\theta}{in} e^{- in \\theta}]^{\\pi}_ {-\\pi} + \\frac{1}{2 \\pi in} \\int^{\\pi}_ {-\\pi} e^{-in \\theta} d \\theta \\\\ \\frac{(-1)^{n+1}}{in}, \\end{aligned} $

且如果n = 0我们有

$ \\hat{f}(0) = \\frac{1}{2 \\pi} \\int^{\\pi}_ {- \\pi} \\theta d \\theta = 0 $

因此，f的傅立叶级数为

$ f(\\theta) \\sim \\sum_ {n \\ne 0} \\frac{(-1)^{n+1}}{in} e^{in\\theta} = 2 \\sum^{\\infty}_ {n=1} (-1)^{n+1} \\frac{\\sin{n \\theta}}{n} $

第一个和在所有非零整数上，且第二个和通过欧拉identities获得。可能通过对每个 $ \\theta $以上级数收敛的基本意义来证明，但它收敛到 $ f( \\theta ) $不明显

例2 定义 $ f( \\theta ) = (\\pi - \\theta)^{2} / 4, 0 \\le \\theta \\le 2 \\pi $。则和分部积分相似

$ f( \\theta ) \\sim \\frac{\\pi^{2}}{12} + \\sum^{\\infty}_ {n=1} \\frac{\\cos{n \\theta}}{n^{2}} $

例3 函数的傅立叶级数

$ f(\\theta) = \\frac{\\pi}{\\sin{\\pi \\alpha}} e^{i(\\pi - \\theta) \\alpha} $

在 $ [0, 2 \\pi] $上是

$ f(\\theta) \\sim \\sum^{\\infty}_ {n = - \\infty} \\frac{e^{in \\theta}}{n + \\alpha} $

$ \\alpha $不是一个整数

例4 三角多项式定义 $ x \\in [- \\pi, \\pi] $

$ D_ {N}(x) = \\sum^{N}_ {n=-N} e^{inx} $

称为第N个Dirichlet kernel且在理论中基本重要的。注意它的傅立叶系数 $ a_ {n} $有属性 $ a_ {n} = 1 $如果 $ \| n \| \\le N $，否则 $ a_ {n} = 0 $。一个Dirichlet kernel的闭合形式公式为

$ D_ {N}(x) = \\frac{\\sin{((N + \\frac{1}{2})x)}}{\\sin{(x/2)}} $

其和为

$ \\sum^{N}_ {n=0} \\omega^{n} \\qquad \\text{and} \\qquad \\sum^{-1}_ {n=-N} \\omega^{n} $

$ \\omega = e^{ix} $。这些和，对应的等于

$ \\frac{1 - \\omega^{N+1}}{1 - \\omega} \\qquad \\text{and} \\qquad \\frac{\\omega^{-N} - 1}{1 - \\omega} $

总和为

$ \\frac{\\omega^{-N} - \\omega^{N+1}}{1 - \\omega} = \\frac{\\omega^{-N - 1/2} - \\omega^{N+ 1/2}}{\\omega^{-1/2} - \\omega^{1/2}} = \\frac{\\sin{((N+ \\frac{1}{2})x)}}{\\sin{(x / 2)}} $

**例5** 函数 $ P_ {r}(\\theta) $称为Poisson kernel，定义为对 $ \\theta \\in [- \\pi, \\pi] $且$ 0 \\le r < 1 $通过绝对统一收敛系列

$ P_ {r}(\\theta) = \\sum^{\\infty}_ {n = - \\infty} r^{\| n \|} e^{in \\theta} $

这个函数为在第一章中讨论的单位盘稳定状态热力等式的解决方案。注意在计算 $ P_ {r}(\\theta) $的傅立叶系数中我们可交换积分的顺序和和因为对每个固定的r，和在 $ \\theta $上统一收敛，且获得第n项傅立叶系数等于 $ r^{\| n \|} $。我们也可统计 $ P_ {r}(\\theta) $系列且看到

$ P_ {r}(\\theta) = \\frac{1 - r^{2}}{1 - 2r \\cos{\\theta} + r^{2}} $

事实上，

$ P_ {r}(\\theta) = \\sum^{\\infty}_ {n=0} \\omega^{n} + \\sum^{\\infty}_ {n=1} \\bar{\\omega}^{n}, \\qquad \\omega = re^{i \\theta} $

两个系列绝对收敛。第一个和等于 $ 1 / (1 - \\omega) $，第二个为 $ \\bar{\\omega} / (1 - \\bar{\\omega}) $

一起，它们组合给出

$ \\frac{1 - \\bar{\\omega} + (1 - \\omega) \\bar{\\omega}}{(1 - \\omega)(1 - \\bar{\\omega})} = \\frac{1 - \| \\omega \|^{2}}{\| 1 - \\omega \|^{2}} = \\frac{1 - r^{2}}{1 - 2r \\cos{\\theta} + r^{2}} $

Poisson核将之后在傅立叶系列函数的Abel和重新出现

让我们回到之前公式化的问题。f的傅立叶系列的定义是纯形式的，是否收敛到f不明显。事实上，这个问题的解决方案非常困难，或相对容易，依赖于我们期望收敛或我们在f上的额外限制

让我们更精确一些。假设，对这个讨论的目的，函数f（总数假设黎曼可积）定义在 $ [-\\pi, \\pi] $上。第一个会问的问题是是否f的傅立叶系数的部分和收敛到f pointwise。我们有

$ \\lim_ {N \\to \\infty}S_ {N}(f)(\\theta) = f(\\theta), \\qquad \\forall \\theta? $

我们容易看到一般情况下我们不能期望这个结果对每个 $ \\theta $为真，因为我们可总是改变一个可积函数在一个点而不改变它的傅立叶系数。结果，我们可问相同的问题假设f是连续且周期的。对一个长时间它相信在那些额外的假设下答案会是是的。它是惊奇的当Du Bois-Reymonnd显示存在一个连续函数其傅立叶系列在一个点上发散。我们将给出这样的一个例子在下一章。尽管这个负面的结果，我们可问会发生什么如果我们添加f上更多的光滑条件：例如，我们可假设f是连续可微的，或两次连续可微。我们将看到f的傅立叶系列统一收敛到f

我们将解释限制（1）通过显示傅立叶系列的和

最后，我们也可定义限制（1），在下一章，我们将显示如果f只是可积，则

$ \\frac{1}{2 \\pi} \\int^{\\pi}_ {- \\pi} \| S_ {N}(f)(\\theta) - f(\\theta) \|^{2} d\\theta \\to 0 \\qquad N \\to \\infty $

有趣地知道傅立叶系列的pointwise收敛在1966年L. Carleson，其显示，如果f是可积的，则f的傅立叶系列收敛到f除了可能在测度为0的集合上。这个定理的证明很困难并超过了本书的范围
