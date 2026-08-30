# Tex math rendering in R

Converts tex-style math expressions to html and mathml for use in manual
pages or markdown documents. The conversion is done in R using V8
("server-side"), hence the resulting fragment can be inserted into an
HTML document without the need for a JavaScript library like MathJax.
Only the
[katex.css](https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.css)
style file is required in the final html document. Use
[math_to_rd](https://docs.ropensci.org/katex/reference/math_to_rd.md)
for embedding math into R documentation (`.rd`) pages.

## Usage

``` r
katex_html(
  tex,
  displayMode = TRUE,
  ...,
  include_css = FALSE,
  preview = interactive()
)

katex_mathml(tex, displayMode = TRUE, ...)

example_math()
```

## Arguments

- tex:

  input string with tex math expression.

- displayMode:

  render math in centered 2D layout, similar to `$$` in tex. Set to
  `FALSE` to render (non-centered) inline layout for use in text. For
  pdf output, this corresponds to the `\deqn{}` and `\eqn{}` macros, see
  [WRE 2.6:
  Mathematics](https://cran.r-project.org/doc/manuals/r-release/R-exts.html#Mathematics)

- ...:

  additional html rendering options passed to
  [katex.render](https://katex.org/docs/options.html)

- include_css:

  adds the katex css file to the output. This is only required once per
  html webpage. Set to `FALSE` if you include css files into the your
  html head some other way.

- preview:

  open an HTML preview page showing the snipped in the browser

## Value

a string with a html/mathml fragment

## Details

Refer to the upstream [katex support
table](https://katex.org/docs/support_table.html) for the full list of
supported tex functions that can be rendered to html using katex.

By default, katex_html returns a mix of HTML for visual rendering and
includes MathML for accessibility. To only get html, pass
`output="html"` in the extra options, see also the [katex
documentation](https://katex.org/docs/options.html).

## See also

Other katex:
[`math_to_rd()`](https://docs.ropensci.org/katex/reference/math_to_rd.md),
[`pandoc`](https://docs.ropensci.org/katex/reference/pandoc.md)

## Examples

``` r
# Basic examples
html <- katex_html(example_math())
mathml <- katex_mathml(example_math())

# Example from katex.org homepage:
macros <- list("\\f" = "#1f(#2)")
math <- "\\f\\relax{x} = \\int_{-\\infty}^\\infty \\f\\hat\\xi\\,e^{2 \\pi i \\xi x} \\,d\\xi"
html <- katex_html(math,  macros = macros)
mathml <- katex_mathml(math,  macros = macros)
```
