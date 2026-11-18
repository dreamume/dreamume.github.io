---
layout:     post
title:      "The Cauchy-Schwarz master class(Chapter 10) by Steele"
subtitle:   "Hilbert's Inequality and Compensating Difficulties"
thumbnail-img: ""
date:       2026-11-18 16:40
author:     "dreamume"
tags: 		[elementary]
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



Hilbert's Inequality: 对每一对实数序列 $ \\{ a_ {n} \\} $ 和 $ \\{ b_ {n} \\} $，有

$ \\sum^{\\infty}_ {m=1} \\sum^{\\infty}_ {n=1} \\frac{a_ {m}b_ {n}}{m+n} < \\pi (\\sum^{\\infty}_ {m=1}a^{2}_ {m})^{\\frac{1}{2}} (\\sum^{\\infty}_ {n=1}b^{2}_ {n})^{\\frac{1}{2}} $

Quarter Circle Lemma: 对所有 $ m \\ge 1 $，有边界

$ \\sum^{\\infty}_ {n=1} \\frac{1}{m + n} (\\frac{m}{n})^{\\frac{1}{2}} < \\pi $
