---
layout:     post
title:      "A Course in Combinatorics(Chapter 9) by J. H. van Lint"
subtitle:   "Two (0,1,*) problems: addressing for graphs and a hash-coding scheme"
thumbnail-img: ""
date:       2022-01-11 18:10
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



  如下问题源于通讯定理。对一个电话网络，终端A和B之间的一个连接在每个方向上在消息流之前建立。对一个计算机网络它想要可能发送一个消息从A到B不需要知道B知道一个消息在它的道路上。想法是让消息被B的某些地址处理使得在网络的每个节点可确定一个决定消息需要处理的方向

  一个自然的事情是尝试给出图形G的每个顶点一个二进制地址，称为 $ \\{0, 1\\}^{k} $，在这样的方法上图形中两个顶点的距离等于地址的被称为Hamming的距离，例如，地址不同的位置数。这相等于视G为一个超立方体 $ H_ {k} $的引导子图形，其 $ V(H_ {k}) := \\{0, 1\\}^{k} $且k元组是邻接的当它们只在一个坐标上不同时。例子 $ G = K_ {3} $已经显示这是不可能的。我们现在引入一个新的字母 $ \\{ 0, 1, * \\} $且从这个字母中取n元形成地址。两个地址的距离是定义为当数字的位置一个为0一个为1时这样的位置数。对一个图形G的一个地址，我们需要G中任意两个顶点的距离等于它们地址的距离。我们记N(G)为n的最小值，其存在G的一个地址比为长度n

