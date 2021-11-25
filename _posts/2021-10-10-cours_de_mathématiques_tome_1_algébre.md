---
layout:     post
title:      "Cours de mathématiques tome 1 Algébre by Arnaudiès chapter 1"
subtitle:   "Vocabulaire de théorie des ensembles"
thumbnail-img: ""
date:       2021-10-10 20:50
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

1.  [集合论理论词汇](#org29f2b13)
    1.  [一点逻辑](#org9ff679d)


<a id="org29f2b13"></a>

# 集合论理论词汇


<a id="org9ff679d"></a>

## 一点逻辑

学习一些数学上抽象的对象：数、向量、多项式、函数、曲线、表面等。这些对象在大体上，是一些概念的排序，表示物理对象上的符号书写。它们是间接地让我们能记住用一个符号优雅地表示我们想要的事物

这些对象上的一个断言：有些是真实的，另一些是有变形的。数学的艺术包含把明显地事实加上可能真的断言，用它们的有用性和优雅庄重地表达观点。正确地继承聚集成课程形成一系列固定想法的堆积

我们放弃了真理的概念：在任何理论的开始，我们都宣布少量的断言是先验正确的，我们称它们为所讨论理论的公理。被认为是正确的理论的其他断言（称为定理、命题、引理、SCHOLIAS或推论）是从一开始就获得的以及几个世纪以来证明其演绎价值的逻辑规则

不言而喻，不应随意选择“有用”和“有效”理论的公理系统；事实上，一方面，同一系统的公理之间存在相互依赖和兼容的问题。另一方面，观察和数学实验允许发展一个好的“公理”系统。我们不会在这里讨论这个问题

尽管在数学证明研究中为利用现代计算机设备做出了许多努力，但数学家的创造性天才似乎没有被计算机取代。只有数学家的想象力才能通过寻找具体问题来激发，其中一些问题在很长一段时间内仍未得到解答，有的现在扔未解决，例如著名的“费马大定理“或”哥德巴赫猜想“。然而，现代计算允许我们完成曾经无法进行的重复性任务；在许多仍有大量需要计算得以得出结论的问题中，它使得在“手动”手段无能为力时继续完成成为可能；例如四色问题、大素数的发现、Warning猜想的证明等

我们在此指出，计算机科学的惊人发展将逻辑学研究重新置于前台，为哥德尔及其追随者的工作注入了强有力的第二次动力

在接下来的内容中，我们不会回到源头，例如甚至不会寻求为集合论提测一连贯的公理系统。我们将满足于回忆从这样的一个公理系统中得出并在实践中普遍使用的真实断言。为避免混淆读者，我们将这些断言命名为规则

**逻辑连接，推理模式**

$ \\bullet $ 对于给定理论的每个断言（真或假），我们将联系其反面，记为（非A），也称为A的否定

规则1: 当A为假且仅当（非A）为真；A为真当且仅当（非A）为假

如果该理论包含一个既真又假的断言，则称该理论是矛盾的。我们可以看到，那么该理论的任何断言都是真和假的。这样的理论显然是无用的。每个人都相信（尽管从未被证明过）通常算术以及各种现代集合理论是不矛盾的

然而，在一个非矛盾的理论中，可能存在这样的断言A，即A（非A）都不能插入到理论内部的论证文本中。这样的断言被称为不可判定的。如果A是不可判定的，我们可以随意将A（非A）添加到理论的公理中，从而得到两个新的不矛盾的理论。在集合论的通常公理系统中，我们已经能够证明连续假设是不可判定的

如果A和B是两个断言，我们可形成一个新的断言，它们的和称为A和B，A或B称为它们的并

规则2: (A或B)为真如果A、B中至少有一个为真，且(A或非A)始终为真（即使A不可判定）

**标注 1** 可能我们知道（A 或者 B）为真而无法证明A或B。例如断言A："$ e + \\pi $ 是超越数和断言B：" $ e \\pi $是超越数"

所以可以肯定（A或B）为真，但是我们不知道是要证明A还是B

如果A和B是两个断言，则((非A) 或B)写为：$ A \\Rightarrow B $

规则2立即表面，对任意断言A，断言 $ A \\Rightarrow A $为真

规则3: 如果（非A）为真，则 $ A \\Rightarrow B $对所有B都为真

规则4: 如果A为真且 $ A \\Rightarrow B $为真，则B是真

重要的是不要将 $ A \\Rightarrow B $和B相混淆！规则4被称为三段式原则

如果A和B是两个断言，断言(非 ((非A) 或 (非B)))被称为A和B的conjunction且记为(A and B)

规则5: (A and B)为真当且仅当A和B都为真

**定义** 两个断言A，B相当当且仅当这两个意味着 $ A \\Rightarrow B, B \\Rightarrow A $都为真，我们记为 $ A \\Leftrightarrow B $

例1 $ A \\Leftrightarrow (非(非 A)) $

例2 $ A \\Rightarrow B $ 相等于 $ (非B) \\Rightarrow (非A) $

对例2，为了证明 $ A \\Rightarrow B $，我们选择 $ A \\Rightarrow B $和 $ (非B) \\Rightarrow (非A) $这两个断言中更容易的一个

以上都可以发展成真正的“命题演算”，这里不做说明。让我们仅限于指出

规则6: 如果 $ A \\Rightarrow B $ 和 $ B \\Rightarrow C $为真，则 $ A \\Rightarrow C $为真

这暗示了传递性，其可写为

$ ((A \\Rightarrow B) \\; and \\; (B \\Rightarrow C)) \\Rightarrow (A \\Rightarrow C) $

规则7: $ A_ {1}, A_ {2}, \\ldots, A_ {n} $和B为断言；如果 $ (A_ {1} \\lor A_ {2} \\lor \\ldots \\lor A_ {n}), (A_ {1} \\Rightarrow B), (A_ {2} \\Rightarrow B), \\ldots, (A_ {n} \\Rightarrow B) $ 为真，则B为真

规则8: 设A是一个理论的断言；将公理(not A)添加到所考虑的理论中，并假设在该理论中找到断言B使得 $ (not A) \\Rightarrow B, (not A) \\Rightarrow (not B) $在这个新理论中为真；那么A在起始理论中为真

这就是“荒诞推理”的原理。在实践中，我们说我们有，从（非A)，最终得到了一个矛盾

**例4** 假设B是起始理论中的真断言，并且 $ (非A) \\Rightarrow (非B) $。所以 $ B \\Rightarrow A $为真，因此A为真因为B是真

很多时候，荒谬的推理采用了例4中的描述形式。但并不总是如此简单，如这个例子所示

**例5** 要证明断言A: 素数集 $ mathfrak{P} $是无限的

断言（非A）：集合 $ mathfrak{P} $是有限的

让我们把(非A)添加到作为算术基础的皮亚诺公理中。我们知道集合 $ \\mathfrak{P} $非空（例如2是素数）。然后让N成为 $ \\mathfrak{P} $中最大的元素（N存在因为(非A)为真，且我们在算术中证明任意非空有限集都有一个最大的元素）。数字 $ 2 \\times 3 \\times 4 \\times \\cdots \\times N + 1 $缩写成 $ N! + 1 $不能被任意 $ \\le N $的素数整除。令q为N！+1，则 $ q \\in \\mathfrak{P}, q > N $。所以在新理论中，断言B: N是 $ \\mathfrak{P} $中最大的元素既假又真。则根据规则8A为真
