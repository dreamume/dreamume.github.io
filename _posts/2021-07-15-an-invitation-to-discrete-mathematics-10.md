---
layout:     post
title:      "An invitation to discrete mathematics(Chapter 10) by Matousek"
subtitle:   "Probability by counting"
thumbnail-img: ""
date:       2021-07-15 09:00
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

1.  [统计证明](#org6e1a4a6)
    1.  [命题](#org0817386)


<a id="org6e1a4a6"></a>

# 统计证明


<a id="org0817386"></a>

## 命题

存在一个n个变量的布尔函数不能被任意少于 $ 2^{n} / \\log_ {2}{(n+8)} $个符号的公式定义。例如，对23个变量我们需要超过一百万个符号的公式

**证明** 所有n个变量的布尔函数的数量是 $ 2^{2^{n}} $，其n个变量公式的数量被最多m个符号写出的不超过 $ (n + 8)^{m} $个，因为公式中每m个位置可被n + 7个可能的符号填充，或可能是空白。这样，我们也统计了许多无意义的字符串符号，但一个初略的上限是有的。如果 $ 2^{2^{n}} > (n + 8)^{m} $，则存在一个布尔函数不能被最多m个符号表达。通过算法中的不等式，我们获得 $ m \\ge 2^{n} / \\log_ {2}{(n+8)} $

