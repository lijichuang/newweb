---
author: Hugo Authors
date: "2019-03-08"
description: A brief guide to setup KaTeX
title: Math Typesetting
---

Mathematical notation in a Hugo project can be enabled by using third party JavaScript libraries.
<!--more-->

In this example we will be using [KaTeX](https://katex.org/)

- Create a partial under `/layouts/partials/math.html`
- Within this partial reference the [Auto-render Extension](https://katex.org/docs/autorender.html) or host these scripts locally.
- Include the partial in your templates like so:  

```
{{ if or .Params.math .Site.Params.math }}
{{ partial "math.html" . }}
{{ end }}
```  
- To enable KaTeX globally set the parameter `math` to `true` in a project's configuration
- To enable KaTeX on a per page basis include the parameter `math: true` in content files.

**Note:** Use the online reference of [Supported TeX Functions](https://katex.org/docs/supported.html)
{{< math.inline >}}
{{ if or .Page.Params.math .Site.Params.math }}
<!-- KaTeX -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.8/dist/katex.min.css" integrity="sha512-7nTa5CnxbzfQgjQrNmHXB7bxGTUVO/DcYX6rpgt06MkzM0rVXP3EYCv/Ojxg5H0dKbY7llbbYaqgfZjnGOAWGA==" crossorigin="anonymous">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.8/dist/katex.min.js" integrity="sha512-aoZChv+8imY/U1O7KIHXvO87EOzCuKO0GhFtpD6G2Cyjo/xPeTgdf3/bchB10iB+AojMTDkMHDPLKNxPJVqDcw==" crossorigin="anonymous"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.8/dist/contrib/auto-render.min.js" integrity="sha512-iWiuBS5nt6r60fCz26Nd0Zqe0nbk1ZTIQbl3Kv7kYsX+yKMUFHzjaH2+AnM6vp2Xs+gNmaBAVWJjSmuPw76Efg==" crossorigin="anonymous" onload="renderMathInElement(document.body);"></script>
{{ end }}
{{</ math.inline >}}

### Examples

Inline math: $ \varphi = \dfrac{1+\sqrt5}{2}= 1.6180339887… $

Block math:

$$
 \varphi = 1+\frac{1} {1+\frac{1} {1+\frac{1} {1+\cdots} } } 
$$
