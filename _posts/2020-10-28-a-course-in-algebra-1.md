---
layout:     post
title:      "A Course in Algebra(Chapter 1) by Vinberg"
subtitle:   "Algebraic Structure"
thumbnail-img: ""
date:       2020-10-28 19:00
author:     "dreamume"
tags: 		[algebra]
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

1.  [代数结构](#org2500f14)
    1.  [简介](#org210ef2c)
    2.  [阿贝尔群](#orgc31e4b3)
    3.  [环和域](#orgc60734c)
    4.  [子群，子环和子域](#org19183fa)


<a id="org2500f14"></a>

# 代数结构


<a id="org210ef2c"></a>

## 简介

定义：设M为一个集合及一个操作o，N为集合及一个操作\*，代数结构(M, o)和(N, \*)为同构仅当存在一个双射f: M -> N，使得对任意 $ a, b \\in M, f(a \\circ b)=f(a) \* f(b) $ 。我们把它记做 $ (M, \\circ) \\simeq(N, *) $ ，映射f称为(M, o)和(N, \*)之间的同构。


<a id="orgc31e4b3"></a>

## 阿贝尔群

定义：加法阿贝尔群为集合A及一个加法有如下属性：

(i) 对任意 $ a, b \\in A, a + b = b + a $

(ii) 对任意 $ a, b, c \\in A, (a + b) + c = a + (b + c) $

(iii) 存在一个元素 $ 0 \\in A $ 使得对任意 $ a \\in A, a + 0 = a  $

(iv) 对任意元素 $ a \\in A $ ，存在一个元素 $ -a \\in A $ ，使得 $ a + (-a) = 0 $

定义乘法阿贝尔群为一个集合A及一个乘法有如下属性：

(i) 对任意 $ a, b \\in A, ab = ba $

(ii) 对任意 $ a, b, c \\in A, (ab)c = a(bc) $

(iii) 存在一个元素 $ e \\in A $ 使得对任意 $ a \\in A, ae = a  $

(iv) 对任意元素 $ a \\in A $ ，存在一个元素 $ a^{-1} \\in A $ ，使得 $ a a^{-1} = e $


<a id="orgc60734c"></a>

## 环和域

定义：环为一个集合K及一个加法和乘法有如下属性：

(i) K为加法上的阿贝尔群

(ii) 对任意 $ a, b, c \\in K \\text{有} a(b+c) = ab + ac \\text{和} (a + b)c = ac + bc $

定义：域为可交换结合的环，对每一个非0元素都可逆。


<a id="org19183fa"></a>

## 子群，子环和子域

定义：阿贝尔群A的一个子集合B被称为子群仅当：

(i) B对于加法是闭的

(ii) $ a \\in B \\Longrightarrow -a \\in B $

(iii) $ 0 \\in B $
