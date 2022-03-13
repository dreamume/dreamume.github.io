---
layout:     post
title:      "A Course in Combinatorics(Chapter 14) by J. H. van Lint"
subtitle:   "Recursions and generating functions"
thumbnail-img: ""
date:       2022-03-10 21:00
author:     "dreamume"
tags: 		[discrete math]
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



许多组合统计问题带一个有参数n的$ a_ {n} $的解决方案，可被解决为找到一个 $ a_ {n} $的递归关系且然后解决该递归。有时候这通过引入一个普通生成函数

$ f(x) := \\sum_ {n \\ge 0}a_ {n}x^{n} $

或一个指数生成函数

$ f(x) := \\sum_ {n \\ge 0}a _{n} \\frac{x^{n}}{n!} $

且使用递归来找到一个等式或一个f(x)的导函数，且解决该等式。我们将展示一些技巧

**例子 14.1** 作为一个介绍，考虑例子10.1。设 $ \\pi $为一个derangement $ \\{1,2,\\ldots,n+1\\} $。对 $ \\pi(n + 1) $有n个选择。如果 $ \\pi(n + 1) = i $且 $ \\pi(i) = n + 1 $ 则 $ \\pi $也是也是集合 $ \\{1,2,\\ldots, n\\} \\backslash \\{i\\} $的一个dearrangement。如果 $ \\pi(n + 1) = i $且 $ \\pi(i) \\ne n + 1 = \\pi(j) $，则用i位的替代 $ \\pi(j) $得到一个集合 $ \\{1,2,\\ldots,n\\} $的dearrangement。因此

$ d_ {n+1} = n(d_ {n} + d_ {n-1}) $

这也是10.3的一个结果。设D(x)为序列 $ d_ {0} = 1, d_ {1} = 0, d_ {2}, \\ldots $的指数生成函数，我们可发现

$ (1 - x) D^{\\prime}(x) = x D(x) $

且从这我们发现 $ D(x) = e^{-x} / (1 - x) $且(10.2)

在许多情况下，我们使用生成函数只作为订阅设备，且我们的加法、乘法操作（甚至替换和求导）会做形式化地解释。它可能给出一个形式化指数系列（代数对象）的完整严谨的理论和我们在附录2中给出一个这个理论的一个简介。在多数情况下，容易验证这些操作是合理的。如果我们使用的系列是收敛的，则我们可使用所有分析中适合的知识来考虑这些系列

**例子 14.2** 假设我们有k个盒子标号从1到k且假设盒子i有 $ r_ {i} $个球，$ 1 \\le i \\le k $。一个形式化的订购设备列出所有可能的配置让对应 $ x^{r_ {1}}_ {1}x^{r_ {2}}_ {2} \\cdots x^{r_ {k}}_ {k} $在乘积中

$ (1 + x_ {1} + x^{2}_ {1} + \\cdots)(1 + x_ {2} + x^{2}_ {2} + \\cdots) \\cdots (1 + x_ {k} + x^{2}_ {k} + \\cdots) $

我们可收集所有的项目包含n个球通过设 $ x_ {i} = x $，对所有的i，且考虑等于 $ x^{n} $的项。因此我们发现分n个球到k个不同的盒子的方法数是 $ (1 - x)^{-k} $展开后 $ x^{n} $的系数，且通过10.6我们得到它为 $ {k-1+n \\choose n} $，这给出了定理13.1的另一个证明

在许多情况下，我们感兴趣的组合问题导致一个常系数的线性迭代关系，容易通过标准方法解决

**例子 14.3** 我们考虑长度为n的路径在X-Y平面中，开始于(0, 0)和步骤R：$ (x, y) \\to (x + 1, y), L: (x, y) \\to (x - 1, y) $和 $ U: (x, y) \\to (x, y + 1) $。我们需要一个步骤R不跟着步骤L之后且相反。设 $ a_ {n} $记为这样的路径的数目。首先观察如果我们记 $ b_ {n} $为开始于步骤U的长度为n的路径数，则 $ b_ {n} = a_ {n-1} $且进一步地有 $ b_ {n+m} \\ge b_ {n}b_ {m} $且 $ b_ {n} \\le 3^{n-1} $。这样通过Fekete引理，引理11.6，$ \\lim_ {n \\to \\infty} b^{1 / n}_ {n} $存在且最多为3。接着，注意 $ a_ {0} = 1 $且 $ a_ {1} = 3 $。我们分割长度为n的路径的集合为依赖最后的一步或两步的子集。明显地有 $ a_ {n-1} $个路径以步骤U结尾。取长度为n - 1的路径且重复最后的步骤如果它是L或R，且如果最后一步是U则接一个步骤L。在这样的方法上我们获得长度为n的所有路径以LL, RR或UL结尾。这样有 $ a_ {n-1} $个。仍然统计以UR结尾且这样的有 $ a_ {n-2} $个。我们显示

$ a_ {n} = 2a_ {n-1} + a_ {n-2} $

设 $ f(x) = \\sum^{\\infty} _{n=0} a _ {n} x^{n} $。则递归意味着

$ f(x) = 1 + 3x + 2x(f(x) - 1) + x^{2}f(x) $

例如：

$ f(x) = \\frac{1+x}{1 - 2x - x^{2}} = \\frac{\\frac{1}{2} \\alpha}{1 - \\alpha x} + \\frac{\\frac{1}{2} \\beta}{1 - \\beta x} $

$ \\alpha = 1 + \\sqrt{2}, \\beta = 1 - \\sqrt{2} $。因此

$ a_ {n} = \\frac{1}{2} (\\alpha^{n+1} + \\beta^{n+1}) $

且我们发现 $ \\lim_ {n \\to \\infty} a^{1 / n}_ {n} = 1 + \\sqrt{2} $
