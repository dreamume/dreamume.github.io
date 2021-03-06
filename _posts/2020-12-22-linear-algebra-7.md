---
layout:     post
title:      "Linear Algebra(Chapter 7) by Hoffman"
subtitle:   "The Rational and Jordan Forms"
thumbnail-img: ""
date:       2020-12-22 19:00
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

1.  [Cyclic Suubspaces and Annihilators](#orgcee1036)
2.  [Cyclic Decompositions and the Rational Form](#orgdd97137)
3.  [The Jordan Form](#org7efeaec)
4.  [Computation of Invariant Factors](#org05d4a06)
5.  [Summary; Semi-Simple Operators](#orgc97c1aa)


<a id="orgcee1036"></a>

# Cyclic Suubspaces and Annihilators

**定义** 如果 $ \\alpha $是V中任意向量，则$ \\alpha $产生的T-cyclic子空间是形如 $ g\\left(T\\right) \\alpha $的所有向量的子空间$ Z\\left(\\alpha; T\\right), g \\in F[x] $。如果 $ Z\\left(\\alpha; T\\right) = V $，则 $ \\alpha $被称为T的一个cyclic向量

**定义** 如果 $ \\alpha $是V中任意向量，则$ \\alpha $的T-annihilator是ideal 在F[x]中的$ M\\left(\\alpha; T\\right) $包含域F上所有polynomials g使得 $ g\\left(T\\right) \\alpha = 0 $。产生这个ideal的唯一monic polynomial也被称为 $ \\alpha $的 T-annihilator

**定理 1** 设 $ \\alpha $为V上任意非零向量且设 $ p_ {\\alpha} $为 $ \\alpha $的T-annihilator

(i) $ p_ {\\alpha} $的degree与cyclic子空间 $ Z\\left(\\alpha; T\\right) $ 的维数相同

(ii)如果 $ p_ {\\alpha} $的degree为k，则向量 $ \\alpha, T\\alpha, T^{2}\\alpha, \\ldots, T^{k-1}\\alpha $形成 $ Z\\left(\\alpha; T\\right) $的一个基

(iii)如果U是由T引导的 $ Z\\left(\\alpha; T\\right) $上的线性算子，则U的minimal polynomial为 $ p_ {\\alpha} $

让我们看一下线性算子U在k维空间W上有一个cyclic向量 $ \\alpha $。通过定理1，向量 $ \\alpha, \\ldots, U^{k-1}\\alpha $形成空间W的一个基，且 $ \\alpha $ 的annihilator $ p_ {\\alpha} $是U的minimal polynomial（因此也是U的特征polynomial）。如果我们设 $ \\alpha_ {i} = U^{i-1} \\alpha, i = 1, \\ldots, k $，则U在有序基 $ \\mathcal{B} = \\{ \\alpha_ {1}, \\ldots, \\alpha_ {k} \\} $上的行为是

$ \\begin{equation} U_ {\\alpha_ {i}} = \\alpha_ {i+1}, \\qquad i = 1, \\ldots, k - 1 \\end{equation} $

$ \\begin{equation} U_ {\\alpha_ {k}} = -c_ {0}\\alpha_ {1} - c_ {1} \\alpha_{2} - \\cdots = c_ {k-1}\\alpha_ {k} \\end{equation} $

其中 $ p_ {\\alpha} = c_ {0} + c_ {1}x + \\cdots + c_ {k-1}x^{k-1} + x^{k} $。$ U_ {\\alpha_ {k}} $表达式根据 $ p_ {\\alpha}\\left(U\\right) \\alpha = 0 $有

$ \\begin{equation} U^{k} \\alpha + c_ {k-1}U^{k-1}\\alpha + \\cdots + c_ {1}U\\alpha + c_ {0} \\alpha = 0 \\end{equation} $

即U在有序基 $ \\mathcal{B} $下的矩阵为

$ \\begin{equation} \\left[ \\begin{array}{ccc} 0 & 0 & 0 & \\cdots & 0 & -c_ {0} \\\\ 1 & 0 & 0 & \\cdots & 0 & -c_ {1} \\\\ 0 & 1 & 0 & \\cdots & 0 & -c_ {2} \\\\ \\vdots & \\vdots & \\vdots & & \\vdots & \\vdots \\\\ 0 & 0 & 0 & \\cdots & 1 & -c_ {k - 1} \\end{array} \\right] \\end{equation} $

该矩阵被称为monic polynomial $ p_ {\\alpha} $的伴随矩阵

**定理 2** 如果U是有限维空间W上的线性算子，则U有一个cyclic向量当且仅当有一个W的有序基，则U以U的minimal polynomial的伴随矩阵的形式呈现

**推论** 如果A是一个monic polynomial p的伴随矩阵，则p是A的minimal和特征polynomial


<a id="orgdd97137"></a>

# Cyclic Decompositions and the Rational Form

**定义** 设T为向量空间V上的一个线性算子且设W为V的一个子空间，我们说W是T-admissible如果

(1) W在T下是invariant的

(2) 如果 $ f\\left(T\\right) \\beta $在W中，存在一个W中的向量 $ \\gamma $使得 $ f\\left(T\\right) \\beta = f\\left(T\\right) \\gamma $

**定理 3(Cyclic Decomposition Theorem)** 设T为有限维向量空间V上的一个线性算子且设 $ W_ {0} $为V的一个T-admissible子空间，则V中存在非零向量 $ \\alpha_ {1}, \\ldots, \\alpha_ {r} $，对应T-annihilators $ p_ {1}, \\ldots, p_ {r} $使得

(i) $ V = W_ {0} \\oplus Z\\left(\\alpha_ {1}; T\\right) \\oplus \\cdots \\oplus Z\\left(\\alpha_ {r}; T\\right) $

(ii) $ p_ {k-1} 整除 p_ {k}, k = 2, \\ldots, r $

更进一步，整数r和annihilators $ p_ {1}, \\ldots, p_ {r} $被(i)和(ii)唯一决定且没有 $ \\alpha_ {k} $为0

证明：证明非常长，因此我们将把它分为4个步骤。第一次看的时候容易设 $ W_ {0} = \\{ 0 \\} $，虽然它不产生任意重要的简化。在证明过程中，我们将缩写 $ f\\left(T\\right) \\beta 为 f\\beta $

步骤1: V中存在非零向量 $ \\beta_ {1}, \\ldots, \\beta_ {r} $使得

(a) $ V = W_ {0} + Z\\left(\\beta_ {1}; T\\right) + \\cdots + Z\\left(\\beta_ {r}; T\\right) $

(b) 如果 $ 1 \\le k \\le r $且

$ \\begin{equation} W_ {k} = W_ {0} + Z\\left(\\beta_ {1};T\\right) + \\cdots + Z\\left(\\beta_ {k}; T\\right) \\end{equation} $

则conductor $ p_ {k} = s\\left(\\beta_ {k}; W_ {k-1}\\right) $在所有T-conductors到子空间 $ W_ {k-1} $中有最大的degree，例如，对每个k

$ \\begin{equation} \\operatorname{deg} p_ {k} = max_ {\\alpha \\in V} \\operatorname{deg} s\\left(\\alpha; W_ {k-1}\\right) \\end{equation} $

这一步只依赖 $ W_ {0} $是一个invariant子空间

如果W是一个适当的T-invariant子空间，则

$ \\begin{equation} 0 < max_ {\\alpha} \\operatorname{deg} s\\left(\\alpha; W\\right) \\le \\operatorname{dim} V \\end{equation} $

我们可以选择一个向量 $ \\beta $使得 $ \\operatorname{deg} s\\left(\\beta; W\\right) $为最大。子空间 $ W + Z\\left(\\beta; T\\right) $是T-invariant且维数比 $ \\operatorname{dim} W $大。应用这个处理到 $ W = W_ {0} $来获得 $ \\beta_ {1} $。如果 $ W_ {1} = W_ {0} + Z\\left(\\beta_ {1}; T\\right) $依然是适当的，则应用该处理到 $ W_ {1} $来获得 $ \\beta_ {2} $。继续该过程。因为 $ \\operatorname{dim} W_ {k} > \\operatorname{dim} W_ {k-1} $我们必须达到 $ W_ {r} = V $在不超过 $ \\operatorname{dim} V $个步骤。

步骤2: 设 $ \\beta_ {1}, \\ldots, \\beta_ {r} $为非零向量满足步骤1中的条件(a)和(b)。固定k，$ 1 \\le k \\le r $。设 $ \\beta $为V中任意向量且设 $ f = s\\left(\\beta; W_ {k-1}\\right) $。如果

$ \\begin{equation} f \\beta = \\beta_ {0} + \\sum_ {1 \\le i < k} g_ {i}\\beta_ {i}, \\qquad \\beta_ {i} \\in W_ {i} \\end{equation} $

则每个polynomial $ g_ {i} $整除f且 $ \\beta_ {0} = f_ {\\tau_ {0}}, \\tau_ {0} \\in W_ {0} $

如果k = 1，这即是说 $ W_ {0} $是T-admissible的。为了证明k > 1的情形，应用如下除数算法；

$ \\begin{equation} g_ {i} = fh_ {i} + r_ {i}, \\qquad r_ {i} = 0 \\quad 或 \\quad \\operatorname{deg} r_ {i} < \\operatorname{deg} f \\end{equation} $

我们希望显示对每个i有 $ r_ {i} = 0 $，设

$ \\begin{equation} \\tau = \\beta - \\sum_ {1}^{k-1}h_ {i}\\beta_ {i} \\end{equation} $

因为 $ \\tau - \\beta $在 $ W_ {k-1} $中，

$ \\begin{equation} s\\left(\\tau; W_ {k-1}\\right) = s\\left(\\beta; W_ {k-1}\\right) = f \\end{equation} $

更进一步

$ \\begin{equation} f \\tau = \\beta_ {0} + \\sum_ {1}^{k-1}r_ {i}\\beta_ {i} \\end{equation} $

假设一些 $ r_ {i} $不为0，我们将导出一个矛盾

设j为最大的下标i，$ r_ {i} \\ne 0 $，则

$ \\begin{equation} f \\tau = \\beta_ {0} + \\sum_ {1}^{j} r_ {i} \\beta_ {i}, \\qquad r_ {j} \\ne 0 且 \\operatorname{deg} r_ {j} < \\operatorname{deg} f \\end{equation} $

设 $ p = s\\left(\\tau; W_ {j-1}\\right) $。因为 $ W_ {k-1} $包含 $ W_ {j-1} $，conductor $ f = s\\left(\\tau; W_ {k-1}\\right) $必须整除p:

$ \\begin{equation} p = fg \\end{equation} $

对两边应用g(T)，得到

$ \\begin{equation} p \\tau = gf \\tau = g r_ {j} \\beta_ {j} + g \\beta_ {0} + \\sum_ {1 \\le i < j} gr_ {i} \\beta_ {i} \\end{equation} $

使用定义，$ p \\tau $在 $ W_ {j-1} $中，且右边最后两项也在 $ W_ {j-1} $中，因此，$ gr_ {j} \\beta_ {j} $在 $ W_ {j-1} $中，现在我们使用步骤1的条件(b)：

$ \\begin{equation} \\begin{aligned} \\operatorname{deg}\\left(gr_ {j}\\right) & \\ge \\operatorname{deg} s\\left(\\beta_ {j}; W_ {j-1}\\right) \\\\ &= \\operatorname{deg} p_ {j} \\\\ &\\ge \\operatorname{deg} s\\left(\\tau; W_ {j-1}\\right) \\\\ &= \\operatorname{deg} p \\\\ &= \\operatorname{deg}\\left(fg\\right) \\end{aligned} \\end{equation} $

这样 $ \\operatorname{deg}r_ {j} \\ge \\operatorname{deg}f $，这跟j的选择矛盾。我们现在知道f整除每个 $ g_ {i} $且因此 $ \\beta_ {0} = f \\tau $。因为 $ W_ {0} $是T-admissible的，当 $ \\tau_ {0} $在 $ W_ {0} $中时 $ \\beta_ {0} = f \\tau_ {0} $。我们通过步骤2重新标识一个直接形式的断言即每个子空间 $ W_ {1}, W_ {2}, \\ldots, W_ {r} $是T-admissible的

步骤3：在V中存在非零向量 $ \\alpha_ {1}, \\ldots, \\alpha_ {r} $满足定理3的条件(i)和(ii)

像步骤1一样设置向量 $ \\beta_ {1}, \\ldots, \\beta_ {r} $，固定k，$ 1 \\le k \\le r $。我们应用步骤2到向量 $ \\beta = \\beta_ {k} $且T-conductor $ f = p_ {k} $。我们获得

$ \\begin{equation} p_ {k}\\beta_ {k} = p_ {k}\\tau_ {0} + \\sum_ {1 \\le i < k}p_ {k}h_ {i}\\beta_ {i} \\end{equation} $

$ \\tau_ {0} 在W_ {0} $中且 $ h_ {1}, \\ldots, h_ {k-1} $是polynomials。设

$ \\begin{equation} a_ {k} = \\beta_ {k} - \\tau_ {0} - \\sum_ {1 \\le i < k} h_ {i} \\beta_ {i} \\end{equation} $

因为 $ \\beta_ {k} - \\alpha_ {k} $在 $ W_ {k-1} $中，

$ \\begin{equation} s\\left(\\alpha_ {k}; W_ {k-1}\\right) = s\\left(\\beta_ {k}; W_ {k-1}\\right) = p_ {k} \\end{equation} $

且因为 $ p_ {k} \\alpha_ {k} = 0 $，我们有

$ \\begin{equation} W_ {k-1} \\cap Z\\left(\\alpha_ {k}; T\\right) = \\{ 0 \\} \\end{equation} $

因为每个 $ \\alpha_ {k} $满足上面两个公式，有

$ \\begin{equation} W_ {k} = W_ {0} \\oplus Z\\left(\\alpha_ {1}; T\\right) \\oplus \\cdots \\oplus Z\\left(\\alpha_ {k}; T\\right) \\end{equation} $

且 $ p_ {k} $是 $ \\alpha_ {k} $的T-annihilator。即向量 $ \\alpha_ {1}, \\ldots, \\alpha_ {r} $定义了如向量 $ \\beta_ {1}, \\ldots, \\beta_ {r} $一样顺序的子空间 $ W_ {1}, W_ {2}, \\ldots $且T-conductors $ p_ {k} = s\\left(\\alpha_ {k}, W_ {k-1}\\right) $有相同的最大化属性（步骤1的条件(b)）。向量 $ \\alpha_ {1}, \\ldots, \\alpha_ {r} $有额外属性即子空间 $ W_ {0}, Z\\left(\\alpha_ {1}; T\\right), Z\\left(\\alpha_ {2}; T\\right), \\ldots $是独立的。因此容易验证定理3的条件(ii)。因为对每个i， $ p_ {i} \\alpha_ {i} = 0 $，我们有如下关系：

$ \\begin{equation} p_ {k} \\alpha_ {k} = 0 + p_ {1} \\alpha_ {1} + \\cdots + p_ {k-1}\\alpha_ {k-1} \\end{equation} $

应用步骤2的 $ \\beta_ {1}, \\ldots, \\beta_ {k} $替代 $ \\alpha_ {1}, \\ldots, \\alpha_ {k} $及 $ \\beta = \\alpha_ {k} $。结论：$ p_ {k} $整除每个 $ p_ {i}, i < k $

步骤4：数字r和polynomials $ p_ {1}, \\ldots, p_ {r} $被定理3的条件唯一决定

假设对定理3的向量 $ \\alpha_ {1}, \\ldots, \\alpha_ {r} $我们有非零向量 $ \\tau_ {1}, \\ldots, \\tau_ {s} $对应T-annihilators $ g_ {1}, \\ldots, g_ {s} $使得

$ \\begin{equation} V = W_ {0} \\oplus Z\\left(\\tau_ {1}; T\\right) \\oplus \\cdots \\oplus Z\\left(\\tau_ {s}; T\\right) \\end{equation} $

$ \\begin{equation} g_ {k} 整除 g_ {k-1}, \\qquad k = 2, \\ldots, s \\end{equation} $

我们将显示对每个i，有r = s且 $ p_ {i} = g_ {i} $

容易看到 $ p_ {1} = g_ {1} $，polynomial $ g_ {1} $作为V到 $ W_ {0} $的T-conductor而确定的。设 $ S\\left(V; W_ {0} \\right) $为polynomial f的集合使得对V中每个 $ \\beta $，$ f \\beta $ 在 $ W_ {0} $中，例如polynomials f使得 $ f\\left(T\\right) $的range 包含在 $ W_ {0} $中。则 $ S\\left(V; W_ {0}\\right) $ 在polynomial代数中是非零ideal。polynomial $ g_ {1} $是该ideal的nomic生成器。对V中每个 $ \\beta $有形式

$ \\begin{equation} \\beta = \\beta_ {0} + f_ {1}\\tau_ {1} + \\cdots + f_ {s}\\tau_ {s} \\end{equation} $

且 $ \\begin{equation} g_ {1} \\beta = g_ {1}\\beta_ {0} + \\sum_ {1}^{s}g_ {1}f_ {i} \\tau_ {i} \\end{equation} $

因为每个 $ g_ {i} $整除 $ g_ {1} $，我们有对所有i, $ g_ {1}\\tau_ {i} = 0且 g_ {1} \\beta = g_ {1} \\beta_ {0} \\in W_ {0} $。这样 $ g_ {1} $在 $ S\\left(V; W_ {0}\\right) $中。因为 $ g_ {1} $是最小degree的monic polynomial把 $ \\tau_ {1} $送到 $ W_ {0} $，我们看到 $ g_ {1} $是在ideal $ S\\left(V; W_ {0}\\right) $中最小degree的monic polynomial。通过相同的讨论，$ p_ {1} $是该ideal的生成器，所以 $ p_ {1} = g_ {1} $

如果f是一个polynomial且W是V的子空间，我们将使用 fW为W中对 $ \\alpha $的所有向量 $ f \\alpha $的集合。

现在我们继续推导使得 $ r = s 且 p_ {i} = g_ {i}, i = 2, \\ldots, r $。我们将给出证明如果 $ r \\ge 2 $则 $ p_ {2} = g_ {2} $。假设 $ r \\ge 2 $，则

$ \\begin{equation} \\operatorname{dim} W_ {0} + \\operatorname{dim} Z\\left(\\alpha_ {1}; T\\right) < \\operatorname{dim} V \\end{equation} $

因为我们知道 $ p_ {1} = g_ {1} $，我们知道 $ Z\\left(\\alpha_ {1}; T\\right) 和 Z\\left(\\tau_ {1}; T\\right) $有相同的维数。因此

$ \\begin{equation} \\operatorname{dim} W_ {0} + \\operatorname{dim} Z\\left(\\tau_ {1}; T\\right) < \\operatorname{dim} V \\end{equation} $

其显示 $ s \\ge 2 $。从这两个V的分解，我们获得子空间 $ p_ {2}V $的两个分解：

$ \\begin{equation} p_ {2} V = p_ {2} W_ {0} \\oplus Z\\left(p_ {2}\\alpha_ {1}; T\\right) \\end{equation} $

$ \\begin{equation} p_ {2} V = p_ {2} W_ {0} \\oplus Z\\left(p_ {2}\\tau_ {1}; T\\right) \\oplus \\cdots \\oplus Z\\left(p_ {2}\\tau_ {s}; T\\right) \\end{equation} $

由之前的事实我们知道 $ Z\\left(p_ {2}\\alpha_ {1}; T\\right)和 Z\\left(p_ {2}\\tau_ {1}; T\\right) $有相同的维数。因此，有

$ \\begin{equation} \\operatorname{dim} Z\\left(p_ {2}\\tau_ {i}; T\\right) = 0, \\qquad i \\ge 2 \\end{equation} $

我们得到 $ p_ {2} \\tau_ {2} = 0 且 g_ {2} 整除 p_ {2} $。同样也可以推得 $ p_ {2} 整除 g_ {2} $，因此有 $ p_ {2} = g_ {2} $

**推论** 如果T是有限维向量空间中的一个线性算子，则每个T-admissible子空间有一个补集子空间，其在T下也是invariant的

**推论** 设T为有限维向量空间V上的一个线性算子

(a) 在V中存在一个向量 $ \\alpha $使得 $ \\alpha $的T-annihilator是T的minimal polynomial

(b) T有一个cyclic向量当且仅当T的特征和minimal polynomial是相同的

**定理 4(Generalized Cayley-Hamilton Theorem)** 设T为有限维向量空间V上的一个线性算子，设p和f为T的minimal和特征polynomials

(i) p整除f

(ii) p和f有相同的质因素，除了因素次数

(iii) 如果

$ \\begin{equation} p = f_ {1}^{T_ {1}} \\cdots f_ {k}^{T_ {k}} \\end{equation} $

是p的质因素，则

$ \\begin{equation} f = f_ {1}^{d_ {1}} \\cdots f_ {k}^{d_ {k}} \\end{equation} $

$ d_ {i} $是$ f_ {i}\\left(T\\right)^{r_ {i}} $的nullity被 $ f_ {i} $的degree整除

现在让我们看一下cyclic分解定理的矩阵形式。如果我们有算子T和定理3的直和分解，设 $ \\mathcal{B}_ {i} 为 Z\\left(\\alpha_ {i}; T\\right) $的cyclic有序基

$ \\begin{equation} \\{ \\alpha_ {i}, T \\alpha_ {i}, \\ldots, T^{k_ {i} - 1} \\alpha_ {i} \\} \\end{equation} $

$ k_ {i} 记为 Z\\left(\\alpha_ {i}; T\\right) $的维数，即annihilator $ p_ {i} $的degree。在有序基 $ \\mathcal{B}_ {i} $上的算子 $ T_ {i} $对应的矩阵是 $ p_ {i} $的伴随矩阵。设 $ \\mathcal{B} $为V的有序基为 $ \\mathcal{B}_ {i} $的联合以这样的顺序排列 $ \\mathcal{B}_ {1}, \\ldots, \\mathcal{B}_ {r} $，则T在有序基 $ \\mathcal{B} $下的矩阵为

$ \\begin{equation} A = \\left[ \\begin{array}{ccc} A_ {1} & 0 & \\cdots & 0 \\\\ 0 & A_ {2} & \\cdots & 0 \\\\ \\vdots & \\vdots & & \\vdots \\\\ 0 & 0 & \\cdots & A_ {r} \\end{array} \\right] \\end{equation} $

$ A_ {i} 是 k_ {i} \\times k_ {i} 的p_ {i} $ 的伴随矩阵，这样的 $ n \\times n $矩阵A是非常量monic polynomials $ p_ {1}, \\ldots, p_ {r} $的伴随矩阵的直和使得 $ p_ {i} 整除 p_ {i+1}, i = 1, \\ldots, r - 1 $，我们说A为rational form。

**定理 5** 设F为一个域且设B为F上一个 $ n \\times n $的矩阵。则B在域F上跟唯一一个rational form的矩阵相似


<a id="org7efeaec"></a>

# The Jordan Form

假设T是V上的一个线性算子且F上的T的特征polynomial因子如下：

$ \\begin{equation} f = \\left(x - c_ {1}\\right)^{d_ {1}} \\cdots \\left(x - c_ {k}\\right)^{d_ {k}} \\end{equation} $

$ c_ {1}, \\ldots, c_ {k} $是F上不同的元素且 $ d_ {i} \\ge 1 $。则T的minimal polynomial为

$ \\begin{equation} f = \\left(x - c_ {1}\\right)^{r_ {1}} \\cdots \\left(x - c_ {k}\\right)^{r_ {k}} \\end{equation} $

$ 1 \\le r_ {i} \\le d_ {i} $。如果 $ W_ {i} $是 $ \\left(T - c_ {i}I\\right)^{r_ {i}} $的null space，则主分解定理告诉我们

$ \\begin{equation} V = W_ {1} \\oplus \\cdots \\oplus W_ {k} \\end{equation} $

且由T在 $ W_ {i} $导入的算子 $ T_ {i} $有minimal polynomial $ \\left(x - c_ {i}\\right)^{r_ {i}} $。设 $ N_ {i} $为 $ W_ {i} $上的线性算子 $ N_ {i} = T_ {i} - c_ {i} I $。则 $ N_ {i} $是nilpotent且有minimal polynomial $ x^{r_ {i}} $。在 $ W_ {i} $上，T跟 $ N_ {i} $加上一个常量 $ c_ {i} $乘以单位算子相当。假设我们选择子空间 $ W_ {i} $的一个基对应nilpotent算子 $ N_ {i} $的cyclic分解。则 $ T_ {i} $的矩阵在这个有序基下为矩阵的直和

$ \\begin{equation} \\left[ \\begin{array}{ccc} c & 0 & \\cdots & 0 & 0 \\\\ 1 & c & \\cdots & 0 & 0 \\\\ \\vdots & \\vdots &  & \\vdots & \\vdots \\\\ & & & c & \\\\ 0 & 0 & \\cdots & 1 & c \\end{array} \\right] \\end{equation} $

$ c = c_ {i} $。更进一步，这些矩阵的大小将从左到右减少。上图矩阵被称为带特征值c的elementary Jordan矩阵。现在如果我们把所有的 $ W_ {i} $的基放一块，我们获得V的一个有序基。让我们描述这个有序基的T的矩阵A

矩阵A为矩阵 $ A_ {1}, \\ldots, A_ {k} $的直和

$ \\begin{equation} A = \\left[ \\begin{array}{ccc} A_ {1} & 0 & \\cdots & 0 \\\\ 0 & A_ {2} & \\cdots \\ 0 \\\\ \\vdots & \\vdots & & \\vdots \\\\ 0 & 0 & \\cdots & A_ {k} \\end{array} \\right] \\end{equation} $

该form的每个 $ A_ {i} $为

$ \\begin{equation} A_ {i} = \\left[ \\begin{array}{ccc} J_ {1}^{\\left(i\\right)} & 0 & \\cdots & 0 \\\\ 0 & J_ {2}^{\\left(i\\right)} & \\cdots & 0 \\\\ \\vdots & \\vdots & & \\vdots \\\\ 0 & 0 & \\cdots & J_ {n_ {i}}^{\\left(i\\right)} \\end{array} \\right] \\end{equation} $

每个 $ J_ {j}^{\\left(i\\right)} $是一个带特征值 $ c_ {i} $的elementary Jordan矩阵，矩阵 $ J_ {j}^{\\left(i\\right)} $的大小随着j的增长而减少。一个 $ n \\times n $ 矩阵A满足本段内容（一些不同的常量 $ c_ {1}, \\ldots, c_ {k} $）提及的所有条件被称为Jordan form

我们已指出如果T是一个线性算子其特征polynomial因子完全在常量域上，则有一个V的有序基使得T的表达矩阵为Jordan form。我们将显示这个矩阵对T是唯一的，即如果两个Jordan form形式的矩阵是相似的，则它们仅是常量 $ c_ {i} $的顺序不同

假设有V的某个有序基，T表达为Jordan矩阵A，如果 $ A_ {i} $是一个 $ d_ {i} \\times d_ {i} $的矩阵，则 $ d_ {i} $是 $ c_ {i} $的次数作为A的特征polynomial的根，即T的特征polynomial是

$ \\begin{equation} f = \\left(x - c_ {1}\\right)^{d_ {1}} \\cdots \\left(x - c_ {k}\\right)^{d_ {k}} \\end{equation} $

这显示 $ c_ {1}, \\ldots, c_ {k} 和 d_ {1}, \\ldots, d_ {k} $是唯一的。A是矩阵 $ A_ {i} $的直和这个事实给我们一个在T上不变的直和分解 $ V = W_ {1} \\oplus \\cdots \\oplus W_ {k} $。现在注意 $ W_ {i} 为 \\left(T - c_ {i}I\\right)^{n} $的null space，$ n = dim V；\\quad A_ {i} - c_ {i} I $ 是nilpotent且 $ A_ {j} - c_ {i}I $是non-singular如果 $ j \\ne i $。这样我们看到子空间 $ W_ {i} $是唯一的。如果 $ T_ {i} $是T在 $ W_ {i} $上导出的算子，则矩阵 $ A_ {i} $是唯一确定的rational form $ \\left(T_ {i} - c_ {i}I\\right) $

现在我们希望做一些更进一步的观察关于算子T和T在某个有序基下的表达式Jordan矩阵A。我们列出一些观察：

(1) A的每个元素不在或主对角之下的都为0。在A的对角线上有T的k个不同的特征值 $ c_ {1}, \\ldots, c_ {k} $。$ c_ {i} $重复 $ d_ {i} $次，$ d_ {i} $是 $ c_ {i} $作为特征polynomial根的次数，例如，$ d_ {i} = \\operatorname{dim} W_ {i} $

(2) 对每个i，矩阵 $ A_ {i} $是特征值 $ c_ {i} $的 $ n_ {i} $个elementary Jordan矩阵 $ J_ {j}^{\\left(i\\right)} $的直和。$ n_ {i} $是特征值 $ c_ {i} $的特征向量空间的维数。 $ n_ {i} $是rational form $ \\left(T_ {i} - c_ {i} I \\right) $的elementary nilpotent块的个数，且跟 $ \\left(T - c_ {i}I \\right) $的null space的维数相同。特别地注意到T是可对角化的当且仅当对每个i有 $ n_ {i} = d_ {i} $

(3) 对每个i，矩阵A中第一个块 $ J_ {1}^{\\left(i\\right)} $是 $ r_ {i} \\times r_ {i} $矩阵，$ r_ {i} $是 $ c_ {i} $作为T的minimal polynomial根的次数，即nilpotent算子 $ \\left(T - c_ {i}I \\right) $的minimal polynomial为 $ x^{r_ {i}} $

如果B是域F上 $ n \\times n $的矩阵且如果B在F下有完全的特征polynomial因子，则B在F上跟一个Jordan form的 $ n \\times n $矩阵A相似，且A重排列它的特征值顺序后是唯一的。我们称A是B的Jordan form


<a id="org05d4a06"></a>

# Computation of Invariant Factors

假设A时一个 $ n \\times n $的矩阵，其元素都在域F中，我们希望找到一个方法计算A的rational form定义的不变因子 $ p_ {1}, \\ldots, p_ {r} $。让我们用最简单的例子开始，A是monic polynomial的伴随矩阵

$ \\begin{equation} p = x^{n} + c_ {n-1}x^{n-1} + \\cdots + c_ {1}x + c_ {0} \\end{equation} $

我们知道p是伴随矩阵的monimal和特征polynomial，现在，我们想要给出一个直接的计算显示p是A的特征polynomial。在这个例子中，

$ \\begin{equation} xI - A = \\left[ \\begin{array}{ccc} x & 0 & 0 & \\cdots & 0 & c_ {0} \\\\ -1 & x & 0 & \\cdots & 0 & c_ {1} \\\\ 0 & -1 & x & \\cdots & 0 & c_ {2} \\\\ \\vdots & \\vdots & \\vdots & & \\vdots & \\vdots \\\\ 0 & 0 & 0 & \\cdots & x & c_ {n-2} \\\\ 0 & 0 & 0 & \\cdots & -1 & x + c_ {n-1} \\end{array} \\right] \\end{equation} $

添加x倍的n行到(n - 1)行，这将消除(n - 1, n - 1)处的x且不改变行列式。然后，添加x倍新的(n - 1)行到(n - 2)行，一直继续直到所有主对角线上的x都被移除。结果为

$ \\begin{equation} \\left[ \\begin{array}{ccc} 0 & 0 & 0 & \\cdots & 0 & x^{n} + \\cdots + c_ {1}x + c_ {0} \\\\ -1 & 0 & 0 & \\cdots & 0 & x^{n-1} + \\cdots + c_ {2}x + c_ {1} \\\\ 0 & -1 & 0 & \\cdots & 0 & x^{n-2} + \\cdots + c_ {3} x + c_ {2} \\\\ \\vdots & \\vdots & \\vdots & & \\vdots & \\vdots \\\\ 0 & 0 & 0 & \\cdots & 0 & x^{2} + c_ {n-1} x + c_ {n-2} \\\\ 0 & 0 & 0 & \\cdots & -1 & x + c_ {n-1} \\end{array} \\right] \\end{equation} $

然后我们得到 $ p = \\operatorname{det}\\left(xI - A\\right) $

**定理 7** 设M和N为 $ m \\times n $矩阵，元素都在polynomial algebra F[x}中，则N跟M相当当且仅当

$ \\begin{equation} N = PMQ \\end{equation} $

P是一个在 $ F[x]^{m \\times m} $上的可逆矩阵，Q是一个在 $ F[x]^{n \\times n} $上的可逆矩阵

**定理 8** 设A为 $ n \\times n $矩阵，元素都在域F上，且设 $ p_ {1}, \\ldots, p_ {r} $为A的不变因子。矩阵xI - A相当于 $ n \\times n $的对角矩阵，对角元素为 $ p_ {1}, \\ldots, p_ {r}, 1, 1, \\ldots, 1 $

**定义** 设N为 $ F[x]^{m \\times n} $上的矩阵，我们说N是（Smith）normal form 如果

(a) N主对角线下的每个元素都是0

(b) N的主对角线上出现（顺序）的polynomials $ f_ {1}, \\ldots, f_ {l} 使得 f_ {k} 整除 f_ {k+1}, 1 \\le k \\le l - 1 $

**定理 9** 设M为元素在polynomial algebra F[x]上的 $ m \\times n $矩阵，则M相当于normal form 矩阵N

**定义** 设M为元素在F[x]上的一个 $ m \\times n $矩阵，如果 $ 1 \\le k \\le min\\left(m, n\\right) $，我们定义 $ \\delta_ {k}\\left(M\\right) $为M所有 $ k \\times k $子矩阵的行列式的最大公约数

**定理 10** 如果M和N是元素在F[x]上相当的 $ m \\times n $矩阵，则

$ \\begin{equation} \\delta_ {k}\\left(M\\right) = \\delta_ {k}\\left(N\\right), \\qquad \\qquad 1 \\le k \\le min\\left(m, n\\right) \\end{equation} $

**推论** $ F[x]^{m \\times n} $上的每个矩阵相当于一个normal form 矩阵N，N主对角线上的polynomials $ f_ {1}, \\ldots, f_ {l} $为

$ \\begin{equation} f_ {k} = \\frac{\\delta_ {k}\\left(M\\right)}{\\delta_ {k-1}\\left(M\\right)}, \\qquad \\qquad 1 \\le k \\le min\\left(m, n\\right) \\end{equation} $

为方便起见，我们定义 $ \\delta_ {0}\\left(M\\right) = 1 $


<a id="orgc97c1aa"></a>

# Summary; Semi-Simple Operators

**定义** 设V为域F上的有限维向量空间，设T为V上的线性算子。我们说T是semi-simple的如果每个T-invariant子空间有一个补的T-invariant子空间

我们将证明的是，在域F上的某些限制下，每个线性算子T唯一表达为形式T = S + N，S是semi-simple的，N是nilpotent的，且SN = NS。首先，我们通过它们的minimal polynomials来特征semi-simple算子，且这个特征将给我们展示，当F是代数闭合的，一个算子是semi-simple的当且仅当它是可对角化的

**引理** 设T为有限维向量空间V上的一个线性算子，设 $ V = W_ {1} \\oplus \\cdots \\oplus W_ {k} $为T的主分解。即如果p是T的minimal polynomial且 $ p =p_ {1}^{r_ {1}} \\cdots p_ {k}^{r_ {k}} $是p的主因子，则 $ W_ {j} $是 $ p_ {j}\\left(T\\right)^{r_ {j}} $的null space。设W为V的任意在T下不变的子空间，则

$ \\begin{equation} W = \\left(W \\cap W_ {1}\\right) \\oplus \\cdots \\oplus \\left(W \\cap W_ {k}\\right) \\end{equation} $

**引理** 设T为V上的线性算子，设T的minimal polynomial在常量域F上是可约的，则T是semi-simple

**定理 11** 设T为有限维向量空间V上的一个线性算子，T是semi-simple的充分必要条件是T的minimal polynomial p是 $ p = p_ {1} \\cdots p_ {k} $的形式，$ p_ {1}, \\ldots, p_ {k} $是在常量域F上不同的可约polynomials

**推论** 如果T是代数闭合域上有限维向量空间中的一个线性算子，则T是semi-simple当且仅当T是可对角化的

**引理 (Taylor's Formula)** 设F为一个特征零的域，且g和h是F上的polynomials，如果f是F上的任意polymonial，$ \\operatorname{deg} f \\le n $，则

$ \\begin{equation} f(g) = f(h) + f^{(1)}(h)(g - h) + \\frac{f^{(2)}(h)}{2 !} (g - h)^{2} + \\cdots + \\frac{f^{(n)}(h)}{n !}(g - h)^{n} \\end{equation} $

**引理** 设F为复数子域，设f为F上一个polynomial，且设f'为f的导数。如下描述等价：

(a) f是F上不同不可约polynomials的乘积

(b) f和f'是互质的

(c) 作为复系数的polynomial，f没有重复的根

**定理 12** 设F为复数子域，设V为F上的有限维向量空间，设T为V上的线性算子，设 $ \\mathcal{B} $为V的一个有序基且设A为T在 $ \\mathcal{B} $上的矩阵，则T是semi-simple当且仅当矩阵A在复数域上跟一个对角矩阵相似

**定理 13** 设F为复数子域，设V为F上的有限维向量空间，设T为V上的线性算子，有一个V上semi-simple算子和V上一个nilpotent算子使得

(i) T = S + N

(ii) SN = NS

满足(i)和(ii)的S和N是唯一的，且都是T的polynomial
