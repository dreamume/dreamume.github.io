---
layout:     post
title:      "Linear Algebra(Chapter 10) by Hoffman"
subtitle:   "Bilinear Forms"
thumbnail-img: ""
date:       2021-01-11 18:38
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

1.  [Bilinear Forms](#org43acb5f)
2.  [Synmmetric Bilinear Forms](#orga7bd71e)
3.  [Skew-Symmetric Bilinear Forms](#org33e6a85)
4.  [Groups Preserving Bilinear Forms](#org2757c82)


<a id="org43acb5f"></a>

# Bilinear Forms

**定义** 设V为域F上的一个向量空间，一个V上的bilinear form是一个函数f，赋值V中每个有序向量对 $ \\alpha, \\beta $一个F中常量 $ f(\\alpha, \\beta) $，且满足

$ \\begin{equation} f(c\\alpha_ {1} + \\alpha_ {2}, \\beta) = cf(\\alpha_ {1}, \\beta) + f(\\alpha_ {2}, \\beta) \\end{equation} $

$ \\begin{equation} f(\\alpha, c\\beta_ {1} + \\beta_ {2}) = cf(\\alpha, \\beta_ {1}) + f(\\alpha, \\beta_ {2}) \\end{equation} $

**定义** 设V为一个有限维向量空间，且设 $ \\mathcal{B} = \\{ \\alpha_ {1}, \\ldots, \\alpha_ {n} \\} $为V的一个有序基，如果f是V上的一个bilinear form，则在有序基 $ \\mathcal{B} $上的f的矩阵是 $ n \\times n $矩阵A，其元素 $ A_ {i j} = f(\\alpha_ {i}, \\alpha_ {j}) $，我们将它记为 $ [f]_ {\\mathcal{B}} $

**定理 1** 设V为域F上的一个有限维向量空间，对V的每个有序基 $ \\mathcal{B} $，函数对应V上基于有序基 $ \\mathcal{B} $的每个bilinear form是在域F上空间L(V, V, F) onto $ n \\times n $矩阵空间的一个isomorphism

**推论** 如果 $ \\mathcal{B} = \\{ \\alpha_ {1}, \\ldots, \\alpha_ {n} \\} $是V的一个有序基，且 $ \\mathcal{B}^{ * } = \\{ L_ {1}, \\ldots, L_ {n} \\} $是 $ V^{ * } $的dual basis，则 $ n^{2} $ bilinear forms

$ \\begin{equation} f_ {i j}(\\alpha, \\beta) = L_ {i}(\\alpha) L_ {j}(\\beta), \\qquad 1 \\le i \\le n, 1 \\le j \\le n \\end{equation} $

形成空间L(V, V, F)的一个基，特别地，L(V, V, F)的维数为 $ n^{2} $

**定理 2** 设f为有限维向量空间V上的一个bilinear form，设 $ L_ {f} $和 $ R_ {f} $为从V到 $ V^{ * } $的线性转换定义为 $ (L_ {f}\\alpha)(\\beta) = f(\\alpha, \\beta) = (R_ {f}\\beta)(\\alpha) $，则 $ \\operatorname{rank}(L_ {f}) = \\operatorname{rank}(R_ {f}) $

**定义** 如果f为有限维向量空间V上的一个bilinear form，f的rank是整数 $ r = \\operatorname{rank}(L_ {f}) = \\operatorname{rank}(R_ {f}) $

**推论 1** 一个bilinear form的rank等于该form在任意有序基下矩阵的rank

**推论 2** 如果f为n维向量空间的一个bilinear form，如下描述相等：

(a) rank(f) = n

(b) 对V中每个非零 $ \\alpha $，有V中一个 $ \\beta $使得 $ f(\\alpha, \\beta) \\ne 0 $

(c) 对V中每个非零 $ \\beta $，有V中一个 $ \\alpha $使得 $ f(\\alpha, \\beta) \\ne 0 $

**定义** 一个向量空间V上的bilinear form f被称为non-degenerate（或non-singular）如果它满足推论2的条件(b)和(c)


<a id="orga7bd71e"></a>

# Synmmetric Bilinear Forms

**定义** 设V为域F上的一个向量空间，一个V上的bilinear form是一个函数f，赋值V中每个有序向量对 $ \\alpha, \\beta $一个F中常量 $ f(\\alpha, \\beta) $，且满足

$ \\begin{equation} f(c\\alpha_ {1} + \\alpha_ {2}, \\beta) = cf(\\alpha_ {1}, \\beta) + f(\\alpha_ {2}, \\beta) \\end{equation} $

$ \\begin{equation} f(\\alpha, c\\beta_ {1} + \\beta_ {2}) = cf(\\alpha, \\beta_ {1}) + f(\\alpha, \\beta_ {2}) \\end{equation} $

**定义** 设V为一个有限维向量空间，且设 $ \\mathcal{B} = \\{ \\alpha_ {1}, \\ldots, \\alpha_ {n} \\} $为V的一个有序基，如果f是V上的一个bilinear form，则在有序基 $ \\mathcal{B} $上的f的矩阵是 $ n \\times n $矩阵A，其元素 $ A_ {i j} = f(\\alpha_ {i}, \\alpha_ {j}) $，我们将它记为 $ [f]_ {\\mathcal{B}} $

**定理 1** 设V为域F上的一个有限维向量空间，对V的每个有序基 $ \\mathcal{B} $，函数对应V上基于有序基 $ \\mathcal{B} $的每个bilinear form是在域F上空间L(V, V, F) onto $ n \\times n $矩阵空间的一个isomorphism

**推论** 如果 $ \\mathcal{B} = \\{ \\alpha_ {1}, \\ldots, \\alpha_ {n} \\} $是V的一个有序基，且 $ \\mathcal{B}^{ * } = \\{ L_ {1}, \\ldots, L_ {n} \\} $是 $ V^{ * } $的dual basis，则 $ n^{2} $ bilinear forms

$ \\begin{equation} f_ {i j}(\\alpha, \\beta) = L_ {i}(\\alpha) L_ {j}(\\beta), \\qquad 1 \\le i \\le n, 1 \\le j \\le n \\end{equation} $

形成空间L(V, V, F)的一个基，特别地，L(V, V, F)的维数为 $ n^{2} $

**定理 2** 设f为有限维向量空间V上的一个bilinear form，设 $ L_ {f} $和 $ R_ {f} $为从V到 $ V^{ * } $的线性转换定义为 $ (L_ {f}\\alpha)(\\beta) = f(\\alpha, \\beta) = (R_ {f}\\beta)(\\alpha) $，则 $ \\operatorname{rank}(L_ {f}) = \\operatorname{rank}(R_ {f}) $

**定义** 如果f为有限维向量空间V上的一个bilinear form，f的rank是整数 $ r = \\operatorname{rank}(L_ {f}) = \\operatorname{rank}(R_ {f}) $

**推论 1** 一个bilinear form的rank等于该form在任意有序基下矩阵的rank

**推论 2** 如果f为n维向量空间的一个bilinear form，如下描述相等：

(a) rank(f) = n

(b) 对V中每个非零 $ \\alpha $，有V中一个 $ \\beta $使得 $ f(\\alpha, \\beta) \\ne 0 $

(c) 对V中每个非零 $ \\beta $，有V中一个 $ \\alpha $使得 $ f(\\alpha, \\beta) \\ne 0 $

**定义** 一个向量空间V上的bilinear form f被称为non-degenerate（或non-singular）如果它满足推论2的条件(b)和(c)
Synmmetric Bilinear Forms

**定义** 设f为向量空间V上的一个bilinear form，我们说f是对称的如果 $ f(\\alpha, \\beta) = f(\\beta, \\alpha) $对V中所有向量 $ \\alpha, \\beta $

**定理 3** 设V为一个特征0的域上的有限维向量空间，且设f为V上的一个对称bilinear form，则有一个V的有序基使得f为一个对角矩阵

**推论** 设F为复数子域，且设A为F上一个$ n \\times n $的对称矩阵，则有一个F上可逆的 $ n \\times n $矩阵P使得 $ P^{t}AP $是对角的

**定理 4** 设V为复数域上一个有限维向量空间，设f为V上一个对称bilinear form其rank为r，则有一个V上的有序基 $ \\mathcal{B} = \\{ \\beta_ {1}, \\ldots, \\beta_ {n} \\} $使得

(i) 在有序基 $ \\mathcal{B} $下的f的矩阵是对角的

(ii) $ f(\\beta_ {j}, \\beta_ {j}) = \\left\\{ \\begin{array}{ll} 1, & j = 1, \\ldots, r \\\\ 0, & j > r \\end{array} \\right. $

**定理 5** 设V为实数域上的一个n维向量空间，且设f为V上一个对称bilinear form其rank为r，则有一个V上的有序基 $ \\{ \\beta_ {1}, \\beta_ {2}, \\ldots, \\beta_ {n} \\} $使得f的矩阵是对角的且

$ \\begin{equation} f(\\beta_ {j}, \\beta_ {j}) = \\pm 1, \\qquad j = 1, \\ldots, r \\end{equation} $

更进一步，基向量 $ \\beta_ {j} $的数 $ f(\\beta_ {j}, \\beta_ {j}) = 1 $对基的选择是独立的


<a id="org33e6a85"></a>

# Skew-Symmetric Bilinear Forms

本节V将作为复数域的子域F上的一个向量空间，一个V上的bilinear form被称为skew-symmetri如果对V中所有向量 $ \\alpha, \\beta, f(\\alpha, \\beta) = -f(\\beta, \\alpha) $

**定理 6** 设V为复数域的子域上的n维向量空间，且设f为V上一个skew-symmetric bilinear form，则f的rank r是偶数，且如果r = 2k有一个V上的有序基使得f的矩阵为 $ (n - r) \\times (n - r) $零矩阵和k个 $ 2 \\times 2 $矩阵的拷贝的直和

$ \\begin{equation} \\left[ \\begin{array}{ll} 0 & 1 \\\\ -1 & 0 \\end{array} \\right] \\end{equation} $


<a id="org2757c82"></a>

# Groups Preserving Bilinear Forms

**定理 17** 设f为有限维向量空间V上的一个non-degenerate bilinear form，V上保留f的所有线性算子的集合是一个组合操作的群

**例子 6** 设V为空间 $ R^{n} 或 C^{n} $，设f为belinear form

$ \\begin{equation} f(\\alpha, \\beta) = \\sum_ {j = 1}^{n}x_ {j}y_ {j} \\end{equation} $

$ \\alpha = (x_ {1}, \\ldots, x_ {n}), \\beta = (y_ {1}, \\ldots, y_ {n}) $。群保留f被称为n维（实数或复数）正交群。因为f的矩阵在标准基上是I，该群包含矩阵M满足 $ M^{t}M = I $。这样的一个矩阵M被称为 $ n \\times n $（实数或复数）正交矩阵。这两个 $ n \\times n $正交群通常记为 O(n, R)和O(n, C)。当然，正交群也是保留二项式form的群

$ \\begin{equation} q(x_ {1}, \\ldots, x_ {n}) = x_ {1}^{2} + \\cdots + x_ {n}^{2} \\end{equation} $

**例子 7** 设f为 $ R^{n} $上的对称bilinear form的二次方 form:

$ \\begin{equation} q(x_ {1}, \\ldots, x_ {n}) = \\sum_ {j=1}^{p} x_ {j}^{2} - \\sum_ {j = p + 1}^{n}x_ {j}^{2} \\end{equation} $

则f是non-degenerate且有signature 2p - n，保留这种类型form的矩阵的群被称为伪正交群。当p = n时是正交群O(n, R)，对每个n + 1的值 $ p = 0, 1, 2, \\ldots, n $，我们获得不同的bilinear forms f；然而，对p = k且p = n - k forms其form互相为其的负且因此有相同的群。这样，当n为奇数，我们有(n + 1) / 2个 $ n \\times n $矩阵的伪正交群，且当n为偶数时，我们有(n + 2) / 2个这样的群

**定理 8** 设V为一个复数域上n维向量空间，且设f为V上一个non-degenerate symmetric bilinear form，则保留f的群跟复数正交群O(n, C) isomorphic

**定理 9** 设V为实数域上的一个n维向量空间，且设f为V上的一个non-degenerate对称bilinear form，则保留f的群跟一个 $ n \\times n $伪正交群是isomorphic的

**例子 8** 设f为 $ R^{4} $上的一个对称bilinear form的二次方form

$ \\begin{equation} q(x, y, z, t) = t^{2} - x^{2} - y^{2} - z^{2} \\end{equation} $

一个 $ R^{4} $上的线性算子T保留这个bilinear form被称为Lorentz转换，且保留f的群被称为Lorentz群，我们将给出一个方法描述某些Lorentz变换

设H为实数向量空间所有 $ 2 \\times 2 $复数矩阵A是Hermitian的，$ A = A^{ * } $，它容易检查为

$ \\begin{equation} \\Phi(x, y, z, t) = \\left[ \\begin{array}{ll} t + x & y + iz \\\\ y - iz & t - x \\end{array} \\right] \\end{equation} $

定义了一个 $ R^{4} $ onto 空间H的isomorphism $ \\Phi $，在这个isomorphism下，二次方form q为行列式方法，及

$ \\begin{equation} q(x, y, z, t) = \\operatorname{det} \\left[ \\begin{array}{ll} t + x & y + iz \\\\ y - iz & t - x \\end{array} \\right] \\end{equation} $

或

$ \\begin{equation} q(\\alpha) = \\operatorname{det} \\Phi(\\alpha) \\end{equation} $

这个建议我们可能通过学习H上保留行列式的线性算子来学习$ R^{4} $上Lorentz转换

设M为任意复数 $ 2 \\times 2 $矩阵且对一个Hermitian矩阵A定义

$ \\begin{equation} U_ {m}(A) = MAM^{ * } \\end{equation} $

现在 $ MAM^{ * } $也是Hermitian的，容易看到 $ U_ {M} $是H上一个（实数）线性算子。因为 $ M^{ * } $的行列式是M的共轭复数的行列式，我们看到

$ \\begin{equation} \\operatorname{det}[U_ {M}(A)] = \| \\operatorname{det} M \|^{2} \\operatorname{det}A \\end{equation} $

当det M的绝对值为1时 $ U_ {M} $保留行列式

这样现在让我们选择任意 $ 2 \\times 2 $复数矩阵M，其 $ \| \\operatorname{det} M \| = 1 $，则 $ U_ {M} $是H上一个线性算子保留行列式，定义

$ \\begin{equation} T_ {M} = \\Phi^{-1}U_ {M}\\Phi \\end{equation} $

因为 $ Phi $是一个isomorphism，$ T_ {M} $是 $ R^{4} $上一个线性算子。$ T_ {M} $也是一个Lorentz变换

$ \\begin{equation} \\begin{aligned} q(T_ {M}\\alpha) &= q(\\Phi^{-1}U_ {M}\\Phi\\alpha) \\\\ &= \\operatorname{det}(\\Phi\\Phi^{-1}U_ {M}\\Phi\\alpha) \\\\ &= \\operatorname{det}(U_ {M}\\Phi\\alpha) \\\\ &= \\operatorname{det}(\\Phi\\alpha) \\\\ &= q(\\alpha) \\end{aligned} \\end{equation} $

所以 $ T_ {M} $保留二次方form q

通过使用特殊的 $ 2 \\times 2 $矩阵M，可以使用如上的方法计算特殊的Lorentz变换，有如下两个评论，其不难验证：

(1) 如果 $ M_ {1} 和 M_ {2} $是复数可逆 $ 2 \\times 2 $矩阵，则 $ U_ {M_ {1}} = U_ {M_ {2}} $当且仅当 $ M_ {2} $是 $ M_ {1} $的常量倍数。这样， 所有上面展现的Lorentz变换可从unimodular矩阵M获得，即从矩阵M满足det M = 1。如果 $ M_ {1} $ 和 $ M_ {2} $为unimodular矩阵使得 $ M_ {1} \\ne M_ {2} 且 M_ {1} \\ne - M_ {2} $，则 $ T_ {M_ {1}} \\ne T_ {M_ {2}} $

(2) 不是每个Lorentz变换都可通过上述方法获得
