---
layout:     post
title:      "Audio Signal Processing and Coding(Chapter 1) by Spanias"
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
    2.  [AUDIO CODER ATTRIBUTES](#orge5620e3)
        1.  [音频质量](#orgc325fd7)
        2.  [比特率](#org8305c97)


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


<a id="orge5620e3"></a>

## AUDIO CODER ATTRIBUTES

感知音频代码典型地基于如下属性评估：音频重生质量，操作比特率，计算复杂度，编解码延迟和频道错误稳定性。目标是用低比特率（<32 kb/s）达到高质量音频输出，及可接受的算法延迟（~5到20ms），且低计算复杂度（每秒~1到10百万指令或MIPS）


<a id="orgc325fd7"></a>

### 音频质量

音频质量是设计一个音频编码算法最重要的因素。从简单近通透感知编码的发展中已取得成功地跨越。典型地，信号保真的经典客观度量比如信号噪音比（SNR）和总调和扰动（THD）为非普世的。感知音频编码领域很快成熟且创造了听力测试地更多需求，因此存在在感知度量方案上对应地兴趣增长。一些主观和客观的质量度量被提出且在最近几十年中标准化。这些方案中的一些包括噪声掩码比（NMR）感知音频质量度量（PAQM），感知评估（PERCEVAL）和客观音频信号评估（OASE）


<a id="org8305c97"></a>

### 比特率

从编解码设计者的视角观点看，一个关键挑战是用最小的比特数呈现高保真音频。例如，如果一个5毫秒音频帧采样率为48kHz（每帧240采样数）使用80比特呈现，则编码率为80比特/5ms = 26 kb/s。低比特率意味着高压缩率和一般的低重生质量。早期编码比如ISO/IEC MPEG-1 (32-448 kb/s)，杜比AC-3(32-384 kb/s)，索尼ATRAC(256 kb/s)和飞利浦PASC(192 kb/s)使用高比特率获得通透的音频重生。然而，一些复杂音频编码工具的发展（比如，MPEG-4音频工具）创造了以8到32 kb/s高效传输或存储音频。将来音频编码算法承诺以低比特率提供可靠质量，扩展使比特率和质量匹配需求比如时间变化频道容量
