---
layout:     post
title:      "Linear Algebra(Chapter 5) by Hoffman"
subtitle:   "Determinants"
thumbnail-img: ""
date:       2020-12-04 17:00
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

1.  [Modules](#orge434519)
2.  [Multilinear Functions](#orge6b44cc)


<a id="orge434519"></a>

# Modules

如果K是带单位元的交换环，K上的module是一个代数系统，其行为跟向量空间相似。精确地说，V是K上的一个module（或K-module），如果

1.  V是一个交换群，V上有一个加法使得 $ \\left( \\alpha + \\beta \\right) \\to \\alpha + \\beta $
2.  有一个乘法使得 $ \\alpha \\in V, c \\in K, \\left(c, \\alpha\\right) \\to c\\alpha $，有
    
    $ \\begin{equation} \\left( c_ {1} + c_ {2}\\right) \\alpha = c_ {1}\\alpha + c_ {2}\\alpha \\end{equation} $
    
    $ \\begin{equation} c\\left( \\alpha_ {1} + \\alpha_ {2}\\right) = c\\alpha_ {1} + c\\alpha_ {2} \\end{equation} $
    
    $ \\begin{equation} \\left( c_ {1} c_ {2}\\right) \\alpha = c_ {1} \\left(c_ {2}\\alpha \\right) \\end{equation} $
    
    $ \\begin{equation} 1 \\alpha = \\alpha \\end{equation} $

**定义** K-module V被称为一个free module，如果它有一个基。如果V有有限个基包含n个元素，则V被称为一个free K-module with n generators


<a id="orge6b44cc"></a>

# Multilinear Functions

设K为带单位元的交换环，设V为K上的一个module。如果r是一个正整数，一个函数从 $ V^{r} = V x V x \\codts x V $ 到K被称为multilinear如果 $ L\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r} \\right) $是线性的，当选择某个 $ \\alpha_ {i} $，固定其他的 $ \\alpha_ {j} $，对每个i，有

$ \\begin{equation} L\\left(\\alpha_ {1}, \\ldots, c\\alpha_ {i} + \\beta_ {j}, \\ldots, \\alpha_ {r}\\right) = cL\\left(\\alpha_ {1}, \\ldots, \\alpha_ {i}, \\ldots, \\alpha_ {r}\\right) + L\\left(\\alpha_ {1}, \\ldots, \\beta_ {i}, \\ldots, \\alpha_ {r}\\right) \\end{equation} $

$ V^{r} $上的multilinear function也被称为V上的一个r-linear form或V上的一个multilinear form of degree r。有时候也被称为V上的r-tensors。$ V^{r} $上的所有multilinear function集合记为 $ M^{r}\\left(V\\right) $。如果L和M都在 $ M^{r}\\left(V\\right) $里，则和L + M:

$ \\begin{equation} \\left(L + M\\right)\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r}\\right) = L\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r}\\right) + M\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r}\\right) \\end{equation} $

也是multilinear，且如果c是K中一个元素，乘积cL:

$ \\begin{equation} \\left(cL\\right)\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r}\\right) = cL\\left(\\alpha_ {1}, \\lodts, \\alpha_ {r}\\right) \\end{equation} $

也是multilinear。因此 $ M^{r}\\left(V\\right) $是一个K-module - 所有从 $ V^{r} $到K的函数的module的submodule。

如果r = 1我们有 $ M^{1}\\left(V\\right) = V^{ * } $，V上的linear functions的dual module。linear functions也能被用来构建更高维multilinear forms的例子。如果 $ f_ {1}, \\ldots, f_ {r} $是V上的linear functions，定义

$ \\begin{equation} L\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r}\\right) = f_ {1}\\left(\\alpha_ {1}\\right) f_ {2}\\left(\\alpha_ {2}\\right) \\cdots f_ {r}\\left(\\alpha_ {r}\\right) \\end{equation} $

假设L是 $ V^{r} $上的multilinear function，M是 $ V^{s} $上的multilinear function，我们定义 $ V^{r+s} $上的函数 $ L \\otimes M $：

$ \\begin{equation} \\left( L \\otimes M \\right)\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r+s} \\right) = L\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r} \\right)M\\left(\\alpha_ {1}, \\ldots, \\alpha_ {s}\\right) \\end{equation} $

如果我们认为 $ V^{r+s} $为 $ V^{r} X V^{s} $，则对 $ \\alpha \\in V^{r}, \\beta \\in V^{s} $，有

$ \\begin{equation} \\left(L \\otimes M \\right)\\left(\\alpha, \\beta\\right) = L\\left(\\alpha\\right)M\\left(\\beta\\right) \\end{equation} $

很明显 $ L \\otimes M $是 $ V^{r+s} $上的一个multilinear。函数 $ L \\otimes M $被称为L和M的tensor product。tensor product是不交换的，事实上， $ M \\otimes L \\neq L \\otimes M $除非L = 0或M = 0；然而，tensor product跟$ M^{r} $和 $ M^{s} $上的module操作相关。

**引理** 设L, $ L_ {1} $为V上的r-linear forms，设M, $ M_ {1} $为V上s-linear forms，c为K上一个元素，有

(a) $ \\left(cL + L_ {1}\\right) \\otimes M = c\\left(L \\otimes M\\right) + L_ {1} \\otimes M $

(b) $ L \\otimes \\left(cM + M_ {1}\\right) = c\\left(L \\otimes M\\right) + L \\otimes M_ {1} $

**定理** 设K为带单位元的交换环，如果V是rank n的free K-module，则 $ M^{r}\\left(V\\right) $是rank $ n^{r} $的free K-module；事实上，如果 $ \\{ f_ {1}, \\ldots, f_ {n} \\} $是dual module $ V^{ * } $的一个基，则 $ n^{r} $ tensor products

$ \\begin{equation} f_ {j_ {1}} \\otimes \\cdots \\otimes f_ {j_ {r}}, \\qquad 1 \\leq j_ {1} \\leq n, \\ldots, 1 \\leq j_ {r} \\leq n \\end{equation} $

是 $ M^{r}\\left(V\\right) $的一个基。

**定义** 设L为一个K-module V上的r-linear form。我们说L是alternating如果 $ L\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r}\\right) = 0 $当 $ \\alpha_ {i} = \\alpha_ {j}, i \\neq j $

如果L是 $ V^{r} $上的一个alternating multilinear function，则

$ \\begin{equation} L\\left(\\alpha_ {1}, \\ldots, \\alpha_ {i}, \\ldots, \\alpha_ {j}, \\ldots, \\alpha_ {r}\\right) = -L\\left(\\alpha_ {1}, \\ldots, \\alpha_ {j}, \\ldots, \\alpha_ {i}, \\ldots, \\alpha_ {r}\\right) \\end{equation} $

即如果我们置换r元组 $ \\left(\\alpha_ {1}, \\ldots, \\alpha_ {r}\\right) $的两个向量（下标不同）将使得L的值改变符号。因为每个排列 $ \\sigma $是置换的乘积，我们看到 $ L\\left(\\alpha_ {\\sigma 1}, \\ldots, \\alpha_ {\\sigma r}\\right) = \\left(sgn \\, \\sigma\\right)L\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r}\\right) $

我们记 $ \\Lambda^{r}\\left(V\\right) $为V上所有alternating r-linear forms的集合。明显，$ \\Lambda^{r}\\left(V\\right) $是 $ M^{r}\\left(V\\right) $的一个submodule。

如果L是一个module V上的r-linear form，如果 $ \\sigma $ 是 $ \\{ 1, \\ldots, r \\} $的一个排列，我们获得另一个r-linear function $ L_ {\\sigma} $，定义：

$ \\begin{equation} L_ {\\sigma}\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r}\\right) = L \\left(\\alpha_ {\\sigma 1}, \\ldots, \\alpha_ {\\sigma r}\\right) \\end{equation} $

如果L是alternating的，则 $ L_ {\\sigma} = \\left(sgn \\, \\sigma\\right)L $，现在，对每个 $ M^{r}\\left(V\\right) $上的L我们定义 $ M^{r}\\left(V\\right) $上的函数 $ \\pi_ {r}L $:

$ \\begin{equation} \\pi_ {r}L = \\sum_ {\\sigma}\\left(sgn \\, \\sigma\\right)L_ {\\sigma} \\end{equation} $

即

$ \\begin{equation} \\left(\\pi_ {r}L\\right)\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r}\\right) = \\sum_ {\\sigma}\\left(sgn \\, \\sigma\\right)L\\left(\\alpha_ {\\sigma 1}, \\ldots, \\alpha_ {\\sigma r}\\right) \\end{equation} $

**引理** $ \\pi_ {r} $是从 $ M^{r}\\left(V\\right) $到 $ \\Lambda^{r}\\left(V\\right) $上的一个linear transformation，如果L在 $ \\Lambda^{r}\\left( V \\right) $中则 $ \\pi_ {r}L = r ! L $

证明：设r为 $ \\{1, \\ldots, r \\} $ 的任意排列，则

$ \\begin{equation} \\begin{aligned} \\left(\\pi_ {r}L\\right)\\left(\\alpha_ {r1}, \\ldots, \\alpha_ {rr}\\right) &= \\sum_ {\\sigma}\\left(sgn \\, \\sigma\\right)L\\left(\\alpha_ {r \\sigma 1}, \\ldots, \\alpha_ {r \\sigma r}\\right) \\\\ &= \\left(sgn \\, r\\right)\\sum_ {\\sigma}\\left(sgn \\, r\\sigma\\right)L\\left(\\alpha_ {r \\sigma 1}, \\ldots, \\alpha_ {r \\sigma r}\\right) \\end{aligned} \\end{equation} $

因为 $ \\sigma $一次运行 $ \\{1, \\ldots, r\\} $的所有排列，所以 $ r\\sigma $也是。因此，

$ \\begin{equation} \\left(\\pi_ {r}L\\right)\\left(\\alpha_ {r1}, \\ldots, \\alpha_ {rr}\\right) = \\left(sgn \\, r\\right)\\left(\\pi_ {r}L\\right)\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r}\\right) \\end{equation} $

这样 $ \\pi_ {r}L $是一个alternating form。

如果L在 $ \\Lambda^{r}\\left(V\\right) $中，则对每个 $ \\sigma, L\\left(\\alpha_ {\\sigma 1}, \\ldots, \\alpha_ {\\sigma r}\\right) = \\left(sgn \\, \\sigma\\right)L\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r}\\right) $；因此 $ \\pi_ {r}L = r ! L $

**定理** 设K为带单位元的交换环，V是rank n的free K-module，如果r > n，则 $ \\Lambda^{r}\\left(V\\right) = \\{ 0 \\} $，如果 $ 1 \\leq r \\leq n $，则 $ \\Lambda^{r}\\left(V\\right) $是一个rank $ {n \\choose r} $的free K-module

**推论** 如果V是rank n的free K-module，则 $ \\Lambda^{r}\\left(V\\right) $是一个rank 1的free K-module，如果T是V上的一个linear operator，K上有唯一一个元素c使得

$ \\begin{equation} L\\left(T\\alpha_ {1}, \\ldots, T\\alpha_ {n}\\right) = cL\\left(\\alpha_ {1}, \\ldots, \\alpha_ {n}\\right) \\end{equation} $

对V上每一个alternating n-linear form L。
