---
layout: post
title:  "Statistics Books"
ref: statsBooks
date:   2016-08-29 09:48:44 +0100
categories: stats
lang: en
excerpt_separator: <!--more-->
---
{% highlight latex %}
\usepackage{setspace}
\doublespacing
\usepackage[margin=1in]{geometry}
\usepackage[notes, isbn=false, backend=biber]{biblatex-chicago}
\bibliography{statsBooks.bib}
\author{בנימן הגלילי}
. . .
\newpage
\nocite{*}
\printbibliography
\end{document}

{% endhighlight %}

I wanted to share a BibLaTeX file with some stats books I'm using on my MA Thesis.
Maybe they will help you with you-R oR Stats oR Research oR Something. /endVisualPun

[Imgur](http://i.imgur.com/ta4Vx7q.png)

So, here R some R and Stats Books in [a .bib](https://github.com/paynito/dotfiles/blob/master/statsBooksAug29.bib)



Check out my main page at [benyomin.cf][benyomin-link].
This is just the blog component for that page.

[benyomin-link]: http://benyomin.cf

xYou’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight latex %}
\usepackage{setspace}
\doublespacing
\usepackage[margin=1in]{geometry}
\usepackage[notes, isbn=false, backend=biber]{biblatex-chicago}
\bibliography{statsBooks.bib}
\author{בנימן הגלילי}
. . .
\newpage
\nocite{*}
\printbibliography
\end{document}

{% endhighlight %}