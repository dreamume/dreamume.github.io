---
layout:     post
title:      "JPEG2000 Image Compression Foundamentals, Standards and Practice(Chapter 1)"
subtitle:   "Image Compression OverView"
thumbnail-img: ""
date:       2021-01-16 02:38
author:     "dreamume"
tags: 		[image]
category:   it
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

1.  [IMAGE COMPRESSION OVERVIEW](#orgb938244)
    1.  [Elementary Concepts](#orgba908b6)
        1.  [Lossless and Lossy Compression](#orgd7eab88)
        2.  [Gamma Correction](#orgfb89b50)


<a id="orgb938244"></a>

# IMAGE COMPRESSION OVERVIEW


<a id="orgba908b6"></a>

## Elementary Concepts


<a id="orgd7eab88"></a>

### Lossless and Lossy Compression

最常见的修改度量方法是MSE(Mean Squared Error)，定义为

$ \\begin{equation} MSE \\stackrel{\\Delta}{=} \\frac{1}{N_ {1}N_ {2}} \\sum_ {n_ {1} = 0}^{N_ {1} - 1} \\sum_ {n_ {2} = 0}^{N_ {2} - 1} \\left(x[n_ {1}, n_ {2}] - \\hat{x}[n_ {1}, n_ {2}]\\right)^{2} \\end{equation} $

对图像压缩，MSE最常见被作为倒数度量引用，PSNR(Peak Signal to Noise Ratio)，定义为

$ \\begin{equation} PSNR \\stackrel{\\Delta}{=} 10 \\log_ {10} \\frac{(2^{B} - 1)^{2}}{MSE} \\end{equation} $

PSNR用dB作为单位。好的重建图像典型地有PSNR值30dB或更多

MSE作为图像修改度量的流行部分源于其计算简便，部分由于线性优化问题的可追溯性包括方差度量


<a id="orgfb89b50"></a>

### Gamma Correction

显示设备比如电视和计算机显示器是高非线性的，传递到电子粉末的动力大约为 $ v^{\\gamma} $，v是应用到电子枪的控制电压，$ \\gamma $的值范围在1.8到2.8之间。

更精确地说，设 $ x_ {lin} [n_ {1}, n_ {2} ] $记为正规化场景下图像位置 $ [n_ {1}, n_ {2}] $的亮度。正规化即使 $ x_ {lin} = 0 $对应无光，$ x_ {lin} = 1 $对应场景中可计数的最强烈级别。所谓的"gamma“函数，参数为$ \\gamma和\\beta $， $ x'[n_ {1}, n_ {2} ] $为正规化后图像采样值，范围从0到1，

$ \\begin{equation} x'[n_ {1}, n_ {2}] = \\left\\{ \\begin{array}{ll} gx_ {lin}[n_ {1}, n_ {2}] & \\text{ if } 0 \\le x_ {lin}[n_ {1}, n_ {2}] \\le \\epsilon \\\\ (1 + \\beta) (x_ {lin}[n_ {1}, n_ {2}])^{\\frac{1}{\\gamma}} - \\beta & \\text{ if } \\epsilon \\le x_ {lin}[n_ {1}, n_ {2}] \\le 1 \\end{array} \\right. \\end{equation} $

$ \\epsilon $和g定义为

$ \\begin{equation} \\epsilon = \\left(\\frac{\\beta}{(1+ \\beta)(1 - \\frac{1}{\\gamma})}\\right)^{\\gamma} \\text{ 和 } g = \\frac{\\beta}{\\epsilon (\\gamma - 1)} \\end{equation} $

这些定义确保gamma函数在断点 $ x_ {lin} = \\epsilon $连续可导

一个呈现彩色图像的合并标准为sRGB（标准RGB）颜色空间，其小心地定义通过上述描述的gamma函数及参数 $ \\gamma = 2.4 和 \\beta = 0.055 $使线性的红绿蓝映射到非线性RGB采样值。该函数描述在下图：

![img](../img/srgb_gamma_function.png)

需要注意大多数图像在实际中被gamma校正，在压缩时会影响图像采样值引入的误差的解释。忽略gamma函数中小的线性段（或假设 $ \\beta = 0 $），这样 $ x_ {lin} = (x')^{\\gamma} $，我们看到一个小误差，$ dx' $，gamma校正值对应场景光误差，$ dx_ {lin} $

$ \\begin{equation} \\begin{aligned} dx_ {lin} &= \\gamma(x')^{\\gamma - 1} dx' \\\\ &= \\gamma (x_ {lin})^{1 - \\frac{1}{\\gamma}} dx' \\end{aligned} \\end{equation} $

这样，场景光误差将在图像更明亮的部分变得更大。但很幸运地是（不是设计），该行为跟人可视系统（Weber's law）能很好匹配。根据Weber's law，场景光的改变 $ dx_ {lin} $，需要有效的明显改变在可察觉亮度到 $ x_ {lin} $自身的比例。对 $ \\gamma $的大值，上述等式显示 $ \\frac{dx_ {lin}}{x_ {lin}} $大约跟 $ dx' $成比例。这样，gamma校正值比线性场景光 $ x_ {lin} $能以更容易察觉的方式统一度量。这样，Weber's law的效果能跟简单的数字改动度量比如MSE自动协调，提供应用到gamma校正采样值

相反地，MSE证明在没有gamma校正的图像采样上用处不大。对这样的图片有损压缩算法会导致更差的视觉性能。当处理非自然图片源时需要特别小心；医学X射线和SAR（合成口径雷达）图像，例如，通常是线性的
