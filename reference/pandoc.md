# Renders math in HTML document

Reads an html file and substitutes elements of class `"math display"`
and `"math inline"` with rendered html math. This is mainly intended as
a post-processing step for pandoc, which generates such html for
equations. As a result the math can be displayed without the need for
including the mathjax library in the html document.

## Usage

``` r
render_math_in_html(
  input,
  output = NULL,
  ...,
  throwOnError = FALSE,
  include_css = TRUE
)
```

## Arguments

- input:

  path to the html input file

- output:

  path to the output html file, or NULL to return as string

- ...:

  additional html rendering options passed to
  [katex.render](https://katex.org/docs/options.html)

- throwOnError:

  should invalid math raise an error in R? See [katex
  options](https://katex.org/docs/options.html)

- include_css:

  automatically inject the required katex css in the html head

## See also

Other katex:
[`katex`](https://docs.ropensci.org/katex/reference/katex.md),
[`math_to_rd()`](https://docs.ropensci.org/katex/reference/math_to_rd.md)
