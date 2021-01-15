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

