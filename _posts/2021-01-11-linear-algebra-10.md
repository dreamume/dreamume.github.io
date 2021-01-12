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

(ii) $ f(\\beta_ {j}, \\beta_ {j}) = \\left{ \\begin{array}{ll} 1, & j = 1, \\ldots, r \\\\ 0, & j > r \\end{array} \\end. $

**定理 5** 设V为实数域上的一个n维向量空间，且设f为V上一个对称bilinear form其rank为r，则有一个V上的有序基 $ \\{ \\beta_ {1}, \\beta_ {2}, \\ldots, \\beta_ {n} \\} $使得f的矩阵是对角的且

$ \\begin{equation} f(\\beta_ {j}, \\beta_ {j}) = \\pm 1, \\qquad j = 1, \\ldots, r \\end{equation} $

更进一步，基向量 $ \\beta_ {j} $的数 $ f(\\beta_ {j}, \\beta_ {j}) = 1 $对基的选择是独立的
