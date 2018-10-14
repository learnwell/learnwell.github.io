---

layout: post
title: KaTeX syntax and examples
author: pulkit
tags: []

---

### Syntax & Examples

1. LaTeX [reference](http://meta.math.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)
2. KaTeX [reference](https://katex.org/docs/supported.html)
3. `$$\Gamma(z) = \int_0^\infty t^{z-1}e^{-t}dt\,.$$`

	$$
	\Gamma(z) = \int_0^\infty t^{z-1}e^{-t}dt\,.
	$$
4. `$$x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}$$`
	$$
	x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}
	$$
5. `$${x}_{1,2}=\frac{-b\pm \sqrt{b^2-4ac}}{2a}$$`
	$$
	{x}_{1,2}=\frac{-b\pm \sqrt{b^2-4ac}}{2a}  
	$$
6. `$$f(x) = \int_{-\infty}^\infty\hat f(\xi)\,e^{2 \pi i \xi x}\,d\xi$$`
	$$
	f(x) = \int_{-\infty}^\infty\hat f(\xi)\,e^{2 \pi i \xi x}\,d\xi
	$$
7. `This apartment has an area of $100m^2$, one must consider the value of $x_z$`
This apartment has an area of $100m^2$
One must consider the value of $x_z$
8. `y^(a+b)^ then something like x~y,z~`
y^(a+b)^ then something like x~y,z~
9. `This formula $f(x)  = x^2$ is an example.`
This formula $f(x)  = x^2$ is an example.
10. `$\sum_{i=0}^n i^2 = \frac{(n^2+n)(2n+1)}{6}$`

$\sum_{i=0}^n i^2 = \frac{(n^2+n)(2n+1)}{6}$ 

### Work In Progress: GitHub Pages Integration

1. [Rendering LaTeX using KaTeX and Jekyll](https://xuc.me/blog/katex-and-jekyll/)
2. [Math support with KaTeX on Github Pages](https://karas.io/blog/math-support-with-katex-on-github-pages/)
3. [Math on GitHub Pages](http://g14n.info/2014/09/math-on-github-pages/)
4. [Type on Strap](https://github.com/Sylhare/Type-on-Strap) theme already has KaTeX enabled but will it work on GitHub Pages? [Maybe](https://blog.github.com/2017-11-29-use-any-theme-with-github-pages/).
	```
	# /_config.yml
	remote_theme: Sylhare/Type-on-Strap
	theme_settings:
	  katex: true # to Enable it
	```
5. [How to enable mathjax/latex in github pages](https://zishuaiz.github.io/blog/how-to-enable-mathjax-in-github-pages)
6. [Search](https://github.com/search?q=use_math+remote_theme&type=Code) for themes that might come with math support enabled.

> Written with [StackEdit](https://stackedit.io/).

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTkwMDIwNDk0MSw0MTM1MDk1NzksLTE0ND
MwNjg3ODAsMjY0MTM5MTAxLDE1MzU1MzMwOTEsMjA4NDg2NDgw
MCwtMTQ5MTcyNDIzNiwtMTg4MjczMjY5NSwxMjA0MzU1OTA3LC
0xMzA3NDQ5OTE3LC0xOTQxMDMwMTAwLC0xMzkzMjI1ODk1XX0=

-->
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3MTA2OTE1MzJdfQ==
-->