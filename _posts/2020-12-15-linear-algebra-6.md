---
layout:     post
title:      "Linear Algebra(Chapter 6) by Hoffman"
subtitle:   "Elementary Canonical Forms"
thumbnail-img: ""
date:       2020-12-15 21:00
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

1.  [Characteristic Values](#org8285248)
2.  [Annihilating Polynomials](#org1d19076)
3.  [Invariant Subspaces](#orga4421ab)
4.  [Direct-Sum Decompositions](#orgc543fdc)
5.  [Invariant Direct Sums](#org9525b87)


<a id="org8285248"></a>

# Characteristic Values

**定义** 设V是域F上的一个向量空间，设T为V上的线性算子。一个T的特征值是一个F上的常量c使得一个V上的非空向量 $ \\alpha $有 $ T\\alpha = c\\alpha $。如果c是T的一个特征值，则

(a) 任意 $ \\alpha $使得 $ T\\alpha = c \\alpha $被称为有特征值c的T的特征向量

(b) 所有使得 $ T\\alpha = c \\alpha $的 $ \\alpha $向量集合被称为c的特征空间

如果T是任意线性算子且c是任意常数，使得 $ T \\alpha = c \\alpha $的向量 $ \\alpha $的集合是V的一个子空间。它是线性转换 $ \\left(T - cI\\right) $的null空间。我们称c是T的一个特征值如果该子空间不是零空间，例如，如果 $ \\left(T - cI\\right) $不是1:1的。如果V是有限维的，$ \\left(T - cI\\right) $不是1:1的当它的行列式的值不为零。

**定理 1** 设T为有限维空间V上的一个线性算子且设c为一个常数。如下描述等效：

(i) c是T的一个特征值

(ii) 算子 $ \\left(T - cI\\right) $是singular（不可逆）

(iii) $ \\operatorname{det}\\left(T - cI\\right) = 0 $

**定义** 如果A是域F上 $ n \\times n $的矩阵，F上A的一个特征值是F上一个常数c使得矩阵(A - cI)是singular（不可逆）的

**引理** 相似矩阵有相同的特征多项式

**定义** 设T为有限维空间V上的一个线性算子，我们说T是可对角化的如果有一个V上的基，其每个向量是T的一个特征向量

**引理** 设 $ T\\alpha = c\\alpha $，如果f是任意polynomial，则 $ f\\left(T\\right) \\alpha = f\\left(c\\right) \\alpha $

**引理** 设T为有限维空间v上的一个线性算子。设 $ c_ {1}, \\ldots, c_ {k} $为T上的不同的特征值，且设 $ W_ {i} $为特征值 $ c_ {i} $对应特征向量空间，如果 $ W = W_ {1} + \\cdots + W_ {k} $，则

$ \\begin{equation} \\operatorname{dim} W = \\operatorname{dim} W_ {1} + \\cdots + \\operatorname{dim} V_ {k} \\end{equation} $

事实上，如果 $ \\mathcal{B}_ {i} $是 $ W_ {i} $的一个有序基，则 $ \\mathcal{B} = \\left(\\mathcal{B}_ {1}, \\ldots, \\mathcal{B}_ {k}\\right) $是W的一个有序基

**定理 2** 设T为有限维空间v上的一个线性算子。设 $ c_ {1}, \\ldots, c_ {k} $为T上的不同的特征值且设 $ W_ {i} $为 $ \\left(T - c_ {i}I\\right) $的null space，则如下描述等价：

(i) T是可对角化的

(ii) T的特征polynomial是

$ \\begin{equation} f = \\left( x - c_ {1}\\right)^{d_ {1}} \\cdots \\left( x - c_ {k}\\right)^{d_ {k}} \\end{equation} $

且 $ \\operatorname{dim} W_ {i} = d_ {i}, i = 1, \\ldots, k $

(iii) $ \\operatorname{dim} W_ {1} + \\cdots + \\operatorname{dim} W_ {k} = \\operatorname{dim} V $


<a id="org1d19076"></a>

# Annihilating Polynomials

**定义** 设T为域F上有限维向量空间V上的一个线性算子。T的minimal polynomial是（唯一的）域F上消除T的polynomials的ideal的monic生成器

如果A是一个域F上 $ n \\times n $的矩阵，我们以类似的方法定义A的minimal polynomial

**定理 3** 设T为n维向量空间V上的一个线性算子[或，设A为 $ n \\times n $矩阵]。T [或A]的特征和minimal polynomials有相同的根，除了重复的根

**定理 4(Cayley-Hamilton)** 设T为有限维向量空间V上的一个线性算子，如果f是T的characteristic polynomial，则f(T) = 0；即minimal polynomial能被T的characteristic polynomial整除


<a id="orga4421ab"></a>

# Invariant Subspaces

**定义** 设V是一个向量空间且T是V上的一个线性算子。如果W是V的一个子空间，我们说W在T下不变如果对W中每个向量 $ \\alpha, T \\alpha \\in W $ ，例如，如果T(W)包含在W中

**定义** 设W是T的invariant subspace且设 $ \\alpha $为V上的一个向量。T-conductor of $ \\alpha $ into W是集合 $ S_ {T}\\left( \\alpha, W\\right) $，包含所有的polynomials g使得 $ g\\left(T\\right) \\alpha $在W中

**引理** 设V是域F上的一个有限维向量空间，设T为V上的线性算子使得T的minimal polynomial是线性因子的乘积

$ \\begin{equation} p = \\left(x - c_ {1}\\right)^{r_ {1}} \\cdots \\left(x - c_ {k}\\right)^{r_ {k}}, \\qquad c_ {i} \\text{ in } F \\end{equation} $

设W是V的子空间（ $ W \\ne V $），invariant under T。存在V中一个向量 $ \\alpha $使得

(a) $ \\alpha $不在W中

(b) $ \\left(T - cI\\right) \\alpha $在W中，c为算子T的某个特质值

**定理 6** 设V为域F上的有限维向量空间，设T为V上的线性算子，则T是可对角化的当且仅当T的minimal polynomial有如下形式

$ \\begin{equation} p = \\left(x - c_ {1}\\right) \\cdots \\left(x - c_ {k}\\right) \\end{equation} $

$ c_ {1}, \\ldots, c_ {k} $是F上不同的元素


<a id="orgc543fdc"></a>

# Direct-Sum Decompositions

**定义** 如果V是一个向量空间，V的projection E是V上的一个线性算子使得 $ E^{2} = E $

假设E是一个projection，设R为E的range，设N为E的null space

1. 向量 $ \\beta $在range R中当且仅当 $ E \\beta = \\beta $。如果 $ \\beta = E \\alpha $，则 $ E \\beta = E^{2} \\alpha = E \\alpha = \\beta $。相反地，如果 $ \\beta == E \\beta $，则 $ \\beta $在E的range中
2. $ V = R \\oplus N $
3. $ \\alpha $作为R和N中向量和的唯一表达为 $ \\alpha = E \\alpha + \\left(\\alpha - E \\alpha\\right) $

任意projection E是可对角化的。如果 $ \\{\\alpha_ {1}, \\ldots, \\alpha_ {r} \\} $是R的一个基且 $ \\{ \\alpha_ {r+1}, \\ldots, \\alpha_ {n} \\} $是N的一个基，则基 $ \\mathcal{B} = \\{\\alpha_ {1}, \\ldots, \\alpha_ {n} \\} $对角化E:

$ \\begin{equation} [E]_ {\\mathcal{B}} = \\left[ \\begin{array}{ccc} I & 0 \\\\ 0 & 0 \\end{array} \\right] \\end{equation} $

I为 $ r \\times r $单位矩阵。projections可被用来描述空间V的直和分解。设 $ V = W_ {1} \\oplus \\cdots \\oplus W_ {k} $，对每个j我们定义一个V上的算子 $ E_ {j} $。设 $ \\alpha $在V中，$ \\alpha = \\alpha_ {1} + \\cdots + \\alpha_ {k}, \\alpha_ {i} \\in W_ {i} $。定义 $ E_ {j} \\alpha = \\alpha_ {j} $，则 $ E_ {j} $的range是 $ W_ {j} $且 $ E_ {j}^{2} = E_ {j} $。$ E_ {j} $的null space是子空间

$ \\begin{equation} \\left( W_ {1} + \\cdots + W_ {j-1} + W_ {j+1} + \\cdots + W_ {k} \\right) \\end{equation} $

我们有

$ \\begin{equation} \\alpha = E_ {1} \\alpha + \\cdots + E_ {k} \\alpha, \\forall \\alpha \\in V \\end{equation} $

即 $ I = E_ {1} + \\cdots + E_ {k} $


<a id="org9525b87"></a>

# Invariant Direct Sums

给定一个V的decomposition，T在每个 $ W_ {i} $的限制上引入一个线性算子 $ T_ {i} $。如果 $ \\alpha $是V中一个向量，我们有唯一的向量 $ \\alpha_ {1}, \\ldots, \\alpha_ {k}, \\alpha_ {i} \\in W_ {i} $，使得

$ \\begin{equation} \\alpha = \\alpha_ {1} + \\cdots + \\alpha_ {k} \\end{equation} $

且 $ \\begin{equation} T \\alpha = T_ {1} \\alpha_ {1} + \\cdots + T_ {k}\\alpha_ {k} \\end{equation} $

我们描述这个形势称T是算子 $ T_ {1}, \\ldots, T_ {k} $的直和。必须记住使用这个术语时 $ T_ {i} $不是V上的线性算子，而是在各自的子空间 $ W_ {i} $上的。

我们注意到矩阵也有类似的情况。假设我们对每个 $ W_ {i} $选择一个有序基 $ \\mathcal{B}_ {i} $且设 $ \\mathcal{B} $为V的有序基包含 $ \\mathcal{B}_ {i} $的联合，按 $ \\mathcal{B}_ {1}, \\ldots, \\mathcal{B}_ {k} $的顺序排列，使得 $ \\mathcal{B} $为V的一个基。容易看到如果 $ A = [T]_ {\\mathcal{B}}且 A_ {i} = [T_ {i}]_ {\\mathcal{B_ {i}}} $则A有如下形式

$ \\begin{equation} A = \\left[ \\begin{array}{ccc} A_ {1} & 0 & \\cdots & 0 \\\\ 0 & A_ {2} & \\cdots & 0 \\\\ \\vdots & \\vdots & & \\vdots \\\\ 0 & 0 & \\cdots & \\ A_ {k} \\end{array} \\right] \\end{equation} $

$ A_ {i} 是一个 d_ {i} \\times d_ {i} $的矩阵（ $ d_ {i} = \\operatorname{dim}W_ {i} $ ），这可被称为A是矩阵 $ A_ {1}, \\ldots, A_ {k} $的直和

**定理 10** 设T为V空间的线性算子，且设 $ W_ {1}, \\ldots, W_ {k}和E_ {1}, \\ldots, E_ {k} $为上节所提。则一个充分必要条件是每个子空间 $ W_ {i} $在T下是invariant的指T在每个projections $ E_ {i} $上可交换，例如

$ \\begin{equation} TE_ {i} = E_ {i}T, \\qquad i = 1, \\ldots, k \\end{equation} $

**定理 11** 设T为有限维空间V上的一个线性算子，如果T是可对角化的且如果 $ c_ {1}, \\ldots, c_ {k} $为T的不同的特征值，则存在V上的线性算子 $ E_ {1}, \\ldots, E_ {k} $使得

(i) $ T = c_ {1}E_ {1} + \\cdots + c_ {k} E_ {k} $

(ii) $ I = E_ {1} + \\cdots + E_ {k} $

(iii) $ E_ {i} E_ {j} = 0, i \\ne j $

(iv) $ E_ {i}^{2} = E_ {i}（E_ {i} $ 是一个projection）

(v) $ E_ {i} $的range是T带特征值 $ c_ {i} $ 的特征空间

相反地，如果存在k个不同的常量 $ c_ {1}, \\ldots, c_ {k} $和k个非零的线性算子 $ E_ {1}, \\ldots, E_ {k} $满足条件(i), (ii)和(iii)，则T是可对角化的，$ c_ {1}, \\ldots, c_ {k} $为T的不同的特征值，且条件(iv)和(v)也会满足
