# Display math in R documentation

Helper function to insert tex math expressions into R documentation
(`.rd`) files. Uses Katex rendering for documentation in html format,
and the appropriate latex macros for documentation rendered in pdf or
plain-text.

## Usage

``` r
math_to_rd(tex, ascii = tex, displayMode = TRUE, ..., include_css = TRUE)
```

## Arguments

- tex:

  input string with tex math expression.

- ascii:

  alternate text-only representation of the input math to show in
  documentation rendered to plain text format.

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

## Value

a string with an rd fragment to be included in R documentation

## Details

Use `math_to_rd()` inside `\Sexpr` to embed math in your R package
documentation pages. For example the code below can be inserted in your
`rd` (or roxygen) source code:

    \Sexpr[results=rd, stage=build]{
      katex::math_to_rd(katex::example_math())
    }

Which results in the following output:

``` math
f(x)= {\frac{1}{\sigma\sqrt{2\pi}}}e^{- {\frac {1}{2}} (\frac {x-\mu}{\sigma})^2}
```

Optionally you can specify an alternate ascii representation that will
be shown in the plain-text format rendering of the documentation:

    \Sexpr[results=rd, stage=build]{
      katex::math_to_rd('E=MC^2', 'E=mc²')
    }

``` math
E=MC^2
```

If no ascii representation is given, the input tex in displayed verbatim
into the plain-text documentation.

## Note for Windows

On Windows, R versions before 4.1.2 had a
[bug](https://bugs.r-project.org/show_bug.cgi?id=18152) which could lead
to incorrect HTML encoding for `\Sexpr{}` output. As a workaround, we
automatically escape non-ascii html characters on these versions of R.
Linux and MacOS are unaffected.

## See also

Other katex:
[`katex`](https://docs.ropensci.org/katex/reference/katex.md),
[`pandoc`](https://docs.ropensci.org/katex/reference/pandoc.md)
