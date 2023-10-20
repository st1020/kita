+++
title = "Math Typesetting"
date = "2019-03-08"
description = "A brief guide to setup KaTeX"
extra.math = true
+++

Kita theme support $\LaTeX$ mathematical formulas using [KaTeX](https://katex.org/).

<!--more-->

- To enable KaTeX globally set the parameter `extra.math` to `true` in a project's configuration
- To enable KaTeX on a per page basis include the parameter `extra.math = true` in content files

**Note:** Use the online reference of [Supported TeX Functions](https://katex.org/docs/supported.html)

### Examples

<p>
Inline math: $(varphi = dfrac{1+sqrt5}{2}= 1.6180339887…)$
</p>

Block math:

$$
 \varphi = 1+\frac{1} {1+\frac{1} {1+\frac{1} {1+\cdots} } }
$$
