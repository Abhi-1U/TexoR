
<!-- README.md is generated from README.Rmd. Please edit that file -->

# texor : Tools for converting LaTeX source files into RJ-web-articles

<!-- badges: start -->

[![GitHub Workflow Status
(branch)](https://img.shields.io/github/workflow/status/Abhi-1U/texor/pkgdown/master?label=pkgdown&style=for-the-badge)](https://github.com/Abhi-1U/texor/actions/workflows/pkg_down.yaml)
[![GitHub Workflow
Status](https://img.shields.io/github/workflow/status/Abhi-1U/texor/R_cmd_check?label=R-CMD-CHECK&style=for-the-badge)](https://github.com/Abhi-1U/texor/actions/workflows/cmdcheck.yaml)
[![GitHub R package version (subdirectory of
monorepo)](https://img.shields.io/github/r-package/v/Abhi-1U/texor?filename=DESCRIPTION&label=texor&style=for-the-badge)](https://github.com/Abhi-1U/texor/blob/master/DESCRIPTION)
![Github
Issues](https://img.shields.io/github/issues/Abhi-1U/texor?color=orange&logo=github&logoColor=&style=for-the-badge)

<!-- badges: end -->

texor is a package that deals with multiple challenges that occour in
conversion of LaTeX source files (which typically generate a PDF) to a
web friendly RJ-web-article format.

### Currently texor can handle R-Journal structured LaTeX files with support for:

1.  RJournal based LaTeX files with macros such as
    `\pkg{}`,`\CRANpkg{}`,`\BIOpkg{}`, `\code{}`, `\acronym{}`
2.  Reading Metadata from LaTeX file as well as DESCRIPTION.
3.  Reading bibliography from bibtex files and ignoring
    `\thebibliography`
4.  Supports code environments like `Sinput`,`Soutput`, `example`
    ,`example*`,`verbatim`, `smallverbatim` with code highlight.
5.  Supports graphics included as PDF, PNG, JPG, tikz, algorithm2e
    graphics supported (some figures might not work).
6.  Functions to convert PDF graphics to PNG.
7.  Almost all tables are supported with a few exceptions.
8.  Other things like citations,links,footnotes,math,CTV,package
    references are also supported.
9.  A parser to read and minimally convert inbuilt `\thebibliography` to
    bibtex (moved to [rebib](https://github.com/Abhi-1U/rebib))
10. Figure/Table/Equation numbering
11. Stream Editor to rename alien commands/environments to accepted
    defaults.
12. Pre and Post conversion statistics of environments for verification.
13. Bibliography aggregation.(moved to
    [rebib](https://github.com/Abhi-1U/rebib))
14. Tikz,algorithm graphics supported (some figures might not work)
15. Logging of events.

![texor features](man/figures/texor.svg)

### Note :

    Please use absolute paths when working with texor/rebib !

    The reason is that earlier rebib used to work with relative paths by using 
    setwd(), getwd() to handle working directories. However this was not an ideal
    method to handle paths and working on files.

    Hence I had to switch to absolute path system for almost all functions where
    automation is possible and works well. As there was no changing of working
    directories there is less risk of setting up a wrong working directory when 
    failing certain function.

    Use forward slashes (/) in paths and do not add a forward slash at the end of 
    the path
    for example 
    Wrong usage : C:\projects\texor\main
    wrong usage : C:/projects/texor/main/
    wrong usage : C:\\projects\\texor\\main\\
    wrong usage : C:\\projects\\texor\\main (this might workout in R but not sure)

    Correct usage : C:/projects/texor/main

## Installation

install these dependency packages (github development versions)

``` r
# install.packages("remotes")
remotes::install_github("rstudio/distill")
remotes::install_github("Abhi-1U/rjtools")
remotes::install_github("Abhi-1U/rebib")
```

install the development version from GitHub with:

``` r
# install.packages("remotes")
remotes::install_github("Abhi-1U/texor")
# install.packages("pak")
pak::pak("Abhi-1U/texor")
# also install rebib for bibliography
remotes::install_github("Abhi-1U/rebib")
```

## General Usage

here is a quick example to use texor package with a sample RJournal
article (included with the package
[inst/article](https://github.com/Abhi-1U/texor/tree/master/inst/examples/article))

``` r
texor::latex_to_web(article_dir)
```