---
layout: post
ref: spaceJekyll
date: 2017-02-08 16:48:44 +0333
categories : spacemacs, emacs
lang: en 
title: "A spacemacs layer for jekyll"
---

hmm, seems that the org-export to .md function has disappeared.
Prompted me to try a new blogging layer for spacemacs.
https://allysonjulian.com/posts/blogging_with_spacemacs_and_jekyll/

I hope it doesn't require too many changes to my old setup.

Seems like I will have to modify the template generator for the 
yaml header section of new
posts. It leaves out the language and date variables I need to sort my
posts.

blogging with the jekyll layer involves hitting SPC a j when you have a
file open in emacs in your blog's directory. hmm.

ok, seems like it lets me "skip" the step of jekyll build from the terminal.

To create a new post:

1. SPC a d - dired window, go to blog dir

2. pick any file

3. SPC a j - jekyll layer window

4. n       - new post

4.5 add lines in YAML header

date: 2016-09-01 16:48:44 +0333
lang: en  (or he)
categories: 
ref: someName          ## this is the same for translations of the same post

5. SPC a j 
   arrow to the post you just created
   c       - commit the post
   
6. M-x magit-push - pushes the blog post to github pages.
