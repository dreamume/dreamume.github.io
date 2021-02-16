---
layout:     post
title:      "Audio Signal Processing and Coding(Chapter 2) by Spanias"
subtitle:   "Introduction"
thumbnail-img: ""
date:       2021-02-17 02:48
author:     "dreamume"
tags: 		[audio]
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

1.  [introduction](#orge40d976)
    1.  [A GENERAL PERCEPTUAL AUDIO CODING ARCHITECTURE](#orgd523d77)


<a id="orge40d976"></a>

# introduction


<a id="orgd523d77"></a>

## A GENERAL PERCEPTUAL AUDIO CODING ARCHITECTURE

最近几年，研究员提议了几种有效的信号模型（例如，基于传输的，subband-filter结构，wavelet-packet）和复现高质量数字音频的压缩标准。多数这些算法基于一般的结构如下：

![img](../img/generic_perceptual_audio_encoder.png)

-   单传输
-   常量时间采样，统一/非统一bandpass过滤
-   变时（信号自适应）采样，统一/非统一bandpass过滤
-   调和/正弦分析器
-   源系统分析（LPC和多脉激发）
-   以上的混合版本

时间频率分析方法的选择总是包含时间和频率解决方案要求的一个基本折中。探测扰动控制通过声音心理学信号分析章节基于心理学原理估计信号掩码动力。心理学声学模型转发掩码阙值测量在时间频率平面每个点的最大扰动数值使得时间频率参数的测量不会引入可听见的一些错误。心理学声学模型因此允许测量阶段开发可发觉的无关事项。该阶段也可开发统计冗余通过经典的技术比如DPCM或ADPCM。一旦一个测量紧参数集形成，剩下的冗余通常通过无杂音run-length(RL)和熵编码技术删除，例如，Huffman，算术或Lempel-Ziv-Welch (LZW)。因为心理学声学扰动控制模型的输出是依赖信号的，多数算法为可变速度。固定频道速度要求通常通过缓存反馈方案满足，经常会引入编码延迟

