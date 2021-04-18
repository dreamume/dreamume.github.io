---
layout:     post
title:      "Fourier analysis an introduction(Chapter 1) by Stein"
subtitle:   "The genesis of fourier analysis"
thumbnail-img: ""
date:       2021-04-18 19:00
author:     "dreamume"
tags: 		[analysis]
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

1.  [The Genesis of Fourier Analysis](#org8842656)
    1.  [The vibrating string](#org8951148)
        1.  [波浪等式的发展](#org051013c)


<a id="org8842656"></a>

# The Genesis of Fourier Analysis


<a id="org8951148"></a>

## The vibrating string

![img](../img/simple_harmonic_oscillator.png)

设y(t)记为在时刻t物体的偏移。我们假设弹簧是理想的，即它满足Hooke法则：运用在弹簧的回复力为F = -ky(t)。这里k > 0是给定的物理量称为弹簧常量。应用牛顿定律（$ 力 = 重量 \\times 加速度 $），我们得到

$ -ky(t) = my^{\\prime \\prime} (t) $

我们使用记号 $ y^{\\prime \\prime} $记为y对t的二次微分。用 $ c = \\sqrt{\\frac{k}{m}} $，该微分等式变为

$ \\begin{equation} y^{\\prime \\prime}(t) + c^{2}y(t) = 0 \\end{equation} $

该等式一般解给定为

$ y(t) = a \\cos{ct} + b \\sin{ct} $

a, b都是常量

在上述表达式中，c是给定常量，但a和b可为任意实数。为了确定等式的特定解，我们必须引入两个初始条件。例如，如果我们给定y(0)和 $ y^{\\prime} (0) $，即初始位置和物体速度，则该物理问题的解是唯一的且给定为

$ y(t) = y(0) \\cos(ct) + \\frac{y^{\\prime} (0)}{c} \\sin{ct} $

我们可容易检查存在常量A > 0和 $ \\varphi \\in \\mathbb{R} $使得

$ a \\cos(ct) + b \\sin(ct) = A \\cos{(ct - \\varphi)} $

因为以上给出了物理解释，我们称 $ A = \\sqrt{a^{2} + b^{2}} $为运动的振幅，c为它的自然频率，$ \\varphi $为它的相，且 $ \\frac{2 \\pi}{c} $为运动的周期

![img](../img/example_of_spring_motion.png)

函数 $ A \\cos{(ct - \\varphi)} $典型的图形如上图

我们做两个观察。首先是最基本的震荡系统的数学描述，名为简单调和运动，包括最基本的三角函数 $ \\cos{t}, \\sin{t} $。它很重要，回忆这些函数和复数的关系，如欧拉公式 $ e^{it} = \\cos{t} + i \\sin{t} $。第二个观察是简单的调和运动确定为一个时间函数和两个初始条件，一个确定位置，另一个是速度（时刻t = 0）。该属性在更一般化震荡系统中共享，如下所示

震动弹簧可被看作为一维波浪运动。我们想要描述两种运动使得它们为简单图形表示形式

-   首先，我们考虑波浪。像波浪的运动描述为图形y = u(x, t)，如下图所示
    
    ![img](../img/example_of_standing_wave.png)
    
    即有一个初始配置 $ y == \\varphi(x) $表示时刻t = 0时的波浪，且一个振幅因子 $ \\psi(t) $，依赖于t，所以y = u(x, t)有
    
    $ u(x, t) = \\varphi(x) \\psi (t) $

-   第二个类型的波浪运动通常被观察为旅行波浪。它的描述特别简单：
    
    有一个初始配置F(x)当t = 0时u(x, t)等于F(x)。随着t变化，该配置向右偏移ct单位，c是一个正常量
    
    $ u(x, t) = F(x - ct) $
    
    图形如下：
    
    ![img](../img/traveling_wave.png)
    
    因为随时间t以速度c移动，该常量表示为波浪的速度。函数F(x - ct)向右移动的一维旅行波浪。相似的，u(x, t) = F(x + ct)为向左移动的一维旅行波浪


<a id="org051013c"></a>

### 波浪等式的发展

想象一个弹簧放在(x, y)平面上，沿着x轴在x = 0和x = L之间伸展。它的位置y = u(x, t)是x和t的一个函数，目标是得到一个微分等式

为这个目标，我们考虑弹簧被分割为N块物体（我们认为是个体颗粒）统一分布在x轴，这样第n个颗粒它的x坐标在 $ x_ {n} = \\frac{nL}{N} $。我们将因此想象弹簧为N个颗粒的复数系统，每个只在垂直方向震荡；然而，不像我们之前考虑的简单调和震荡，每个颗粒有它的震荡通过弹簧张力连接到它的邻居

![img](../img/vibrating_string_as_discrete_system_masses.png)

我们然后设置 $ y_ {n}(t) = u(x_ {n}, t) $，且注意 $ x_ {n+1} - x_ {n} = h, h = \\frac{L}{N} $。如果我们假设弹簧有常量密度 $ \\rho > 0 $，每个颗粒有质量 $ \\rho h $。通过牛顿定律，$ \\rho h y^{\\prime \\prime}_ {n}(t) $等于作用在作用在第n个颗粒上的力。我们现在使用简单假设该力影响两个临近的颗粒，如上图所示x坐标的 $ x_ {n-1}, x_ {n+1} $。我们进一步假设来自于第n个颗粒右边的该力是 $ \\frac{y_ {n+1} - y_ {n}}{h} $的部分，h是 $ x_ {n+1}, x_ {n} $之间的距离；因为我们可写该张量为

$ ( \\frac{\\tau}{h} ) (y_ {n+1} - y_ {n}) $

$ \\tau > 0 $是一个常量等于弹簧张力的常数。有一个相似的力来自于左边，为

$ ( \\frac{\\tau}{h} ) (y_ {n-1} - y_ {n}) $

添加这些力给我们想要的在震荡 $ y_ {n}(t) $的关系，名为

$ \\begin{equation} \\rho h y^{\\prime \\prime}_ {n}(t) = \\frac{\\tau}{h} \\{ y_ {n+1}(t) + y_ {n-1}(t) - 2y_ {n}(t) \\} \\end{equation} $

一方面，选择上面的记号，我们看到

$ y_ {n+1} (t) + y_ {n-1}(t) - 2y_ {n}(t) = u(x_ {n} + h, t) + u(x_ {n} - h, t) - 2u(x_ {n}, t) $

另一方面，对任意函数F(x)，我们有

$ \\frac{F(x+h) + F(x - h) - 2F(x)}{h^{2}} \\to F^{\\prime \\prime}(x) \\qquad h \\to 0 $

这样我们可概括，在除了h且让h趋于0，有

$ \\rho \\frac{\\partial^{2} u}{\\partial t^{2}} = \\tau \\frac{\\partial^{2} u}{\\partial x^{2}} $

或

$ \\frac{1}{c^{2}} \\frac{\\partial^{2} u}{\\partial t^{2}} = \\frac{\\partial^{2} u}{\\partial x^{2}}, c = \\sqrt{\\frac{\\tau}{\\rho}} $

这个关系被称为一维波浪等式，或更简单的波浪等式。系数c > 0被称为运动的速度

