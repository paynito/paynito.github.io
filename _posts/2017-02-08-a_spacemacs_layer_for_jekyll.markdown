---
layout: post
ref: spaceJekyll
date: 2017-02-08 16:48:44 +0333
comments: true
categories : spacemacs
tags: jekyll spacemacs layer emacs elisp
lang: en 
title: "A spacemacs layer for jekyll"
---
Apparently tags and categories are not the same thing to jekyll.
https://superdevresources.com/tag-cloud-jekyll/
https://jovandeginste.github.io/2016/05/04/add-a-tag-cloud-to-my-jekyll-site.html

hmm, seems that the org-export to .md function has disappeared.
Prompted me to try a new blogging layer for spacemacs.
https://allysonjulian.com/posts/blogging_with_spacemacs_and_jekyll/
https://github.com/0x414A/spacemacs-jekyll

The spacemacs-jekyll layer is in .emacs.d/private/jekyll
It uses the hyde layer @         .emacsd/elpa/hyde-20160507.2008

It shouldn't be auto-updating, so any mods I make to it shouldn't
get overwritten.
Possibly my mods actually do in the elpa subdir, where they are vulnerable
to overwrites.

I hope it doesn't require too many changes to my old setup.

Seems like I will have to modify the template generator for the 
yaml header section of new
posts. It leaves out the language and date variables I need to sort my
posts.

blogging with the jekyll layer involves hitting SPC a j when you have a
file open in emacs in your blog's directory. hmm.

ok, seems like it lets me "skip" 

1. export from org-mode to .md

2. jekyll build

To create a new post:


1. SPC a d - dired window, go to blog dir

2. pick any file

3. SPC a j - jekyll layer window

4. n       - new post

4.5 fixed !

how: edit the file hyde.el, section 
{% highlight elisp %}
(defun hyde/new-post (title)
      (insert "date: 2017-MM-DD TT:TT:TT \n")
      (insert "categories: \n")
      (insert "lang: end\n")
      (insert "ref: \n")
{% endhighlight %}
still todo: make date/time automatic

old:
add lines in YAML header

date: 2016-09-01 16:48:44 +0333
lang: en  (or he)
categories: 
ref: someName          ## this is the same for translations of the same post

5. SPC a j 
   arrow to the post you just created
   c       - commit the post
   
6. M-x magit-push - pushes the blog post to github pages.


huh, 
looks like I had to edit org-export-backends in .emacs.d/elpa/org-plus-contrib-date/org.el
http://randomgeekery.org/post/2014/exporting-from-org-to-markdown/
had to add md to the list.  now i can/could compose in .org instead of .md,
then my code blocks would actually be executable, I guess really for my current
workflow I need to blog from .Rmd, is that possible?
https://www.r-bloggers.com/blogging-with-rmarkdown-knitr-and-jekyll/

Ok, it's been possible for more than a year. I guess that's something I could look into then
since I seem to prefer rmarkdown at the moment to org-babel-tangle-R blocks.


----
broken:
Added disqus to this post.
broken: tag cloud is just a list and links are dead

<h1>Tag Cloud</h1>
{% assign tags = site.tags | sort %}
{% for tag in tags %}
 <span class="site-tag">
    <a href="/tag/{{ tag | first | slugify }}/"
        style="font-size: {{ tag | last | size  |  times: 4 | plus: 80  }}%">
            {{ tag[0] | replace:'-', ' ' }} ({{ tag | last | size }})
    </a>
</span>
{% endfor %}
