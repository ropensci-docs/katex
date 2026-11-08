# Rending math to HTML in R using katex

This vignette demonstrates some example math rendered server-side in R
using the katex package. Refer to the upstream [katex support
table](https://katex.org/docs/support_table.html) for the full list of
supported tex functions.

Example equations from:
<https://www.intmath.com/cg5/katex-mathjax-comparison.php>

### Equation 1

``` r

tex1 <- "\\frac{1}{\\Bigl(\\sqrt{\\phi \\sqrt{5}}-\\phi\\Bigr) e^{\\frac25 \\pi}} \\equiv 1+\\frac{e^{-2\\pi}} {1+\\frac{e^{-4\\pi}} {1+\\frac{e^{-6\\pi}} {1+\\frac{e^{-8\\pi}} {1+\\cdots} } } }"
katex_html(tex1, include_css = TRUE)
```

``` math
\frac{1}{\Bigl(\sqrt{\phi \sqrt{5}}-\phi\Bigr) e^{\frac25 \pi}} \equiv 1+\frac{e^{-2\pi}} {1+\frac{e^{-4\pi}} {1+\frac{e^{-6\pi}} {1+\frac{e^{-8\pi}} {1+\cdots} } } }
```

### Equation 2

``` r

tex2 <- "\\left( \\sum_{k=1}^n a_k b_k \\right)^2 \\leq \\left( \\sum_{k=1}^n a_k^2 \\right) \\left( \\sum_{k=1}^n b_k^2 \\right)"
katex_html(tex2)
```

``` math
\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)
```

### Equation 3

``` r

tex3 <- "1 +  \\frac{q^2}{(1-q)}+\\frac{q^6}{(1-q)(1-q^2)}+\\cdots = \\prod_{j=0}^{\\infty}\\frac{1}{(1-q^{5j+2})(1-q^{5j+3})}, \\text{ for }\\lvert q\\rvert < 1."
katex_html(tex3)
```

``` math
1 +  \frac{q^2}{(1-q)}+\frac{q^6}{(1-q)(1-q^2)}+\cdots = \prod_{j=0}^{\infty}\frac{1}{(1-q^{5j+2})(1-q^{5j+3})}, \text{ for }\lvert q\rvert < 1.
```

### Equation 4

``` r

tex4 <- "\\int u \\frac{dv}{dx}\\,dx=uv-\\int \\frac{du}{dx}v\\,dx"
katex_html(tex4)
```

``` math
\int u \frac{dv}{dx}\,dx=uv-\int \frac{du}{dx}v\,dx
```

### Equation 5

``` r

tex5 <- "S (\\omega)=\\frac{\\alpha g^2}{\\omega^5} \\,e ^{[-0.74\\bigl\\{\\frac{\\omega U_\\omega 19.5}{g}\\bigr\\}^{-4}]}"
katex_html(tex5)
```

``` math
S (\omega)=\frac{\alpha g^2}{\omega^5} \,e ^{[-0.74\bigl\{\frac{\omega U_\omega 19.5}{g}\bigr\}^{-4}]}
```

### Equation 6

``` r

tex6 <- "f(n) = \\begin{cases} \\frac{n}{2}, & \\text{if } n\\text{ is even} \\\\ 3n+1, & \\text{if } n\\text{ is odd} \\end{cases}"
katex_html(tex6)
```

``` math
f(n) = \begin{cases} \frac{n}{2}, & \text{if } n\text{ is even} \\ 3n+1, & \text{if } n\text{ is odd} \end{cases}
```

### Equation 7

``` r

tex7 <- "\\begin{aligned}
\\dot{x} & = \\sigma(y-x) \\\\ 
\\dot{y} & = \\rho x - y - xz \\\\ 
\\dot{z} & = -\\beta z + xy 
\\end{aligned}"
katex_html(tex7)
```

``` math
\begin{aligned}
\dot{x} & = \sigma(y-x) \\ 
\dot{y} & = \rho x - y - xz \\ 
\dot{z} & = -\beta z + xy 
\end{aligned}
```

### Equation 8

``` r

tex8 <- "\\begin{pmatrix} 
a_{11} & a_{12} & a_{13}\\\\ 
a_{21} & a_{22} & a_{23}\\\\ 
a_{31} & a_{32} & a_{33} 
\\end{pmatrix}"
katex_html(tex8)
```

``` math
\begin{pmatrix} 
a_{11} & a_{12} & a_{13}\\ 
a_{21} & a_{22} & a_{23}\\ 
a_{31} & a_{32} & a_{33} 
\end{pmatrix}
```
