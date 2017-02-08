---
layout: post
title: "blog from .Rmd"
date: 2017-02-08 03:48:44 +0333
comments: true
ref: yakShaving
categories: spacemacs
tags: rmd package servr jekyll knitr
lang: en
---
But, what I'd really like to do is 
run 
```r
rmarkdown::render("elispVersionOfBufferName", "pdf_document")
```
and add that to the org-export C-c C-e menu probably.
Currently have to skip to the last line and execute. 
And type the file name. 
Here's my Rmd template at the moment.

```r
---
title: "TDD eg"
date: 2017-02-08
output: 
pdf_document: 
latex_engine: xelatex
---
# Simple example of Test Driven Development in R.
  {r, definefxn}
foo <- function(x) x^2

Test fxn
{r testfxn}
library(testthat)
expect_is(foo(8), "numeric")
#expect_equal(foo(8), 6) #when this fails pdf won't build

## build with:
{r, eval=FALSE}
rmarkdown::render("tddR.Rmd", "pdf_document")

```
