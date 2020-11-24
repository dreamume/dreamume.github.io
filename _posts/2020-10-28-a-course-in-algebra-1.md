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
    5.  [余类的环](#org5160204)
    6.  [向量空间](#org97c8839)
    7.  [Algebras](#orgd2724c7)


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

定义：环K的一个子集合L被称为子环仅当：

(i) L是环K的加法群的子群

(ii) L对于乘法是闭的

定义：域K的一个子集合L被称为子域仅当

(i) L是K的一个子环

(ii) $ a \\in L, a \\neq 0 \Longrightarrow a^{-1} \\in L $

(iii) $ 1 \\in L $


<a id="org5160204"></a>

## 余类的环

考虑一个集合M，任何子集 $ R \\subset M \\times M $ 被称为集合M上的一个关系。如果 $ (a, b) \\in R $ ，我们说a和b相关并记为aRb

一个相等关系R为一个关系，有：

(i) 自反性：aRa

(ii) 对称性：$ a R b \\Longrightarrow b R a $

(iii) 传递性：$ a R b \\text{且} b R c \\Longrightarrow a R c $

相等关系通常记为 $ a \\stackrel{R}{\\sim} b $ 或 a ~ b

设R为集合M上的一个相等关系，对任意 $ a \\in M $ ，有 $ \\begin{equation} R(a)=\\{b \\in M: a \\stackrel{R}{\\sim} b\\} \\end{equation} $

相等关系的属性意味着 $ \\begin{equation} R(a) \\cap R(b) \\neq \\varnothing \\quad \\Longrightarrow \\quad R(a)=R(b) \\end{equation} $

关系R下的相等类集合被称为关系R下的M的商集，并记为M / R。映射

$ \\begin{equation} M \\rightarrow M / R, \\quad a \\mapsto R(a) \\end{equation} $

被称为商映射

现在我们定义余类的环，考虑如下等价关系，在集合上称为模n：如果a - b能被n整除或如果a和b被n除后有相同的余数，记为 $ a \\equiv b(\\bmod n) $

设 $ \\begin{equation} a \\equiv a^{\\prime}(\\bmod n), \\quad b \\equiv b^{\\prime}(\\bmod n) \\end{equation} $

则 $ \\begin{equation} a+b \\equiv a^{\\prime}+b \\equiv a^{\\prime}+b^{\\prime}(\\bmod n) \\end{equation} $

及 $ \\begin{equation} a b \\equiv a^{\\prime} b \\equiv a^{\\prime} b^{\\prime}(\\bmod n) \\end{equation} $

因此，我们定义集合Z<sub>n</sub> 上加法和乘法操作：

$ \\begin{equation} [a]_ {n} + [b]_ {n} = [a+b]_ {n}, \\quad[a]_ {n}[b]_ {n} = [a b]_ {n} \\end{equation} $

这样Z<sub>n</sub> 变成带单位元的交换结合环，它被称为模n的余类的环（或余环）

定理：环Z<sub>n</sub> 为域当且仅当n为一个质数

Example 1.52. Let us solve the quadratic equation x<sup>2</sup> + x + 1 = 0 in the field Z<sub>11</sub> . The standard formules yields

$ \\begin{equation} x_ {1,2}=\\frac{[-1] \\pm \\sqrt{[5]}}{[2]} \\end{equation} $

Since [5] = [16] = [4]<sup>2</sup> , we can assume that $ \\sqrt{[5]}=[4] $ (one of the values of the square root). Hence,

$ \\begin{equation} x_ {1}=\\frac{[-1]+[4]}{[2]}=\\frac{[3]}{[2]}=\\frac{[14]}{[2]}=[7], \\quad x_ {2}=\\frac{[-1]-[4]}{[2]}=\\frac{[-5]}{[2]}=\\frac{[6]}{[2]}=[3] \\end{equation} $


<a id="org97c8839"></a>

## 向量空间

定义：域K上的向量（线性）空间为一个集合V及域上元素的加法和乘法操作，有如下属性：

(i) V是一个加法上的阿贝尔群

(ii) $ \\lambda(a+b)=\\lambda a+\\lambda b \\text { for any } \\lambda \\in K, a, b \\in V $

(iii) $ (\\lambda+\\mu) a=\\lambda a+\\mu a \\text { for any } \\lambda, \\mu \\in K, a \\in V $

(iv) $ (\\lambda \\mu) a=\\lambda(\\mu a) \\text { for any } \\lambda, \\mu \\in K, a \\in V $

(v) $ 1 a=a \\text { for any } a \\in V $

定义：一个向量空间V的子集U称为子空间，如果

(i) U为V加法群的一个子群

(ii) $ a \\in U \\Longrightarrow \\lambda a \\in U \\quad \\text{for any } \\quad \\lambda \\in K $

定义：域K上的向量空间V和U被称为同构如果存在一个双射

$ \\begin{equation} \\varphi: V \\rightarrow U \\end{equation} $

有

(i) $ \\varphi(a + b) = \\varphi(a) + \\varphi(b) \\quad \\text{for any} \\quad a, b \\in V $

(ii) $ \\varphi(\\lambda a) = \\lambda \\varphi(a) \\quad \\text{for any} \\quad \\lambda \\in K, a \\in V $

映射 $ \\varphi $ 被称为V和U之间的同构关系


<a id="orgd2724c7"></a>

## Algebras

**定义** 一个algebra是域K上的集合及加法、乘法操作，K上元素的乘法有如下属性：

(i) A是一个向量空间及有域上元素的加法和乘法

(ii) A是加法和乘法的环

(iii) $ \\forall \\lambda \\in K, \\, a, b \\in A, \\quad \\left( \\lambda a \\right) b = a \\left( \\lambda b \\right) = \\lambda \\left(ab\\right) $
