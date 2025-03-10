---
layout:     post
title:      "Extended Euclidean Algorithm"
subtitle:   ""
thumbnail-img: ""
date:       2025-03-09 21:00
author:     "dreamume"
tags: 		[algorithm]
category:   it
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

1.  [Extended Euclidean Algorithm](#org3b208ce)
    1.  [算法](#orgb988ab5)
    2.  [C++ 代码实现](#orgd9f85b8)
    3.  [迭代版本](#org1a87fb2)


<a id="org3b208ce"></a>

# Extended Euclidean Algorithm

[Extended Euclidean Algorithm](https://cp-algorithms.com/algebra/extended-euclid-algorithm.html)

欧几里得算法只计算两个整数 a 和 b 的最大公因数，扩展版本还能发现一个方法来用 a 和 b 表示 GCD，比如系数 x 和 y 使得

$ a \\times x + b \\times y = gcd(a, b) $

注意到通过 Bézout's identity 我们也可以找到这样的表达式。例如，gcd(55, 80) = 5，因此我们可表达 5 作为一个与 55 和 80 的线性组合：$ 55 \\times 3 + 80 \\times (-2) = 5 $

一个该问题的更一般化形式在文章 [Linear Diophantine Equations](https://cp-algorithms.com/algebra/linear-diophantine-equation.html) 中讨论。它用这个算法构建


<a id="orgb988ab5"></a>

## 算法

在本章节中我们将用 g 表示 a 和 b 的 GCD

对原算法的改变非常简单。如果我们回忆算法，我们可看到算法以 b = 0 和 a = g 结束。对这些参数我们可容易地找到系数， $ g \\times 1 + 0 \\times 0 = g $

从 (x, y) = (1, 0) 这些系数开始，我们可回溯递归调用。所有我们需要做的是指明系数 x 和 y 在从 (a, b) 到 (b, a mod b) 之间如何改变

让我们假设我们找到了 (b, a mod b) 的系数 $ (x_ {1}, y_ {1}) $:

$ b \\times x_ {1} + (a \\bmod b) \\times y_ {1} = g $

且我们想要找到 (a, b) 的 (x, y) 对：

$ a \\times x + b \\times y = g $

我们可表达 a mod b 为：

$ a \\bmod b = a - \\lfloor \\frac{a}{b} \\rfloor \\times b $

用 $ (x_ {1}, y_ {1}) $ 的系数等式替代这个表达式：

$ g = b \\times x_ {1} + (a \\bmod b) \\times y_ {1} = b \\times x_ {1} + \\left( a - \\lfloor \\frac{a}{b} \\rfloor \\times b \\right) \\times y_ {1} $

且整理条目后：

$ g = a \\times y_ {1} + b \\times \\left( x_ {1} - y_ {1} \\times \\lfloor \\frac{a}{b} \\rfloor \\right) $

这样我们找到 x 和 y 的值：

$ \\left\\{\\begin{array}{l} x = y_ {1} \\ y = x_ {1} - y_ {1} \\times \\left\\lfloor\\frac{a}{b}\\right\\rfloor \\end{array}\\right. $


<a id="orgd9f85b8"></a>

## C++ 代码实现

    int gcd(int a, int b, int& x, int& y) {
      if (b == 0) {
        x = 1;
        y = 0;
        return a;
      }
    
      int x1, y1;
      int d = gcd(b, a % b, x1, y1);
      x = y1;
      y = x1 - y1 * (a / b);
    
      return d;
    }

这个扩展欧几里得算法的实现对负整数也能产生正确的结果


<a id="org1a87fb2"></a>

## 迭代版本

也可以用迭代的方式写欧几里得算法。因为它避免回调，代码比回调版本要快一些

    int gcd(int a, int b, int& x, int& y) {
      x = 1;
      y = 0;
      int x1 = 0, y1 = 1, a1 = a, b1 = b;
      while (b1) {
        int q = a1 / b1;
        tie(x, x1) = make_tuple(x1, x - q * x1);
        tie(y, y1) = make_tuple(y1, y - q * y1);
        tie(a1, b1) = make_tuple(b1, a1 - q * b1);
      }
    
      return a1;
    }

