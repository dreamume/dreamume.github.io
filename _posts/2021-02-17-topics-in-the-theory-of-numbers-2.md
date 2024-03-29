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

作为第二个例子让我们确定对哪个素数数字5是一个quadratic residue。为此，我们需要确定 $ 5, 10, \\ldots, 5(p - 1) / 2 $，哪个数有一个负数作为模p的residue的最小绝对值。所有这些数小于 $ 5p / 2 $，且我们需要统计整数除以5的间隔里个数

$ (p/2, p) $ 和 $ (3p/2, 2p) $

这和统计如下间隔的个数相同

$ (p/10, p/5) $和 $ (3p/10, 2p/5) $

p = 5时，当然，是忽略的，且因此这些端点不是整数

把p写成20k + r的形式是有帮助的。因为p是素数，r现在可用值1, 3, 7, 9, 11, 13, 17或19。对这些数我们需要确定是否每个间隔的整数个数

$ (2k+r/10, 4k+r/5) $ 和 $ (6k+3r/10, 8k + 2r/5) $

是奇数还是偶数。这子间隔

$ (2k + r/10, 4k + r/10) $ 和 $ (6k + 3r/10, 8k + 3r/10) $

可被忽略，因为这些里的整数是偶数个，考虑以下部分足够了

$ (4k + r/10, 4k + r/5) $和 $ (8k+3r/10, 8k+2r/5) $

或如下间隔

$ (r/10, r/5) $ 和 $ (3r/10, 2r/ 5) $

以上间隔的整数个数选择r为0,1,1,2,2,3,3,4。我们可形式化我们的结果如下：5对素数p是一个quadratic residue，p除以20有余数 $ \\pm 1 $或 $ \\pm 9 $；余 $ \\pm 3 $或 $ \\pm 7 $则为nonresidue。更简单地，我们形式化如下：对形如 $ 10k \\pm 1 $的素数5是一个quadratic residue，形如 $ 10k \\pm 3 $则为一个nonresidue

作为第3个例子，我们检查当-3是一个quadratic residue，例如，我们确定对某个素数p有偶数个数在 $ -3, -6, \\ldots, -3(p-1)/2 $除以p的余数的最小绝对值是负数。排除素数p = 3。我们需要统计乘以3在 $ -3p / 2 $和-p之间的数和 $ -p/2 $到0之间，0不统计

从0映射数，我们有间隔 $ (0, p/2) $和 $ (p, 3p/2) $，包含乘以3的相同数目。这些数是 $ [p/6] + [p/2] - [p/3] $。p为12k + r的形式，r为1, 5, 7, 或11，p是素数。这四个情况的值的和为

$ \\begin{array}{cc} 2k + 6k - 4k = 4; & 2k + 6k + 2 - 4k - 1 = 4k + 1; \\\\ 2k + 1 + 6k + 3 - 4k - 2 = 4k + 2; & 2k + 1 + 6k + 5 - 4k - 3 = 4k + 3 \\end{array} $

对 12k + 1和 12k + 7的素数-3是一个quadratic residue，或对6k + 1的素数；对其他的，例如，6k - 1的素数是一个nonresidue

**引理** -3对形如6k + 1的素数为一个quadratic residue，对6p - 1的素数是一个nonresidue

明显地对任意c我们可用相似的方法分割素数模c是一个quadratic residue。对不同值的c，我们看到是否它模一个素数p是一个quadratic residue只依赖p模4c的residue。这不是偶然。我们将限制c为正数的情况

我们需要确定多少乘以c落入区间 $ ((2t-1)p/2, tp) $，t是一个正整数不大于c/2

末点不能被c乘，因为我们只考虑不能被c除的素数，且开始点不是一个整数因为t < c

问题是多少个整数在区间中

$ \\left( \\frac{(2t-1)p}{2c}, \\frac{tp}{c} \\right) $

适合把p写成4ck + r，k是一个整数且 $ 1 \\le r \\le 4c $，且我们对落入如下区间的整数个数感兴趣

$ \\left( 2(2t-1)k + \\frac{(2t-1)r}{2c}, 4tk + \\frac{tr}{c} \\right) $

我们丢弃间隔

$ \\left( 2(2t-1)k + \\frac{(2t-1)r}{2c}, 4tk + \\frac{(2t-1)r}{c} \\right) $

因为其包含偶数个整数，剩下的间隔

$ \\left( 4tk + \\frac{(2t-1)r}{2c}, 4tk + \\frac{tr}{c} \\right) $

包含和如下间隔的整数相同

$ \\left( \\frac{(2t-1)r}{2c}, \\frac{tr}{c} \\right) $

且这只依赖r，不依赖k，这是我们想要显示的

Legendre符号的乘法属性给了我们一个方法来写每个Legendre符号作为形如 $ (\\frac{p}{q}) $的项的乘积，q是正奇素数，p是一个正素数或-1。我们已经涉猎了 $ (\\frac{2}{q}) $ 和 $ (\\frac{-1}{q}) $的情况，这样只剩下确定对任意奇素数p和q的 $ ((\\frac{p}{q})) $

欧拉确定对许多不同素数moduli的quadratic residue，且他注意到两件事：首先，正数c模一个素数p的quadratic特征只依赖p模4c的residue；第二，residue r和4c -r的素数给出确定c的quadratic特征的相同结果，因为我们在2和5的例子里看到了

这些事实的第一个的证明可用高斯引理。欧拉，当然，在他的时期还没有，没有这个则他不能成功证明他的结论。我们将显示第二个观察也可从高斯引理得到

定义quadratic特征，LEGENDRE是第一个人描述reciprocity定理。如果p和q是不同的素数，则lengendre符号 $ (\\frac{p}{q}) $和 $ (\\frac{q}{p}) $有相同的值，除了p和q都是4k+3形式的情况，这时一个为1另一个为-1

高斯独立完成定理且在19岁时给出了一个使用归纳法的相当复杂的证明。在他的一生他经常回看这个定理并给出总共7个证明，使用不同的方法

在第一个欧拉观察的证明我们已经看到确定是否一个数c是一个quadratic residue模形如4ck + r的素数只依赖于是否 $ ((2t-1)r/2c, tr/c) $的间隔中整数个数是偶数还是奇数。对形如4ck - r的素数，我们需要考虑对应间隔 $ r^{\\prime} = 4c -r $

如果两个quadratic 特征相同，则意味着在第一个情况和第二个情况里整数个数的和为偶数。我们将显示这对两个系统对应相同值t的间隔对也是真的。用r替代 $ r^{\\prime} $，我们获得间隔

$ \\left(4t-2 - \\frac{(2t-1)r}{2c}, 4t - \\frac{tr}{c} \\right) $

通过点2t映射间隔且镜像象，我们获得间隔

$ \\left(\\frac{tr}{c}, 2 + \\frac{(2t-1)r}{2c} \\right) $

其包含和之前相同的整数个数

间隔和源是长度为2的间隔，且端点不是整数；因此间隔包含2个整数，且我们证明了欧拉的第二个观察

**定理** 对一个正数c，模一个素数是否为quadratic residue只依赖4c模该素数的residue；更进一步，同residue r和4c - r的那些素数，或更简单地，同residue r和-r的那些素数

我们现在使用该定理和Legendre符号的已知属性证明reciprocity定理。设p和q为两个奇素数，让我们先看一个素数为4k + 1，另一个为4k + 3的情况。我们可写p + q = 4c，c是一个正整数，且我们有

$ (\\frac{p}{q}) = (\\frac{4c - q}{q}) = (\\frac{4c}{q}) = (\\frac{4}{q})(\\frac{c}{q}) = (\\frac{c}{q}) $

因为Legendre符号是对更小的数周期的，是可乘的，当上面的数是一个平方时是1

相同的方法我们可显示 $ (\\frac{q}{p}) = (\\frac{c}{p}) $。通过假设，4c模p和q的residue是相反的，通过上面定理的第二部分我们有

$ (\\frac{p}{q}) = (\\frac{c}{q}) = (\\frac{c}{p}) = (\\frac{q}{p}) $

如果p和q模4有相同的余数，则称更大的p为p - q = 4c，c是一个正整数。我们可然后写

$ (\\frac{p}{q}) = (\\frac{4c + q}{q}) = (\\frac{4c}{q}) = (\\frac{4}{q}) (\\frac{c}{q}) = (\\frac{c}{q}) $

且

$ (\\frac{q}{p}) = (\\frac{p - 4c}{q}) = (\\frac{-4c}{p}) = (\\frac{-1}{p}) (\\frac{4}{p}) (\\frac{c}{p}) = (\\frac{-1}{p}) (\\frac{c}{p}) $

通过以下定理的第二部分我们有 $ (\\frac{c}{p}) = (\\frac{c}{q}) $且 $ (\\frac{p}{q}) = (\\frac{-1}{p}) (\\frac{q}{p}) $。如果p和q模4有residue 1，则我们有 $ (\\frac{p}{q}) = (\\frac{q}{p}) $。否则，如果有residue 3，我们有 $ (\\frac{p}{q}) = - (\\frac{q}{p}) $。我们可用如下公式表达我们的结果

**Reciprocity定理** 如果p和q是不同的奇素数，则

$ (\\frac{p}{q}) (\\frac{q}{p}) = (-1)^{\\frac{1}{2}(p-1) \\cdot \\frac{1}{2}(q-1)} $

指数这里是奇仅当两个素数都是4k + 3的形式。这种情况下Legendre符号之一是1且另一个是-1。其他所有情况两个Legendre符号要么都是1或要么都是-1

**补充定理** 对一个正奇素数

$ (\\frac{-1}{p}) = (-1)^{(p-1)/2}, \\qquad (\\frac{2}{p}) = (-1)^{(p^{2}-1)/8} $

对第二个式子，该公式表达了我们的结果。指数是

$ \\frac{1}{2} \\frac{(p-1)}{2} \\frac{(p+1)}{2} $

且括号里的数是连续的偶数，因此只有一个能被4整除。指数因此甚至该因子也能被8整除，例如，当p为 $ 8k \\pm 1 $时

作为一个应用的结果，让我们确定是否congruence

$ x^{2} \\equiv 611 \\; (mod \\; 1009) $

有解决方案，即让我们确定 $ (\\frac{611}{1009}) $（这里 $ 1009 = 16 \\cdot 63 + 1 $是一个素数且 $ 611 = 13 \\cdot 47 $）：

$ \\begin{aligned} (\\frac{611}{1009}) &= (\\frac{13}{1009}) (\\frac{47}{1009}) = (\\frac{1009}{13}) (\\frac{1009}{47}) = (\\frac{-5}{13})(\\frac{22}{47}) \\\\ &= (\\frac{-1}{13}) (\\frac{5}{13}) (\\frac{2}{47}) (\\frac{11}{47}) = +1 \\cdot (\\frac{13}{5}) (+1) (- (\\frac{47}{11})) \\\\ &= - (\\frac{3}{5}) (\\frac{3}{11}) = - (\\frac{5}{3}) (- (\\frac{11}{3})) = (\\frac{2}{3}) (\\frac{2}{3}) = 1 \\end{aligned} $

这个congruence因此有解（它的解是653和356）
