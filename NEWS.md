# Version 0.6.7

## Feature Updates

1. Equation labeling and numbering
2. Code/table/equation/figure pre-processors
3. fixed many meta data related issues
4. We now use Mathjax V3
5. New testthat test cases
6. pkgdown website
7. `texor::latex_to_web()` for a single article
8. new stat tools for some metrics and conversion coverage check
9. environment/word count for pandoc convert

## Bug Fixes

1. Support for absolute paths
2. Fixed a lot of logic errors
3. Fixed incompatibilities
4. removed unnecessary code and features
5. R-CMD-check passing
6. Github workflows should work now
7. Improved stat filter which exports pre and post conversion stats yaml file
8. namespaces in logger
9. URL fix for non http:// web Links
10. Figure max width : 100% extra option added to figures.
11. fixed pre processing of tikz
12. fixed problems in journal volume
13. comment filter mechanism for latex
14. improved lua filter for numbering and centering figures
15. fixed slug issue

# Version 0.5.9

## Feature Updates

1. Automated orchestration of conversion
2. New stream editor in R 
3. Using stream editor instead of lua filter for code
4. Using stream editor instead of GNU sed for table
5. changes in lua filter for R code
6. Using stream editor for figure environment patching
7. Automatic fetching of volume and issue from folder

## Bug Fixes

1. Support for absolute paths fixed(in almost all functions)
2. Fixed some logic errors
3. Fixes in metafix.sty

# Version 0.5.5 

## Update Highlights :

1. Placeholder abstract text for articles missing abstract
2. `\CRANpkg()`,`\BIOpkg()` and `CRAN_TASK_VIEWS` are supported
3. Tables have numbering
4. A new lua filter for numbering tables
5. Patched Metafix.sty
6. More vignettes

# Version 0.5.2 
This package matures at this point where almost all features are working, and soon will be ready for CRAN deployment.
The following are the features working:

1. LaTeX macros such as `\pkg`,`\CRANpkg`,`\code` are supported.
2. Reading Metadata from LaTeX file as well as DESCRIPTION.
3. Reading bibliography from bibtex files and ignoring `\thebibliography`
4. A parser to read and convert inbuilt `\thebibliography` to bibtex
5. Supports code environments like `Sinput`,`Soutput`, `example` ,`example*`,`verbatim` with code highlight.
6. Supports graphics included as PDF,PNG,JPG.
7. Functions to convert PDF graphics to PNG.
8. Almost all tables are converted with a few exceptions.
9. Other things like citations,links,footnotes,math(limited) are also supported.