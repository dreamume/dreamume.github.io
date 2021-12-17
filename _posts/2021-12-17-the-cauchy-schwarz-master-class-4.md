---
layout:     post
title:      "The Cauchy-Schwarz master class(Chapter 4) by Steele"
subtitle:   "On Geometry and Sums of Squares"
thumbnail-img: ""
date:       2021-12-17 20:00
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

1.  [Gram-Schmidt and Products of Linear Forms](#org4015247)
2.  [A Gram-Schmidt Finale](#org0169ed1)


<a id="org4015247"></a>

# Gram-Schmidt and Products of Linear Forms

对三项系列 $ \\{x, y, z\\} $使用Gram-Schmidt过程显示在实数内积空间有

$ <x, y><x, z> \\le \\frac{1}{2} (<y, z> + \|\| y \| \| \| \| z \| \| ) \| \| x \| \|^{2} $

解答：不失一般性我们可假设x, y和z是线性无关的且 $ \| \| x \| \| = 1 $，这样Gram-Schmidt关系可写为 $ x = e_ {1}, y = \\mu_ {1}e_ {2} + \\mu_ {2} e_ {2} $, z = \\upsilon_ {1}e_ {1} + \\upsilon_ {2}e_ {2} + \\upsilon_ {3}e_ {3} $，从中我们有 $ <x, x> = 1, <x, y> = \\mu_ {1}, <x, z> = \\upsilon_ {1}, <y, z> = \\mu_ {1}\\upsilon_ {1} + \\mu_ {2}\\upsilon_ {2} $。问题不等式的边界断言 $ \\mu_ {1}\\upsilon_ {1} \\le \\frac{1}{2} (\\mu_ {1}\\upsilon_ {1} + \\mu_ {2}\\upsilon_ {2} + (\\mu^{2}_ {1} + \\mu^{2}_ {2})^{\\frac{1}{2}} (\\upsilon^{2}_ {1} + \\upsilon^{2}_ {2} + \\upsilon^{2}_ {3})^{\\frac{1}{2}}) $或 $ \\mu_ {1} \\upsilon_ {1} - \\mu_ {2} \\upsilon_ {2} \\le (\\mu^{2}_ {1} + \\mu^{2}_ {2})^{\\frac{1}{2}} (\\upsilon^{2}_ {1} + \\upsilon^{2}_ {2} + \\upsilon^{2}_ {3})^{\\frac{1}{2}} $，这从柯西不等式立即可得到


<a id="org0169ed1"></a>

# A Gram-Schmidt Finale

如果x, y, z是内积空间V的元素且如果 $ \| \| x \| \| = \| \| y \| \| = \| \| z \| \| = 1 $，则有不等式

$ \| <x, x><y, z> - <x, y><x, z> \| \\le \\{<x, x>^{2} - \| <x,y> \|^{2}\\} \\{<x, x>^{2} - \| <x, z> \|^{2} \\} $

且不等式

$ <x, x>^{2} (\| <y, z> \|^{2} + \|<y, x>\|^{2} + \| <x, z> \|^{2}) \\\\ \\le <x, x>^{4} + <x, x><z, y><y, x><x, z> \\\\ + <x, x><y, z><x, y><z, x> $

我们使用上一题解答的正定性和记号，左边L的边界可写为

$ \| <x, x><y, z> - <x,y><x,z> \| = \| \\{(\\mu_ {1} \\bar{\\upsilon_ {1}} + \\mu_ {2} \\bar{\\upsilon_ {2}} \\} \|^{2} = \| \\mu_ {2} \\bar{\\upsilon_ {2}} \|^{2} $

且右边R可写为

$ \\{<x,x>^{2} - \| <x,y> \|^{2} \\} \\{<x,x>^{2} - \| <x, z> \|^{2} \\} \\\\ = (1 - \| \\mu_ {1} \|^{2}) (1 - \| \\upsilon_ {1} \|^{2}) = \| \\mu_ {2}\|^{2} (\| \\upsilon_ {2} \|^{2} + \| \\upsilon_ {3} \|^{2}) $

因为我们有 $ 1 = \| \| y \| \| = \| \\mu_ {1} \|^{2} + \| \\mu_ {2} \|^{2}, 1 = \| \| z \| \| = \| \\upsilon_ {1} \|^{2} + \| \\upsilon_ {2} \|^{2} + \| \\upsilon_ {3} \|^{2} $

这使得 $ L \\le R $

现在为证明第二个不等式，它可以缩减为

$ \| \\mu_ {1} \\bar{\\upsilon_ {1}} + \\mu_ {2}\\bar{\\upsilon_ {2}} \|^{2} + \| \\mu_ {1} \|^{2} + \| \\upsilon_ {1} \|^{2} \\\\ le 1 + (\\bar{\\mu}_ {1} \\upsilon_ {1} + \\bar{\\mu}_ {2}\\upsilon_ {2})\\mu_ {1} \\bar{\\upsilon_ {1}} + (\\mu_ {1}\\bar{\\upsilon}_ {1} + \\mu_ {2}\\bar{\\upsilon}_ {2}) \\bar{\\mu}_ {1}\\upsilon_ {1} $

且通过扩展，有

$ \| \\mu_ {1} \|^{2} + \| \\upsilon_ {1} \|^{2} + \| \\mu_ {1} \\upsilon_ {1} \|^{2} + \| \\mu_ {2} \\upsilon_ {2} \|^{2} + 2 \\Re\\{\\mu_ {1}\\bar{\\upsilon}_ {1} \\bar{\\mu}_ {1} \\upsilon_ {2}\\} \\\\ \\le 1 + 2 \| \\mu_ {1}\\upsilon_ {1} \|^{2} + 2 Re \\{\\mu_ {1}\\bar{\\upsilon}_ {1}\\bar{\\mu}_ {2}\\upsilon_ {2}\\} $

在取消项目后，我们看到

$ L \\equiv \| \\mu_ {1} \|^{2} + \| \\upsilon_ {1} \|^{2} + \| \\mu_ {2}\\upsilon_ {2} \|^{2} \\le 1 + \| \\mu_ {1}\\upsilon_ {1} \|^{2} $

但替代 $ \| \\mu_ {2} \\upsilon_ {2} \|^{2} = (1 - \| \\mu_ {1} \|^{2})(1 - \| \\upsilon_ {1} \|^{2} - \| \\upsilon_ {3} \|^{2}) $给了我们 $ L = 1 + \| \\mu_ {1}\\upsilon_ {1} \|^{2} + \| \\upsilon_ {3} \|^{2} (\| \\mu_ {1} \|^{2} - 1) \\le 1 + \| \\mu_ {1}\\upsilon_ {1} \|^{2} $因为 $ \| \\mu_ {1} \|^{2}  \\le 1 $
