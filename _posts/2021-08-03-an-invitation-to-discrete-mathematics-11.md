---
layout:     post
title:      "An invitation to discrete mathematics(Chapter 11) by Matousek"
subtitle:   "Order from disorder: Ramsey's theorem"
thumbnail-img: ""
date:       2021-08-03 07:00
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

1.  [6个人的聚会](#org12b5603)
    1.  [定理](#org82b7db9)


<a id="org12b5603"></a>

# 6个人的聚会

我们现在看一个6个人聚会的例子。设G为一个图形，我们引入如下的记号：$ \\omega(G) $记为一个完全子图的最大顶点数，且 $ \\alpha(G) $为G中一个独立集合的最大顶点数，即集合中两个顶点之间没有被一条边连接


<a id="org82b7db9"></a>

## 定理

设G为一个至少6个顶点的图，则 $ \\alpha(G) \\ge 3 $ 或 $ \\omega(G) \\ge 3 $

**证明** 让我们任意选择G中一个顶点且让我们把它记为u。设 $ A \\subseteq V(G) \\ \\{u\\} $为不连接到u的顶点集合；形式为 $ A = \\{v \\in V(G): v \\ne u, \\{u, v\\} \\notin E(G) \\} $。设 $ B = V(G) \\ A \\ \\{u \\} $ 包含连接到u的顶点。因为 $ \| V(G) \| \\ge 6 $，A、B集合中必须至少有一个有3个元素。我们现在区分两种情况

