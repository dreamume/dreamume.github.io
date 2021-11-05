---
layout:     post
title:      "An Introduction to the theory of numbers(Chapter 2) by hardy"
subtitle:   "The series of primes"
thumbnail-img: ""
date:       2021-11-05 18:10
author:     "dreamume"
tags: 		[number]
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

1.  [The Series of Primes](#orgbb7855c)
    1.  [Euclid定理的第三个证明](#org65d0853)


<a id="orgbb7855c"></a>

# The Series of Primes


<a id="org65d0853"></a>

## Euclid定理的第三个证明

假设 $ 2, 3, \\ldots, p_ {j} $为头j个素数且设N(x)为不大于x且不能被任意 $ p > p_ {j} $的素数整除的数的个数n。如果我们表达这样的数n用如下形式

$ n = n^{2}_ {1}m $

m是squrefree的，例如，不能被任意素数的平方整除，我们有

$ m = 2^{b_ {1}} 3^{b_ {2}} \\cdots p^{b_ {j}}_ {j} $

每个b要么是1要么是0。只有 $ 2^{j} $个可能的指数的选择且这样不超过 $ 2^{j} $个不同值的m。而 $ n_ {1} \\le \\sqrt{n} \\le \\sqrt{x} $且这样不超过 $ \\sqrt{x} $个不同的 $ n_ {1} $值。因此

$ N(x) \\le 2^{j} \\sqrt{x} $

如果之前的定理是错的，这样素数数是有限的，设素数为 $ 2, 3, \\ldots, p_ {j} $。这个例子中N(x) = x对每个x且这样

$ x \\le 2^{j} \\sqrt{x}, \\qquad x \\le 2^{2j} $

对 $ x \\ge 2^{2j} + 1 $是不成立的

*定理* 级数

$ \\sum \\frac{1}{p} = \\frac{1}{2} + \\frac{1}{3} + \\frac{1}{5} + \\frac{1}{7} + \\frac{1}{11} + \\cdots $

是发散的

如果该级数收敛，我们可选择j使得j项之后的余数小于 $ \\frac{1}{2} $，例如

$ \\frac{1}{p_ {j+1}} + \\frac{1}{p_ {j+2}} + \\cdots < \\frac{1}{2} $

$ n \\le x $能被p整除的个数最多x / p个。因此x - N(x)，$ n \\le x $可被一个或多个 $ p_ {j+1}, p_ {j+2}, \\ldots $整除的个数不超过

$ \\frac{x}{p_ {j+1}} + \\frac{x}{p_ {j+2}} + \\cdots < \\frac{1}{2} x $

因此

$ \\frac{1}{2}x < N(x) \\le 2^{j} \\sqrt{x}, \\qquad x < 2^{2j+2} $

对 $ x \\ge 2^{2j+2} $来说这时不成立的，因此级数是发散的
