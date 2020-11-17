---
layout:     post
title:      "The Cauchy-Schwarz master class(Chapter 1) by Steele"
subtitle:   "Starting with Cauchy"
thumbnail-img: ""
date:       2020-11-17 19:00
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

1.  [Starting with Cauchy](#org32d5c21)


<a id="org32d5c21"></a>

# Starting with Cauchy

Cauchy's inequality for real numbers tells us that

$ \\begin{equation} a_ {1} b_ {1}+a_ {2} b_ {2}+\\cdots+a_ {n} b_ {n} \\leq \\sqrt{a_ {1}^{2}+a_ {2}^{2}+\\cdots+a_ {n}^{2}} \\sqrt{b_ {1}^{2}+b_ {2}^{2}+\\cdots+b_ {n}^{2}} \\end{equation} $

Thus, if neither of the sequences is made up of all zeros, we can introcduce new variables

$ \\begin{equation} \\hat{a}_ {k}=a_ {k} /\\left(\\sum_ {j} a_ {j}^{2}\\right)^{\\frac{1}{2}} \\quad \\text { and } \\quad \\hat{b}_ {k}=b_ {k} /\\left(\\sum_ {j} b_ {j}^{2}\\right)^{\\frac{1}{2}} \\end{equation} $

which are normalized in the sense that

$ \\begin{equation} \\sum_ {k=1}^{\\infty} \\hat{a}_ {k}^{2}=\\sum_ {k=1}^{\\infty}\\left\\{a_ {k}^{2} /\\left(\\sum_ {j} a_ {j}^{2}\\right)\\right\\}=1 \\end{equation} $

and

$ \\begin{equation} \\sum_ {k=1}^{\\infty} \\hat{b}_ {k}^{2}=\\sum_ {k=1}^{\\infty}\\left\\{b_ {k}^{2} /\\left(\\sum_ {j} b_ {j}^{2}\\right)\\right\\}=1 \\end{equation} $

we obtain the simple-looking bound

$ \\begin{equation} \\sum_ {k=1}^{\\infty} \\hat{a}_ {k} \\hat{b}_ {k} \\leq \\frac{1}{2} \\sum_ {k=1}^{\\infty} \\hat{a}_ {k}^{2}+\\frac{1}{2} \\sum_ {k=1}^{\\infty} \\hat{b}_ {k}^{2}=1 \\end{equation} $

and, in terms of the original sequence {a<sub>k</sub> } and {b<sub>k</sub> }, we have

$ \\begin{equation} \\sum_ {k=1}^{\\infty}\\left\\{a_ {k} /\\left(\\sum_ {j} a_ {j}^{2}\\right)^{\\frac{1}{2}}\\right\\}\\left\\{b_ {k} /\\left(\\sum_ {j} b_ {j}^{2}\\right)^{\\frac{1}{2}}\\right\\} \\leq 1 \\end{equation} $

Finally, when we clear the denominators, we find out old friend Cauchy's inequality:

$ \\begin{equation} \\sum_ {k=1}^{\\infty} a_ {k} b_ {k} \\leq\\left(\\sum_ {j=1}^{\\infty} a_ {j}^{2}\\right)^{\\frac{1}{2}}\\left(\\sum_ {j=1}^{\\infty} b_ {j}^{2}\\right)^{\\frac{1}{2}} \\end{equation} $

We often benefit from the introduction of shorthand notation such as

$ \\begin{equation} \\langle\\mathbf{a}, \\mathbf{b}\\rangle=\\sum_ {j=1}^{n} a_ {j} b_ {j} \\end{equation} $

This shorthand now permits us to write Cauchy's inequality quite succinctly as

$ \\begin{equation} \\langle\\mathbf{a}, \\mathbf{b}\\rangle \\leq\\langle\\mathbf{a}, \\mathbf{a}\\rangle^{\\frac{1}{2}}\\langle\\mathbf{b}, \\mathbf{b}\\rangle^{\\frac{1}{2}} \\end{equation} $

Specifically, if V is a real vector space (such as $ \\mathbb{R}^{d} $ ), then we say that a function on V x V defined by the mapping (a, b) -> <a, b> is an inner product and we say that (V, <.,.>) is a real inner product space provided that the pair (V, <.,.>) has the following five properties:

(i) <v, v> >= 0    for all $ v \\in V $

(ii) <v, v> = 0    if and only if v = 0

(iii) $ \\langle\\alpha \\mathbf{v}, \\mathbf{w}\\rangle=\\alpha\\langle\\mathbf{v}, \\mathbf{w}\\rangle $   for all $ \\alpha \\in R $ and all $ v, w \\in V $

(iv) $ \\langle\\mathbf{u}, \\mathbf{v}+\\mathbf{w}\\rangle=\\langle\\mathbf{u}, \\mathbf{v}\\rangle+\\langle\\mathbf{u}, \\mathbf{w}\\rangle $ for all $ u, v, w \\in V $

(v) $ \\langle\\mathbf{v}, \\mathbf{w}\\rangle=\\langle\\mathbf{w}, \\mathbf{v}\\rangle $ for all $ v, w \\in V $

For any real inner product space (V, <.,.>), one has for all v and w in V that

$ \\begin{equation} \\langle\\mathbf{v}, \\mathbf{w}\\rangle \\leq\\langle\\mathbf{v}, \\mathbf{v}\\rangle^{\\frac{1}{2}}\\langle\\mathbf{w}, \\mathbf{w}\\rangle^{\\frac{1}{2}} \\end{equation} $

moreover, for nonzero vectors v and w, one has

$ \\begin{equation} \\langle\\mathbf{v}, \\mathbf{w}\\rangle=\\langle\\mathbf{v}, \\mathbf{v}\\rangle^{\\frac{1}{2}}\\langle\\mathbf{w}, \\mathbf{w}\\rangle^{\\frac{1}{2}} \\quad \\text { if and only } i f \\mathbf{v}=\\lambda \\mathbf{w} \\end{equation} $

for a nonzero constant $ \\lambda $

A great many of those applications depend on a natural analog of Cauchy's inqeuality where sums are replaced by integrals,

$ \\begin{equation} \\int_ {a}^{b} f(x) g(x) d x \\leq\\left(\\int_ {a}^{b} f^{2}(x) d x\\right)^{\\frac{1}{2}}\\left(\\int_ {a}^{b} g^{2}(x) d x\\right)^{\\frac{1}{2}} \\end{equation} $

