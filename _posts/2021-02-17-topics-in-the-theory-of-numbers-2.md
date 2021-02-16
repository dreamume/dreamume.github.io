---
layout:     post
title:      "Topics in the Theory of Numbers(Chapter 2) by Erdos"
subtitle:   "Congruences"
thumbnail-img: ""
date:       2021-02-17 01:00
author:     "dreamume"
tags: 		[number theory]
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



在许多情况下规则被学习为对一个给定除数给出一个新的数比被除数更小，在除数（例如，除以2、3、4、5、8、9、10和11）下有相同的余数。一般的，两个数在给定的除数下有相同的余数这样的关系证明在数论中为一个有用的工具，高斯引入一个特别的记号来表达它很快变成几乎每个数学家工作词典中的一部分。名字起源于拉丁文，我们称这样的两个数congruent，且它们的除数为modulus

我们说a和b congruent modulo m（或mod m）如果a和b除m时有相同的余数，或，一个相当的表述，a - b能被m整除。我们写 $ a \\equiv b (mod m) $。两个数不是congruent被称为incongruent，我们写为 $ a \\not\\equiv b (mod m) $

我们现在可表达整除

$ \\begin{equation} a \\equiv 0 (mod m) \\end{equation} $

这跟m | a等价

我们通常需要modulus为大于1的整数，但定义对所有整数都有效。负数可被忽略，因为congruence modulus m和modulus -m是相同的

modulo 0跟相等等价，因为 $ a \\equiv b (mod 0) $表示a = b，且它不需要引入一个更复杂的记号

modulo 1也用处不大，因为这种情况下所有的整数都是congruent

congruence有跟相等相似的属性使它非常有用。很明显congruence是自反的、对称的和可传递关系，例如，对所有整数a, b, c和m，有如下属性：

(a) $ a \\equiv a (mod m) $

(b) 如果 $ a \\equiv b (mod m) $，则 $ b \\equiv a (mode m) $

(c) 如果 $ a \\equiv b (mod m) $且 $ b \\equiv c (mod m) $，则 $ a \\equiv c (mod m) $

如果 $ a \\equiv b (mod m) $，则有

(d) $ a + c \\equiv b + c (mod m) $

(e) $ a - c \\equiv b - c (mod m) $

(f) $ ac \\equiv bc (mod m) $

(g) 如果 $ a \\equiv b (mod m) $ 则 $ ac \\equiv bc (mod mc) $

属性(g)反过来也成立

(h) 如果 $ ac \\equiv bc (mod mc) $ 且 $ c \\neq 0 $，则 $ a \\equiv b (mod m) $

(i) 如果 $ ac \\equiv bc (mod m) $ 且 $ (c, m) = 1 $，则 $ a \\equiv b (mod m) $

如果 $ a \\equiv b (mod m) $ 且 $ c \\equiv d (mod m) $，则

(j) $ a + c \\equiv b + d (mod m) $

(k) $ a - c \\equiv b - d (mod m) $

(l) $ ac \\equiv bd (mod m) $

(m) 如果 $ a \\equiv b (mod m) $且n是一个正整数，则 $ a^{n} \\equiv b^{n} (mod m) $

(n) 如果f(x)是一个整系数的多项式，且 $ a \\equiv b (mod m) $，则

$ \\begin{equation} f(a) \\equiv f(b) \\end{equation} $

(o) 如果 $ a \\equiv b (mod mm') $且 $ m' \\neq 0 $，则 $ a \\equiv b (mod m) $

