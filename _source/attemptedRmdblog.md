---
title: "blog from .Rmd"
date: 2017-02-08
ref: rmdblog1
output: 
pdf_document: 
categories : spacemacs
lang: en
latex_engine: xelatex
---
A live-blog post setting up blogging in Rmd.

Pre-reqs:
I already have a working jekyll / github pages setup.

Todo:

I want to blog from .Rmd instead of .md.

Why?:

Code blocks will be executable, not just syntax-highlighted, no need to retype my 
data exploration just to blog about it.

How: 
follow instructions from https://jekyll.yihui.name/2014/09/jekyll-with-knitr.html
and
https://www.r-bloggers.com/blogging-with-rmarkdown-knitr-and-jekyll/

```r
# install some helper functions for Rmd to jekyll workflow
devtools::install_github(``brendan-R/brocks'')
install.packages(``servr'')
```

```
## Error: attempt to use zero-length variable name
```
include some code.

```r
x <-99
y <- x + 1
cat(``hello world'')
y
knitr::kable(head(mtcars))
```

```
## Error: attempt to use zero-length variable name
```
hmm, seems this .Rmd needs to be in the _source directory inside a jekyll site directory.

No, just the jekyll site dir, if I run the

```r
servr::jekyll() 
```

```
## Error: Failed to compile ./attemptedRmdblog.Rmd
```
from inside the _site, then the post (.hmtl) goes there, that's not where I want it.

Post still isn't showing up. I need to add more to my YAML section in the .Rmd, all that
lang and ref stuff that I needed in the .md.

## build blog post with:

fails, try again after setwd(path/to/jekyllblog/_source)
quotes are messed up, some problem with smart quotes, hmm.

## build pdf with:


