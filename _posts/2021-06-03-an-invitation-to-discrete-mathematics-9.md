---
layout:     post
title:      "An invitation to discrete mathematics(Chapter 9) by Matousek"
subtitle:   "Finite projective planes"
thumbnail-img: ""
date:       2021-06-03 09:00
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

1.  [定义和基本属性](#org26c438d)
    1.  [定义](#org00539b3)


<a id="org26c438d"></a>

# 定义和基本属性

finite projective plane是带某些属性的有限集合的子集的系统


<a id="org00539b3"></a>

## 定义

设X为一个有限集，且设 $ \\mathcal{L} $为X的子集的系统。二元组 $ (X, \\mathcal{L}) $被称为finite projective plane，如果它满足如下公理：

(P0) 存在一个4元素集合 $ F \\subseteq X $使得对每个集合 $ L \\in \\mathcal{L}, \| L \\cap F \| \\le 2 $

(P1) 任意两个不同的集合 $ L_ {1}, L_ {2} \\in \\mathcal{L} $ 相交只有一个元素，例如，$ \| L_ {1} \\cap L_ {2} \| = 1 $

(P2) 对任意两个不同的元素 $ x_ {1}, x_ {2} \\in X $，只存在一个集合 $ L \\in \\mathcal{L} $ 使得 $ x_ {1} \\in L, x_ {2} \\in L $
