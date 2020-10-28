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


<a id="org2500f14"></a>

# 代数结构


<a id="org210ef2c"></a>

## 简介

定义：设M为一个集合及一个操作o，N为集合及一个操作\*，代数结构(M, o)和(N, \*)为同构仅当存在一个双射f: M -> N，使得对任意 $ a, b \\in M, f(a \\circ b)=f(a) \* f(b) $ 。我们把它记做 $ (M, \\circ) \\simeq(N, *) $ ，映射f称为(M, o)和(N, \*)之间的同构。


<a id="orgc31e4b3"></a>

## 阿贝尔群

定义：加法阿贝尔群为集合A及一个加法有如下属性：

(i) 对任意 $ a, b \\in A, a + b = b + a $

