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

我们说a和b congruent modulo m（或mod m）如果a和b除m时有相同的余数，或，一个相当的表述，a - b能被m整除。我们写 $ a \\equiv b (mod \\, m) $。两个数不是congruent被称为incongruent，我们写为 $ a \\not\\equiv b (mod \\, m) $

我们现在可表达整除

$ \\begin{equation} a \\equiv 0 (mod \\, m) \\end{equation} $

这跟m \| a等价

我们通常需要modulus为大于1的整数，但定义对所有整数都有效。负数可被忽略，因为congruence modulus m和modulus -m是相同的

modulo 0跟相等等价，因为 $ a \\equiv b (mod 0) $表示a = b，且它不需要引入一个更复杂的记号

modulo 1也用处不大，因为这种情况下所有的整数都是congruent

congruence有跟相等相似的属性使它非常有用。很明显congruence是自反的、对称的和可传递关系，例如，对所有整数a, b, c和m，有如下属性：

(a) $ a \\equiv a (mod \\, m) $

(b) 如果 $ a \\equiv b (mod \\, m) $，则 $ b \\equiv a (mod \\, m) $

(c) 如果 $ a \\equiv b (mod \\, m) $且 $ b \\equiv c (mod \\, m) $，则 $ a \\equiv c (mod \\, m) $

如果 $ a \\equiv b (mod \\, m) $，则有

(d) $ a + c \\equiv b + c (mod \\, m) $

(e) $ a - c \\equiv b - c (mod \\, m) $

(f) $ ac \\equiv bc (mod \\, m) $

(g) 如果 $ a \\equiv b (mod \\, m) $ 则 $ ac \\equiv bc (mod \\, mc) $

属性(g)反过来也成立

(h) 如果 $ ac \\equiv bc (mod \\, mc) $ 且 $ c \\neq 0 $，则 $ a \\equiv b (mod \\, m) $

(i) 如果 $ ac \\equiv bc (mod \\, m) $ 且 $ (c, m) = 1 $，则 $ a \\equiv b (mod \\, m) $

如果 $ a \\equiv b (mod \\, m) $ 且 $ c \\equiv d (mod \\, m) $，则

(j) $ a + c \\equiv b + d (mod \\, m) $

(k) $ a - c \\equiv b - d (mod \\, m) $

(l) $ ac \\equiv bd (mod \\, m) $

(m) 如果 $ a \\equiv b (mod \\, m) $且n是一个正整数，则 $ a^{n} \\equiv b^{n} (mod \\, m) $

(n) 如果f(x)是一个整系数的多项式，且 $ a \\equiv b (mod \\, m) $，则

$ \\begin{equation} f(a) \\equiv f(b) \\end{equation} $

(o) 如果 $ a \\equiv b (mod \\, mm') $且 $ m' \\neq 0 $，则 $ a \\equiv b (mod \\, m) $

**定理** 对任意给定的数N，存在一个素数至少比其前一个素数大N，且至少比下一个素数小N

**Dirichlet定理** 如果a和m为整数，且互质，则有无穷多个正整数k使得a + km是素数

我们注意到定理的假设是必要的，有无穷多个素数在序列中（为什么？）

我们将基于理想的证明，我们选择2N个素数，$ p_ {1}, p_ {2}, \\ldots, p_ {2N} $，且我们找一个素数p使得对 $ i = 1, 2, \\ldots, N $，p - i被 $ p_ {i} $整除，且 $ p + i $被 $ p_ {N+i} $整除

我们首先尝试找到这样一个数p，忽略它是素数的要求。该数是如下系统的解决方案：

$ x \\equiv j \\, (mod \\, p_ {j}), \\qquad x \\equiv -j \\, (mod \\, p_ {N+j}), \\qquad j = 1, 2, \\ldots, N $

因为模数互质，我们知道系统有一个解决方案，一个留数类

$ x \\equiv x_ {0} \\, (mod \\, p_ {1}p_ {2} \\cdots p_ {2N}) $

所以解决方案为如下形式的数

$ x_ {0} + kp_ {1}p_ {2}\\cdots p_ {2N} $

k是任意整数。这是一个算术进展，通过Dirichlet定理它包含无穷多个素数使得 $ (x_ {0}, p_ {1}p_ {2} \\cdots p_ {2N}) = 1 $。这个条件是立即的，因为如果最大公因子大于1，它会被 $ p_ {i} $中的一个整除。这意味着一方面 $ x_ {0} $被 $ p_ {i} $整除，另一方面，两个congruence之一对 $ p_ {i} $成立，取决于 $ i \\le N $ 还是 $ i > N $。这两种情况都意味着 $ p_ {i} \| j $，这是不可能的。因为 $ p_ {i} > j $

因此有无限多个形如 $ x_ {0} + kp_ {1}p_ {2}\\cdots p_ {2N} $的素数，k是一个正整数。对这样形式的p，p + i不是素数，因为它被 $ p_ {i} $整除，相似地，p - i不是素数因为它被 $ p_ {N+i} $整除。且从 $ p_ {1} = 2 $有

$ p - i = x_ {0} + kp_ {1}p_ {2} \\cdots p_ {2N} - i > 2p_ {2N} - i > p_ {2N} + 2N - i > p_ {i} $

**定理（Wilson定理）** 如果p是一个素数，则

$ (p - 1)! + 1 \\equiv 0 \\, (mod \\, p) $

**定理** 对所有形如4k + 1的素数p，存在一个整数c，使得

$ c^{2} + 1 \\equiv 0 \\, (mod \\, p) $

使用如下

$ p - j \\equiv -j \\, (mod \\, p), \\qquad j = \\frac{p-1}{2}, \\frac{p-1}{2} - 1, \\ldots, 2, 1 $

Wilson定理可被写为如下

$ (-1)^{\\frac{p-1}{2}} ((\\frac{p-1}{2})!)^{2} + 1 \\equiv 0 \\, (mod \\, p) $

如果p为形如4k+1的素数，则有c = ((p-1) / 2)! 满足定理要求

**定理** 如果p是一个奇素数且 $ k \| p - 1 $，则

$ x^{k} - 1 \\equiv 0 \\quad (mod \\quad p) $

有k个根

**定理** 如果一个数c有序n modulo m，则数 $ 1, c, c^{2}, \\cdots, c^{n-1} $配对incongruent modulo m。如果

$ c^{u} \\equiv c^{\\upsilon} \\quad (mod \\quad m), \\qquad \\text{则} u \\equiv \\upsilon \\quad (mod \\quad n) $

特别地，当 $ \\upsilon = 0 $，例如，$ c^{u} \\equiv 1 \\quad (mod \\quad m), \\text{则} n \| u $

根据定理，从欧拉 - 费马定理有 $ n \| \\varphi(m) $

不失一般性，我们可假设 $ u \\ge \\upsilon $。则 $ c^{u - \\upsilon} \\equiv 1 \\quad (mod \\quad m) $。用n除以 $ u - \\upsilon $得

$ u - \\upsilon = nq + s $

q是一个整数，$ 0 \\le s < n $。基于此我们有

$ c^{u - \\upsilon} = (c^{n})^{q}c^{s} \\equiv c^{s} \\equiv 1 \\quad (mod \\quad m) $

在c的正积分指数上，第n个是第一个1 modulo m，则s = 0，因此 $ n \| u - \\upsilon $

某个g的序是 $ \\varphi(m) $，如果这样的g存在，它扮演了一个重要的角色。$ g, g^{2}, \\cdots, g^{\\varphi(m)} $，形成一个modulo m的缩减余数系统。这些有序 $ \\varphi(m) $的数被称为modulo m的congruence的原始根，或原始根。如果对一个给定的modulu m存在一个原始根g，则对每个与m互质的c，我们称最小的非负指数k

$ c \\equiv g^{k} \\; (mod \\; m) $

为modulo m的c的索引

我们将显示对每个素数p，存在一个modulo p的原始根

**定理** 序为n modulo 一个素数p的元素个数是 $ \\varphi(n) $如果 $ n \| p - 1 $。否则，它是0。基于此，有 $ \\varphi(p - 1) $个modulo p的原始根

如果modulus可被两个奇素数整除或者modulus被4和大于4的素数整除则没有原始根。这样有原始根只在modulus为2，4，一个奇素数平方，或一个奇素数平方的两倍时才有

**定理** 两个数的乘积是一个quadratic residue如果这两个都是quadratic residue或两个都是nonresidue；乘积是一个quadratic nonnresidue如果其中一个是quadrati residue另一个是nonresidue

我们写 $ ( \\frac{c}{p} ) $称之为Legendre符号。如果c是一个quadratic residue modulo p则值为1，c是一个quadratic nonnresidue则为-1，如果c能被p整除则为0

**定理（欧拉引理）** 如果p是一个奇素数，则对每个c

$ ( \\frac{c}{p} ) \\equiv c^{(p-1) / 2} \\; (mod \\; p) $

$ c \\equiv 0 \\; (mod \\; p) $的情况可忽略。在其他情况中，定理说c要么是一个quadratic residue要么是一个nonresidue，取决于c的(p - 1) / 2次方模p是否为1或-1

我们对两边去平方来利用费马定理

我们呈现一个不使用Wilson定理或费马定理的证明，且我们也给出了这两个定理的新的证明。设c为不被p整除的任意数。记 $ x_ {i}, i = 1, 2, \\ldots, p - 1 $为最小的正整数使得

$ ix_ {i} \\equiv c \\; (mod \\; p) $

从之前的定理我们知道这些解在不同的residue class里，我们可看到如果 $ x_ {i} = j $，则 $ ij \\equiv c \\; (mod \\; p) $，则 $ x_ {j} = i $

如果c是一个quadratic nonresidue，这样没有y满足

$ y^{2} \\equiv c \\; (mod \\; p) $

则每个congruence出现两次，如果我们每个只取一个且把它们相乘，左边我们获得(p - 1)!。这样，如果c是一个quadratic nonresidue，则

$ (p - 1)! \\equiv c^{(p - 1) / 2} \\; (mod \\; p) $

如果y是一个解决方案，则p - y也是一个解决方案。选择y从0到p，则p - y也是从0到p。则

$ y(p - y) \\equiv -c \\; (mod \\; p) $

因每个congruence出现两次，我们取一次并把它们相乘，如果c是一个quadratic residue，则

$ (p - 1)! \\equiv -c^{(p-1) / 2} \\; (mod \\; p) $

我们知道1对所有p都是quatratic residue，则

$ (p - 1)! \\equiv -1 \\; (mod \\; p) $

这是Wilson定理。同样也不难得出欧拉引理

利用欧拉引理，我们现在有一个方法来确定一个数对一个素数模是否是一个quadratic residue。因为我们只需要residue模p的次方，这个方法非常有用如果数不大但不太容易计算的时候。让我们确定是否30是模103的一个quadratic residue。通过欧拉引理，我们需要计算 $ 30^{51} $模103

$ 30^{2} = 900 \\equiv -27, \\qquad 30^{32} \\equiv 576 \\equiv -42 $

$ 30^{4} \\equiv (-27)^{2} = 729 \\equiv 8, \\qquad 30^{48} = 30^{16 + 32} \\equiv -24(-42) = 1008 \\equiv -22 $

$ 30^{8} \\equiv 64 \\equiv -39, \\qquad 30^{50} \\equiv -27(-22) \\equiv 594 \\equiv -24 $

$ 30^{16} \\equiv 1521 \\equiv -24, \\qquad 30^{51} \\equiv -720 \\equiv 1 $

$ x^{2} \\equiv 30 \\; (mod \\; 103) $因此有一个解决方案

当c = -1时欧拉引理提供了一个一般化结果。如果指数是偶数，例如，p是4k + 1的形式，则结果是1，如果指数是奇数，例如，p是4k + 3的形式，则结果是-1.这给了我们一般化结果，-1是所有形如4k + 1素数的quadratic residue和形如4k + 3的素数的quadratic nonresidue

回忆欧拉-费马定理的第一个证明，我们可尝试简化确定是否一个数c，不被p整除，是一个quadratic residue。考虑如下数的residue的最小绝对值

$ c, 2c, \\ldots, ((p-1)/2)c $

有如下congruences:

$ ic \\equiv e_ {i}b_ {i} \\; (mod \\; p) \\quad (i = 1, 2, \\ldots, (p-1)/2) $

$ e_ {i} $为1或-1且 $ 1 \\le b_ {i} \\le (p-1)/2 $

我们将显示b中数都不相同。明显没有两个是相同且有相同的符号，因为我们乘以半个缩减residue系统通过一个跟素数p互质的数。我们需要显示，没有i，j使得

$ e_ {i}b_ {i} + e_ {j}b_ {j} = 0 $

这意味着

$ ic + jc \\equiv 0 \\; (mod \\; p), \\text{因此} p \| (i+j)c $

这是不可能的，因为我们假设c不能被p整除，且i和j有 $ 1 \\le i + j \\le (p - 1) $。则

$ b_ {1}b_ {2} \\ldots b_ {(p-1)/2} = ((p-1)/2)! $

把之前的式子相乘，设m为congruences数，则

$ ((p-1)/2)!c^{(p-1)/2} \\equiv (-1)^{m} ((p-1)/2)! \\; (mod \\; p) $

没有因子能被p整除，我们可简化，通过欧拉引理，我们可写为

$ ( \\frac{c}{p} ) \\equiv (-1)^{m} \\; (mod \\; p) $

因为两边的不同可为2, 0, -2，模至少是3，则两边必须相等。这个重要结果为Gauss引理

**定理 22（Gauss引理）** 设p为一个奇素数且c为一个不被p整除的整数。考虑 $ c, 2c, \\ldots, ((p-1)/2)c $的最小绝对值的residue是负的。则c是一个residue或nonresidue根据是否该数是偶数还是奇数

用这个定理，对任意数我们可确定对哪个素数是一个quadratic residue和对哪个素数它是一个nonresidue

对2的情况，例如，我们需要确定多少个数 $ 2,4, \\ldots, p-1 $，有一个负数作为它们residue模p的绝对值。即我们只需要统计p/2和p之间偶整数的个数，或用另一种方式表达，(p/4, p/2)之间整数的个数

它写p为形式8k + r，r是1，3，5或7。我们然后需要确定是否整数的个数在(2k + r / 4, 4k + r / 2)间隔是偶数还是奇数。末端不是整数，且我们可提交长度为2k的子间隔(2k + r/4, 4k + r/4)，因为有2k，例如，一个偶数，在这个间隔的整数，且在(4k + r/4, 4k + r/2)中

我们也注意到在(r/4, r/2)中有相同的整数。对每个4个可能的r值，对应在这个间隔中整数的个数是0,1,1和2。这样2是第一个和最后一个的quadratic residue，其他两个是一个nonresidue。我们可形式化如下：2是形如 $ 8k \\pm 1 $的素数的quadratic residue，对形如 $ 8k \\pm 3 $的素数是一个nonresidue。注意这只依赖p模8的residue类
