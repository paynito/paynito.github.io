---
layout: post
title: Compiling a thesisdown directory in ess
date: 2017-03-07 13:48:44 +0333
categories: spacemacs
lang: en
ref: thesisDown1
published: true
---
The [thesisdown](https://github.com/ismayc/thesisdown) package for R compiles a nice pdf. Chapters are stored
as separate .Rmd files. So, when typing away in [ess](http://ess.r-project.org/) how do you compile the whole thing?

I made an R script that can be called from bash.
{% highlight R %}
#!/usr/bin/env Rscript

## stored @ ~/school/makeThesis.R
## call from bash:  Rscript ~/school/makeThesis.R 
## makes the thesis as /Volumes/Bmac/febThesis/thesis.pdf

setwd("/Volumes/Bmac/febThesis/index")
bookdown::render_book("Index.Rmd")

{% endhighlight %}

Then I wrote a defun - define function, in emacs that calls this script.

{% highlight racket %}
;; a function to compile my thesis
  (defun compileThesis (arg)       ; Interactive version.
    "Compiles thesis."
    (interactive "p")
    (shell-command "Rscript ~/school/makeThesis.R"))

{% endhighlight %}
And finally, a keybinding to call it. Now I can be working in 03-chap3.Rmd and quickly compile the project, which of course will auto-refresh
if you use [Skim](http://skim-app.sourceforge.net/) instead of Preview as your pdf viewer.
{% highlight racket %}

(global-set-key (kbd "M-m c t")   (lambda () (interactive) 'compileThesis))   ;            ;; mnemonic - "compile Thesis"

{% endhighlight %}

Sometimes you are just working in a single file in ess, 
without the complications of multiple chapters and a separate Index.Rmd. 
But, I haven't found the best knitr function in ess or [polymode](https://github.com/vspinu/polymode), 
so I have a function to compile a single r-markdown notebook, just like the knit button in RStudio.
{% highlight EmacsLisp %}
  ;; a function to compileRmdToPdf
  (defun compileRmdToPdf () "Compiles the current buffer as a pdf" (interactive)
         (call-process("R -e 'rmarkdown::render(%s, \"pdf_document\")' " buffer-file-name)))
         
  (global-set-key (kbd "M-m c p")   (lambda () (interactive) 'compileRmdToPdf)) ; compile pdf
{% endhighlight %}

I'm still not very good at writing keybindings for emacs. I'm sure it would be better to make this
in the polymode keymap.
