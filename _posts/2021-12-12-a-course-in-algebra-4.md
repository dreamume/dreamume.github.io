---
layout:     post
title:      "A Course in Algebra(Chapter 4) by Vinberg"
subtitle:   "Elements of Group Theory"
thumbnail-img: ""
date:       2021-12-12 19:00
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



**命题** 对每个子群 $ G \\subset GL(V) $，集合

$ \\operatorname{Tran} V \\cdot G = \\{t_ {a} \\varphi: a \\in V, \\varphi \\in G \\} $

是空间V上的一个传递转换群

证明：对 $ a, b \\in V, \\varphi, \\psi \\in GL(V) $有

$ (t_ {a} \\varphi)(t_ {b} \\psi) = t_ {a}(\\varphi t_ {b} \\varphi^{-1}) \\varphi \\psi = t_ {a+ \\varphi(b)} \\varphi \\psi \\in \\operatorname{Tran} V \\cdot G $

它有

$ (t_ {a} \\varphi)^{-1} = t_ {-\\varphi^{-1}(a)} \\varphi^{-1} \\in \\operatorname{Tran} V \\cdot G $

因此，$ \\operatorname{Tran} V \\cdot G $是一个传输群。它是传递的因为它的子群Tran V是传递的

特别地，我们可使G = GL(V)，结果群为

$ GA(V) = \\operatorname{Tran} V \\cdot GL(V) $

被称为V的完全affine群，且它的元素，（双射）affine转换的。对应的几何被称为affine几何

在 $ V = E^{2} $的情况下，我们获得欧几里得平面的affine几何

**命题** 欧几里得平面运动的群是群 $ GA(E^{2}) $的一个子群等于 $ \\operatorname{Tran} E^{2} \\cdot O_ {2} $

证明 首先，观察所有的平行传递和垂直传递是运动。现在选一个运动f。设 a = f(o)。则运动 $ \\varphi = t^{-1}_ {a} f $不移动点o且属于群 $ O_ {2} $。因此

$ f = t_ {a}\\varphi \\in \\operatorname{Tran} E^{2} \\cdot O_ {2} $

**推论** 如果图 $ F_ {1}, F_ {2} \\subset E^{2} $在欧几里得几何中congruent，它们在affine几何中也congruent

群 $ GA(E^{2}) $比运动群大。一个affine转换不是运动的例子是缩放或沿着轴的收缩。这样，群 $ GA(E^{2}) $范围比运动群大，且在欧几里得几何不congruent但可能在affine几何中congruent。例如，所有圆在affine几何中congruent
