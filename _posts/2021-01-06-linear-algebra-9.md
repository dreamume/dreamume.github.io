---
layout:     post
title:      "Linear Algebra(Chapter 9) by Hoffman"
subtitle:   "Operators on Inner Product Spaces"
thumbnail-img: ""
date:       2021-01-06 08:38
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

1.  [Forms on Inner Product Spaces](#org33aee2c)
2.  [Positive Forms](#orgf123329)
3.  [More on Forms](#orgf41eb85)
4.  [Spectral Theory](#org50de053)
5.  [Further Properties of Normal Operators](#org58ed36f)


<a id="org33aee2c"></a>

# Forms on Inner Product Spaces

**定义** 一个在实数或复数向量空间V上的（sesqui-linear）form是一个 $ V \\times V $的函数使得

(a) $ f(c\\alpha + \\beta, \\gamma) = cf(\\alpha, \\gamma) + f(\\beta, \\gamma) $

(b) $ f(\\alpha, c\\beta + \\gamma) = \\bar{c}f(\\alpha, \\beta) + f(\\alpha, \\gamma) $

对所有V中的 $ \\alpha, \\beta, \\gamma $及所有常量c

当为实数时，$ f(\\alpha, \\beta) $对每个参数该函数都是线性的，即f是一个bilinear form

**定理 1** 设V为一个有限维内积空间且f为V上一个form，则V上有唯一一个线性算子T使得

$ \\begin{equation} f(\\alpha, \\beta) = (T\\alpha \| \\beta) \\end{equation} $

对V中所有 $ \\alpha, \\beta $，且映射 $ f \\to T $是forms空间在L(V, V)上的同构

**推论** 等式 $ (f \| g) = \\operatorname{tr}(T_ {f}T_ {g}^{ * }) $定义了一个在forms空间上的内积有属性

$ \\begin{equation} (f \| g) = \\sum_ {j,k}f(\\alpha_ {k}, \\alpha_ {j})\\overline{g(\\alpha_ {k}, \\alpha_ {j})} \\end{equation} $

对V上每个标准正交基 $ \\{ \\alpha_ {1}, \\ldots, \\alpha_ {n} \\} $

**定义** 如果f是一个form且 $ \\mathcal{B} = \\{\\alpha_ {1}, \\ldots, \\alpha_{n} \\} $是V的一个任意有序基，矩阵A $ A_ {j k} = f(\\alpha_ {k}, \\alpha_ {j}) $被称为在有序基 $ \\mathcal{B} $上f的矩阵

**定理 2** 设f是在有限维复数内积空间V上的一个form，则有一个V的标准正交基使得f的矩阵是上三角的

**定义** 一个在实数或复数向量空间V上的form f被称为Hermitian如果

$ \\begin{equation} f(\\alpha, \\beta) = \\overline{f(\\beta, \\alpha)} \\end{equation} $

对V中所有 $ \\alpha, \\beta $

**定理 3** 设V为一个复数向量空间且f是V上一个form使得 $ f(\\alpha, \\alpha) $对每个 $ \\alpha $是实数，则f是Hermitian的

**推论** 设T为复数有限维内积空间V上的一个线性算子，则T是self-adjoint当且仅当 $ (T \\alpha \| \\alpha) $对V中每个 $ \\alpha $是实数

**定理 4(Principal Axis Theorem)** 对有限维内积空间V上的每个Hermitian form f有一个V上的标准正交基使得f为一个实数元素的对角矩阵

**推论** 使用上述条件，有

$ \\begin{equation} f(\\sum_ {j}x_ {j}\\alpha_ {j}, \\sum_ {k}y_ {k}\\alpha_ {k}) = \\sum_ {j}c_ {j}x_ {j}\\bar{y}_ {j} \\end{equation} $


<a id="orgf123329"></a>

# Positive Forms

**定义** 一个在实数或复数向量空间V上的form f是非负的如果它是Hermitian且 $ f(\\alpha, \\alpha) \\ge 0 $对V中每个 $ \\alpha $。form f是正的如果f是Hermitian且 $ f(\\alpha, \\alpha) > 0 $对所有 $ \\alpha \\ne 0 $

**定理 5** 设F为实数域或复数域，设A为F上 $ n \\times n $矩阵，函数g被定义为

$ \\begin{equation} f(X, Y) = Y^{ * }AX \\end{equation} $

是在空间 $ F^{ n \\times 1 } $上的正form当且仅当存在一个可逆 $ n \\times n $矩阵P，元素在F上，使得 $ A = P^{ * }P $

**定义** 设A为域F上的 $ n \\times n $矩阵，A的principal minors为常量 $ \\Delta_ {k}(A) $定义为

$ \\begin{equation} \\Delta_ {k}(A) = \\operatorname{det} \\left[ \\begin{array}{ccc} A_ {11} & \\cdots & A_ {1k} \\\\ \\vdots & & \\vdots \\\\ A_ {k1} & \\cdots & A_ {kk} \\end{array} \\right], \\qquad 1 \\le k \\le n \\end{equation} $

**引理** 设A为域F上的可逆 $ n \\times n $矩阵，下面两个叙述等价

(a) 有一个上三角矩阵P，$ P_ {k k} = 1 (1 \\le k \\le n) $使得矩阵B = AP是下三角的

(b) A的principal minors都不为0

**定理 6** 设f为有限维向量空间上的一个form且设A为有序基 $ \\mathcal{ B} $下f的矩阵，则f是一个正form当且仅当 $ A = A^{ * } $且A的principal minors都是正的

如果A是带复数元素的 $ n \\times n $矩阵且如果A满足 $ \\forall 实数X \\ne 0, X^{t}AX > 0 $，我们称A为一个正矩阵

**定义** 一个有限维内积空间V上的线性算子T是非负的如果 $ T = T^{ * } 且 (T\\alpha \| \\alpha) \\ge 0 $，对V中所有 $ \\alpha $。一个正的线性算子是使得 $ T = T^{ * } 且 (T\\alpha \| \\alpha) > 0 $，对所有 $ \\alpha \\ne 0 $

如果A是复数域上的 $ n \\times n $矩阵，如下描述等价：

(1) A是正的，例如，$ \\sum_ {j}\\sum_ {k}A_ {k j}x_ {j}\\bar{x}_ {k} > 0, x_ {1}, \\ldots, x_ {n} $是复数，不全为0

(2) $ (X \| Y) = Y^{ * }AX $是 $ n \\times 1 $复数矩阵空间上的内积

(3) 对于在 $ n \\times 1 $矩阵上的标准内积 $ (X \| Y) = Y^{ * } X $，线性算子 $ X \\to AX $是正的

(4) 对C上某个可逆 $ n \\times n $矩阵P有 $ A = P^{ * }P $

(5) $ A = A^{ * } $，且A的principal minors是正的

如果A中每个元素都是实数，以下是等价的

(6) $ A = A^{t} 且 \\sum_ {j}\\sum_ {k}A_ {k j}x_ {j}x_ {k} > 0, x_ {1}, \\ldots, x_ {n} $是实数且不全为0

(7) $ (X \| Y) = Y^{t}AX $是 $ n \\times 1 $实数矩阵空间上的内积

(8) 对于 $ n \\times 1 $实数矩阵上的标准内积 $ (X \| Y) = Y^{t}X $，线性算子 $ X \\to AX $是正的

(9) 有一个实数元素的可逆 $ n \\times n $矩阵P，使得 $ A = P^{t}P $


<a id="orgf41eb85"></a>

# More on Forms

**定理 7** 设f为实数或复数向量空间V上的一个form且 $ \\{ \\alpha_ {1}, \\ldots, \\alpha_ {r} \\} $是V的有限维子空间W上的一个基，设M为 $ r \\times r $矩阵，其元素为

$ \\begin{equation} M_ {j k} = f(\\alpha_ {k}, \\alpha_ {j}) \\end{equation} $

且W'为V中所有向量 $ \\beta $的集合使得 $ f(\\alpha, \\beta) = 0 $对W中所有 $ \\alpha $。则W'是V的一个子空间，且 $ W \\cap W' = \\{ 0 \\} $当且仅当M是可逆的，这种情况下，V = W + W'

**定理 8** 设f为实数或复数向量空间V上的一个form且A为f在V的有序基 $ \\{ \\alpha_ {1}, \\ldots, \\alpha_ {n} \\} $下的矩阵。假设A的principal minors都不为0，则有唯一的一个上三角矩阵P，$ P_ {k k} = 1(1 \\le k \\le n) $使得

$ \\begin{equation} P^{ * } AP \\end{equation} $

是上三角的


<a id="org50de053"></a>

# Spectral Theory

**定理 9(Spectral Theorem)** 设T为有限维复数内积空间V上的normal算子或有限维实数内积空间V上的self-adjoint算子，设 $ c_ {1}, \\ldots, c_ {k} $为T的不同的特征值，设 $ W_ {j} $为 $ c_ {j} $对应的特征空间且 $ E_ {j} $为V在 $ W_ {j} $上的正交映射，则 $ W_ {j} $正交 $ W_ {i} $当 $ i \\ne j $，V是 $ W_ {1}, \\ldots, W_ {k} $的直和，且

$ \\begin{equation} T = c_ {1}E_ {1} + \\cdots + c_ {k}E_ {k} \\end{equation} $

**推论** 如果 $ e_ {j} = \\prod_ {i \\ne j}\\left(\\frac{x - c_ {i}}{c_ {j} - c_ {i}} \\right), 则 E_ {j} = e_ {j}(T), 1 \\le j \\le k $

**定义** 设T为有限维内积空间上的一个可对角化normal算子且

$ \\begin{equation} T = \\sum_ {j = 1}^{k} c_ {j}E_ {j} \\end{equation} $

是它的spectral resolution。假设f是一个函数定义域包含T的spectrum在常量域上有值，则线性算子f(T)被定义为如下等式

$ \\begin{equation} f(T) = \\sum_ {j = 1}^{k} f(c_ {j})E_ {j} \\end{equation} $

**定理 10** 设T为有限维内积空间上的一个可对角化normal算子，有Spectrum S，假设f是一个函数定义域包含S在常量域上有值，则f(T)是一个可对角化normal算子有spectrum f(S)。如果U是一个V到V'的unitary映射且 $ T' = UTU^{-1} $，则S是T'的spectrum且

$ \\begin{equation} f(T') = Uf(T)U^{-1} \\end{equation} $

**推论** 在定理10的假设下，假设在有序基 $ \\mathcal{B} = \\{\\alpha_ {1}, \\ldots, \\alpha_ {n} \\} $下T表达为对角矩阵D，元素为 $ d_ {1}, \\ldots, d_ {n} $，则在基 $ \\mathcal{B} $下，f(T)表达为对角矩阵f(D)，元素为 $ f(d_ {1}), \\ldots, f(d_ {n}) $。如果 $ \\mathcal{B}' = \\{\\alpha_ {1}', \\ldots, \\alpha_ {n}' \\} $是任意其他有序基且P矩阵使得

$ \\begin{equation} \\alpha_ {j}' = \\sum_ {i}P_ {i j}\\alpha_ {i} \\end{equation} $

则 $ P^{-1}f(D)P $是基 $ \\mathcal{B}' $下f(T)的矩阵

**定理 11** 设A为normal矩阵且 $ c_ {1}, \\ldots, c_ {k} $为 $ \\operatorname{det}(xI - A) $不同的复数根，设

$ \\begin{equation} e_ {i} = \\prod_ {j \\ne i}\\left(\\frac{x - c_ {j}}{c_ {i} - c_ {j}}\\right) \\end{equation} $

且 $ E_ {i} = e_ {i}(A)(1 \\le k) $。则 $ E_ {i}E_ {j} = 0, i \\ne j, E_ {i}^{2} = E_ {i}, E_ {i}^{ * } = E_ {i} $，且

$ \\begin{equation} I = E_ {1} + \\cdots + E_ {k} \\end{equation} $

如果f是一个复数函数其定义域包含 $ c_ {1}, \\ldots, c_ {k} $，则

$ \\begin{equation} f(A) = f(c_ {1})E_ {1} + \\cdots + f(c_ {k})E_ {k}; \\end{equation} $

特别地， $ A = c_ {1}E_ {1} + \\cdots + c_ {k}E_ {k} $

**定理 12** 设T为有限维内积空间V上的一个可对角化normal算子，则T是一个self-adjoint，非负或unitary对应T的每个特征值为实数的，非负的或绝对值为1

**定理 13** 设V为一个有限维内积空间且T为V上一个非负算子，则T有一个唯一的非负平方根，在V上有唯一一个非负算子N使得 $ N^{2} = T $

**定理 14** 设V为一个有限维内积空间且设T为V上任意线性算子，则存在V上一个unitary算子U和V上一个非负算子N使得T = UN，非负算子是唯一的，如果T可逆，算子U也是唯一的

**定义** 设 $ \\mathcal{F} $为内积空间V上的一族算子，$ \\mathcal{F} $上的有域F上常量值的函数r被称为 $ \\mathcal{F} $的一个根如果在V中有一个非零 $ \\alpha $使得

$ \\begin{equation} T \\alpha = r(T) \\alpha \\end{equation} $

对 $ \\mathcal{F} $上所有T。对任意从 $ \\mathcal{F} $到F的函数，设V(r)为V中所有 $ \\alpha $的集合使得对 $ \\mathcal{F} $中每个T，有 $ T \\alpha = r(T)\\alpha $

则V(r)是V的一个子空间，且r是 $ \\mathcal{F} $的一个根当且仅当 $ V(r) \\ne \\{0\\} $。V(r)中每个非零 $ \\alpha $同时也是 $ \\mathcal{F} $中每个T的一个特性向量

**定理 15** 设 $ \\mathcal{F} $为在有限维内积空间V上的一族可交换可对角化normal算子，则 $ \\mathcal{F} $只有有限个根。如果 $ r_ {1}, \\ldots, r_ {k} $为 $ \\mathcal{F} $的不同根，则

(i) $ V(r_ {i}) $正交 $ V(r_ {j}), i \\ne j $，且

(ii) $ V = V(r_ {1}) \\oplus \\cdots \\oplus V(r_ {k}) $

**推论** 在上面定理的假设下，设 $ P_ {j} $为V在 $ V(r_ {j}) $上的正交映射，$ (1 \\ne j \\ne k) $，则 $ P_ {i}P_ {j} = 0, i \\ne j $，

$ \\begin{equation} I = P_ {1} + \\cdots + P_ {k} \\end{equation} $

且 $ \\mathcal{F} $中每个T可写成如下形式

$ \\begin{equation} T = \\sum_ {j}r_ {j} (T)P_ {j} \\end{equation} $

**定义** 正交映射族 $ \\{P_ {1}, \\ldots, P_ {k} \\} $被称为由 $ \\mathcal{F} $决定的resolution of identity，且上式为在该族中T的spectral resolution

**定义** 一个在内积空间V上的算子的self-adjoint代数是一个L(V, V)的线性子代数，其包含每个成员的adjoint

**定义** 如果 $ \\mathcal{F} $是有限维内积空间上的一族线性算子，由 $ \\mathcal{F} $产生的self-adjoint代数是包含 $ \\mathcal{F} $的最小self-adjoint代数

**定理 16** 设 $ \\mathcal{F} $是有限维内积空间V上的可对角化normal算子的交换族，且设 $ \\mathcal{G} $为由 $ \\mathcal{F} $产生的self-adjoint代数和identity算子，设 $ \\{P_ {1}, \\ldots, P_ {k} \\} $为由 $ \\mathcal{F} $定义的resolution of the identity，则 $ \\mathcal{G} $为V上所有算子的如下形式的集合

$ \\begin{equation} T = \\sum_ {j=1}^{k} c_ {j}P_ {j} \\end{equation} $

$ c_ {1}, \\ldots, c_ {k} $为任意常量

**推论** 在上述定理假设下，在 $ \\mathcal{G} $中有一个算子T使得 $ \\mathcal{G} $中的每个成员是T的多项式


<a id="org58ed36f"></a>

# Further Properties of Normal Operators

**定理 17** 设T为在有限维内积空间V中的一个normal算子，设p为T的minimal polynomial且 $ p_ {1}, \\cdots, p_ {k} $为它的不同的monic质因子，则每个 $ p_ {j} $在p中出现次数为1且degree为1或2，假设 $ W_ {j} $是 $ p_ {j}(T) $的null space，则

(i) $ W_ {j} $正交 $ W_ {i}, i \\ne j $

(ii) $ V = W_ {1} \\oplus \\cdots \\oplus W_ {k} $

(iii) $ W_ {j} $在T下不变，且 $ p_ {j} $是T限制在 $ W_ {j} $下的minimal polynomial

(iv) 对每个j，有一个系数为常量的polynomial $ e_ {j} $使得 $ e_ {j}(T) $是V到 $ W_ {j} $的正交映射

**引理 1** 设N为内积空间W上的normal算子，则N的null space它的范围的正交补

**引理 2** 如果N是一个normal算子且 $ \\alpha $是一个向量使得 $ N^{2}\\alpha = 0 $，则 $ N\\alpha = 0 $

**引理 3** 设T为一个normal算子且f为系数为常量的任意polynomial，则f(T)也是normal的

**引理 4** 设T为一个normal算子且f、g为系数为常数的互质polynomials，假设 $ \\alpha, \\beta $为向量使得 $ f(T)\\alpha = 0, g(T)\\beta = 0 $，则 $ (\\alpha \| \\beta) = 0 $

**定义** 我们称子空间 $ W_ {j} (1 \\le j \\le k) $为V在T之下的主部分

**推论** 设T为有限维复数内积空间V上的normal算子且 $ W_ {1}, \\ldots, W_ {k} $为V在T之下的主部分，假设W是V的一个子空间在T下不变，则

$ \\begin{equation} W = \\sum_ {j} W \\cap W_ {j} \\end{equation} $

**定理 18** 设T为有限维实数内积空间V上的一个normal算子且p是它的minimal polynomial，假设

$ \\begin{equation} p = (x - a)^{2} + b^2 \\end{equation} $

a、b为实数且 $ b \\ne 0 $，则有一个整数s > 0使得 $ p^{s} $是T的特征polynomial，且存在V的子空间 $ V_ {1}, \\ldots, V_ {s} $使得

(i) $ V_ {j} $正交 $ V_ {i}, i \\ne j $

(ii) $ V = V_ {1} \\oplus \\cdots \\oplus V_ {s} $

(iii) 每个 $ V_ {j} $有一个标准正交基 $ \\{ \\alpha_ {j}, \\beta_ {j} \\} $及属性

$ \\begin{equation} T \\alpha_ {j} = a \\alpha_ {j} + b \\beta_ {j} \\end{equation} $

$ \\begin{equation} T \\beta_ {j} = -b \\alpha_ {j} + a \\beta_ {j} \\end{equation} $

**引理** 设V为一个实数内积空间且S为V上一个normal算子使得 $ S^{2} + I = 0 $，设 $ \\alpha $为V中任意向量且 $ \\beta = S \\alpha $，则

$ \\begin{equation} S^{ * } \\alpha = - \\beta \\end{equation} $

$ \\begin{equation} S^{ * } \\beta = \\alpha \\end{equation} $

$ (\\alpha \| \\beta) = 0 且 \|\| \\alpha \|\| = \|\| \\beta \|\| $

**推论** 在上述定理条件下，T是可逆的，且

$ \\begin{equation} T^{ * } = (a^{2} + b^{2})T^{-1} \\end{equation} $

**定理 19** 设T为在有限维内积空间V中的一个normal算子，则任意可与T交换的线性算子也能与 $ T^{ * } $交换，更进一步，在T下不变的每个子空间也在$ T^{ * } $下不变

**定理 20** 设T为有限维内积空间V上的一个normal线性算子（$ \\operatorname{dim} V \\ge 1 $），则V中存在r个非零向量 $ \\alpha_ {1}, \\ldots, \\alpha_ {r} $对应T-annihilators $ e_ {1}, \\ldots, e_ {r} $使得

(i) $ V = Z(\\alpha_ {1}; T) \\oplus \\cdots \\oplus Z(\\alpha_ {r}; T) $

(ii) 如果 $ 1 \\le k \\le r - 1 $，则 $ e_ {k+1} $整除 $ e_ {k} $

(iii) $ Z(\\alpha_ {j}; T) $正交 $ Z(\\alpha_ {k}; T), j \\ne k $，更进一步，整数r和annihilators $ e_ {1}, \\ldots, e_ {r} $由条件(i)和(ii)唯一决定且没有 $ \\alpha_ {k} $为0

**推论** 如果A是一个normal矩阵，其元素为实数（复数），则有一个实的正交（unitary）矩阵P使得 $ P^{-1}AP $是rational cononical form

**定义** 设V和V'为相同域上的内积空间，一个线性转换

$ \\begin{equation} U: V \\to V' \\end{equation} $

被称为unitary转换如果它映射V onto V'且保留内积，如果T是V上的一个线性算子且T'是V'上的一个线性算子，则T unitarily equivelant to T'如果存在从V onto V'的unitary转换U使得

$ \\begin{equation} UTU^{-1} = T' \\end{equation} $

**引理** 设V和V'为相同域上的有限维内积空间，设T为V上的一个线性算子且T'为V'上的一个线性算子，则T unitarily equivalent to T'当且仅当有一个V的标准正交基 $ \\mathcal{B} $和V'的标准正交基 $ \\mathcal{B}' $使得

$ \\begin{equation} [T]_ {\\mathcal{B}} = [T']_ {\\mathcal{B}'} \\end{equation} $

**定理 21** 设V和V'为相同域上的有限维内积空间，假设T为V上的一个normal算子且T'为V'上的normal算子，则T unitarily equivalent to T'当且仅当T和T'有相同的特征polynomial
