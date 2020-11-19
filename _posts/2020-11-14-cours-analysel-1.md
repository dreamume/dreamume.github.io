---
layout:     post
title:      "Cours Analysel(Chapter 1) by Paulin"
subtitle:   "Vocabulaire"
thumbnail-img: ""
date:       2020-11-14 21:00
author:     "dreamume"
tags: 		[topology]
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

1.  [Vocabulaire](#org914e96e)
    1.  [Espaces topologiques](#org1d1fc55)
        1.  [Espaces métriques](#org1562dd5)


<a id="org914e96e"></a>

# Vocabulaire


<a id="org1d1fc55"></a>

## Espaces topologiques

Soit E un ensemble. Une topologie sur E est un ensemble $ \\mathscr{O} $ de parties de E tel que

(1) toute intersection finie d'éléments de $ \\mathscr{O} $ appartient à $ \\mathscr{O} $

(2) toute union d'éléments de $ \\mathscr{O} $ appartient à $ \\mathscr{O} $


<a id="org1562dd5"></a>

### Espaces métriques

Soit E un ensemble. Une distance sur E est une application $ d: E \\times E \\rightarrow[0,+\\infty[ $ telle que, pour tous x,y,z dans E,

(1) (annulation sur la diagonale) d(x,x) = 0

(2) (séparation) si d(x,y) = 0, alors x = y

(3) (symétrie) d(x,y) = d(y,x)

(4) (inégalité triangulaire) d(x,y)<=d(x,z) + d(z,y)

Si d est une distance sur E, alors

$ \\begin{equation} d(x,y) \\geq \| d(x,z) - d(z,y) \| \\end{equation} $

pour tous x,y,z dans E (cette inégalité s'appelle l'inégalité triangulaire inverse)

Une application f: X -> Y entre deux espaces métriques est isométrique si

$ \\begin{equation} \\forall x, y \\in X, \\quad d(f(x), f(y))=d(x, y) \\end{equation} $

Soit (X, d) un espace métrique.

Soient $ x \\in X $ et r > 0. La boule ouverte de centre x et rayon r est

$ \\begin{equation} B(x, r) = \\{ y \\in X : d(x,y) < r\\} \\end{equation} $

La boule fermée de centre x et de rayon r est

$ \\begin{equation} \\bar{B}(x, r)=\\{y \\in X: d(x, y) \\leq r\\} \\end{equation} $

La sphére de centre x et de rayon r est

$ S(x, r) = \\{y \\in X : d(x, y) = r\\} $

Lorsque l'on veut préciser la distance, on pourra la mettre en indice, et noter $ B_ {d}(x, r), \\bar{B}_ {d}(x,r), S_ {d}(x, r) $

