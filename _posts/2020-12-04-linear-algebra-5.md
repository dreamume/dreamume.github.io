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
3.  [The Grassman Ring](#orgc4e09e6)


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

设K为带单位元的交换环，设V为K上的一个module。如果r是一个正整数，一个函数从 $ V^{r} = V X V X \\cdots X V $ 到K被称为multilinear如果 $ L\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r} \\right) $是线性的，当选择某个 $ \\alpha_ {i} $，固定其他的 $ \\alpha_ {j} $，对每个i，有

$ \\begin{equation} L\\left(\\alpha_ {1}, \\ldots, c\\alpha_ {i} + \\beta_ {j}, \\ldots, \\alpha_ {r}\\right) = cL\\left(\\alpha_ {1}, \\ldots, \\alpha_ {i}, \\ldots, \\alpha_ {r}\\right) + L\\left(\\alpha_ {1}, \\ldots, \\beta_ {i}, \\ldots, \\alpha_ {r}\\right) \\end{equation} $

$ V^{r} $上的multilinear function也被称为V上的一个r-linear form或V上的一个multilinear form of degree r。有时候也被称为V上的r-tensors。$ V^{r} $上的所有multilinear function集合记为 $ M^{r}\\left(V\\right) $。如果L和M都在 $ M^{r}\\left(V\\right) $里，则和L + M:

$ \\begin{equation} \\left(L + M\\right)\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r}\\right) = L\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r}\\right) + M\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r}\\right) \\end{equation} $

也是multilinear，且如果c是K中一个元素，乘积cL:

$ \\begin{equation} \\left(cL\\right)\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r}\\right) = cL\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r}\\right) \\end{equation} $

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


<a id="orgc4e09e6"></a>

# The Grassman Ring

行列式和alternating multilinear forms的许多重要属性是以forms上的乘积操作描述的，称为外部乘积。如果L和M是module V上alternating r和s-linear forms，我们有一个L和M的可结合乘积，tensor product $ L \\otimes M $。它不是一个alernating form除非L = 0 或 M = 0；然而，我们有一个自然的方法投射到 $ \\Lambda^{r+s}\\left(V\\right) $，如下：

$ \\begin{equation} L \\cdot M = \\pi_ {r+s}\\left(L \\otimes M \\right) \\end{equation} $

应该是一个自然的alternating forms乘法。但，它是吗？

让我们用一个特殊的例子。假设V是一个module $ K^{n} $及 $ f_ {1}, \\ldots, f_ {n} $是 $ K^{n} $上的标准坐标函数。如果 $ i \\neq j $，则

$ \\begin{equation} f_ {i} \\cdot f_ {j} = \\pi_ {2}\\left(f_ {i} \\otimes f_ {j}\\right) \\end{equation} $

是行列式函数：

$ \\begin{equation} D_ {i j} = f_ {i} \\otimes f_ {j} - f_ {j} \\otimes f_ {i} \\end{equation} $

现在假设k是一个索引，不同于i和j，则

$ \\begin{equation} \\begin{aligned} D_ {i j} \\cdot f_ {k} &= \\pi_ {3} [\\left(f_ {i} \\otimes f_ {j} - f_ {j} \\otimes f_ {i}\\right) \\otimes f_ {k}] \\\\ &= \\pi_ {3}\\left(f_ {i} \\otimes f_ {j} \\otimes f_ {k}\\right) - \\pi_ {3}\\left(f_ {j} \\otimes f_ {i} \\otimes f_ {k}\\right) \\end{aligned} \\end{equation} $

对任意 r-linear form L和 $ \\{ 1, \\ldots, r \\} $ 的任意排序

$ \\begin{equation} \\pi_ {r}\\left(L_ {\\sigma} \\right) = sng \\, \\sigma \\, \\pi_ {r}\\left(L\\right) \\end{equation} $

因此，$ D_ {i j} \\cdot f_ {k} = 2 \\pi_ {3}\\left(f_ {i} \\otimes f_ {j} \\otimes f_ {k}\\right) $。通过相似的计算，$ f_ {i} \\cdot D_ {j k} = 2 \\pi_ {3}\\left(f_ {i} \\otimes f_ {j} \\otimes f_ {k}\\right) $。这样我们有

$ \\begin{equation} \\left(f_ {i} \\cdot f_ {j}\\right) \\cdot f_ {k} = f_ {i} \\cdot \\left(f_ {j} \\cdot f_ {k} \\right) \\end{equation} $

所有这些看起来非常好。但有个问题。尽管我们完成了计算，该计算是不可结合的。事实上，如果l是一个索引不同于i，j，k，则可计算

$ \\begin{equation} D_ {i j} \\cdot D_ {k l} = 4 \\pi_ {4} \\left( f_ {i} \\otimes f_ {j} \\otimes f_ {k} \\otimes f_ {l} \\right) \\end{equation} $

及

$ \\begin{equation} \\left( D_ {i j} \\cdot f_ {k} \\right) \\cdot f_ {l} = 6 \\pi_ {4} \\left(f_ {i} \\otimes f_ {j} \\otimes f_ {k} \\otimes f_ {l}\\right) \\end{equation} $

这样，一般地

$ \\begin{equation} \\left( f_ {i} \\cdot f_ {j}\\right) \\cdot \\left( f_ {k} \\cdot f_ {l}\\right) \\neq [ \\left(f_ {i} \\cdot f_ {j}\\right) \\cdot f_ {k}] \\cdot f_ {l} \\end{equation} $

这样我们看到该乘法不是一个可结合的操作。

假设在module V上L是一个r-linear form且M是一个s-linear form，则

$ \\begin{equation} \\begin{aligned} \\pi_ {r+s}\\left(\\left(\\pi_ {r}L\\right) \\otimes \\left(\\pi_ {s}M\\right)\\right) &= \\pi_ {r+s}\\left(\\sum_ {\\sigma, r}\\left(sgn \\, \\sigma\\right) \\left(sgn \\, r\\right)L_ {\\sigma} \\otimes M_ {r}\\right) \\\\ &= \\sum_ {\\sigma, r}\\left(sgn \\, \\sigma\\right)\\left(sgn \\, r\\right) \\pi_ {r+s}\\left(L_ {\\sigma} \\otimes M_ {r}\\right) \\end{aligned} \\end{equation} $

$ \\sigma $随着对称组 $ S_ {r} $的 $ \\{ 1, \\ldots, r \\} $的所有排列改变，r随着 $ S_ {s} $改变。每对 $ \\sigma $，r定义 $ S_ {r+s} $的一个 $ \\left(\\sigma, r\\right) $元素，根据 $ \\sigma $排列 $ \\{ 1, \\ldots, r + s \\} $的前r个元素，后s个元素根据r排列。则

$ \\begin{equation} sng \\, \\left(\\sigma, r\\right) = \\left(sgn \\, \\sigma\\right)\\left(sgn \\, r\\right) \\end{equation} $

及

$ \\begin{equation} \\left( L \\otimes M \\right)_ {\\left(\\sigma, r\\right)} = L_ {\\sigma} \\otimes L_ {r} \\end{equation} $

因此

$ \\begin{equation} \\pi_ {r+s}[\\left(\\pi_ {r}L\\right) \\otimes \\left(\\pi_ {s}M\\right)] = \\sum_ {\\sigma, r} sgn\\left(\\sigma, r\\right) \\pi_ {r+s}[\\left(L \\otimes M\\right)_ {\\left(\\sigma, r\\right)}] \\end{equation} $

现在我们观察到

$ \\begin{equation} sgn \\, \\left(\\sigma, r\\right)\\pi_ {r+s}[\\left(L \\otimes M\\right)_ {\\left(\\sigma,r\\right)}] = \\pi_ {r+s}\\left(L \\otimes M\\right)\\end{equation} $

这样的话

$ \\begin{equation} \\pi_ {r+s}[\\left(\\pi_ {r}L\\right) \\otimes \\left(\\pi_ {s}M\\right)] = r ! s ! \\pi_ {r+s}\\left(L \\otimes M\\right) \\end{equation} $

这个公式简化了计算。例如，假设我们有一个r-shuffle $ I = \\left(i_ {1}, \\ldots, i_ {r}\\right) $和s-suffle $ J = \\left(j_ {1}, \\ldots, j_ {s}\\right) $。为简单化，假设

$ \\begin{equation} i_ {1} < \\cdots < i_ {r} < j_ {1} < \\cdots < j_ {s} \\end{equation} $

则我们有相关行列式函数

$ \\begin{equation} \\begin{aligned} D_ {I} = \\pi_ {r}\\left(E_ {I}\\right) \\\\ &D_ {J} = \\pi_ {s}\\left(E_ {J}\\right) \\end{aligned} \\end{equation} $

这样我们有

$ \\begin{equation} \\begin{aligned} D_ {I} \\cdot D_ {J} &= \\pi_ {r+s}[\\pi_ {r}\\left(E_ {I}\\right) \\otimes \\pi_ {s}\\left(E_ {J}\\right) ] \\\\ &= r ! s ! \\pi_ {r+s}\\left(E_ {I} \\otimes E_ {J}\\right) \\end{aligned} \\end{equation} $

因为 $ E_ {I} \\otimes E_ {J} = E_ {I \\cup J} $，因此有

$ \\begin{equation} D_ {I} \\cdot D_ {J} = r ! s ! D_ {I \\cup J}\\end{equation} $

由于 $ D_ {I} \\cdot D_ {J} \\neq D_ {I \\cup J} $，表示该乘法没有结合律，为让该等式成立，我们应该定义一个新的乘积，一个alternating r-linear form L和alternating s-linear form M的外部乘积（或wedge product）：

$ \\begin{equation} L \\land M = \\frac{1}{r ! s !}\\pi_ {r+s}\\left(L \\otimes M\\right) \\end{equation} $

然后对K<sup>n</sup> 的行列式，我们有

$ \\begin{equation} D_ {I} \\land D_ {J} = D_ {I \\cup J} \\end{equation} $

不幸的是，上述式子在最一般的情况下无意义，因为我们可能在K环中不能被r!s!除。如果K是一个特征零的域，则该式子是有意义的，且很容易证明该乘积是可结合的。

**定理** 设K为一个特征零的域且V是K上的一个向量空间。则V上alternating forms的外部乘积是可结合的。即如果L, M, N是V上的alternating multilinear forms，degree分别为r, s和t，则

$ \\begin{equation} \\left( L \\land M\\right) \\land N = L \\land \\left( M \\land N \\right) \\end{equation} $

现在我们回到一般情况，假设K是带单位元的交换环。我们的第一个问题是想用一般化的相当的定义。如果L和M是degree r和s的alternating multilinear forms，我们想要构建一个重要的degree r+s的alternating multilinear form $ L \\land M $使得

$ \\begin{equation} r ! s ! \\left( L \\land M \\right) = \\pi_ {r+s}\\left(L \\otimes M \\right) \\end{equation} $

让我们回忆如何定义 $ \\pi_ {r+s}\\left(L \\otimes M \\right) $。对 $ \\{ 1, \\ldots, r + s \\} $的每个排列 $ \\sigma $我们联系multilinear function：

$ \\begin{equation} \\left(sgn \\, \\sigma\\right)\\left(L \\otimes M \\right)_ {\\sigma} \\end{equation} $

及

$ \\begin{equation} \\left(L \\otimes M\\right)_ {\\sigma}\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r+s}\\right) = \\left(L \\otimes M\\right)\\left(\\alpha_ {\\sigma 1}, \\ldots, \\alpha_ {\\sigma\\left(r+s\\right)}\\right) \\end{equation} $

我们对该函数所有的排列 $ \\sigma $求和。有 (r + s)! 个排列；然而，因为L和M是alternating的，许多函数相等。事实上，有最多

$ \\begin{equation} \\frac{\\left(r+s\\right) !}{r ! s !} \\end{equation} $

不同的函数。让我们看看为什么。设 $ S_ {r+s} $为 $ \\{ 1, \\ldots, r+s \\} $ 的排列集合，例如，$ S_ {r+s} $为degree r + s 的对称组。我们区分子集合G包含排列集合 $ \\{1, \\ldots, r \\} $ 和 $ \\{r + 1, \\ldots, r + s \\} $的排列 $ \\sigma $。即 $ \\sigma $在G中如果 $ 1 \\leq \\sigma i \\leq r $，i在1和r之间（j在r + 1和r + s之间，$ r + 1 \\leq \\sigma_ {j} \\leq r + s $）。现在G是 $ S_ {r+s} $的一个子群，如果 $ \\sigma $和r在G中则 $ \\sigma r^{-1} $也在G中。明显地，G有r!s!个成员。

我们有一个映射 $ S_ {r+s} \\stackrel{\\Psi}{\\to} M^{r+s}\\left(V\\right) $

定义 $ \\Psi\\left(\\sigma\\right) = \\left(sgn \\, \\sigma\\right)\\left(L \\otimes M \\right)_ {\\sigma} $

因为L和M是alternating的， $ \\forall \\gamma \\in G, \\Psi\\left(\\gamma\\right) = L \\otimes M $

因此，因为对V上任意(r+s)-linear form N， $ \\left(N\\sigma\\right)_ {\\tau} = N_ {\\tau \\sigma} $，我们有

$ \\begin{equation} \\Psi\\left(\\tau \\gamma\\right) = \\Psi\\left(\\tau\\right), r \\, in \\, S_ {r+s}, r \\, in \\, G \\end{equation} $

这表示映射 $ \\Psi $在每个子群G的（左）coset rG是个常数。如果 $ \\tau_ {1} $ 和 $ \\tau_ {2} $在 $ S_ {r+s} $中，则cosets $ \\tau_ {1}G $和 $ \\tau_ {2}G $要么相等要么不相交，根据 $ \\tau_ {2}^{-1}\\tau_ {1} $是不是在G中。每个coset包含r!s!个元素；因此，有

$ \\begin{equation} \\frac{\\left(r + s\\right) !}{r ! s !} \\end{equation} $

个不同的coset。如果 $ S_ {r+s} / G $记为coset集合则 $ \\Psi $ 定义了一个在 $ S_ {r+s} / G $上的函数，例如，通过我们所展示的，有一个函数 $ \\bar{\\Psi} $在集合上，这样

$ \\begin{equation} \\forall \\tau \\in S_ {r+s}, \\Psi\\left(\\tau\\right) = \\widetilde{\\Psi}\\left(\\tau G\\right) \\end{equation} $

如果H是G的一个左coset，则 $ \\forall \\tau \\in H, \\bar{\\Psi} \\left(H\\right) = \\Psi\\left(\\tau\\right) $

我们现在定义degree为r和s的alternating multilinear forms L和M的外积为

$ \\begin{equation} L \\land M = \\sum_ {H}\\widetilde{\\Psi}\\left(H\\right) \\end{equation} $

H在 $ S_ {r+s} / G $上遍历。另一种表达 $ L \\land M $定义的方法如下。设S为排列 $ \\{1, \\ldots, r + s \\} $的任意集合包含G的每个left coset中的一个元素。则

$ \\begin{equation} L \\land M = \\sum_ {\\sigma}\\left(sng \\, \\sigma\\right)\\left(L \\otimes M \\right)_ {\\sigma} \\end{equation} $

$ \\sigma $在S上遍历。明显地

$ \\begin{equation} r ! s ! L \\land M = \\pi_ {r + s}\\left(L \\otimes M \\right) \\end{equation} $

**定理** 设K为带单位元的交换环，V为K上的一个module，则外积是一个在V上的alternating multilinear forms的可结合操作。即如果K，M和N是对应degree r、s和t的alternating multilinear forms，则

$ \\begin{equation} \\left( L \\land M \\right) \\land N = L \\land \\left( M \\land N \\right) \\end{equation} $

证明：设G(r, s, t)为 $ S_ {r+s+t} $的子群包含排列 $ \\{1, \\ldots, r \\}, \\{r + 1, \\ldots, r + s \\}, \\{ r + s + 1, \\ldots, r + s + t \\} $ 集合里的排列。则 $ \\left(sgn \\, \\mu\\right)\\left(L \\otimes M \\otimes N\\right)_ {\\mu} $是在给定G(r, s, t)的左coset中的所有 $ \\mu $的相同multilinear函数。从每个G(r, s, t)的左coset中选择一个元素，设E为对应 $ \\left(sng \\, \\mu\\right)\\left(L \\otimes M \\otimes N\\right)_ {\\mu} $的和。则E是代表 $ \\mu $被选择的独立方法，且

$ \\begin{equation} r ! s ! t ! E = \\pi_ {r+s+t}\\left(L \\otimes M \\otimes N\\right) \\end{equation} $

我们将显示 $ \\left(L \\land M\\right) \\land N $和 $ L \\land \\left( M \\land N\\right) $都是和E相等的。

设G(r + s, t)为 $ S_ {r+s+t} $的子群排列 $ \\{1, \\ldots, r + s \\}, \\{r + s + 1, \\ldots, r + s + t\\} $的集合。设T为排列 $ \\{1, \\ldots, r + s + t \\} $的任意集合包含G(r + s, t)每个左coset的一个元素，通过

$ \\begin{equation} \\left(L \\land M\\right) \\land N = \\sum_ {\\tau} \\left(sgn \\, \\tau\\right)[\\left(L \\land M\\right) \\otimes N]_ {\\tau} \\end{equation} $

其和扩展了T上 $ \\tau $的排列。现在设G(r, s)为 $ S_ {r+s} $的子群排列集合 $ \\{1, \\ldots, r\\}, \\{r + 1, \\ldots, r + s \\} $。设S为排列 $ \\{1, \\ldots, r + s \\} $的任意集合包含G(r, s)的每个左coset的一个元素。则

$ \\begin{equation} \\left(L \\land M\\right) \\land N = \\sum_ {\\sigma, \\tau}\\left(sgn \\, \\sigma\\right) \\left(sgn \\, \\tau\\right)[\\left(L \\otimes M\\right)_ {\\sigma} \\otimes N]_ {\\tau} \\end{equation} $

其和扩展了S X T上所有 $ \\sigma, \\tau $对。如果我们同意每个 $ S_ {r+s} $上的 $ \\sigma $对应 $ S_ {r+s+t} $上的元素 $ \\{ 1, \\ldots, r + s\\} $上的 $ \\sigma $，及 $ \\{ r + s + 1, \\ldots, r + s + t \\} $，则我们可写为：

$ \\begin{equation} \\left(L \\land M\\right) \\land N = \\sum_ {\\sigma, \\tau}sgn\\left(\\sigma \\tau\\right)[\\left(L \\otimes M \\otimes N\\right)_ {\\sigma}]_ {\\tau} \\end{equation} $

但

$ \\begin{equation} [\\left(L \\otimes M \\otimes N\\right)_ {\\sigma}]_ {\\tau} = \\left(L \\otimes M \\otimes N\\right)_ {\\tau \\sigma} \\end{equation} $

因此

$ \\begin{equation} \\left(L \\land M\\right) \\land N = \\sum_ {\\sigma, \\tau}sgn\\left(\\tau \\sigma\\right)\\left(L \\otimes M \\otimes N\\right)_ {\\tau \\sigma} \\end{equation} $

现在假设我们有

$ \\begin{equation} \\tau_ {1} \\sigma_ {1} = \\tau_ {2} \\sigma_ {2} \\gamma \\end{equation} $

$ \\sigma_ {i} \\in S, \\tau_ {i} \\in T, \\gamma \\in G\\left(r, s, t\\right) $。则 $ \\tau_ {2}^{-1} \\tau_ {1} = \\sigma_ {2} \\gamma \\sigma_ {1}^{-1} $，因为 $ \\sigma_ {2} \\gamma \\sigma_ {1}^{-1} $在G(r+s, t)中，则 $ \\tau_ {1} $ 和 $ \\tau_ {2} $是在G(r + s, t)中相同的左coset里。因此，$ \\tau_ {1} = \\tau_ {2} $ 且 $ \\sigma_ {1} = \\sigma_ {2} \\gamma $。但这意味着 $ \\sigma_ {1} $ 和 $ \\sigma_ {2} $在G(r, s)的相同coset中；因此，$ \\sigma_ {1} = \\sigma_ {2} $。因此，乘积 $ \\tau \\sigma $ 对应

$ \\begin{equation} \\frac{\\left(r + s + t\\right) !}{\\left(r + s\\right) ! t !} \\frac{\\left(r + s \\right) ! }{r ! s !} \\end{equation} $

$ \\left(\\tau, \\sigma\\right) $对在T X S中是都不同的且在G(r, s, t)不同的coset中。

因为在 $ S_ {r+s+t} $中有

$ \\begin{equation} \\frac{\\left(r + s + t\\right) !}{r ! s ! t !} \\end{equation} $

个G(r, s, t)的左coset，则 $ \\left(L \\land M\\right) \\land N = E $。通过相似的计算，也有$ L \\land \\left( M \\land N\\right) = E$ 

例子13 外积跟计算行列式的相关公式紧密相关叫Laplace expansions。设K为带单位元的交换环及n是一个正整数。假设 $ 1 \\le r < n $，设L为 $ K^{n} $上的alternating r-linear form定义为：

$ \\begin{equation} L\\left(\\alpha_ {1}, \\ldots, \\alpha_ {r}\\right) = \\operatorname{det}\\left[\\begin{array}{ccc}A_ {11} & \\cdots & A_ {1 r} \\\\ \\vdots & & \\vdots \\\\ A_ {r 1} & \\cdots & A_ {r r} \\end{array} \\right] \\end{equation} $

如果s = n - r且M是alternating s-linear form

$ \\begin{equation} M\\left(\\alpha_ {1}, \\ldots, \\alpha_ {s}\\right) = \\operatorname{det}\\left[\\begin{array}{ccc}A_ {1\\left(r+1\\right)} & \\cdots & A_ {1n} \\\\ \\vdots & & \\vdots \\\\ A_ {s\\left(r+s\\right)} & \\cdots & A_ {sn} \\end{array} \\right] \\end{equation} $

则 $ L \\land M = D, K^{n}$上的行列式函数。因为 $ L \\land M $是一个alternating n-linear form且

$ \\begin{equation} \\left(L \\land M\\right)\\left(\\epsilon_ {1}, \\ldots, \\epsilon_ {n}\\right) = 1 \\end{equation} $

如果我们现在用正确的方法描述 $ L \\land M $，我们获得一个K的n x n矩阵行列式的Laplace expansion。

在排列群 $ S_ {n} $中，设G为排列集合 $ \\{1, \\ldots, r \\} $和 $ \\{ r+1, \\ldots, n \\} $的子群。G的每个左coset包含一个排列 $ \\sigma $使得 $ \\sigma 1 < \\sigma 2 < \\ldots < \\sigma r $ 和 $ \\sigma \\left(r + 1\\right) < \\ldots < \\sigma n $。排列的符号被给定为：

$ \\begin{equation} sng \\, \\sigma = \\left(-1\\right)^{\\sigma 1 + \\cdots + \\sigma r + \\left(\\frac{r\\left(r-1\\right)}{2}\\right) } \\end{equation} $

wedge product $ L \\land M $被给定为：

$ \\begin{equation} \\left(L \\land M \\right) \\left(\\alpha_ {1}, \\ldots, \\alpha_ {n}\\right) = \\sum \\left(sgn \\, \\alpha\\right) L\\left(\\alpha_ {\\sigma_ {1}}, \\ldots, \\alpha_ {\\sigma r}\\right) M\\left(\\alpha_ {\\sigma \\left(r+1\\right)}, \\ldots, \\alpha_ {\\sigma n}\\right) \\end{equation} $

其和为 $ \\sigma $的集合，每个G中coset一个。因此，

$ \\begin{equation} \\left(L \\land M \\right)\\left(\\alpha_ {1}, \\ldots, \\alpha_ {n}\\right) = \\sum_ {j_ {1} < \\cdots < j_ {r}}e_ {J} L\\left(\\alpha_ {j_ {1}}, \\ldots, \\alpha_ {j_ {r}}\\right)M\\left(\\alpha_ {k_ {1}}, \\ldots, \\alpha_ {k_ {s}}\\right) \\end{equation} $

其中

$ \\begin{equation} e_ {J} = \\left(-1\\right)^{j_ {1} + \\cdots + j_ {r} + \\left(\\frac{r\\left(r - 1\\right)}{2}\\right)} \\end{equation} $

$ \\begin{equation} k_ {i} = \\sigma\\left(r + i\\right) \\end{equation} $

即

$ \\begin{equation} \\operatorname{det} A = \\sum_ {j_ {1} < \\cdots < j_ {r}} e_ {J} \\left\| \\begin{array}{ccc}A_ {j_ {1}, 1} & \\cdots & A_ {j_ {1}, r} \\\\ \\vdots & & \\vdots \\\\ A_ {j_ {r}, 1} & \\cdots & A_ {j_ {r}, r} \\end{array} \\right\| \\left\| \\begin{array}{ccc} A_ {k_ {1}, r+1} & \\cdots & A_ {k_ {1}, n} \\\\ \\vdots & & \\vdots \\\\ A_ {k_ {r}, r+1} & \\cdots & A_ {k_ {r}, n} \\end{array} \\right\| \\end{equation} $

这是一个Laplace expansion。其他的可通过替换集合 $ \\{1, \\ldots, r \\} $和 $ \\{r+1, \\ldots, n \\} $为两个不同补集索引来获得。
